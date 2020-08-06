---
title: Navigateur d’indicateur de performance clé (onglet indicateurs de performance clés, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602402"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="cc6fe-102">Navigateur d'indicateur de performance clé (onglet Indicateurs de performance clés, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="cc6fe-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="cc6fe-103">Le volet **Navigateur d’indicateur de performance clé** de l’onglet **Indicateurs de performance clés** du Concepteur de cube permet d’afficher et de tester les résultats des indicateurs de performance clés (KPI).</span><span class="sxs-lookup"><span data-stu-id="cc6fe-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="cc6fe-104">Vous devez d’abord déployer les indicateurs de performance clés sur une [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance avant de naviguer.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc6fe-105">Ce volet s'affiche uniquement en mode Navigateur.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc6fe-106">Options</span><span class="sxs-lookup"><span data-stu-id="cc6fe-106">Options</span></span>  
 <span data-ttu-id="cc6fe-107">**Grille Sous-cube**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-107">**Subcube grid**</span></span>  
 <span data-ttu-id="cc6fe-108">Permet de définir un sous-cube et de limiter les résultats des indicateurs de performance clés à afficher dans le volet **Résultats** .</span><span class="sxs-lookup"><span data-stu-id="cc6fe-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="cc6fe-109">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc6fe-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="cc6fe-110">**Dimension**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-110">**Dimension**</span></span>  
 <span data-ttu-id="cc6fe-111">Sélectionnez la dimension à laquelle ce filtre s'applique.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="cc6fe-112">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-112">**Hierarchy**</span></span>  
 <span data-ttu-id="cc6fe-113">Sélectionnez la hiérarchie à laquelle ce filtre s'applique.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="cc6fe-114">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-114">**Operator**</span></span>  
 <span data-ttu-id="cc6fe-115">Sélectionnez l’opérateur qui définit comment l’expression dans **Expression de filtre** est appliquée à la hiérarchie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="cc6fe-116">Le tableau suivant décrit les opérateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="cc6fe-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="cc6fe-117">Value</span></span>|<span data-ttu-id="cc6fe-118">Description</span><span class="sxs-lookup"><span data-stu-id="cc6fe-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cc6fe-119">**Égal**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-119">**Equal**</span></span>|<span data-ttu-id="cc6fe-120">Les résultats se limitent à l'ensemble défini dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-121">**Différent de**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-121">**Not Equal**</span></span>|<span data-ttu-id="cc6fe-122">Les résultats se limitent aux membres n'appartenant pas à l'ensemble défini dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-123">**Dans**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-123">**In**</span></span>|<span data-ttu-id="cc6fe-124">Les résultats se limitent à l'ensemble nommé choisi dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-125">**Pas dans**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-125">**Not In**</span></span>|<span data-ttu-id="cc6fe-126">Les résultats se limitent aux membres n'appartenant pas à l'ensemble nommé choisi dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-127">**Contains**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-127">**Contains**</span></span>|<span data-ttu-id="cc6fe-128">Les résultats se limitent aux membres dont le nom contient la chaîne de caractères figurant dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-129">**Commence par**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-129">**Begins With**</span></span>|<span data-ttu-id="cc6fe-130">Les résultats se limitent aux membres dont le nom commence par la chaîne de caractères figurant dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-131">**Plage (limites incluses)**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="cc6fe-132">Les résultats se limitent à la plage choisie dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-133">**Plage (limites exclues)**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="cc6fe-134">Les résultats se limitent aux membres n'appartenant pas à la plage choisie dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="cc6fe-135">**MDX**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-135">**MDX**</span></span>|<span data-ttu-id="cc6fe-136">Les résultats se limitent aux expressions MDX (Multidimensional Expressions) définies dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="cc6fe-137">**Expression de filtre**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-137">**Filter Expression**</span></span>  
 <span data-ttu-id="cc6fe-138">Tapez l’expression que **Opérateur**doit évaluer, qui se limite aux résultats des indicateurs de performance clés à parcourir.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc6fe-139">Ce champ est un élément dynamique de saisie des données dont l'aspect change en fonction des types de données nécessaires à l'opérateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="cc6fe-140">**Grille de résultats**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-140">**Results grid**</span></span>  
 <span data-ttu-id="cc6fe-141">Affiche la valeur évaluée, l’objectif, l’état et la tendance pour les indicateurs de performance clés, en fonction du filtre défini dans la **Grille de filtrage**.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="cc6fe-142">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc6fe-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="cc6fe-143">**Afficher la structure**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-143">**Display Structure**</span></span>  
 <span data-ttu-id="cc6fe-144">Affiche les indicateurs de performance clés contenus dans le cube. Ils sont organisés hiérarchiquement en fonction des valeurs **Afficher le dossier** ou **Indicateur de performance clé parent** pour chaque KPI.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-145">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-145">**Value**</span></span>  
 <span data-ttu-id="cc6fe-146">Affiche la valeur de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-147">**Objectif**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-147">**Goal**</span></span>  
 <span data-ttu-id="cc6fe-148">Affiche l'objectif de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-149">**État**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-149">**Status**</span></span>  
 <span data-ttu-id="cc6fe-150">Affiche le graphique d'état de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-151">**Tendance**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-151">**Trend**</span></span>  
 <span data-ttu-id="cc6fe-152">Affiche le graphique de tendance de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-153">**Poids**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-153">**Weight**</span></span>  
 <span data-ttu-id="cc6fe-154">Affiche le facteur poids de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-155">**Descriptive**</span><span class="sxs-lookup"><span data-stu-id="cc6fe-155">**(Description)**</span></span>  
 <span data-ttu-id="cc6fe-156">Affiche une icône d'information si l'indicateur de performance clé est associé à une description.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="cc6fe-157">Placez le pointeur de la souris sur l'icône d'information afin d'afficher une info-bulle contenant la description de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc6fe-158">Si une erreur se produit lors du calcul d’un indicateur de performance clé sur l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , cette option affiche les informations relatives à l’erreur.</span><span class="sxs-lookup"><span data-stu-id="cc6fe-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6fe-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc6fe-159">See Also</span></span>  
 [<span data-ttu-id="cc6fe-160">Indicateurs de performance clés &#40;&#41; &#40;concepteur de cube Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="cc6fe-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
