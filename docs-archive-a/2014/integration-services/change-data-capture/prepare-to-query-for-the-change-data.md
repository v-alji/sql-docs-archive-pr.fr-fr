---
title: Préparer la recherche des données modifiées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601035"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="1691d-102">Préparer la recherche des données modifiées</span><span class="sxs-lookup"><span data-stu-id="1691d-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="1691d-103">Dans le flux de contrôle d'un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue un chargement incrémentiel des données modifiées, la troisième et dernière tâche consiste à préparer la recherche des données modifiées et à ajouter une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="1691d-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1691d-104">La deuxième tâche pour le flux de contrôle est de garantir que les données modifiées pour l'intervalle sélectionné sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="1691d-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="1691d-105">Pour plus d’informations, consultez [Déterminer si les données modifiées sont prêtes](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="1691d-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="1691d-106">Pour obtenir une description du processus d’ensemble de la conception du flux de contrôle, consultez [Capture de données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="1691d-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="1691d-107">Remarques sur la conception</span><span class="sxs-lookup"><span data-stu-id="1691d-107">Design Considerations</span></span>  
 <span data-ttu-id="1691d-108">Pour récupérer les données modifiées, vous appellerez une fonction table Transact-SQL qui accepte les points de terminaison de l'intervalle comme paramètres d'entrée et qui retourne les données modifiées pour l'intervalle spécifié.</span><span class="sxs-lookup"><span data-stu-id="1691d-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="1691d-109">Un composant source dans le flux de données appelle cette fonction.</span><span class="sxs-lookup"><span data-stu-id="1691d-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="1691d-110">Pour plus d’informations sur ce composant source, consultez [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="1691d-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="1691d-111">Les composants sources [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] les plus fréquemment utilisés, notamment la source OLE DB, la source ADO et la source ADO NET, ne peuvent pas dériver d’informations de paramètre pour une fonction table.</span><span class="sxs-lookup"><span data-stu-id="1691d-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="1691d-112">Ainsi, la plupart des sources ne peuvent pas appeler directement une fonction paramétrable.</span><span class="sxs-lookup"><span data-stu-id="1691d-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="1691d-113">Deux options de conception s'offrent à vous pour passer les paramètres d'entrée à la fonction :</span><span class="sxs-lookup"><span data-stu-id="1691d-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="1691d-114">**Assembler la requête paramétrable en tant que chaîne**.</span><span class="sxs-lookup"><span data-stu-id="1691d-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="1691d-115">Vous pouvez utiliser une tâche de script ou une tâche d'exécution SQL pour assembler une chaîne SQL dynamique avec les valeurs de paramètre codées en dur dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="1691d-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="1691d-116">Vous pouvez ensuite stocker cette chaîne dans une variable de package et l'utiliser pour définir la propriété SqlCommand d'un composant source.</span><span class="sxs-lookup"><span data-stu-id="1691d-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="1691d-117">Cette approche aboutit car le composant source n'a plus besoin des informations de paramètre.</span><span class="sxs-lookup"><span data-stu-id="1691d-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1691d-118">Un script précompilé nécessite un temps de traitement inférieur à une tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="1691d-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="1691d-119">**Utiliser un wrapper paramétrable**.</span><span class="sxs-lookup"><span data-stu-id="1691d-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="1691d-120">Vous pouvez également créer une procédure stockée paramétrable en tant que wrapper qui appelle la fonction table paramétrable.</span><span class="sxs-lookup"><span data-stu-id="1691d-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="1691d-121">Cette approche part du principe qu'un composant source peut correctement dériver des informations de paramètre pour une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="1691d-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="1691d-122">Cette rubrique utilise la première option de conception et assemble une requête paramétrable en tant que chaîne.</span><span class="sxs-lookup"><span data-stu-id="1691d-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="1691d-123">Préparation de la requête</span><span class="sxs-lookup"><span data-stu-id="1691d-123">Preparing the Query</span></span>  
 <span data-ttu-id="1691d-124">Avant de pouvoir concaténer les valeurs des paramètres d'entrée dans une chaîne de requête unique, vous devez installer les variables de package dont la requête a besoin.</span><span class="sxs-lookup"><span data-stu-id="1691d-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="1691d-125">Pour configurer des variables de package</span><span class="sxs-lookup"><span data-stu-id="1691d-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="1691d-126">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans la fenêtre **Variables** , créez une variable du type de données string pour contenir la chaîne de requête retournée par la tâche d’exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="1691d-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="1691d-127">Cet exemple utilise le nom de variable SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="1691d-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="1691d-128">Une fois la variable de package créée, vous pouvez utiliser une tâche de script ou une tâche d'exécution SQL pour concaténer les valeurs des paramètres d'entrée.</span><span class="sxs-lookup"><span data-stu-id="1691d-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="1691d-129">Les deux procédures suivantes décrivent comment configurer ces composants.</span><span class="sxs-lookup"><span data-stu-id="1691d-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="1691d-130">Pour utiliser une tâche de script pour concaténer la chaîne de requête</span><span class="sxs-lookup"><span data-stu-id="1691d-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="1691d-131">Sous l’onglet **Flux de contrôle** , ajoutez une tâche de script au package après le conteneur de boucles For et connectez ce dernier à la tâche.</span><span class="sxs-lookup"><span data-stu-id="1691d-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1691d-132">Cette procédure suppose que le package effectue un chargement incrémentiel à partir d'une table unique.</span><span class="sxs-lookup"><span data-stu-id="1691d-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="1691d-133">Si le package effectue le chargement à partir de plusieurs tables et qu'il possède un package parent avec plusieurs packages enfants, cette tâche est ajoutée en tant que premier composant à chaque package enfant.</span><span class="sxs-lookup"><span data-stu-id="1691d-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="1691d-134">Pour plus d’informations, consultez [Exécuter un chargement incrémentiel de plusieurs tables](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1691d-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="1691d-135">Dans **l’Éditeur de tâche de script**, dans la page **Script** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1691d-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="1691d-136">Pour **ReadOnlyVariables**, sélectionnez **User::DataReady**, **User::ExtractStartTime**et **User::ExtractEndTime** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1691d-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="1691d-137">Pour **ReadWriteVariables**, sélectionnez User::SqlDataQuery dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1691d-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="1691d-138">Dans **l’Éditeur de tâche de script**, dans la page **Script** , cliquez sur **Modifier le script** pour ouvrir l’environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="1691d-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="1691d-139">Dans la procédure Main, entrez l'un des segments de code suivants :</span><span class="sxs-lookup"><span data-stu-id="1691d-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="1691d-140">Si vous programmez en C#, entrez les lignes de code suivantes :</span><span class="sxs-lookup"><span data-stu-id="1691d-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="1691d-141">\- ou -</span><span class="sxs-lookup"><span data-stu-id="1691d-141">\- or -</span></span>  
  
    -   <span data-ttu-id="1691d-142">Si vous programmez en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], entrez les lignes de code suivantes :</span><span class="sxs-lookup"><span data-stu-id="1691d-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="1691d-143">Laissez la ligne de code par défaut qui retourne `DtsExecResult.Success` suite à l'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="1691d-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="1691d-144">Fermez l’environnement de développement de script et **l’Éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="1691d-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="1691d-145">Pour utiliser une tâche d'exécution SQL pour concaténer la chaîne de requête</span><span class="sxs-lookup"><span data-stu-id="1691d-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="1691d-146">Sous l’onglet **Flux de contrôle** , ajoutez une tâche d’exécution SQL au package après le conteneur de boucles For et connectez ce dernier à cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1691d-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1691d-147">Cette procédure suppose que le package effectue un chargement incrémentiel à partir d'une table unique.</span><span class="sxs-lookup"><span data-stu-id="1691d-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="1691d-148">Si le package effectue le chargement à partir de plusieurs tables et qu'il possède un package parent avec plusieurs packages enfants, cette tâche est ajoutée en tant que premier composant à chaque package enfant.</span><span class="sxs-lookup"><span data-stu-id="1691d-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="1691d-149">Pour plus d’informations, consultez [Exécuter un chargement incrémentiel de plusieurs tables](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="1691d-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="1691d-150">Dans **l’Éditeur de tâche d’exécution de requêtes SQL**, dans la page **Général** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1691d-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="1691d-151">Pour **ResultSet**, sélectionnez **Ligne unique**.</span><span class="sxs-lookup"><span data-stu-id="1691d-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="1691d-152">Configurez une connexion valide à la base de données source.</span><span class="sxs-lookup"><span data-stu-id="1691d-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="1691d-153">Pour **SQLSourceType**, sélectionnez **Entrée directe**.</span><span class="sxs-lookup"><span data-stu-id="1691d-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="1691d-154">Pour **SQLStatement**, entrez l’instruction SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="1691d-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="1691d-155">La clause `else` dans cet exemple génère une requête pour le chargement initial des données modifiées en passant une valeur Null pour la date et l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="1691d-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="1691d-156">Cet exemple ne s'applique pas au scénario selon lequel des modifications qui ont été apportées avant l'activation de la capture de données modifiées doivent aussi être téléchargées dans l'entrepôt de données.</span><span class="sxs-lookup"><span data-stu-id="1691d-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="1691d-157">Dans la page **Mappage de paramètre** de **l’Éditeur de tâche d’exécution de requêtes SQL**, effectuez le mappage suivant :</span><span class="sxs-lookup"><span data-stu-id="1691d-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="1691d-158">Mappez la variable DataReady au paramètre 0.</span><span class="sxs-lookup"><span data-stu-id="1691d-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="1691d-159">Mappez la variable ExtractStartTime au paramètre 1.</span><span class="sxs-lookup"><span data-stu-id="1691d-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="1691d-160">Mappez la variable ExtractEndTime au paramètre 2.</span><span class="sxs-lookup"><span data-stu-id="1691d-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="1691d-161">Dans la page **Ensemble de résultats** de **l’Éditeur de tâche d’exécution de requêtes SQL**, mappez le Nom de résultat à la variable SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="1691d-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="1691d-162">Le Nom de résultat est le nom de la colonne unique retournée, SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="1691d-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="1691d-163">Les procédures précédentes configurent une tâche qui prépare une chaîne de requête avec des valeurs de chaîne codées en dur pour les paramètres d'entrée.</span><span class="sxs-lookup"><span data-stu-id="1691d-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="1691d-164">Le code suivant est un exemple d'une telle chaîne de requête :</span><span class="sxs-lookup"><span data-stu-id="1691d-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="1691d-165">Ajout d’une tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="1691d-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="1691d-166">La dernière étape de la conception du flux de contrôle pour le package consiste à ajouter une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="1691d-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="1691d-167">Pour ajouter une tâche de flux de données et terminer le flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="1691d-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="1691d-168">Sous l’onglet **Flux de contrôle** , ajoutez une tâche de flux et connectez la tâche ayant concaténé la chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="1691d-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1691d-169">étape suivante</span><span class="sxs-lookup"><span data-stu-id="1691d-169">Next Step</span></span>  
 <span data-ttu-id="1691d-170">Une fois que vous avez préparé la chaîne de requête et configuré la tâche de flux de données, l'étape suivante consiste à créer la fonction table qui récupèrera les données modifiées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1691d-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="1691d-171">**Rubrique suivante :** [Créer la fonction de récupération des données modifiées](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="1691d-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
