---
title: Créer et gérer des partitions dans la base de données de l’espace de travail (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603658"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="96e45-102">Créer et gérer des partitions dans la base de données de l'espace de travail (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="96e45-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="96e45-103">Les partitions divisent une table en sections logiques.</span><span class="sxs-lookup"><span data-stu-id="96e45-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="96e45-104">Chaque partition peut ensuite être traitée (actualisée) indépendamment ou parallèlement à d'autres partitions.</span><span class="sxs-lookup"><span data-stu-id="96e45-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="96e45-105">Les partitions peuvent améliorer l'évolutivité et la gestion de bases de données volumineuses.</span><span class="sxs-lookup"><span data-stu-id="96e45-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="96e45-106">Par défaut, chaque table possède une partition qui inclut toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="96e45-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="96e45-107">Les tâches de cette rubrique décrivent comment créer et gérer des partitions dans la base de données model de l’espace de travail à l’aide de la boîte de dialogue **Gestionnaire de partition** dans[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e45-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="96e45-108">Une fois que le modèle a été déployé sur une autre instance Analysis Services, les administrateurs de bases de données peuvent créer et gérer des partitions dans le modèle (déployé) à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96e45-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="96e45-109">Pour plus d’informations, consultez [Créer et gérer des partitions de modèles tabulaires &#40;SSAS Tabulaire&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="96e45-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="96e45-110">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="96e45-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="96e45-111">Pour créer une nouvelle partition</span><span class="sxs-lookup"><span data-stu-id="96e45-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="96e45-112">Pour copier une partition</span><span class="sxs-lookup"><span data-stu-id="96e45-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="96e45-113">Pour supprimer une partition</span><span class="sxs-lookup"><span data-stu-id="96e45-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="96e45-114">Vous ne pouvez pas fusionner des partitions dans la base de données model de l'espace de travail à l'aide de la boîte de dialogue Gestionnaire de partitions.</span><span class="sxs-lookup"><span data-stu-id="96e45-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="96e45-115">Les partitions peuvent être fusionnées dans un modèle déployé uniquement à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96e45-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="96e45-116">Tâches</span><span class="sxs-lookup"><span data-stu-id="96e45-116">Tasks</span></span>  
 <span data-ttu-id="96e45-117">Pour créer et gérer des partitions, vous allez utiliser la boîte de dialogue **Gestionnaire de partition** .</span><span class="sxs-lookup"><span data-stu-id="96e45-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="96e45-118">Pour consulter la boîte de dialogue **Gestionnaire de partition** , dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Table** , puis sur **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="96e45-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="96e45-119">Pour créer une nouvelle partition</span><span class="sxs-lookup"><span data-stu-id="96e45-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="96e45-120">Dans le générateur de modèles, sélectionnez la table pour laquelle vous souhaitez définir une partition.</span><span class="sxs-lookup"><span data-stu-id="96e45-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="96e45-121">Cliquez sur le menu **Table** , puis sur **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="96e45-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="96e45-122">Dans **Gestionnaire de partition**, dans la zone de liste **Table** , vérifiez ou sélectionnez la table que vous voulez partitionner, puis cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="96e45-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="96e45-123">Dans **Nom de la partition**, tapez un nom pour la partition.</span><span class="sxs-lookup"><span data-stu-id="96e45-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="96e45-124">Par défaut, le nom de la partition par défaut est numéroté de manière incrémentielle pour chaque nouvelle partition.</span><span class="sxs-lookup"><span data-stu-id="96e45-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="96e45-125">Vous pouvez sélectionner les lignes et les colonnes à inclure dans la partition à l'aide du mode Aperçu de la table ou d'une requête SQL créée avec le mode Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="96e45-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="96e45-126">Pour utiliser le mode Aperçu de la table (valeur par défaut), cliquez sur le bouton **Aperçu de la table** en haut à droite dans la fenêtre d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="96e45-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="96e45-127">Sélectionnez les colonnes à inclure dans la partition en activant la case à cocher en regard du nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="96e45-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="96e45-128">Pour filtrer des lignes, cliquez avec le bouton droit sur une valeur de cellule, puis cliquez sur **Filtrer par valeur de la cellule sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="96e45-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="96e45-129">Pour utiliser une instruction SQL, cliquez sur le bouton **Éditeur de requête** en haut à droite dans la fenêtre d’aperçu, puis tapez ou collez une instruction de requête SQL dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="96e45-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="96e45-130">Pour valider votre instruction, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="96e45-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="96e45-131">Pour utiliser le concepteur de requêtes, cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="96e45-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="96e45-132">Pour copier une partition</span><span class="sxs-lookup"><span data-stu-id="96e45-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="96e45-133">Dans **Gestionnaire de partition**, dans la zone de liste **Table** , vérifiez ou sélectionnez la table qui contient la partition que vous souhaitez copier.</span><span class="sxs-lookup"><span data-stu-id="96e45-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="96e45-134">Dans la liste **Partitions** , sélectionnez la partition à copier, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="96e45-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="96e45-135">Dans **Nom de la partition**, tapez un nouveau nom pour la partition.</span><span class="sxs-lookup"><span data-stu-id="96e45-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="96e45-136">Pour supprimer une partition</span><span class="sxs-lookup"><span data-stu-id="96e45-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="96e45-137">Dans **Gestionnaire de partition**, dans la zone de liste **Table** , vérifiez ou sélectionnez la table qui contient la partition à supprimer.</span><span class="sxs-lookup"><span data-stu-id="96e45-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="96e45-138">Dans la liste **Partitions** , sélectionnez la partition à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="96e45-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e45-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96e45-139">See Also</span></span>  
 <span data-ttu-id="96e45-140">[Partitions &#40;&#41;tabulaire SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="96e45-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="96e45-141">Traiter les partitions dans la base de données de l’espace de travail &#40;SSAS tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="96e45-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
