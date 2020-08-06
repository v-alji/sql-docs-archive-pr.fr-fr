---
title: Filtres couramment utilisés (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 201cf83d431d1b61e0f20e9d039b2016ad4f13e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610452"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a><span data-ttu-id="7eff4-102">Filtres couramment utilisés (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="7eff4-102">Commonly Used Filters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7eff4-103">Pour créer un filtre, vous devez spécifier une ou plusieurs équations de filtre.</span><span class="sxs-lookup"><span data-stu-id="7eff4-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="7eff4-104">Une équation de filtre comprend une expression, un type de données, un opérateur et une valeur.</span><span class="sxs-lookup"><span data-stu-id="7eff4-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="7eff4-105">Cette rubrique donne des exemples de filtres couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="7eff4-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="7eff4-106">Exemples de filtres</span><span class="sxs-lookup"><span data-stu-id="7eff4-106">Filter Examples</span></span>  
 <span data-ttu-id="7eff4-107">Le tableau ci-dessous donne des exemples d'équations de filtre qui utilisent différents types de données et différent opérateurs.</span><span class="sxs-lookup"><span data-stu-id="7eff4-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="7eff4-108">L'étendue de la comparaison est déterminée par l'élément de rapport pour lequel un filtre est défini.</span><span class="sxs-lookup"><span data-stu-id="7eff4-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="7eff4-109">Par exemple, pour un filtre défini sur un dataset, **10 principaux %** représente les 10 premiers pour cent des valeurs dans le dataset ; pour un filtre défini sur un groupe, **10 principaux %** représente les 10 premiers pour cent des valeurs dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="7eff4-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="7eff4-110">Expression simple</span><span class="sxs-lookup"><span data-stu-id="7eff4-110">Simple Expression</span></span>|<span data-ttu-id="7eff4-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="7eff4-111">Data Type</span></span>|<span data-ttu-id="7eff4-112">Opérateur</span><span class="sxs-lookup"><span data-stu-id="7eff4-112">Operator</span></span>|<span data-ttu-id="7eff4-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="7eff4-113">Value</span></span>|<span data-ttu-id="7eff4-114">Description</span><span class="sxs-lookup"><span data-stu-id="7eff4-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="7eff4-115">Inclut des valeurs de données supérieures à 7.</span><span class="sxs-lookup"><span data-stu-id="7eff4-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="7eff4-116">Inclut les 10 premières valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="7eff4-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="7eff4-117">Inclut les 20 premiers pour cent des valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="7eff4-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="7eff4-118">Inclut toutes les valeurs de type System.Decimal (types de données money SQL) supérieures à 100 $.</span><span class="sxs-lookup"><span data-stu-id="7eff4-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|<span data-ttu-id="7eff4-119">Inclut toutes les dates du 1er janvier 2008 à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="7eff4-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="7eff4-120">Inclut les dates à partir du 1er janvier 2008 jusqu'au 1er février 2008 compris.</span><span class="sxs-lookup"><span data-stu-id="7eff4-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="7eff4-121">Tous les noms de secteurs qui se terminent par « est ».</span><span class="sxs-lookup"><span data-stu-id="7eff4-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="7eff4-122">Tous les secteurs dont le nom commence par Nord et Sud.</span><span class="sxs-lookup"><span data-stu-id="7eff4-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="7eff4-123">Toutes les valeurs de sous-catégorie commençant par les lettres B, C ou T.</span><span class="sxs-lookup"><span data-stu-id="7eff4-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="examples-with-report-parameters"></a><span data-ttu-id="7eff4-124">Exemples avec des paramètres de rapport</span><span class="sxs-lookup"><span data-stu-id="7eff4-124">Examples with Report Parameters</span></span>  
 <span data-ttu-id="7eff4-125">Le tableau suivant fournit des exemples d'expressions de filtre comprenant une référence de paramètre à valeur unique ou à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="7eff4-125">The following table provides examples of filter expression that includes a single-value or multivalue parameter reference.</span></span>  
  
|<span data-ttu-id="7eff4-126">Type de paramètre</span><span class="sxs-lookup"><span data-stu-id="7eff4-126">Parameter type</span></span>|<span data-ttu-id="7eff4-127">Expression (de filtre)</span><span class="sxs-lookup"><span data-stu-id="7eff4-127">(Filter) Expression</span></span>|<span data-ttu-id="7eff4-128">Opérateur</span><span class="sxs-lookup"><span data-stu-id="7eff4-128">Operator</span></span>|<span data-ttu-id="7eff4-129">Valeur</span><span class="sxs-lookup"><span data-stu-id="7eff4-129">Value</span></span>|<span data-ttu-id="7eff4-130">Type de données</span><span class="sxs-lookup"><span data-stu-id="7eff4-130">Data Type</span></span>|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|<span data-ttu-id="7eff4-131">Valeur unique</span><span class="sxs-lookup"><span data-stu-id="7eff4-131">Single value</span></span>|`[EmployeeID]`|=|`[@EmployeeID]`|<span data-ttu-id="7eff4-132">Integer</span><span class="sxs-lookup"><span data-stu-id="7eff4-132">Integer</span></span>|  
|<span data-ttu-id="7eff4-133">Valeurs multiples</span><span class="sxs-lookup"><span data-stu-id="7eff4-133">Multivalue</span></span>|`[EmployeeID]`|<span data-ttu-id="7eff4-134">IN</span><span class="sxs-lookup"><span data-stu-id="7eff4-134">IN</span></span>|`[@EmployeeID]`|<span data-ttu-id="7eff4-135">Integer</span><span class="sxs-lookup"><span data-stu-id="7eff4-135">Integer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eff4-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7eff4-136">See Also</span></span>  
 <span data-ttu-id="7eff4-137">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7eff4-137">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="7eff4-138">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7eff4-138">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7eff4-139">[Les expressions sont utilisées dans les rapports &#40;Générateur de rapports et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7eff4-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7eff4-140">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7eff4-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7eff4-141">Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7eff4-141">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
