---
title: Ajout d’attributs aux dimensions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600278"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="068be-102">Ajout d'attributs aux dimensions</span><span class="sxs-lookup"><span data-stu-id="068be-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="068be-103">Une fois les dimensions définies, vous pouvez les remplir avec les attributs qui représentent chaque élément de données dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="068be-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="068be-104">Les attributs reposent généralement sur les champs d'une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="068be-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="068be-105">Lorsque vous ajoutez des attributs à une dimension, vous pouvez inclure des champs de n'importe quelle table dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="068be-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="068be-106">Dans cette tâche, vous utiliserez le Concepteur de dimensions pour ajouter des attributs aux dimensions Customer et Product.</span><span class="sxs-lookup"><span data-stu-id="068be-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="068be-107">La dimension Customer inclut des attributs basés sur des champs des deux tables Customer et Geography.</span><span class="sxs-lookup"><span data-stu-id="068be-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="068be-108">Ajout d'attributs à la dimension Customer</span><span class="sxs-lookup"><span data-stu-id="068be-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="068be-109">Pour ajouter des attributs</span><span class="sxs-lookup"><span data-stu-id="068be-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="068be-110">Ouvrez le Concepteur de dimensions pour la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="068be-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="068be-111">Pour cela, double-cliquez sur la dimension **Customer** du nœud **Dimensions** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="068be-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="068be-112">Dans le volet **Attributs** , remarquez les attributs Customer Key et Geography Key créés par l'Assistant Cube.</span><span class="sxs-lookup"><span data-stu-id="068be-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="068be-113">Dans la barre d'outils de l'onglet **Structure de dimension** , assurez-vous que l'icône Zoom qui permet d'afficher les tables du volet **Vue de source de données** est définie avec un zoom de 100 %.</span><span class="sxs-lookup"><span data-stu-id="068be-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="068be-114">Faites glisser les colonnes suivantes de la table **Customer** du volet **Vue de source de données** vers le volet **Attributs** :</span><span class="sxs-lookup"><span data-stu-id="068be-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="068be-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="068be-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="068be-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="068be-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="068be-117">**Sexe**</span><span class="sxs-lookup"><span data-stu-id="068be-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="068be-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="068be-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="068be-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="068be-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="068be-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="068be-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="068be-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="068be-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="068be-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="068be-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="068be-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="068be-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="068be-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="068be-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="068be-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="068be-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="068be-126">**Numéros**</span><span class="sxs-lookup"><span data-stu-id="068be-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="068be-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="068be-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="068be-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="068be-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="068be-129">Faites glisser les colonnes suivantes de la table **Geography** du volet **Vue de source de données** vers le volet **Attributs** :</span><span class="sxs-lookup"><span data-stu-id="068be-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="068be-130">**Ville**</span><span class="sxs-lookup"><span data-stu-id="068be-130">**City**</span></span>  
  
    -   <span data-ttu-id="068be-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="068be-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="068be-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="068be-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="068be-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="068be-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="068be-134">Dans le menu Fichier, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="068be-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="068be-135">Ajout d'attributs à la dimension Product</span><span class="sxs-lookup"><span data-stu-id="068be-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="068be-136">Pour ajouter des attributs</span><span class="sxs-lookup"><span data-stu-id="068be-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="068be-137">Ouvrez le Concepteur de dimensions pour la dimension Product.</span><span class="sxs-lookup"><span data-stu-id="068be-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="068be-138">Double-cliquez sur la dimension **Product** dans l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="068be-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="068be-139">Dans le volet **Attributs** , remarquez que l'attribut Product Key été créé par l'Assistant Cube.</span><span class="sxs-lookup"><span data-stu-id="068be-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="068be-140">Dans la barre d'outils de l'onglet **Structure de dimension** , assurez-vous que l'icône Zoom qui permet d'afficher les tables du volet **Vue de source de données** est définie avec un zoom de 100 %.</span><span class="sxs-lookup"><span data-stu-id="068be-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="068be-141">Faites glisser les colonnes suivantes de la table **Product** du volet **Vue de source de données** vers le volet **Attributs** :</span><span class="sxs-lookup"><span data-stu-id="068be-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="068be-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="068be-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="068be-143">**Couleur**</span><span class="sxs-lookup"><span data-stu-id="068be-143">**Color**</span></span>  
  
    -   <span data-ttu-id="068be-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="068be-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="068be-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="068be-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="068be-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="068be-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="068be-147">**Taille**</span><span class="sxs-lookup"><span data-stu-id="068be-147">**Size**</span></span>  
  
    -   <span data-ttu-id="068be-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="068be-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="068be-149">**Poids**</span><span class="sxs-lookup"><span data-stu-id="068be-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="068be-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="068be-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="068be-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="068be-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="068be-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="068be-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="068be-153">**Classe**</span><span class="sxs-lookup"><span data-stu-id="068be-153">**Class**</span></span>  
  
    -   <span data-ttu-id="068be-154">**Style**</span><span class="sxs-lookup"><span data-stu-id="068be-154">**Style**</span></span>  
  
    -   <span data-ttu-id="068be-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="068be-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="068be-156">**StartDate**</span><span class="sxs-lookup"><span data-stu-id="068be-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="068be-157">**EndDate**</span><span class="sxs-lookup"><span data-stu-id="068be-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="068be-158">**État**</span><span class="sxs-lookup"><span data-stu-id="068be-158">**Status**</span></span>  
  
5.  <span data-ttu-id="068be-159">Dans le menu Fichier, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="068be-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="068be-160">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="068be-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="068be-161">Vérification des propriétés de cube et de dimension</span><span class="sxs-lookup"><span data-stu-id="068be-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="068be-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="068be-162">See Also</span></span>  
 [<span data-ttu-id="068be-163">Référence des propriétés d’attribut de dimension</span><span class="sxs-lookup"><span data-stu-id="068be-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
