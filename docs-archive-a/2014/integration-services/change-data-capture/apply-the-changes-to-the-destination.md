---
title: Appliquer les modifications à la destination | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614750"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="29cf3-102">Appliquer des modifications à la destination</span><span class="sxs-lookup"><span data-stu-id="29cf3-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="29cf3-103">Dans le flux d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue un chargement incrémentiel des données modifiées, la troisième et dernière tâche consiste à appliquer les modifications à votre destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="29cf3-104">Vous aurez besoin de trois composants : un pour appliquer les insertions, un pour appliquer les mises à jour et un pour appliquer les suppressions.</span><span class="sxs-lookup"><span data-stu-id="29cf3-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29cf3-105">La deuxième tâche pour concevoir le flux de données d'un package qui effectue un chargement incrémentiel des données modifiées consiste à séparer les insertions, les mises à jour et les suppressions.</span><span class="sxs-lookup"><span data-stu-id="29cf3-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="29cf3-106">Pour plus d’informations sur ce composant, consultez [Traiter les insertions, les mises à jour et les suppressions](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="29cf3-107">Pour obtenir une description du processus global de création d’un package qui effectue un chargement incrémentiel des données modifiées, consultez [Capture des données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="29cf3-108">Application d'insertions</span><span class="sxs-lookup"><span data-stu-id="29cf3-108">Applying Inserts</span></span>  
 <span data-ttu-id="29cf3-109">Pour appliquer des insertions, vous utilisez une destination OLE DB car les nouvelles lignes ne requièrent pas de traitement spécial.</span><span class="sxs-lookup"><span data-stu-id="29cf3-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="29cf3-110">Pour traiter des insertions à l'aide d'une destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="29cf3-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="29cf3-111">Sous l’onglet **Flux de données** , ajoutez une destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="29cf3-112">Connectez la sortie qui contient les insertions de la transformation de fractionnement conditionnel à la destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="29cf3-113">Dans **l’Éditeur de destination OLE DB**, dans la page **Gestionnaire de connexions** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="29cf3-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="29cf3-114">Sélectionnez ou créez un gestionnaire de connexions OLE DB pour la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="29cf3-115">Sélectionnez une option **Mode d’accès aux données** , puis sélectionnez la table de destination ou entrez une instruction SQL qui contient les colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="29cf3-116">Dans la page **Mappages** de l’éditeur, mappez les colonnes appropriées des données modifiées à la table de destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="29cf3-117">Application de mises à jour</span><span class="sxs-lookup"><span data-stu-id="29cf3-117">Applying Updates</span></span>  
 <span data-ttu-id="29cf3-118">Pour appliquer des mises à jour, vous utilisez une transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="29cf3-119">Cela s'explique par le fait que vous devez utiliser une instruction UPDATE paramétrable pour mettre à jour une ligne à la fois avec les nouvelles valeurs de colonne.</span><span class="sxs-lookup"><span data-stu-id="29cf3-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29cf3-120">Vous pouvez aussi utiliser des composants de destination pour appliquer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="29cf3-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="29cf3-121">Lorsque vous utilisez cette approche, vous utilisez les composants de destination pour enregistrer les lignes dans des tables temporaires que vous créez à cet effet.</span><span class="sxs-lookup"><span data-stu-id="29cf3-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="29cf3-122">Ensuite, vous utilisez des tâches d'exécution SQL pour effectuer les opérations de mise à jour en bloc et de suppression en bloc sur la destination à partir des tables temporaires.</span><span class="sxs-lookup"><span data-stu-id="29cf3-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="29cf3-123">Pour traiter des mises à jour à l'aide d'une transformation de commande OLE DB</span><span class="sxs-lookup"><span data-stu-id="29cf3-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="29cf3-124">Sous l’onglet **Flux de données** , ajoutez une transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="29cf3-125">Connectez la sortie qui contient les mises à jour de la transformation de fractionnement conditionnel à la transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="29cf3-126">Dans **l’Éditeur avancé pour Commande OLE DB**, sous l’onglet **Gestionnaire de connexions** , sélectionnez ou créez un gestionnaire de connexions OLE DB pour la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="29cf3-127">Dans **l’Éditeur avancé pour Commande OLE DB**, sous l’onglet **Propriétés du composant** , pour **SqlCommand**, entrez une instruction UPDATE paramétrable.</span><span class="sxs-lookup"><span data-stu-id="29cf3-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="29cf3-128">Par exemple, une instruction UPDATE pour une table Customer peut avoir la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="29cf3-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="29cf3-129">Sous l’onglet **Mappage de colonnes** de l’éditeur, mappez les colonnes appropriées des données modifiées aux paramètres dans l’instruction UPDATE.</span><span class="sxs-lookup"><span data-stu-id="29cf3-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="29cf3-130">Application de suppressions</span><span class="sxs-lookup"><span data-stu-id="29cf3-130">Applying Deletes</span></span>  
 <span data-ttu-id="29cf3-131">Pour appliquer des suppressions, vous utilisez une transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="29cf3-132">Cela s'explique par le fait que vous devez utiliser une instruction DELETE paramétrable qui supprime une ligne à la fois en fonction de la valeur de colonne qui identifie la ligne de façon unique.</span><span class="sxs-lookup"><span data-stu-id="29cf3-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29cf3-133">Vous pouvez aussi utiliser des composants de destination pour appliquer des suppressions.</span><span class="sxs-lookup"><span data-stu-id="29cf3-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="29cf3-134">Lorsque vous utilisez cette approche, vous utilisez les composants de destination pour enregistrer les lignes dans des tables temporaires que vous créez à cet effet.</span><span class="sxs-lookup"><span data-stu-id="29cf3-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="29cf3-135">Ensuite, vous utilisez des tâches d'exécution SQL pour effectuer les opérations de mise à jour en bloc et de suppression en bloc sur la destination à partir des tables temporaires.</span><span class="sxs-lookup"><span data-stu-id="29cf3-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="29cf3-136">Pour traiter des suppressions à l'aide d'une transformation de commande OLE DB</span><span class="sxs-lookup"><span data-stu-id="29cf3-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="29cf3-137">Sous l’onglet **Flux de données** , ajoutez une transformation de commande OLE DB au flux.</span><span class="sxs-lookup"><span data-stu-id="29cf3-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="29cf3-138">Connectez la sortie qui contient les suppressions de la transformation de fractionnement conditionnel à la transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="29cf3-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="29cf3-139">Ouvrez l'Éditeur avancé pour configurer la transformation.</span><span class="sxs-lookup"><span data-stu-id="29cf3-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="29cf3-140">Dans **l’Éditeur avancé pour Commande OLE DB**, sous l’onglet **Gestionnaire de connexions** , sélectionnez ou créez un gestionnaire de connexions OLE DB pour la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="29cf3-141">Dans **l’Éditeur avancé pour Commande OLE DB**, sous l’onglet **Propriétés du composant** de l’éditeur, pour **SqlCommand**, entrez une instruction DELETE paramétrable.</span><span class="sxs-lookup"><span data-stu-id="29cf3-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="29cf3-142">Par exemple, une instruction DELETE pour une table Customer peut avoir la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="29cf3-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="29cf3-143">Sous l’onglet **Mappage de colonnes** de l’éditeur, mappez la colonne appropriée des données modifiées au paramètre dans l’instruction DELETE.</span><span class="sxs-lookup"><span data-stu-id="29cf3-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="29cf3-144">Optimisation des insertions et des mises à jour à l'aide de la fonctionnalité MERGE</span><span class="sxs-lookup"><span data-stu-id="29cf3-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="29cf3-145">Vous pouvez optimiser le traitement des insertions et des mises à jour en combinant certaines options de capture de données modifiées avec l'utilisation du mot clé MERGE Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="29cf3-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="29cf3-146">Pour plus d’informations sur le mot clé MERGE, consultez [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29cf3-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="29cf3-147">Dans l’instruction Transact-SQL qui récupère les données modifiées, vous pouvez spécifier *all with merge* comme valeur du paramètre *row_filter_option* quand vous appelez la fonction **cdc.fn_cdc_get_net_changes_<instance_capture>** .</span><span class="sxs-lookup"><span data-stu-id="29cf3-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="29cf3-148">Cette fonction de capture de données modifiées fonctionne plus efficacement lorsqu'elle ne doit pas effectuer le traitement supplémentaire requis pour différencier les insertions des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="29cf3-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="29cf3-149">Quand vous spécifiez la valeur de paramètre *all with merge* , la valeur **__$operation** des données modifiées est 1 pour les suppressions ou 5 pour les modifications résultant d’insertions ou de mises à jour.</span><span class="sxs-lookup"><span data-stu-id="29cf3-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="29cf3-150">Pour plus d’informations sur la fonction Transact-SQL utilisée pour récupérer les données modifiées, consultez [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md). Après avoir extrait les modifications avec la valeur de paramètre *all with merge* , vous pouvez appliquer des suppressions et générer en sortie les lignes restantes dans une table temporaire ou une table de transit.</span><span class="sxs-lookup"><span data-stu-id="29cf3-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="29cf3-151">Ensuite, dans une tâche d'exécution SQL en aval, vous pouvez utiliser une instruction MERGE unique pour appliquer toutes les insertions ou mises à jour de la table intermédiaire à la destination.</span><span class="sxs-lookup"><span data-stu-id="29cf3-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
