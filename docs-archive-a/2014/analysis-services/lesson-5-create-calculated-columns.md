---
title: 'Leçon 6 : créer des colonnes calculées | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604244"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="e4778-102">Leçon 6 : Créer des colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="e4778-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="e4778-103">Dans cette leçon, vous allez créer des données dans votre modèle en ajoutant des colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="e4778-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="e4778-104">Une colonne calculée est basée sur les données qui existent déjà dans votre modèle.</span><span class="sxs-lookup"><span data-stu-id="e4778-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="e4778-105">Pour en savoir plus, consultez [Colonnes calculées &#40;SSAS Tabulaire&#41;](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e4778-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="e4778-106">Vous allez créer cinq colonnes calculées dans trois tables différentes.</span><span class="sxs-lookup"><span data-stu-id="e4778-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="e4778-107">Les étapes sont légèrement différentes pour chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="e4778-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="e4778-108">Il s'agit de montrer qu'il existe plusieurs façons de créer de nouvelles colonnes, de les renommer, puis de les placer à différents emplacements dans une table.</span><span class="sxs-lookup"><span data-stu-id="e4778-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="e4778-109">Durée estimée pour suivre cette leçon : **15 minutes**</span><span class="sxs-lookup"><span data-stu-id="e4778-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4778-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e4778-110">Prerequisites</span></span>  
 <span data-ttu-id="e4778-111">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="e4778-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="e4778-112">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la [Leçon 5 : Créer des relations](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e4778-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="e4778-113">Créer des colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="e4778-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="e4778-114">Créer une colonne calculée de calendrier mensuel dans la table Date</span><span class="sxs-lookup"><span data-stu-id="e4778-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="e4778-115">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis pointez sur **Vue du modèle**et sur **Vue de données**.</span><span class="sxs-lookup"><span data-stu-id="e4778-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="e4778-116">Les colonnes calculées ne peuvent être créées qu'à l'aide du concepteur de modèles dans la vue de données.</span><span class="sxs-lookup"><span data-stu-id="e4778-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="e4778-117">Dans le concepteur de modèles, cliquez sur la table **Date** (onglet).</span><span class="sxs-lookup"><span data-stu-id="e4778-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="e4778-118">Cliquez avec le bouton droit sur la colonne **calendrier Quarter** , puis cliquez sur **Insérer une colonne**.</span><span class="sxs-lookup"><span data-stu-id="e4778-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="e4778-119">Une nouvelle colonne nommée **CalculatedColumn1** est insérée à gauche de la colonne **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="e4778-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="e4778-120">Dans la barre de formule au-dessus de la table, tapez la formule suivante.</span><span class="sxs-lookup"><span data-stu-id="e4778-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="e4778-121">La saisie semi-automatique vous aide à taper les noms complets de colonnes et de tables, et répertorie les fonctions disponibles.</span><span class="sxs-lookup"><span data-stu-id="e4778-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="e4778-122">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e4778-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="e4778-123">Les valeurs remplissent alors toutes les lignes de la colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="e4778-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="e4778-124">Si vous faites défiler la table vers le bas, vous remarquez que les lignes peuvent avoir des valeurs différentes pour cette colonne, en fonction des données figurant dans chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="e4778-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e4778-125">Si vous obtenez une erreur, vérifiez que les noms de colonne dans la formule correspondent aux noms de colonne que vous avez modifiés dans la [Leçon 3 : Renommer des colonnes](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e4778-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="e4778-126">Renommez cette colonne en `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="e4778-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="e4778-127">La colonne calculée Month Calendar fournit un nom triable pour le mois.</span><span class="sxs-lookup"><span data-stu-id="e4778-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="e4778-128">Créer une colonne calculée de jour de la semaine dans la table Date</span><span class="sxs-lookup"><span data-stu-id="e4778-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="e4778-129">Avec la table **Date** encore active, cliquez sur le menu **Colonne** , puis sur **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="e4778-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="e4778-130">Une nouvelle colonne est ajoutée à droite de la table.</span><span class="sxs-lookup"><span data-stu-id="e4778-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="e4778-131">Dans la barre de formule, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="e4778-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="e4778-132">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e4778-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="e4778-133">Renommez la colonne en `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="e4778-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="e4778-134">Cliquez sur l’en-tête de colonne et faites glisser la colonne entre les colonnes **Day Name** et **Day of Month** .</span><span class="sxs-lookup"><span data-stu-id="e4778-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e4778-135">Déplacer les colonnes dans la table facilite la navigation.</span><span class="sxs-lookup"><span data-stu-id="e4778-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="e4778-136">La colonne calculée Day of Week fournit un nom triable pour le jour de la semaine.</span><span class="sxs-lookup"><span data-stu-id="e4778-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="e4778-137">Créer une colonne calculée de nom de sous-catégorie de produit dans la table Product</span><span class="sxs-lookup"><span data-stu-id="e4778-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="e4778-138">Dans le concepteur de modèles, sélectionnez la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="e4778-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="e4778-139">Faites défiler la table sur la droite.</span><span class="sxs-lookup"><span data-stu-id="e4778-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="e4778-140">Notez que la colonne la plus à droite est nommée **Add Column** (en italique). Cliquez sur l’en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="e4778-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="e4778-141">Dans la barre de formule, tapez la formule suivante.</span><span class="sxs-lookup"><span data-stu-id="e4778-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="e4778-142">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e4778-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="e4778-143">Renommez la colonne en `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="e4778-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="e4778-144">La colonne calculée Product Subcategory Name est utilisée pour créer une hiérarchie dans la table Product, incluant les données de la colonne Product Subcategory Name dans la table Product Subcategory.</span><span class="sxs-lookup"><span data-stu-id="e4778-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="e4778-145">Les hiérarchies ne peuvent pas couvrir plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="e4778-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="e4778-146">Vous allez créer des hiérarchies plus loin, dans la leçon 7.</span><span class="sxs-lookup"><span data-stu-id="e4778-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="e4778-147">Créer une colonne calculée de nom de catégorie de produit dans la table Product</span><span class="sxs-lookup"><span data-stu-id="e4778-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="e4778-148">Avec la table **Product** encore active, cliquez sur le menu **Colonne** , puis sur **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="e4778-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="e4778-149">Dans la barre de formule, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="e4778-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="e4778-150">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e4778-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="e4778-151">Renommez la colonne en `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="e4778-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="e4778-152">La colonne calculée Product Category Name est utilisée pour créer une hiérarchie dans la table Product, incluant les données de la colonne Product Category Name dans la table Product Category.</span><span class="sxs-lookup"><span data-stu-id="e4778-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="e4778-153">Les hiérarchies ne peuvent pas couvrir plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="e4778-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="e4778-154">Créer une colonne calculée de marge dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="e4778-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="e4778-155">Dans le concepteur de modèles, sélectionnez la table **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="e4778-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="e4778-156">Ajoutez une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="e4778-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="e4778-157">Dans la barre de formule, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="e4778-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="e4778-158">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e4778-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="e4778-159">Renommez la colonne en `Margin` .</span><span class="sxs-lookup"><span data-stu-id="e4778-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="e4778-160">Faites glisser la colonne entre les colonnes **Sales Amount** et **Tax Amt** .</span><span class="sxs-lookup"><span data-stu-id="e4778-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="e4778-161">La colonne calculée Margin est utilisée pour analyser les marges bénéficiaires pour chaque ligne (produit).</span><span class="sxs-lookup"><span data-stu-id="e4778-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e4778-162">étape suivante</span><span class="sxs-lookup"><span data-stu-id="e4778-162">Next Step</span></span>  
 <span data-ttu-id="e4778-163">Pour continuer cette leçon, passez à la [Leçon 7 : Créer des mesures](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="e4778-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
