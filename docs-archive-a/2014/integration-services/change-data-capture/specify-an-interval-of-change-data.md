---
title: Spécifier un intervalle de données modifiées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603576"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="d1f52-102">Spécifier un intervalle de données modifiées</span><span class="sxs-lookup"><span data-stu-id="d1f52-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="d1f52-103">Dans le flux de contrôle d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue un charge incrémentielle de données modifiées, la première tâche consiste à calculer les points de terminaison de l’intervalle de modification.</span><span class="sxs-lookup"><span data-stu-id="d1f52-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="d1f52-104">Ces points de terminaison sont des valeurs `datetime` qui seront stockées dans des variables de package pour une utilisation ultérieure dans le package.</span><span class="sxs-lookup"><span data-stu-id="d1f52-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1f52-105">Pour obtenir une description du processus d’ensemble de la conception du flux de contrôle, consultez [Capture de données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="d1f52-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="d1f52-106">Configurer des variables de package pour les points de terminaison</span><span class="sxs-lookup"><span data-stu-id="d1f52-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="d1f52-107">Avant de configurer la tâche d'exécution SQL pour calculer les points de terminaison, vous devez définir les variables de package qui stockeront les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="d1f52-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="d1f52-108">Pour configurer des variables de package</span><span class="sxs-lookup"><span data-stu-id="d1f52-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="d1f52-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez un nouveau projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1f52-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="d1f52-110">Dans la fenêtre **Variables** , créez les variables suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1f52-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="d1f52-111">Créez une variable du type de données `datetime` pour contenir le point de départ de l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="d1f52-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="d1f52-112">Cet exemple utilise le nom de variable ExtractStartTime.</span><span class="sxs-lookup"><span data-stu-id="d1f52-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="d1f52-113">Créez une autre variable du type de données `datetime` pour contenir le point de fin pour l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="d1f52-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="d1f52-114">Cet exemple utilise le nom de variable ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="d1f52-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="d1f52-115">Si vous calculez les points de terminaison dans un package principal qui exécute plusieurs packages enfants, vous pouvez utiliser des configurations Variable de package parent pour passer les valeurs de ces variables à chaque package enfant.</span><span class="sxs-lookup"><span data-stu-id="d1f52-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="d1f52-116">Pour plus d’informations, consultez [Tâche d’exécution de package](../control-flow/execute-package-task.md) et [Utiliser les valeurs des variables et des paramètres dans un package enfant](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="d1f52-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="d1f52-117">Calculer un point de départ et un point de fin pour les données modifiées</span><span class="sxs-lookup"><span data-stu-id="d1f52-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="d1f52-118">Après avoir configuré les variables de package pour les points de terminaison d'intervalle, vous pouvez calculer les valeurs réelles pour ces points de terminaison et mapper ces valeurs aux variables de package correspondantes.</span><span class="sxs-lookup"><span data-stu-id="d1f52-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="d1f52-119">Ces points de terminaison étant des valeurs `datetime`, vous devez utiliser des fonctions capables de calculer ou d'exploiter des valeurs `datetime`.</span><span class="sxs-lookup"><span data-stu-id="d1f52-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="d1f52-120">Le langage d'expression [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et Transact-SQL possèdent des fonctions qui prennent en charge les valeurs `datetime` :</span><span class="sxs-lookup"><span data-stu-id="d1f52-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="d1f52-121">Fonctions en langage d'expression [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui prennent en charge les valeurs `datetime`</span><span class="sxs-lookup"><span data-stu-id="d1f52-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="d1f52-122">DATEADD &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-123">DATEDIFF &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-124">DATEPART &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-125">DAY &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-126">GETDATE &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-127">GETUTCDATE &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-128">MONTH &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="d1f52-129">YEAR &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="d1f52-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="d1f52-130">Fonctions en Transact-SQL qui prennent en charge les valeurs `datetime`</span><span class="sxs-lookup"><span data-stu-id="d1f52-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="d1f52-131">[Types de données et fonctions de date et d’heure &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1f52-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="d1f52-132">Avant d'utiliser l'une de ces fonctions `datetime` pour calculer les points de terminaison, vous devez déterminer si l'intervalle est fixe et s'il a lieu selon une planification régulière.</span><span class="sxs-lookup"><span data-stu-id="d1f52-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="d1f52-133">En général, vous appliquez les modifications qui se sont produites dans les tables sources aux tables de destination selon une planification régulière.</span><span class="sxs-lookup"><span data-stu-id="d1f52-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="d1f52-134">Par exemple, vous pouvez appliquer ces modifications toutes les heures, tous les jours ou toutes les semaines.</span><span class="sxs-lookup"><span data-stu-id="d1f52-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="d1f52-135">Après avoir déterminé si votre intervalle de modification est fixe ou plus aléatoire, vous pouvez calculer les points de terminaison :</span><span class="sxs-lookup"><span data-stu-id="d1f52-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="d1f52-136">**Calcul de la date et de l’heure de début**.</span><span class="sxs-lookup"><span data-stu-id="d1f52-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="d1f52-137">Vous utilisez la date et l'heure de fin du chargement précédent comme date et heure de début actuelles.</span><span class="sxs-lookup"><span data-stu-id="d1f52-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="d1f52-138">Si vous utilisez un intervalle fixe pour les chargements incrémentiels, vous pouvez calculer cette valeur en utilisant les fonctions `datetime` de Transact-SQL ou du langage d'expression [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1f52-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="d1f52-139">Autrement, vous devrez peut-être rendre les points de terminaison persistants entre les exécutions et utilisez une tâche d'exécution SQL ou une tâche de script pour charger le point de terminaison précédent.</span><span class="sxs-lookup"><span data-stu-id="d1f52-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="d1f52-140">**Calcul de la date et de l’heure de fin**.</span><span class="sxs-lookup"><span data-stu-id="d1f52-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="d1f52-141">Si vous utilisez un intervalle fixe pour les chargements incrémentiels, calculez la date et l'heure de fin actuelles sur la base d'un décalage par rapport à la date et à l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="d1f52-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="d1f52-142">Là encore, vous pouvez calculer cette valeur à l’aide `datetime` des fonctions de Transact-SQL ou du [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] langage d’expression.</span><span class="sxs-lookup"><span data-stu-id="d1f52-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="d1f52-143">Dans la procédure suivante, l'intervalle de modification utilise un intervalle fixe et suppose que le package de chargement incrémentiel est exécuté tous les jours sans exception.</span><span class="sxs-lookup"><span data-stu-id="d1f52-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="d1f52-144">Sinon, les données modifiées pour les intervalles ratés seraient perdues.</span><span class="sxs-lookup"><span data-stu-id="d1f52-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="d1f52-145">Le point de départ pour l'intervalle est avant-hier à minuit, soit une période écoulée comprise entre 24 à 48 heures.</span><span class="sxs-lookup"><span data-stu-id="d1f52-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="d1f52-146">Le point de fin pour l'intervalle est hier à minuit (la nuit précédente), soit une période écoulée comprise entre 0 et 24 heures.</span><span class="sxs-lookup"><span data-stu-id="d1f52-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="d1f52-147">Pour calculer le point de départ et le point de fin pour l'intervalle de capture</span><span class="sxs-lookup"><span data-stu-id="d1f52-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="d1f52-148">Sous l’onglet **Flux de contrôle** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez une tâche d’exécution SQL au package.</span><span class="sxs-lookup"><span data-stu-id="d1f52-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="d1f52-149">Ouvrez **l’Éditeur de tâche d’exécution de requêtes SQL**, puis dans la page **Général** de l’éditeur, sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1f52-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="d1f52-150">Pour **ResultSet**, sélectionnez **Ligne unique**.</span><span class="sxs-lookup"><span data-stu-id="d1f52-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="d1f52-151">Configurez une connexion valide à la base de données source.</span><span class="sxs-lookup"><span data-stu-id="d1f52-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="d1f52-152">Pour **SQLSourceType**, sélectionnez **Entrée directe**.</span><span class="sxs-lookup"><span data-stu-id="d1f52-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="d1f52-153">Pour **SQLStatement**, entrez l’instruction SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="d1f52-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="d1f52-154">Dans la page **Ensemble de résultats** de **Éditeur de tâche d’exécution de requêtes SQL**, mappez le résultat d’ExtractStartTime à la variable de package ExtractStartTime, et le résultat d’ExtractEndTime à la variable de package ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="d1f52-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d1f52-155">Quand vous utilisez une expression pour définir la valeur d’une variable [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , l’expression est évaluée chaque fois que la valeur de la variable fait l’objet d’un accès.</span><span class="sxs-lookup"><span data-stu-id="d1f52-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d1f52-156">étape suivante</span><span class="sxs-lookup"><span data-stu-id="d1f52-156">Next Step</span></span>  
 <span data-ttu-id="d1f52-157">Une fois que vous avez calculé le point de départ et le point de fin pour une plage de modifications, l'étape suivante consiste à déterminer si les données modifiées sont prêtes.</span><span class="sxs-lookup"><span data-stu-id="d1f52-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="d1f52-158">**Rubrique suivante :** [Déterminer si les données modifiées sont prêtes](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="d1f52-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f52-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1f52-159">See Also</span></span>  
 <span data-ttu-id="d1f52-160">[Utiliser des variables dans des packages](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d1f52-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="d1f52-161">[Expressions Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="d1f52-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="d1f52-162">[Exécution de requêtes SQL, tâche](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="d1f52-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="d1f52-163">Tâche de script</span><span class="sxs-lookup"><span data-stu-id="d1f52-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
