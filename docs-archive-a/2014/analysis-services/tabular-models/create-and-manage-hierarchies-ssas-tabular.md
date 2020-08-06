---
title: Créer et gérer des hiérarchies (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603662"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="2e108-102">Créer et gérer des hiérarchies (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="2e108-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="2e108-103">Les hiérarchies peuvent être créées et gérées dans le générateur de modèles, dans la vue de diagramme.</span><span class="sxs-lookup"><span data-stu-id="2e108-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="2e108-104">Pour afficher le concepteur de modèles dans la Vue de diagramme, dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , pointez sur **Vue du modèle**, puis cliquez sur **Vue de diagramme**.</span><span class="sxs-lookup"><span data-stu-id="2e108-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="2e108-105">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e108-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="2e108-106">Créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="2e108-107">Modifier une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="2e108-108">Supprimer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="2e108-109">Créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="2e108-110">Vous pouvez créer une hiérarchie en utilisant les colonnes et le menu contextuel de table.</span><span class="sxs-lookup"><span data-stu-id="2e108-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="2e108-111">Lorsque vous créez une hiérarchie, un nouveau niveau parent s'affiche avec les colonnes sélectionnées en tant que niveaux enfants.</span><span class="sxs-lookup"><span data-stu-id="2e108-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="2e108-112">Pour créer une hiérarchie à partir du menu contextuel</span><span class="sxs-lookup"><span data-stu-id="2e108-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="2e108-113">Dans le générateur de modèles (Vue de diagramme), dans une fenêtre de table, cliquez avec le bouton droit sur une colonne, puis sélectionnez **Créer une hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="2e108-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="2e108-114">Pour sélectionner plusieurs colonnes, cliquez sur chaque colonne, puis cliquez avec le bouton droit pour ouvrir le menu contextuel, puis sélectionnez **Créer une hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="2e108-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="2e108-115">Un niveau de hiérarchie parent est créé au bas de la fenêtre de table et les colonnes sélectionnées sont copiées sous la hiérarchie en tant que niveaux enfants.</span><span class="sxs-lookup"><span data-stu-id="2e108-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="2e108-116">Tapez un nom pour la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="2e108-117">Vous pouvez faire glisser des colonnes supplémentaires dans le niveau parent de votre hiérarchie, ce qui a pour fonction de copier les colonnes.</span><span class="sxs-lookup"><span data-stu-id="2e108-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="2e108-118">Placez le niveau enfant à l'endroit où vous souhaitez qu'il apparaisse dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e108-119">La commande Créer une hiérarchie est désactivée dans le menu contextuel si vous sélectionnez plusieurs mesures avec une ou plusieurs colonnes, ou si vous sélectionnez des colonnes à partir de plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="2e108-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="2e108-120">Modifier une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="2e108-121">Vous pouvez renommer une hiérarchie, renommer un niveau enfant, modifier l'ordre des niveaux enfants, ajouter des colonnes supplémentaires en tant que niveaux enfants, supprimer un niveau enfant d'une hiérarchie, afficher le nom de la source d'un niveau enfant (le nom de la colonne) et masquer un niveau enfant s'il a le même nom que le niveau de hiérarchie parent.</span><span class="sxs-lookup"><span data-stu-id="2e108-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="2e108-122">Pour modifier le nom d'une hiérarchie ou d'un niveau enfant</span><span class="sxs-lookup"><span data-stu-id="2e108-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="2e108-123">Cliquez avec le bouton droit sur le niveau de hiérarchie parent ou sur un niveau enfant, puis sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="2e108-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="2e108-124">Entrez le nouveau nom ou modifiez le nom existant.</span><span class="sxs-lookup"><span data-stu-id="2e108-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="2e108-125">Pour modifier l'ordre d'un niveau enfant dans une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="2e108-126">Cliquez et faites glisser un niveau enfant vers une nouvelle position dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="2e108-127">Ou cliquez avec le bouton droit sur un niveau enfant de la hiérarchie, puis cliquez sur Monter pour déplacer le niveau plus haut dans la liste, ou sur Descendre pour déplacer le niveau plus bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2e108-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="2e108-128">Vous pouvez également cliquer sur un niveau enfant pour le sélectionner, puis appuyez sur Alt + Flèche haut pour déplacer le niveau vers le haut dans la liste, ou sur Alt + Flèche bas pour déplacer le niveau vers le bas.</span><span class="sxs-lookup"><span data-stu-id="2e108-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="2e108-129">Pour ajouter un autre niveau enfant à une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="2e108-130">Cliquez et faites glisser une colonne sur le niveau parent ou à un emplacement spécifique de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="2e108-131">La colonne est copiée en tant que niveau enfant de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="2e108-132">Vous pouvez également cliquer avec le bouton droit sur une colonne, pointer sur **Ajouter à la hiérarchie**, puis cliquer sur la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e108-133">Vous pouvez ajouter une colonne masquée (une colonne qui n'apparaît pas dans les rapports) en tant que niveau enfant à la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="2e108-134">Le niveau enfant n'est pas masqué.</span><span class="sxs-lookup"><span data-stu-id="2e108-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="2e108-135">Pour supprimer un niveau enfant d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="2e108-136">Cliquez avec le bouton droit sur un niveau enfant, puis sélectionnez **Supprimer de la hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="2e108-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="2e108-137">Ou bien, cliquez sur un niveau enfant, puis appuyez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2e108-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e108-138">Si vous renommez un niveau de hiérarchie enfant, il ne porte plus le même nom que la colonne à partir de laquelle il a été copié.</span><span class="sxs-lookup"><span data-stu-id="2e108-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="2e108-139">Utilisez la commande **Afficher le nom de la source** pour voir la colonne à partir de laquelle il a été copié.</span><span class="sxs-lookup"><span data-stu-id="2e108-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="2e108-140">Pour afficher un nom de source</span><span class="sxs-lookup"><span data-stu-id="2e108-140">To show a source name</span></span>  
  
-   <span data-ttu-id="2e108-141">Cliquez avec le bouton droit sur un niveau enfant de la hiérarchie, puis sélectionnez **Afficher le nom de la source**.</span><span class="sxs-lookup"><span data-stu-id="2e108-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="2e108-142">Le nom de la colonne à partir de laquelle il a été copié s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2e108-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a><span data-ttu-id="2e108-143">Supprimer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2e108-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="2e108-144">Pour supprimer une hiérarchie et ses niveaux enfants</span><span class="sxs-lookup"><span data-stu-id="2e108-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="2e108-145">Cliquez avec le bouton droit sur le niveau de hiérarchie parent, puis cliquez sur Supprimer la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="2e108-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="2e108-146">Ou bien, cliquez sur le niveau de hiérarchie parent, puis appuyez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="2e108-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="2e108-147">Cela supprime également tous les niveaux enfants.</span><span class="sxs-lookup"><span data-stu-id="2e108-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e108-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e108-148">See Also</span></span>  
 <span data-ttu-id="2e108-149">[Concepteur de modèles tabulaires &#40;&#41;SSAS tabulaire](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="2e108-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="2e108-150">[Hiérarchies &#40;&#41;tabulaires SSAS](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="2e108-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="2e108-151">Mesures &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="2e108-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
