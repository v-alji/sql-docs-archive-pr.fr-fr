---
title: 'Leçon 10 : créer des hiérarchies | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700451"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="93909-102">Leçon 10 : Créer des hiérarchies</span><span class="sxs-lookup"><span data-stu-id="93909-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="93909-103">Dans cette leçon, vous allez créer des hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="93909-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="93909-104">Les hiérarchies sont des groupes de colonnes ordonnées par niveaux ; par exemple, une hiérarchie Geography peut avoir des sous-niveaux Country, State, County et City.</span><span class="sxs-lookup"><span data-stu-id="93909-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="93909-105">Les hiérarchies peuvent être affichées séparément des autres colonnes, dans une liste de champs d’applications clientes de création de rapports, ce qui permet aux utilisateurs clients de naviguer facilement parmi les hiérarchies et de les inclure dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="93909-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="93909-106">Pour plus d’informations, consultez [Hiérarchies &#40;SSAS Tabulaire&#41;](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="93909-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="93909-107">Pour créer des hiérarchies, vous allez utiliser le concepteur de modèles dans la *Vue du diagramme*.</span><span class="sxs-lookup"><span data-stu-id="93909-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="93909-108">La création et la gestion des hiérarchies n'est pas prise en charge dans le générateur de modèles dans la vue de données.</span><span class="sxs-lookup"><span data-stu-id="93909-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="93909-109">Durée estimée pour suivre cette leçon : **20 minutes**</span><span class="sxs-lookup"><span data-stu-id="93909-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93909-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="93909-110">Prerequisites</span></span>  
 <span data-ttu-id="93909-111">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="93909-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="93909-112">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [Leçon 9 : Créer des perspectives](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="93909-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="93909-113">Créer des hiérarchies</span><span class="sxs-lookup"><span data-stu-id="93909-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="93909-114">Pour créer une hiérarchie de catégorie dans la table Product</span><span class="sxs-lookup"><span data-stu-id="93909-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="93909-115">Dans le générateur de modèles, cliquez sur le `Model` menu, pointez sur **vue du modèle**, puis cliquez sur vue de **diagramme**.</span><span class="sxs-lookup"><span data-stu-id="93909-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="93909-116">Utilisez les contrôles de la minicarte dans l'angle supérieur droit du concepteur de modèles pour ajuster la vue des objets dans la vue du diagramme.</span><span class="sxs-lookup"><span data-stu-id="93909-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="93909-117">Si vous replacez les objets dans la vue de diagramme, cette vue sera conservée lorsque vous enregistrerez le projet.</span><span class="sxs-lookup"><span data-stu-id="93909-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="93909-118">Dans le générateur de modèles, cliquez avec le bouton droit sur la `Product` table, puis cliquez sur **créer une hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="93909-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="93909-119">Une hiérarchie apparaît en bas de la fenêtre de la table.</span><span class="sxs-lookup"><span data-stu-id="93909-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="93909-120">Dans le nom de la hiérarchie, renommez la hiérarchie en tapant `Category` , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="93909-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="93909-121">Dans le `Product` tableau, cliquez sur la colonne **Product Category Name** , puis faites-la glisser vers la `Category` hiérarchie, puis relâchez-la au-dessus du `Category` nom.</span><span class="sxs-lookup"><span data-stu-id="93909-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="93909-122">Dans la `Category` hiérarchie, cliquez avec le bouton droit sur la colonne **Product Category Name** , puis cliquez sur **Renommer**et tapez `Category` .</span><span class="sxs-lookup"><span data-stu-id="93909-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93909-123">Renommer une colonne dans une hiérarchie ne renomme pas cette colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="93909-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="93909-124">Une colonne dans une hiérarchie est simplement une représentation de la colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="93909-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="93909-125">Dans le `Product` tableau, cliquez avec le bouton droit sur la colonne nom de la **sous-catégorie de produit** , puis dans le menu contextuel, pointez sur **Ajouter à la hiérarchie**, puis cliquez sur `Category` .</span><span class="sxs-lookup"><span data-stu-id="93909-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="93909-126">Renommez le nom de la **sous-catégorie du produit** en `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="93909-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="93909-127">En utilisant les commandes cliquer et faire glisser, ou en utilisant la commande **Ajouter à la hiérarchie** dans le menu contextuel, ajoutez les colonnes nom du **modèle** et **nom du produit** (dans l’ordre) et placez-les sous la colonne nom de la sous- **catégorie de produit** .</span><span class="sxs-lookup"><span data-stu-id="93909-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="93909-128">Renommez ces colonnes `Model` et `Product` , respectivement.</span><span class="sxs-lookup"><span data-stu-id="93909-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="93909-129">Pour créer des hiérarchies dans la table Date</span><span class="sxs-lookup"><span data-stu-id="93909-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="93909-130">Dans le concepteur de modèles, cliquez avec le bouton droit sur la table **Date** , puis cliquez sur **Créer une hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="93909-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="93909-131">Renommez la hiérarchie en **Calendar**.</span><span class="sxs-lookup"><span data-stu-id="93909-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="93909-132">Ajoutez les colonnes suivantes, dans l'ordre, puis renommez-les :</span><span class="sxs-lookup"><span data-stu-id="93909-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="93909-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="93909-133">Column</span></span>|<span data-ttu-id="93909-134">Renommer en :</span><span class="sxs-lookup"><span data-stu-id="93909-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="93909-135">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="93909-135">Calendar Year</span></span>|<span data-ttu-id="93909-136">Year</span><span class="sxs-lookup"><span data-stu-id="93909-136">Year</span></span>|  
    |<span data-ttu-id="93909-137">Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="93909-137">Calendar Semester</span></span>|<span data-ttu-id="93909-138">Semester</span><span class="sxs-lookup"><span data-stu-id="93909-138">Semester</span></span>|  
    |<span data-ttu-id="93909-139">Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="93909-139">Calendar Quarter</span></span>|<span data-ttu-id="93909-140">Quarter (Trimestre)</span><span class="sxs-lookup"><span data-stu-id="93909-140">Quarter</span></span>|  
    |<span data-ttu-id="93909-141">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="93909-141">Month Calendar</span></span>|<span data-ttu-id="93909-142">Month</span><span class="sxs-lookup"><span data-stu-id="93909-142">Month</span></span>|  
    |<span data-ttu-id="93909-143">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="93909-143">Day Of Month</span></span>|<span data-ttu-id="93909-144">jour</span><span class="sxs-lookup"><span data-stu-id="93909-144">Day</span></span>|  
  
4.  <span data-ttu-id="93909-145">Dans la table **Date** , répétez les étapes ci-dessus, en créant une hiérarchie **Fiscal** , y compris les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="93909-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="93909-146">Colonne</span><span class="sxs-lookup"><span data-stu-id="93909-146">Column</span></span>|<span data-ttu-id="93909-147">Renommer en :</span><span class="sxs-lookup"><span data-stu-id="93909-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="93909-148">Fiscal Year</span><span class="sxs-lookup"><span data-stu-id="93909-148">Fiscal Year</span></span>|<span data-ttu-id="93909-149">Year</span><span class="sxs-lookup"><span data-stu-id="93909-149">Year</span></span>|  
    |<span data-ttu-id="93909-150">Fiscal Semester</span><span class="sxs-lookup"><span data-stu-id="93909-150">Fiscal Semester</span></span>|<span data-ttu-id="93909-151">Semester</span><span class="sxs-lookup"><span data-stu-id="93909-151">Semester</span></span>|  
    |<span data-ttu-id="93909-152">Fiscal Quarter</span><span class="sxs-lookup"><span data-stu-id="93909-152">Fiscal Quarter</span></span>|<span data-ttu-id="93909-153">Quarter (Trimestre)</span><span class="sxs-lookup"><span data-stu-id="93909-153">Quarter</span></span>|  
    |<span data-ttu-id="93909-154">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="93909-154">Month Calendar</span></span>|<span data-ttu-id="93909-155">Month</span><span class="sxs-lookup"><span data-stu-id="93909-155">Month</span></span>|  
    |<span data-ttu-id="93909-156">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="93909-156">Day Of Month</span></span>|<span data-ttu-id="93909-157">jour</span><span class="sxs-lookup"><span data-stu-id="93909-157">Day</span></span>|  
  
5.  <span data-ttu-id="93909-158">Enfin, dans la table **Date** , répétez les étapes ci-dessus, en créant une hiérarchie **Production Calendar** , comprenant les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="93909-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="93909-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="93909-159">Column</span></span>|<span data-ttu-id="93909-160">Renommer en :</span><span class="sxs-lookup"><span data-stu-id="93909-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="93909-161">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="93909-161">Calendar Year</span></span>|<span data-ttu-id="93909-162">Year</span><span class="sxs-lookup"><span data-stu-id="93909-162">Year</span></span>|  
    |<span data-ttu-id="93909-163">Week Number Of Year</span><span class="sxs-lookup"><span data-stu-id="93909-163">Week Number Of Year</span></span>|<span data-ttu-id="93909-164">Semaine</span><span class="sxs-lookup"><span data-stu-id="93909-164">Week</span></span>|  
    |<span data-ttu-id="93909-165">Jour de la semaine</span><span class="sxs-lookup"><span data-stu-id="93909-165">Day Of Week</span></span>|<span data-ttu-id="93909-166">jour</span><span class="sxs-lookup"><span data-stu-id="93909-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="93909-167">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="93909-167">Next Steps</span></span>  
 <span data-ttu-id="93909-168">Pour poursuivre l’étude de ce didacticiel, passez à la [Leçon 11 : Créer des partitions](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="93909-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
