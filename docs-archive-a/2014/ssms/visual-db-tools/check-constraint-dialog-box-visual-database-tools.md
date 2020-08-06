---
title: Contraintes de validation, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599742"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="82f27-102">Boîte de dialogue Contraintes de validation (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="82f27-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="82f27-103">Cette boîte de dialogue apparaît quand vous cliquez avec le bouton droit sur une grille de définition de table dans le Concepteur de tables puis cliquez sur **Vérifier les contraintes**.</span><span class="sxs-lookup"><span data-stu-id="82f27-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="82f27-104">Elle contient un jeu de propriétés pour les contraintes non uniques jointes aux tables de votre base de données.</span><span class="sxs-lookup"><span data-stu-id="82f27-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="82f27-105">Les propriétés qui s’appliquent aux contraintes uniques apparaissent dans la boîte de dialogue **Index/Clés** .</span><span class="sxs-lookup"><span data-stu-id="82f27-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82f27-106">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="82f27-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="82f27-107">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="82f27-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="82f27-108">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="82f27-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82f27-109">Options</span><span class="sxs-lookup"><span data-stu-id="82f27-109">Options</span></span>  
 <span data-ttu-id="82f27-110">**Contraintes de validation sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="82f27-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="82f27-111">Répertorie les contraintes de validation disponibles.</span><span class="sxs-lookup"><span data-stu-id="82f27-111">Lists available check constraints.</span></span> <span data-ttu-id="82f27-112">Pour afficher les propriétés d'une contrainte, sélectionnez-la dans la liste.</span><span class="sxs-lookup"><span data-stu-id="82f27-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="82f27-113">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="82f27-113">**Add**</span></span>  
 <span data-ttu-id="82f27-114">Crée une nouvelle contrainte pour la table de base de données sélectionnée et fournit un nom par défaut ainsi que d'autres valeurs pour la contrainte.</span><span class="sxs-lookup"><span data-stu-id="82f27-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="82f27-115">La contrainte ne devient valide que lorsqu'une expression est entrée pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="82f27-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="82f27-116">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="82f27-116">**Delete**</span></span>  
 <span data-ttu-id="82f27-117">Supprime la contrainte sélectionnée de la table.</span><span class="sxs-lookup"><span data-stu-id="82f27-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="82f27-118">Pour annuler l'ajout d'une contrainte de validation, supprimez la contrainte à l'aide de ce bouton.</span><span class="sxs-lookup"><span data-stu-id="82f27-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="82f27-119">**Catégorie Général**</span><span class="sxs-lookup"><span data-stu-id="82f27-119">**General Category**</span></span>  
 <span data-ttu-id="82f27-120">Se développe pour afficher le champ de la propriété **Expression** .</span><span class="sxs-lookup"><span data-stu-id="82f27-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="82f27-121">**Expression**</span><span class="sxs-lookup"><span data-stu-id="82f27-121">**Expression**</span></span>  
 <span data-ttu-id="82f27-122">Affiche l'expression pour la contrainte de validation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="82f27-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="82f27-123">Pour les nouvelles contraintes, vous devez entrer l'expression avant de quitter cette zone.</span><span class="sxs-lookup"><span data-stu-id="82f27-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="82f27-124">Vous pouvez également modifier des contraintes de validation existantes.</span><span class="sxs-lookup"><span data-stu-id="82f27-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="82f27-125">Pour plus d’informations, consultez [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="82f27-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="82f27-126">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="82f27-126">**Identity Category**</span></span>  
 <span data-ttu-id="82f27-127">Se développe pour afficher les propriétés de **Nom** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="82f27-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="82f27-128">**Nom**</span><span class="sxs-lookup"><span data-stu-id="82f27-128">**Name**</span></span>  
 <span data-ttu-id="82f27-129">Indique le nom de la contrainte de validation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="82f27-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="82f27-130">Pour modifier le nom de cette contrainte, tapez directement le texte dans le champ de la propriété.</span><span class="sxs-lookup"><span data-stu-id="82f27-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="82f27-131">**Description**</span><span class="sxs-lookup"><span data-stu-id="82f27-131">**Description**</span></span>  
 <span data-ttu-id="82f27-132">Description de cette contrainte de validation.</span><span class="sxs-lookup"><span data-stu-id="82f27-132">Describing this check constraint.</span></span> <span data-ttu-id="82f27-133">Vous pouvez modifier la description en la tapant dans le champ de propriété ou cliquer sur le bouton de sélection ( **...** ) qui s’affiche à droite du champ de propriété et modifier la description dans la boîte de dialogue **Propriété de la description**.</span><span class="sxs-lookup"><span data-stu-id="82f27-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="82f27-134">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="82f27-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="82f27-135">Se développe pour afficher les propriétés de **Vérifier les données existantes à la création ou à la réactivation**, **Appliquer INSERTs et UPDATEs**et **Appliquer la réplication**.</span><span class="sxs-lookup"><span data-stu-id="82f27-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="82f27-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="82f27-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="82f27-137">Spécifie si toutes les données préexistantes (données qui existaient dans la table avant la création de la contrainte) sont vérifiées par rapport à la contrainte.</span><span class="sxs-lookup"><span data-stu-id="82f27-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="82f27-138">**Appliquer INSERTs et UPDATEs**</span><span class="sxs-lookup"><span data-stu-id="82f27-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="82f27-139">Spécifie si la contrainte est appliquée lors de l'insertion ou de la mise à jour de données dans la table.</span><span class="sxs-lookup"><span data-stu-id="82f27-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="82f27-140">**Appliquer la réplication**</span><span class="sxs-lookup"><span data-stu-id="82f27-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="82f27-141">Indique si la contrainte doit être appliquée lorsqu'un Agent de réplication effectue une requête Insert ou Update sur cette table.</span><span class="sxs-lookup"><span data-stu-id="82f27-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f27-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82f27-142">See Also</span></span>  
 <span data-ttu-id="82f27-143">[Contraintes uniques et contraintes de validation](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="82f27-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="82f27-144">Index et clés, boîte de dialogue &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="82f27-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
