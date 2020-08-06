---
title: Outils et approches de traitement (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605801"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="a4b9c-102">Outils et approches de traitement (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a4b9c-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="a4b9c-103">Le traitement est une opération selon laquelle Analysis Services interroge les données provenant d'une source de données relationnelle et remplit des objets Analysis Services à l'aide de ces données.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="a4b9c-104">En tant qu'administrateur système Analysis Services, vous pouvez exécuter et contrôler le traitement d'objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'aide des ces approches.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="a4b9c-105">Exécuter une analyse d'impact pour comprendre les dépendances entre les objets et l'étendue des opérations</span><span class="sxs-lookup"><span data-stu-id="a4b9c-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="a4b9c-106">Traiter un objet dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b9c-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="a4b9c-107">Traiter un ou plusieurs objets dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b9c-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="a4b9c-108">Exécutez une analyse d'impact pour examiner la liste des objets connexes non traités à la suite de l'action actuelle.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="a4b9c-109">Générer et exécuter un script dans une fenêtre de requête XMLA [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour traiter un ou plusieurs objets</span><span class="sxs-lookup"><span data-stu-id="a4b9c-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="a4b9c-110">Utiliser des applets de commande [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4b9c-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="a4b9c-111">Utiliser des flux de contrôle et des tâches dans des packages [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b9c-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="a4b9c-112">Surveiller le traitement avec SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a4b9c-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="a4b9c-113">Programmez une solution personnalisée à l'aide d'AMO.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="a4b9c-114">Pour plus d’informations, consultez [Programmation d’objets de base OLAP AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="a4b9c-115">Le traitement est une opération hautement configurable, contrôlée par un ensemble d'options de traitement qui déterminent si un traitement complet ou incrémentiel se produit au niveau de l'objet.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="a4b9c-116">Pour plus d’informations sur les options de traitement et sur le traitement des objets, consultez [Options et paramètres de traitement &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) et [Traitement des objets Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4b9c-117">Cette rubrique décrit les outils et approches pour traiter des modèles multidimensionnels.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="a4b9c-118">Pour plus d’informations sur le traitement des modèles tabulaires, consultez [traiter une base de données, une table ou une partition](../tabular-models/process-database-table-or-partition-analysis-services.md) et [traiter des données &#40;SSAS tabulaire&#41;](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="a4b9c-119">Objets de traitement dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4b9c-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a4b9c-120">Démarrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et connectez-vous à Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="a4b9c-121">Cliquez avec le bouton droit sur l’objet Analysis Services à traiter, puis cliquez sur **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="a4b9c-122">Vous pouvez traiter les données à tous les niveaux :</span><span class="sxs-lookup"><span data-stu-id="a4b9c-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="a4b9c-123">Bases de données</span><span class="sxs-lookup"><span data-stu-id="a4b9c-123">Databases</span></span>  
  
    -   <span data-ttu-id="a4b9c-124">Cubes</span><span class="sxs-lookup"><span data-stu-id="a4b9c-124">Cubes</span></span>  
  
    -   <span data-ttu-id="a4b9c-125">Groupes de mesures ou partitions individuelles dans le groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="a4b9c-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="a4b9c-126">Dimensions</span><span class="sxs-lookup"><span data-stu-id="a4b9c-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="a4b9c-127">Modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="a4b9c-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="a4b9c-128">Structures d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="a4b9c-128">Mining Structures</span></span>  
  
     <span data-ttu-id="a4b9c-129">Les objets Analysis Services sont hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="a4b9c-130">Si vous choisissez la base de données, le traitement concernera tous les objets contenus dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="a4b9c-131">En fonction de l'option de traitement sélectionnée et de l'état de l'objet, le traitement va avoir lieu ou ne pas avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="a4b9c-132">Notamment, si un objet n'est pas traité, le traitement de son objet parent entraînera le traitement de l'objet d'origine.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="a4b9c-133">Pour plus d’informations sur les dépendances entre les objets, consultez [Traitement des objets Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="a4b9c-134">Dans la boîte de dialogue **Traitement** dans **Options de traitement**, utilisez la valeur par défaut fournie ou sélectionnez une option différente dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="a4b9c-135">Pour plus d’informations sur chaque option, consultez [Options et paramètres de traitement &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="a4b9c-136">Cliquez sur **Analyse d’impact** pour identifier et éventuellement traiter les objets dépendants affectés si les objets figurant dans la boîte de dialogue Traiter sont traités.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="a4b9c-137">Vous pouvez également cliquer sur **Modifier les paramètres** pour modifier l’ordre de traitement, le comportement de traitement relatif aux types d’erreurs spécifiques et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="a4b9c-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="a4b9c-139">La boîte de dialogue État d'avancement du traitement fournit l'état de chaque commande en cours.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="a4b9c-140">Si un message d’état est tronqué, vous pouvez cliquer sur **Afficher les détails** pour lire le message en entier.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="a4b9c-141">Traitement d'objets dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4b9c-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="a4b9c-142">Démarrez [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et ouvrez un projet qui a été déployé.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="a4b9c-143">Dans l'Explorateur de solutions, sous le projet déployé, développez le dossier **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="a4b9c-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="a4b9c-144">Cliquez avec le bouton droit sur une dimension, puis cliquez sur **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="a4b9c-145">Vous pouvez cliquer avec le bouton droit sur plusieurs dimensions pour traiter plusieurs objets à la fois.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="a4b9c-146">Pour plus d’informations, consultez [Traitement par lots &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="a4b9c-147">Dans la boîte de dialogue **Traiter la dimension** , dans la colonne **Options de traitement** sous **Liste d'objets**, vérifiez que l'option pour cette colonne est **Traiter entièrement**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="a4b9c-148">Si ce n’est pas le cas, sous **Options de traitement**, cliquez sur l’option, puis sélectionnez **Traiter entièrement** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="a4b9c-149">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="a4b9c-150">Une fois le traitement terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="a4b9c-151">Exécuter une analyse d’impact pour identifier les dépendances des objets et l’étendue des opérations</span><span class="sxs-lookup"><span data-stu-id="a4b9c-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="a4b9c-152">Avant de traiter un objet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] ou [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], vous pouvez analyser l’impact du traitement sur les objets associés en cliquant sur **Analyse d’impact** dans l’une des boîtes de dialogue **Traiter les objets** .</span><span class="sxs-lookup"><span data-stu-id="a4b9c-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="a4b9c-153">Cliquez avec le bouton droit sur une dimension, un cube, un groupe de mesures ou une partition pour ouvrir une boîte de dialogue **Traiter les objets** .</span><span class="sxs-lookup"><span data-stu-id="a4b9c-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="a4b9c-154">Cliquez sur **Analyse d’impact**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="a4b9c-155">analyse le modèle et génère un rapport sur les conditions requises pour les objets liés à celui qui est sélectionné en vue du traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="a4b9c-156">Traitement d'objets à l'aide de XMLA</span><span class="sxs-lookup"><span data-stu-id="a4b9c-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="a4b9c-157">Démarrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et connectez-vous à Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="a4b9c-158">Cliquez avec le bouton droit sur l’objet à traiter, puis cliquez sur **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="a4b9c-159">Dans la boîte de dialogue **Traitement** , sélectionnez l’option de traitement à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="a4b9c-160">Modifiez tout autre paramètre.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-160">Modify any other settings.</span></span> <span data-ttu-id="a4b9c-161">Exécutez une analyse d'impact pour déterminer si vous devez apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="a4b9c-162">Cliquez sur **Script** sur l’écran **Traiter les objets** .</span><span class="sxs-lookup"><span data-stu-id="a4b9c-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="a4b9c-163">Cela génère un script XMLA et ouvre la fenêtre Requête XMLA [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4b9c-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="a4b9c-164">Fermez la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-164">Close the dialog box.</span></span> <span data-ttu-id="a4b9c-165">Le script contient la commande et les options de traitement spécifiées dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="a4b9c-166">Éventuellement, vous pouvez continuer à ajouter des objets au script si vous souhaitez traiter des objets supplémentaires dans le même traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="a4b9c-167">Pour continuer, répétez les étapes précédentes, en ajoutant des objets au script généré afin de disposer d'un seul script pour toutes les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="a4b9c-168">Pour afficher un exemple, consultez [Planifier des tâches administratives SSAS avec SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="a4b9c-169">Dans la barre de menus, cliquez sur **Requête**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="a4b9c-170">Traitement d'objets à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4b9c-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="a4b9c-171">À partir de cette version de SQL Server, vous pouvez utiliser les applets de commande Analysis Services PowerShell pour traiter les objets.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="a4b9c-172">Les applets de commande suivants peuvent être exécutées de façon interactive ou dans un script :</span><span class="sxs-lookup"><span data-stu-id="a4b9c-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="a4b9c-173">Applet de commande Invoke-ProcessCube</span><span class="sxs-lookup"><span data-stu-id="a4b9c-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="a4b9c-174">Applet de commande Invoke-ProcessDimension</span><span class="sxs-lookup"><span data-stu-id="a4b9c-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="a4b9c-175">Invoke-ProcessPartition, applet de commande</span><span class="sxs-lookup"><span data-stu-id="a4b9c-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="a4b9c-176">[Applet de commande Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd), qui peut être utilisée pour exécuter un script XMLA, MDX ou DMX qui inclut les commandes de traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="a4b9c-177">Surveillance du traitement des objets à l'aide de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a4b9c-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="a4b9c-178">Connectez-vous à une instance Analysis Services dans SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="a4b9c-179">Dans Sélection des événements, cliquez sur **Afficher tous les événements** pour ajouter tous les événements à la liste.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="a4b9c-180">Choisissez l'un des événements suivants :</span><span class="sxs-lookup"><span data-stu-id="a4b9c-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="a4b9c-181">**Début de la commande** et **Fin de la commande** pour afficher le démarrage et l’arrêt du traitement</span><span class="sxs-lookup"><span data-stu-id="a4b9c-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="a4b9c-182">**Erreur** pour capturer les erreurs</span><span class="sxs-lookup"><span data-stu-id="a4b9c-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="a4b9c-183">**Début du rapport de progression**, **Rapport de progression actuel**et **Fin du rapport de progression** pour créer un rapport sur l’état de processus et afficher les requêtes SQL utilisées pour récupérer les données</span><span class="sxs-lookup"><span data-stu-id="a4b9c-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="a4b9c-184">**Exécuter script MDX Début** et **Exécuter script MDX Fin** pour afficher les calculs de cube</span><span class="sxs-lookup"><span data-stu-id="a4b9c-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="a4b9c-185">Éventuellement, ajoutez des événements de verrou si vous analysez des problèmes de performances liés au traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="a4b9c-186">Traiter des objets Analysis Services à l'aide d'Integration Services</span><span class="sxs-lookup"><span data-stu-id="a4b9c-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="a4b9c-187">Dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], créez un package qui utilise la tâche de traitement Analysis Services pour remplir automatiquement des objets avec de nouvelles données quand vous effectuez des mises à jour régulières de votre base de données relationnelle source.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="a4b9c-188">Dans **Boîte à outils SSIS**, double-cliquez sur **Traitement Analysis Services** pour l’ajouter au package.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="a4b9c-189">Modifiez la tâche pour spécifier une connexion à la base de données, les objets à traiter et l'option de traitement.</span><span class="sxs-lookup"><span data-stu-id="a4b9c-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="a4b9c-190">Pour plus d'informations sur la manière d'implémenter cette tâche, consultez [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="a4b9c-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b9c-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4b9c-191">See Also</span></span>  
 [<span data-ttu-id="a4b9c-192">Traitement des objets de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="a4b9c-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
