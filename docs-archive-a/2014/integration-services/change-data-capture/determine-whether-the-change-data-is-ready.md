---
title: Déterminer si les données modifiées sont prêtes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707719"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="a7877-102">Déterminer si les données modifiées sont prêtes</span><span class="sxs-lookup"><span data-stu-id="a7877-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="a7877-103">Dans le flux de contrôle d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue une charge incrémentielle des données modifiées, la deuxième tâche consiste à s’assurer que les données modifiées pour l’intervalle sélectionné sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="a7877-104">Cette étape est nécessaire car le processus de capture asynchrone n'a peut-être pas encore pu traiter toutes les modifications jusqu'au point de terminaison sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7877-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7877-105">La première tâche pour le flux de contrôle consiste à calculer les points de terminaison de l'intervalle de modification.</span><span class="sxs-lookup"><span data-stu-id="a7877-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="a7877-106">Pour plus d’informations sur cette tâche, consultez [Spécifier un intervalle de données modifiées](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="a7877-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="a7877-107">Pour obtenir une description du processus d’ensemble de la conception du flux de contrôle, consultez [Capture de données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="a7877-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="a7877-108">Présentation des composants de la solution</span><span class="sxs-lookup"><span data-stu-id="a7877-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="a7877-109">La solution décrite dans cette rubrique utilise quatre composants [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a7877-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="a7877-110">Un conteneur de boucles For qui évalue à plusieurs reprises la sortie d'une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="a7877-111">Une tâche d'exécution SQL qui interroge les tables spéciales gérées par le processus de capture de données modifiées, puis utilise ces informations pour déterminer si les données sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="a7877-112">Un composant qui implémente un délai de traitement lorsque les données ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="a7877-113">Il peut s'agir d'une tâche de script ou d'une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="a7877-114">En option, un composant qui signale une erreur ou un délai d'attente lorsque la tâche d'exécution SQL retourne une valeur qui indique une erreur ou une condition de délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="a7877-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="a7877-115">Ces composants définissent ou lisent les valeurs de plusieurs variables de package pour contrôler le flux d'exécution à l'intérieur de la boucle et, ultérieurement, dans le package.</span><span class="sxs-lookup"><span data-stu-id="a7877-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="a7877-116">Pour configurer des variables de package</span><span class="sxs-lookup"><span data-stu-id="a7877-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="a7877-117">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans la fenêtre **Variables** , créez les variables suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="a7877-118">Créez une variable du type de données integer pour contenir la valeur d'état retournée par la tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="a7877-119">Cet exemple utilise la variable nommée DataReady avec une valeur initiale de 0.</span><span class="sxs-lookup"><span data-stu-id="a7877-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="a7877-120">Créez une variable pour contenir la durée du délai lorsque les données ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="a7877-121">Si vous prévoyez d'utiliser une tâche de script pour implémenter le délai, la variable doit être du type de données integer.</span><span class="sxs-lookup"><span data-stu-id="a7877-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="a7877-122">Si vous prévoyez d'utiliser une tâche d'exécution SQL avec une instruction WAITFOR, la variable doit être du type de données string pour accepter des valeurs telles que « 00:00:10 ».</span><span class="sxs-lookup"><span data-stu-id="a7877-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="a7877-123">Cet exemple utilise la variable nommée DelaySeconds avec une valeur initiale de 10.</span><span class="sxs-lookup"><span data-stu-id="a7877-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="a7877-124">Créez une variable du type de données integer pour contenir l'itération actuelle de la boucle.</span><span class="sxs-lookup"><span data-stu-id="a7877-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="a7877-125">Cet exemple utilise la variable nommée TimeoutCount avec une valeur initiale de 0.</span><span class="sxs-lookup"><span data-stu-id="a7877-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="a7877-126">Créez une variable du type de données integer pour spécifier le nombre de fois que la boucle doit tester les données avant de signaler une condition de délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="a7877-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="a7877-127">Cet exemple utilise la variable nommée TimeoutCeiling avec une valeur initiale de 20.</span><span class="sxs-lookup"><span data-stu-id="a7877-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="a7877-128">(Facultatif) Créez une variable du type de données integer que vous pouvez utiliser pour indiquer le premier chargement des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a7877-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="a7877-129">Cet exemple utilise la variable nommée IntervalID et vérifie uniquement l'existence de la valeur 0 pour indiquer le chargement initial.</span><span class="sxs-lookup"><span data-stu-id="a7877-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="a7877-130">Configuration d'un conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="a7877-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="a7877-131">Une fois les variables définies, le conteneur de boucles For est le premier composant à être ajouté.</span><span class="sxs-lookup"><span data-stu-id="a7877-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="a7877-132">Pour configurer un conteneur de boucles For pour attendre que les données modifiées soient prêtes</span><span class="sxs-lookup"><span data-stu-id="a7877-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="a7877-133">Sous l’onglet **Flux de contrôle** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez un conteneur de boucles For au flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="a7877-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="a7877-134">Connectez la tâche d'exécution SQL qui calcule les points de terminaison de l'intervalle au conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="a7877-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="a7877-135">Dans **l’Éditeur de boucle For**, sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-136">Pour **InitExpression**, entrez `@DataReady = 0`.</span><span class="sxs-lookup"><span data-stu-id="a7877-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="a7877-137">Cette expression définit la valeur initiale de la variable de boucle.</span><span class="sxs-lookup"><span data-stu-id="a7877-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="a7877-138">Pour **EvalExpression**m, entrez `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="a7877-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="a7877-139">Quand cette expression renvoie **False**, l’exécution sort de la boucle et la charge incrémentielle démarre.</span><span class="sxs-lookup"><span data-stu-id="a7877-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="a7877-140">Configuration de la tâche d'exécution SQL qui recherche les données modifiées</span><span class="sxs-lookup"><span data-stu-id="a7877-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="a7877-141">Dans le conteneur de boucles For, vous ajoutez une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="a7877-142">Cette tâche interroge les tables que le processus de capture de données modifiées gère dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a7877-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="a7877-143">Le résultat de cette requête est une valeur d'état qui indique si les données modifiées sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="a7877-144">Dans la table suivante, la première colonne montre les valeurs retournées de la tâche d'exécution SQL par l'exemple de requête Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="a7877-145">La deuxième colonne montre comment les autres composants répondent à ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="a7877-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="a7877-146">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a7877-146">Return Value</span></span>|<span data-ttu-id="a7877-147">Signification</span><span class="sxs-lookup"><span data-stu-id="a7877-147">Meaning</span></span>|<span data-ttu-id="a7877-148">response</span><span class="sxs-lookup"><span data-stu-id="a7877-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="a7877-149">0</span><span class="sxs-lookup"><span data-stu-id="a7877-149">0</span></span>|<span data-ttu-id="a7877-150">Indique que les données modifiées ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="a7877-151">Il n'existe aucun enregistrement de capture de données modifiées postérieur au point de fin de l'intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7877-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="a7877-152">L'exécution se poursuit avec le composant qui implémente un délai.</span><span class="sxs-lookup"><span data-stu-id="a7877-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="a7877-153">Le contrôle retourne ensuite au conteneur de boucles For qui continue à vérifier la tâche d'exécution SQL tant que la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="a7877-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="a7877-154">1</span><span class="sxs-lookup"><span data-stu-id="a7877-154">1</span></span>|<span data-ttu-id="a7877-155">Peut indiquer que les données modifiées n'ont pas été capturées pour l'intervalle complet ou qu'elles ont été supprimées.</span><span class="sxs-lookup"><span data-stu-id="a7877-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="a7877-156">Cela est traité comme une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a7877-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="a7877-157">Il n'existe aucun enregistrement de capture de données modifiées antérieur au point de départ de l'intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7877-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="a7877-158">L'exécution se poursuit avec le composant facultatif qui enregistre l'erreur.</span><span class="sxs-lookup"><span data-stu-id="a7877-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="a7877-159">2</span><span class="sxs-lookup"><span data-stu-id="a7877-159">2</span></span>|<span data-ttu-id="a7877-160">Indique que les données sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="a7877-161">Il existe des enregistrements de capture de données modifiées qui sont antérieurs au point de départ et postérieurs au point de fin de l'intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7877-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="a7877-162">L'exécution sort du conteneur de boucles For et le chargement incrémentiel démarre.</span><span class="sxs-lookup"><span data-stu-id="a7877-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="a7877-163">3</span><span class="sxs-lookup"><span data-stu-id="a7877-163">3</span></span>|<span data-ttu-id="a7877-164">Indique le chargement initial de toutes les données modifiées disponibles.</span><span class="sxs-lookup"><span data-stu-id="a7877-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="a7877-165">La logique conditionnelle obtient cette valeur à partir d'une variable de package spéciale qui est utilisée uniquement dans ce but.</span><span class="sxs-lookup"><span data-stu-id="a7877-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="a7877-166">L'exécution sort du conteneur de boucles For et le chargement incrémentiel démarre.</span><span class="sxs-lookup"><span data-stu-id="a7877-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="a7877-167">5</span><span class="sxs-lookup"><span data-stu-id="a7877-167">5</span></span>|<span data-ttu-id="a7877-168">Indique que la variable TimeoutCeiling a été atteinte.</span><span class="sxs-lookup"><span data-stu-id="a7877-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="a7877-169">La boucle a testé les données le nombre spécifié de fois et les données ne sont toujours pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a7877-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="a7877-170">Sans ce test ou un test semblable, le package peut s'exécuter indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="a7877-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="a7877-171">L'exécution se poursuit avec le composant facultatif qui enregistre le délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="a7877-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="a7877-172">Pour configurer une tâche d'exécution SQL pour déterminer si les données modifiées sont prêtes</span><span class="sxs-lookup"><span data-stu-id="a7877-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="a7877-173">Dans le conteneur de boucles For, ajoutez une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="a7877-174">Dans **l’Éditeur de tâche d’exécution de requêtes SQL**, dans la page **Général** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-175">Pour **ResultSet**, sélectionnez **Ligne unique**.</span><span class="sxs-lookup"><span data-stu-id="a7877-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="a7877-176">Configurez une connexion valide à la base de données source.</span><span class="sxs-lookup"><span data-stu-id="a7877-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="a7877-177">Pour **SQLSourceType**, sélectionnez **Entrée directe**.</span><span class="sxs-lookup"><span data-stu-id="a7877-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="a7877-178">Pour **SQLStatement**, entrez l’instruction SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="a7877-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="a7877-179">Dans la page **Mappage de paramètre** de **l’Éditeur de tâche d’exécution de requêtes SQL**, effectuez les mappages suivants :</span><span class="sxs-lookup"><span data-stu-id="a7877-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="a7877-180">Mappez la variable ExtractEndTime au paramètre 0.</span><span class="sxs-lookup"><span data-stu-id="a7877-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="a7877-181">Mappez la variable IntervalID au paramètre 1.</span><span class="sxs-lookup"><span data-stu-id="a7877-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="a7877-182">Mappez la variable ExtractStartTime au paramètre 2.</span><span class="sxs-lookup"><span data-stu-id="a7877-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="a7877-183">Mappez la variable TimeoutCount au paramètre 3.</span><span class="sxs-lookup"><span data-stu-id="a7877-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="a7877-184">Mappez la variable TimeoutCeiling au paramètre 4.</span><span class="sxs-lookup"><span data-stu-id="a7877-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="a7877-185">Dans la page **Ensemble de résultats** de **Éditeur de tâche d’exécution de requêtes SQL**, mappez le résultat de DataReady à la variable DataReady, et le résultat de TimeoutCount à la variable TimeoutCount.</span><span class="sxs-lookup"><span data-stu-id="a7877-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="a7877-186">Attendre jusqu'à ce que les données modifiées soient prêtes</span><span class="sxs-lookup"><span data-stu-id="a7877-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="a7877-187">Vous pouvez utiliser l'une des diverses méthodes disponibles pour implémenter un délai lorsque les données modifiées ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="a7877-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="a7877-188">Les deux procédures suivantes illustrent comment utiliser une tâche de script ou une tâche d'exécution SQL pour implémenter le délai.</span><span class="sxs-lookup"><span data-stu-id="a7877-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7877-189">Un script précompilé nécessite un temps de traitement inférieur à une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="a7877-190">Pour implémenter un délai en utilisant une tâche de script</span><span class="sxs-lookup"><span data-stu-id="a7877-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="a7877-191">Dans le conteneur de boucles For, ajoutez une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="a7877-192">Connectez la tâche d'exécution SQL utilisée pour déterminer si les données modifiées sont prêtes à la nouvelle tâche de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="a7877-193">Pour la contrainte de précédence qui connecte la tâche d’exécution de requêtes SQL à la tâche de script, ouvrez **Éditeur de contrainte de précédence** , puis sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-194">Pour **Opération d’évaluation**, sélectionnez **Expression et contrainte**.</span><span class="sxs-lookup"><span data-stu-id="a7877-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="a7877-195">Pour **Valeur**, sélectionnez **Succès**.</span><span class="sxs-lookup"><span data-stu-id="a7877-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="a7877-196">La valeur de contrainte **Succès** fait référence au succès de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="a7877-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="a7877-197">Dans le cas présent, il s’agit du succès de la tâche d’exécution de requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="a7877-198">Pour **Expression**, entrez `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span><span class="sxs-lookup"><span data-stu-id="a7877-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="a7877-199">Sélectionnez **Opérateur logique AND. Toutes les contraintes doivent avoir la valeur True**, si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="a7877-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="a7877-200">Dans **l’Éditeur de tâche de script**, dans la page **Script** , pour **ReadOnlyVariables**, sélectionnez la variable de type entier **User::DelaySeconds** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a7877-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="a7877-201">Dans **l’Éditeur de tâche de script**, dans la page **Script** , cliquez sur **Modifier le script** pour ouvrir l’environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="a7877-202">Dans la procédure Main, entrez l'une des lignes de code suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="a7877-203">Si vous programmez en C#, entrez la ligne de code suivante :</span><span class="sxs-lookup"><span data-stu-id="a7877-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="a7877-204">\- ou -</span><span class="sxs-lookup"><span data-stu-id="a7877-204">\- or -</span></span>  
  
    -   <span data-ttu-id="a7877-205">Si vous programmez en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], entrez la ligne de code suivante :</span><span class="sxs-lookup"><span data-stu-id="a7877-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="a7877-206">La méthode `Thread.Sleep` attend un argument spécifié en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="a7877-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="a7877-207">Laissez la ligne de code par défaut qui retourne `DtsExecResult.Success` suite à l'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="a7877-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="a7877-208">Fermez l’environnement de développement de script et **l’Éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="a7877-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="a7877-209">Pour implémenter un délai en utilisant une tâche d'exécution SQL</span><span class="sxs-lookup"><span data-stu-id="a7877-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="a7877-210">Dans le conteneur de boucles For, ajoutez une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="a7877-211">Connectez la tâche d'exécution SQL utilisée pour déterminer si les données modifiées sont prêtes à la nouvelle tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="a7877-212">Pour la contrainte de précédence qui connecte les deux tâches d’exécution de requêtes SQL, ouvrez l’ **Éditeur de contrainte de précédence** sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-213">Pour **Opération d’évaluation**, sélectionnez **Expression et contrainte**.</span><span class="sxs-lookup"><span data-stu-id="a7877-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="a7877-214">Pour **Valeur**, sélectionnez **Succès**.</span><span class="sxs-lookup"><span data-stu-id="a7877-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="a7877-215">La valeur de contrainte **Succès** fait référence au succès de la tâche d’exécution de requêtes SQL précédente.</span><span class="sxs-lookup"><span data-stu-id="a7877-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="a7877-216">Pour **Expression**, entrez `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="a7877-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="a7877-217">Sélectionnez **Opérateur logique AND. Toutes les contraintes doivent avoir la valeur True**, si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="a7877-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="a7877-218">Cette sélection requiert que les deux conditions, la contrainte et l'expression, soient vraies.</span><span class="sxs-lookup"><span data-stu-id="a7877-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="a7877-219">Dans **l’Éditeur de tâche d’exécution de requêtes SQL**, dans la page **Général** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-220">Pour **ResultSet**, sélectionnez **Ligne unique**.</span><span class="sxs-lookup"><span data-stu-id="a7877-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="a7877-221">Configurez une connexion valide à la base de données source.</span><span class="sxs-lookup"><span data-stu-id="a7877-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="a7877-222">Pour **SQLSourceType**, sélectionnez **Entrée directe**.</span><span class="sxs-lookup"><span data-stu-id="a7877-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="a7877-223">Pour **SQLStatement**, entrez l’instruction SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="a7877-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="a7877-224">Dans la page **Mappage de paramètre** de l’éditeur, mappez la variable de type chaîne DelaySeconds au paramètre 0.</span><span class="sxs-lookup"><span data-stu-id="a7877-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="a7877-225">Traitement d'une condition d'erreur</span><span class="sxs-lookup"><span data-stu-id="a7877-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="a7877-226">Vous pouvez éventuellement configurer un composant supplémentaire dans la boucle pour enregistrer une erreur ou une condition de délai d'attente :</span><span class="sxs-lookup"><span data-stu-id="a7877-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="a7877-227">Ce composant peut enregistrer une condition d'erreur lorsque la variable DataReady a pour valeur 1.</span><span class="sxs-lookup"><span data-stu-id="a7877-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="a7877-228">Cette valeur indique qu'il n'y a pas de données modifiées de disponibles avant le début de l'intervalle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a7877-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="a7877-229">Ce composant peut également enregistrer une condition de délai d'attente lorsque la valeur de la variable TimeoutCeiling est atteinte.</span><span class="sxs-lookup"><span data-stu-id="a7877-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="a7877-230">Cette valeur indique que la boucle a testé les données le nombre spécifié de fois et que les données ne sont toujours pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a7877-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="a7877-231">Sans ce test ou un test semblable, le package peut s'exécuter indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="a7877-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="a7877-232">Pour configurer une tâche de script facultative pour enregistrer une condition d'erreur</span><span class="sxs-lookup"><span data-stu-id="a7877-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="a7877-233">Si vous souhaitez signaler l'erreur ou le délai d'attente en écrivant un message dans le journal, configurez l'enregistrement pour le package.</span><span class="sxs-lookup"><span data-stu-id="a7877-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="a7877-234">Pour plus d’informations, consultez [Activer la journalisation des packages dans les outils de données SQL Server](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a7877-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="a7877-235">Dans le conteneur de boucles For, ajoutez une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="a7877-236">Connectez la tâche d'exécution SQL utilisée pour déterminer si les données modifiées sont prêtes à la nouvelle tâche de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="a7877-237">Pour la contrainte de précédence qui connecte la tâche d’exécution de requêtes SQL à la tâche de script, ouvrez **Éditeur de contrainte de précédence** , puis sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7877-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="a7877-238">Pour **Opération d’évaluation**, sélectionnez **Expression et contrainte**.</span><span class="sxs-lookup"><span data-stu-id="a7877-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="a7877-239">Pour **Valeur**, sélectionnez **Succès**.</span><span class="sxs-lookup"><span data-stu-id="a7877-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="a7877-240">La valeur de contrainte **Succès** fait référence au succès de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="a7877-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="a7877-241">Dans le cas présent, il s’agit du succès de la tâche d’exécution de requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="a7877-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="a7877-242">Pour **Expression**, entrez `@DataReady == 1 || @DataReady == 5`.</span><span class="sxs-lookup"><span data-stu-id="a7877-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="a7877-243">Sélectionnez **Opérateur logique AND. Toutes les contraintes doivent avoir la valeur True**, si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="a7877-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="a7877-244">Cette sélection requiert que les deux conditions, la contrainte et l'expression, soient vraies.</span><span class="sxs-lookup"><span data-stu-id="a7877-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="a7877-245">Dans **l’Éditeur de tâche de script**, dans la page **Script** de l’éditeur, pour **ReadOnlyVariables**, sélectionnez **User::DataReady** et **User::ExtractStartTime** dans la liste pour rendre leurs valeurs disponibles pour le script.</span><span class="sxs-lookup"><span data-stu-id="a7877-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="a7877-246">Si vous souhaitez inclure les informations de certaines variables système (par exemple, System::PackageName) dans les informations que vous écrivez dans le journal, sélectionnez également ces variables.</span><span class="sxs-lookup"><span data-stu-id="a7877-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="a7877-247">Dans **l’Éditeur de tâche de script**, dans la page **Script** , cliquez sur **Modifier le script** pour ouvrir l’environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="a7877-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="a7877-248">Dans la procédure Main, entrez le code soit pour enregistrer une erreur en appelant la méthode `Dts.Log`, soit pour déclencher un événement en appelant l'une des méthodes de l'interface `Dts.Events`.</span><span class="sxs-lookup"><span data-stu-id="a7877-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="a7877-249">Informez le package de l'erreur en retournant `Dts.TaskResult = Dts.Results.Failure`.</span><span class="sxs-lookup"><span data-stu-id="a7877-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="a7877-250">L'exemple suivant montre comment écrire un message dans le journal.</span><span class="sxs-lookup"><span data-stu-id="a7877-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="a7877-251">Pour plus d’informations, consultez [Journalisation dans la tâche de script](../extending-packages-scripting/task/logging-in-the-script-task.md), [Déclenchement d’événements dans la tâche de script](../extending-packages-scripting/task/raising-events-in-the-script-task.md)et [Retour de résultats de la tâche de script](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="a7877-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="a7877-252">Fermez l’environnement de développement de script et **l’Éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="a7877-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a7877-253">étape suivante</span><span class="sxs-lookup"><span data-stu-id="a7877-253">Next Step</span></span>  
 <span data-ttu-id="a7877-254">Après avoir déterminé que les données modifiées sont prêtes, l'étape suivante consiste à préparer la recherche des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a7877-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="a7877-255">**Rubrique suivante :** [Préparer la recherche des données modifiées](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="a7877-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
