---
title: Créer et gérer des indicateurs de performance clés (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603660"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="98f4a-102">Créer et gérer les indicateurs de performance clés (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="98f4a-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="98f4a-103">Cette rubrique décrit comment créer, modifier ou supprimer un indicateur de performance clé (KPI) dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="98f4a-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="98f4a-104">Pour créer un indicateur de performance clé, vous sélectionnez une mesure qui correspond à la valeur de base de l’indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="98f4a-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="98f4a-105">Utilisez ensuite la boîte de dialogue Indicateur de performance clé pour sélectionner une seconde mesure ou une valeur absolue qui prend une valeur cible.</span><span class="sxs-lookup"><span data-stu-id="98f4a-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="98f4a-106">Vous pourrez ensuite définir des seuils d'état qui mesurent les performances entre les mesures de base et cible.</span><span class="sxs-lookup"><span data-stu-id="98f4a-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="98f4a-107">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="98f4a-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="98f4a-108">Pour créer un KPI</span><span class="sxs-lookup"><span data-stu-id="98f4a-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="98f4a-109">Pour modifier un KPI</span><span class="sxs-lookup"><span data-stu-id="98f4a-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="98f4a-110">Pour supprimer un KPI et la mesure de base</span><span class="sxs-lookup"><span data-stu-id="98f4a-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="98f4a-111">Pour supprimer un KPI, mais conserver la mesure de base</span><span class="sxs-lookup"><span data-stu-id="98f4a-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="98f4a-112">Tâches</span><span class="sxs-lookup"><span data-stu-id="98f4a-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98f4a-113">Avant de créer un KPI, vous devez d'abord créer une mesure de base qui retourne une valeur.</span><span class="sxs-lookup"><span data-stu-id="98f4a-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="98f4a-114">La mesure de base doit ensuite être étendue à un KPI.</span><span class="sxs-lookup"><span data-stu-id="98f4a-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="98f4a-115">Pour savoir comment créer des mesures, consultez la rubrique [Créer et gérer des mesures &#40;SSAS Tabulaire&#41;](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="98f4a-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="98f4a-116">Un KPI nécessite également une valeur cible.</span><span class="sxs-lookup"><span data-stu-id="98f4a-116">A KPI also requires a target value.</span></span> <span data-ttu-id="98f4a-117">Cette valeur peut être obtenue à partir d'une autre valeur prédéfinie ou d'une valeur absolue.</span><span class="sxs-lookup"><span data-stu-id="98f4a-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="98f4a-118">Une fois que vous avez étendu une mesure de base à un KPI, vous pouvez sélectionner la valeur cible et définir les seuils d’état dans la boîte de dialogue Indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="98f4a-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a><span data-ttu-id="98f4a-119">Pour créer un indicateur de performance clé</span><span class="sxs-lookup"><span data-stu-id="98f4a-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="98f4a-120">Dans la Grille de mesures, cliquez avec le bouton droit sur la mesure qui sert de mesure de base (valeur), puis cliquez sur **Créer un KPI**.</span><span class="sxs-lookup"><span data-stu-id="98f4a-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="98f4a-121">Dans la boîte de dialogue **Indicateur de performance clé** , dans **Définir la valeur cible**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="98f4a-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="98f4a-122">Sélectionnez **Mesure**, puis sélectionnez une mesure cible dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="98f4a-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="98f4a-123">Sélectionnez **Valeur absolue**, puis entrez une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="98f4a-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="98f4a-124">Dans **Définir les seuils d’état**, cliquez sur les valeurs des seuils et faites-les glisser.</span><span class="sxs-lookup"><span data-stu-id="98f4a-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="98f4a-125">Dans **Sélectionner le style d’icône**, cliquez sur un type d’image.</span><span class="sxs-lookup"><span data-stu-id="98f4a-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="98f4a-126">Cliquez sur **Descriptions**, puis tapez une description du KPI, de la valeur, de l’état et de la cible.</span><span class="sxs-lookup"><span data-stu-id="98f4a-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="98f4a-127">Vous pouvez utiliser la fonctionnalité Analyser dans Excel pour tester votre indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="98f4a-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="98f4a-128">Pour plus d'informations, consultez la section [Analyser dans Excel &#40;SSAS Tabulaire&#41;](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="98f4a-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a><span data-ttu-id="98f4a-129">Pour modifier un KPI</span><span class="sxs-lookup"><span data-stu-id="98f4a-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="98f4a-130">Dans la grille de mesures, cliquez avec le bouton droit sur la mesure qui sert de mesure de base (valeur) du KPI, puis cliquez sur **Modifier les paramètres du KPI**.</span><span class="sxs-lookup"><span data-stu-id="98f4a-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="98f4a-131">Pour supprimer un KPI et la mesure de base</span><span class="sxs-lookup"><span data-stu-id="98f4a-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="98f4a-132">Dans la grille de mesures, cliquez avec le bouton droit sur la mesure qui sert de mesure de base (valeur) du KPI, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="98f4a-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="98f4a-133">Pour supprimer un KPI, mais conserver la mesure de base</span><span class="sxs-lookup"><span data-stu-id="98f4a-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="98f4a-134">Dans la grille de mesures, cliquez avec le bouton droit sur la mesure qui sert de mesure de base (valeur) du KPI, puis cliquez sur **Supprimer le KPI**.</span><span class="sxs-lookup"><span data-stu-id="98f4a-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="98f4a-135">Raccourcis Alt</span><span class="sxs-lookup"><span data-stu-id="98f4a-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="98f4a-136">Section de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="98f4a-136">UI section</span></span>|<span data-ttu-id="98f4a-137">Combinaison de touches</span><span class="sxs-lookup"><span data-stu-id="98f4a-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="98f4a-138">Mesure de base du KPI</span><span class="sxs-lookup"><span data-stu-id="98f4a-138">KPI base measure</span></span>|<span data-ttu-id="98f4a-139">Alt+B</span><span class="sxs-lookup"><span data-stu-id="98f4a-139">ALT+B</span></span>|  
|<span data-ttu-id="98f4a-140">État du KPI</span><span class="sxs-lookup"><span data-stu-id="98f4a-140">KPI Status</span></span>|<span data-ttu-id="98f4a-141">Alt+S</span><span class="sxs-lookup"><span data-stu-id="98f4a-141">ALT+S</span></span>|  
|<span data-ttu-id="98f4a-142">Measure</span><span class="sxs-lookup"><span data-stu-id="98f4a-142">Measure</span></span>|<span data-ttu-id="98f4a-143">Alt+M</span><span class="sxs-lookup"><span data-stu-id="98f4a-143">ALT+M</span></span>|  
|<span data-ttu-id="98f4a-144">Valeur absolue</span><span class="sxs-lookup"><span data-stu-id="98f4a-144">Absolute value</span></span>|<span data-ttu-id="98f4a-145">ALT + A</span><span class="sxs-lookup"><span data-stu-id="98f4a-145">ALT+A</span></span>|  
|<span data-ttu-id="98f4a-146">Définir les seuils d’état</span><span class="sxs-lookup"><span data-stu-id="98f4a-146">Define status thresholds</span></span>|<span data-ttu-id="98f4a-147">Alt+U</span><span class="sxs-lookup"><span data-stu-id="98f4a-147">ALT+U</span></span>|  
|<span data-ttu-id="98f4a-148">Sélectionner le style d’icône</span><span class="sxs-lookup"><span data-stu-id="98f4a-148">Select icon style</span></span>|<span data-ttu-id="98f4a-149">Alt+I</span><span class="sxs-lookup"><span data-stu-id="98f4a-149">ALT+I</span></span>|  
|<span data-ttu-id="98f4a-150">Tendance</span><span class="sxs-lookup"><span data-stu-id="98f4a-150">Trend</span></span>|<span data-ttu-id="98f4a-151">Alt+T</span><span class="sxs-lookup"><span data-stu-id="98f4a-151">ALT+T</span></span>|  
|<span data-ttu-id="98f4a-152">Descriptions</span><span class="sxs-lookup"><span data-stu-id="98f4a-152">Descriptions</span></span>|<span data-ttu-id="98f4a-153">Alt+D</span><span class="sxs-lookup"><span data-stu-id="98f4a-153">ALT+D</span></span>|  
|<span data-ttu-id="98f4a-154">Tendance</span><span class="sxs-lookup"><span data-stu-id="98f4a-154">Trend</span></span>|<span data-ttu-id="98f4a-155">Alt+T</span><span class="sxs-lookup"><span data-stu-id="98f4a-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98f4a-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98f4a-156">See Also</span></span>  
 <span data-ttu-id="98f4a-157">[KPI &#40;&#41;tabulaires SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="98f4a-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="98f4a-158">[Mesures &#40;&#41;tabulaire SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="98f4a-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="98f4a-159">Créer et gérer des mesures &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="98f4a-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
