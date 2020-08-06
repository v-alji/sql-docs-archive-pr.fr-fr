---
title: Préparation des données à afficher dans une région de données de tableau matriciel (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613308"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="14450-102">Préparation des données à afficher dans une région de données de tableau matriciel (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="14450-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="14450-103">Une région de données de tableau matriciel affiche les données d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="14450-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="14450-104">Vous pouvez afficher toutes les données récupérées pour le dataset ou créer des filtres afin d'afficher uniquement un sous-ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="14450-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="14450-105">Vous pouvez également ajouter des expressions conditionnelles pour combler des valeurs NULL ou modifier la requête de dataset afin d'inclure des colonnes qui définissent l'ordre de tri d'une colonne existante.</span><span class="sxs-lookup"><span data-stu-id="14450-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="14450-106">Utilisation de valeurs NULL et d'espaces dans les valeurs de champ</span><span class="sxs-lookup"><span data-stu-id="14450-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="14450-107">Les données de la collection de champs d'un dataset incluent toutes les valeurs extraites de la source de données au moment de l'exécution, y compris les valeurs NULL et les espaces.</span><span class="sxs-lookup"><span data-stu-id="14450-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="14450-108">Normalement, les valeurs NULL et les espaces sont indifférenciables.</span><span class="sxs-lookup"><span data-stu-id="14450-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="14450-109">C'est le comportement souhaité dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="14450-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="14450-110">Par exemple, les fonctions d’agrégation numériques comme [Sum](report-builder-functions-sum-function.md) et [Avg](report-builder-functions-avg-function.md) ignorent les valeurs null.</span><span class="sxs-lookup"><span data-stu-id="14450-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="14450-111">Pour plus d’informations, consultez [Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="14450-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="14450-112">Si vous souhaitez gérer les valeurs NULL différemment, vous pouvez utiliser des expressions conditionnelles ou du code personnalisé pour substituer une valeur personnalisée à la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="14450-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="14450-113">Par exemple, l’expression suivante substitue le texte `Null` quand une valeur null est présente dans le champ `[Size]`.</span><span class="sxs-lookup"><span data-stu-id="14450-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="14450-114">Pour plus d’informations sur la suppression des valeurs null dans vos données avant d’extraire les données d’une source de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide de requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] , consultez « Valeurs Null » et « Valeurs Null et jointures » dans la documentation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au sein de la [documentation en ligne SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="14450-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="14450-115">Gestion de noms de champ NULL</span><span class="sxs-lookup"><span data-stu-id="14450-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="14450-116">Il est acceptable de tester une expression à la recherche de valeurs NULL tant que le champ lui-même existe dans le jeu de résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="14450-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="14450-117">À partir de code personnalisé, vous pouvez vérifier si le champ lui-même est présent dans la collection de champs retournée par la source de données au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="14450-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="14450-118">Pour plus d’informations, consultez [Référence à une collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="14450-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="14450-119">Ajout d'une colonne Ordre de tri</span><span class="sxs-lookup"><span data-stu-id="14450-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="14450-120">Par défaut, vous pouvez trier alphabétiquement les valeurs dans un champ de dataset.</span><span class="sxs-lookup"><span data-stu-id="14450-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="14450-121">Pour les trier dans un ordre différent, vous pouvez ajouter une nouvelle colonne à votre dataset qui définit l'ordre de tri souhaité dans une région de données.</span><span class="sxs-lookup"><span data-stu-id="14450-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="14450-122">Par exemple, pour trier les données en fonction du champ `[Color]` en commençant par les éléments noirs et blancs, vous pouvez ajouter une colonne `[ColorSortOrder]`, comme le montre la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="14450-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="14450-123">Pour trier une région de données de table conformément à cet ordre de tri, affectez la valeur `=Fields!ColorSortOrder.Value`à l’expression de tri sur le groupe de détails.</span><span class="sxs-lookup"><span data-stu-id="14450-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="14450-124">Pour plus d’informations, consultez [Trier des données dans une région de données &#40;Générateur de rapports et SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14450-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14450-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14450-125">See Also</span></span>  
 <span data-ttu-id="14450-126">[Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14450-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14450-127">[Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14450-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="14450-128">Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14450-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
