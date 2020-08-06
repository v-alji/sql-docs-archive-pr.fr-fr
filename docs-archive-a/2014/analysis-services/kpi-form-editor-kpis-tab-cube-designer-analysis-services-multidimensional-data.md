---
title: Éditeur de formulaire d’indicateur de performance clé (onglet indicateurs de performance clés, concepteur de cube) (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c88d6fcec60634f37ddad8b6d0f5cb2124fa1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602399"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="74943-102">Éditeur de formulaire d'indicateur de performance clé (onglet Indicateurs de performance clés, Concepteur de cube) (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="74943-102">KPI Form Editor (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="74943-103">Utilisez le volet **Éditeur de formulaire d’indicateur de performance clé** de l’onglet **Indicateurs de performance clés** dans le Concepteur de cube pour créer ou modifier l’indicateur de performance clé sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-103">Use the **KPI Form Editor** pane on the **KPIs** tab in Cube Designer to create or modify the selected Key Performance Indicator (KPI).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-104">Ce volet s'affiche uniquement en mode Formulaire.</span><span class="sxs-lookup"><span data-stu-id="74943-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74943-105">Options</span><span class="sxs-lookup"><span data-stu-id="74943-105">Options</span></span>  
 <span data-ttu-id="74943-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="74943-106">**Name**</span></span>  
 <span data-ttu-id="74943-107">Tapez le nom de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-107">Type the name of the KPI.</span></span>  
  
 <span data-ttu-id="74943-108">**Groupe de mesures associé**</span><span class="sxs-lookup"><span data-stu-id="74943-108">**Associated measure group**</span></span>  
 <span data-ttu-id="74943-109">Sélectionnez le groupe de mesures associé à l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-109">Select the measure group associated with the KPI.</span></span> <span data-ttu-id="74943-110">L'application cliente peut utiliser cette information pour déterminer les dimensions disponibles lorsque l'utilisateur consulte les indicateurs de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-110">The client application can use this information to determine which dimensions are available when the user browses this KPI.</span></span>  
  
 <span data-ttu-id="74943-111">**Expression de valeur**</span><span class="sxs-lookup"><span data-stu-id="74943-111">**Value Expression**</span></span>  
 <span data-ttu-id="74943-112">Développez pour afficher ou modifier l'expression MDX (Multidimensional Expressions) de la valeur de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-112">Expand to view or edit the Multidimensional Expressions (MDX) expression for the value of the KPI.</span></span>  
  
 <span data-ttu-id="74943-113">Tapez l'expression MDX qui retourne la valeur de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="74943-113">Type the MDX expression that returns the value of the KPI.</span></span>  
  
 <span data-ttu-id="74943-114">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-114">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="74943-115">**Expression d'objectif**</span><span class="sxs-lookup"><span data-stu-id="74943-115">**Goal Expression**</span></span>  
 <span data-ttu-id="74943-116">Développez pour afficher ou modifier l'expression MDX de la valeur d'objectif de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-116">Expand to view or edit the MDX expression for the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="74943-117">Tapez l'expression MDX qui retourne la valeur d'objectif de l'indicateur de performance clé lorsque ce dernier est exécuté.</span><span class="sxs-lookup"><span data-stu-id="74943-117">Type the MDX expression that returns the goal value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="74943-118">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-118">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="74943-119">**État**</span><span class="sxs-lookup"><span data-stu-id="74943-119">**Status**</span></span>  
 <span data-ttu-id="74943-120">Développez pour afficher les options **Graphique d’état** et **Expression d’état** .</span><span class="sxs-lookup"><span data-stu-id="74943-120">Expand to view the **Status graphic** and **Status expression** options.</span></span>  
  
 <span data-ttu-id="74943-121">**Graphique d’état**</span><span class="sxs-lookup"><span data-stu-id="74943-121">**Status graphic**</span></span>  
 <span data-ttu-id="74943-122">Sélectionnez le graphique que doit utiliser l'application cliente pour représenter la valeur d'état dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="74943-122">Select the graphic to be used by the client application to represent the status value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-123">L'application cliente peut prendre en charge le graphique sélectionné ou le remplacer par un autre graphique.</span><span class="sxs-lookup"><span data-stu-id="74943-123">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="74943-124">**Expression d’état**</span><span class="sxs-lookup"><span data-stu-id="74943-124">**Status expression**</span></span>  
 <span data-ttu-id="74943-125">Tapez l'expression MDX qui retourne la valeur d'état de l'indicateur de performance clé lorsque ce dernier est exécuté.</span><span class="sxs-lookup"><span data-stu-id="74943-125">Type the MDX expression that returns the status value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="74943-126">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-126">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="74943-127">Il est recommandé que cette expression retourne un nombre décimal compris entre-1 et 1.</span><span class="sxs-lookup"><span data-stu-id="74943-127">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="74943-128">Une valeur inférieure représente une situation négative alors qu'une valeur supérieure représente une situation positive.</span><span class="sxs-lookup"><span data-stu-id="74943-128">A lower number represents a negative situation, while a higher number represents a positive situation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-129">Les valeurs inférieures à 1 et supérieures à 1 sont possibles, mais elles peuvent ne pas être interprétées correctement par des applications clientes tierces.</span><span class="sxs-lookup"><span data-stu-id="74943-129">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="74943-130">**Tendance**</span><span class="sxs-lookup"><span data-stu-id="74943-130">**Trend**</span></span>  
 <span data-ttu-id="74943-131">Développez pour afficher les options **Graphique de tendance** et **Expression de tendance** .</span><span class="sxs-lookup"><span data-stu-id="74943-131">Expand to view the **Trend graphic** and **Trend expression** options.</span></span>  
  
 <span data-ttu-id="74943-132">**Graphique de tendance**</span><span class="sxs-lookup"><span data-stu-id="74943-132">**Trend graphic**</span></span>  
 <span data-ttu-id="74943-133">Sélectionnez le graphique que doit utiliser l'application cliente pour représenter la valeur de tendance dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="74943-133">Select the graphic to be used by the client application to represent the trend value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-134">L'application cliente peut prendre en charge le graphique sélectionné ou le remplacer par un autre graphique.</span><span class="sxs-lookup"><span data-stu-id="74943-134">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="74943-135">**Expression de tendance**</span><span class="sxs-lookup"><span data-stu-id="74943-135">**Trend expression**</span></span>  
 <span data-ttu-id="74943-136">Tapez l'expression MDX qui retourne la valeur de tendance de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-136">Type the MDX expression that returns the trend value of the KPI.</span></span>  
  
 <span data-ttu-id="74943-137">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-137">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="74943-138">L'expression de tendance peut être basée sur un critère temps qui a une signification dans un contexte d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="74943-138">The trend expression can be based on any time-based criteria that makes sense in a given business context.</span></span> <span data-ttu-id="74943-139">Il est recommandé que cette expression retourne un nombre décimal compris entre-1 et 1.</span><span class="sxs-lookup"><span data-stu-id="74943-139">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="74943-140">Une valeur inférieure représente une tendance négative dans le temps alors qu'une valeur supérieure représente une tendance positive.</span><span class="sxs-lookup"><span data-stu-id="74943-140">A lower number represents a negative trend over time; a higher number represents a positive trend over time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-141">Les valeurs inférieures à 1 et supérieures à 1 sont possibles, mais elles peuvent ne pas être interprétées correctement par des applications clientes tierces.</span><span class="sxs-lookup"><span data-stu-id="74943-141">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="74943-142">**Propriétés supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="74943-142">**Additional Properties**</span></span>  
 <span data-ttu-id="74943-143">Développez pour afficher les options **Afficher le dossier**, **Indicateur de performance clé parent**, **Membre à l’heure actuelle**, **Poids**et **Description** .</span><span class="sxs-lookup"><span data-stu-id="74943-143">Expand to view the **Display folder**, **Parent KPI**, **Current time member**, **Weight**, and **Description** options.</span></span>  
  
 <span data-ttu-id="74943-144">**Dossier d’affichage**</span><span class="sxs-lookup"><span data-stu-id="74943-144">**Display folder**</span></span>  
 <span data-ttu-id="74943-145">Tapez la catégorisation de l'indicateur de performance clé que doit utiliser l'application cliente pour l'affichage.</span><span class="sxs-lookup"><span data-stu-id="74943-145">Type the categorization of the KPI for use by the client application for display purposes.</span></span>  
  
 <span data-ttu-id="74943-146">Utilisez une barre oblique inverse (\\) pour séparer les noms de dossiers dans le dossier d’affichage, et un point-virgule (;) pour séparer plusieurs dossiers d’affichage.</span><span class="sxs-lookup"><span data-stu-id="74943-146">Use a backward slash (\\) to separate folder names in a display folder and a semicolon (;) to separate multiple display folders.</span></span> <span data-ttu-id="74943-147">Par exemple, tapez `Category\Goal\Scientific;Category\Goal\Metric`.</span><span class="sxs-lookup"><span data-stu-id="74943-147">For example, type `Category\Goal\Scientific;Category\Goal\Metric`.</span></span>  
  
 <span data-ttu-id="74943-148">**Indicateur de performance clé parent**</span><span class="sxs-lookup"><span data-stu-id="74943-148">**Parent KPI**</span></span>  
 <span data-ttu-id="74943-149">Sélectionnez un indicateur de performance clé existant pour catégoriser l'indicateur de performance clé que doit utiliser l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="74943-149">Select an existing KPI under which to categorize the KPI for use by the client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74943-150">Si cette option est affectée d’un indicateur de performance clé existant, **Afficher le dossier** est ignoré.</span><span class="sxs-lookup"><span data-stu-id="74943-150">If this option is set to an existing KPI, **Display folder** is ignored.</span></span>  
  
 <span data-ttu-id="74943-151">**Membre à l'heure actuelle**</span><span class="sxs-lookup"><span data-stu-id="74943-151">**Current time member**</span></span>  
 <span data-ttu-id="74943-152">Tapez l'expression MDX qui retourne le membre qui identifie le contexte temporel de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-152">Type the MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>  
  
 <span data-ttu-id="74943-153">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74943-154">L’expression MDX doit retourner le nom unique d’un membre dans une dimension de temps associée au groupe de mesures défini dans **Groupe de mesures associé**.</span><span class="sxs-lookup"><span data-stu-id="74943-154">The MDX expression must return the unique name of a member within a time dimension associated with the measure group specified in **Associated measure group**.</span></span>  
  
 <span data-ttu-id="74943-155">**Poids**</span><span class="sxs-lookup"><span data-stu-id="74943-155">**Weight**</span></span>  
 <span data-ttu-id="74943-156">Développez pour afficher ou modifier l'expression MDX du facteur de poids de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-156">Expand to view or edit the MDX expression for the weighting factor of the KPI.</span></span>  
  
 <span data-ttu-id="74943-157">Faites glisser les éléments sélectionnés du volet **Outils de calcul** dans cette option pour inclure la syntaxe MDX de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74943-157">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="74943-158">**Description**</span><span class="sxs-lookup"><span data-stu-id="74943-158">**Description**</span></span>  
 <span data-ttu-id="74943-159">Tapez la description facultative de l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="74943-159">Type the optional description of the KPI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74943-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74943-160">See Also</span></span>  
 [<span data-ttu-id="74943-161">Indicateurs de performance clés &#40;&#41; &#40;concepteur de cube Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="74943-161">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
