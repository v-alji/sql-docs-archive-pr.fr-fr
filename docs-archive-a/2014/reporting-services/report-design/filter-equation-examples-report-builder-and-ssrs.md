---
title: Exemples d’équations de filtre (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b4d7c7c561c9185c141190e26f37bc29fe52eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603841"
---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a><span data-ttu-id="0975b-102">Exemples d'équations de filtre (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="0975b-102">Filter Equation Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0975b-103">Pour créer un filtre, vous devez spécifier une ou plusieurs équations de filtre.</span><span class="sxs-lookup"><span data-stu-id="0975b-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="0975b-104">Une équation de filtre comprend une expression, un type de données, un opérateur et une valeur.</span><span class="sxs-lookup"><span data-stu-id="0975b-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="0975b-105">Cette rubrique donne des exemples de filtres couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="0975b-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="0975b-106">Exemples de filtres</span><span class="sxs-lookup"><span data-stu-id="0975b-106">Filter Examples</span></span>  
 <span data-ttu-id="0975b-107">Le tableau ci-dessous donne des exemples d'équations de filtre qui utilisent différents types de données et différent opérateurs.</span><span class="sxs-lookup"><span data-stu-id="0975b-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="0975b-108">L'étendue de la comparaison est déterminée par l'élément de rapport pour lequel un filtre est défini.</span><span class="sxs-lookup"><span data-stu-id="0975b-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="0975b-109">Par exemple, pour un filtre défini sur un dataset, **10 principaux %** représente les 10 premiers pour cent des valeurs dans le dataset ; pour un filtre défini sur un groupe, **10 principaux %** représente les 10 premiers pour cent des valeurs dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="0975b-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="0975b-110">Expression simple</span><span class="sxs-lookup"><span data-stu-id="0975b-110">Simple Expression</span></span>|<span data-ttu-id="0975b-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="0975b-111">Data Type</span></span>|<span data-ttu-id="0975b-112">Opérateur</span><span class="sxs-lookup"><span data-stu-id="0975b-112">Operator</span></span>|<span data-ttu-id="0975b-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="0975b-113">Value</span></span>|<span data-ttu-id="0975b-114">Description</span><span class="sxs-lookup"><span data-stu-id="0975b-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="0975b-115">Inclut des valeurs de données supérieures à 7.</span><span class="sxs-lookup"><span data-stu-id="0975b-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="0975b-116">Inclut les 10 premières valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="0975b-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="0975b-117">Inclut les 20 premiers pour cent des valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="0975b-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="0975b-118">Inclut toutes les valeurs de type System.Decimal (types de données money SQL) supérieures à 100 $.</span><span class="sxs-lookup"><span data-stu-id="0975b-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2008-01-01`|<span data-ttu-id="0975b-119">Inclut toutes les dates du 1er janvier 2008 à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="0975b-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="0975b-120">Inclut les dates à partir du 1er janvier 2008 jusqu'au 1er février 2008 compris.</span><span class="sxs-lookup"><span data-stu-id="0975b-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="0975b-121">Tous les noms de secteurs qui se terminent par « est ».</span><span class="sxs-lookup"><span data-stu-id="0975b-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="0975b-122">Tous les secteurs dont le nom commence par Nord et Sud.</span><span class="sxs-lookup"><span data-stu-id="0975b-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="0975b-123">Toutes les valeurs de sous-catégorie commençant par les lettres B, C ou T.</span><span class="sxs-lookup"><span data-stu-id="0975b-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0975b-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0975b-124">See Also</span></span>  
 <span data-ttu-id="0975b-125">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="0975b-125">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="0975b-126">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="0975b-126">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="0975b-127">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0975b-127">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0975b-128">[Les expressions sont utilisées dans les rapports &#40;Générateur de rapports et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0975b-128">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0975b-129">Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0975b-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
