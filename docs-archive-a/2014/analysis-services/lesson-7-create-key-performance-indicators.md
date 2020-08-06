---
title: 'Leçon 8 : créer des indicateurs de performance clés | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698730"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="e0cbd-102">Leçon 8 : Créer les indicateurs de performance clés</span><span class="sxs-lookup"><span data-stu-id="e0cbd-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="e0cbd-103">Au cours de cette leçon, vous allez créer des indicateurs de performance clés (KPI).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="e0cbd-104">Les KPI évaluent la performance d’une valeur, définie par une mesure de *base* , par rapport à une valeur *cible* , également définie par une mesure ou par une valeur absolue.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="e0cbd-105">Dans les applications clientes de création de rapports, les indicateurs de performance clés offrent aux professionnels un moyen d’obtenir rapidement et aisément un résumé d’un succès commercial ou d’identifier les tendances.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="e0cbd-106">Pour en savoir plus, consultez [KPI &#40;SSAS Tabulaire&#41;](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="e0cbd-107">Durée estimée pour suivre cette leçon : **15 minutes**</span><span class="sxs-lookup"><span data-stu-id="e0cbd-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0cbd-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e0cbd-108">Prerequisites</span></span>  
 <span data-ttu-id="e0cbd-109">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="e0cbd-110">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la [Leçon 7 : Créer des mesures](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="e0cbd-111">Créer des indicateurs de performance clés (KPI)</span><span class="sxs-lookup"><span data-stu-id="e0cbd-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="e0cbd-112">Pour créer un KPI des performances des ventes Internet du trimestre en cours</span><span class="sxs-lookup"><span data-stu-id="e0cbd-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="e0cbd-113">Dans le concepteur de modèles, cliquez sur la table **Internet Sales** (onglet).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="e0cbd-114">Dans la grille de mesures, cliquez sur une cellule vide.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="e0cbd-115">Dans la barre de formule située au-dessus de la table, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="e0cbd-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="e0cbd-116">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="e0cbd-117">Cette mesure servira de mesure de base à l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="e0cbd-118">Dans la grille de mesures, cliquez avec le bouton droit sur la mesure **Internet Current Quarter Sales Performance** , puis cliquez sur **Créer un KPI**.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="e0cbd-119">La boîte de dialogue **Indicateur de performance clé** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="e0cbd-120">Dans la boîte de dialogue **Indicateur de performance clé** , dans **Définir la valeur cible**, sélectionnez l’option **Valeur absolue** .</span><span class="sxs-lookup"><span data-stu-id="e0cbd-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="e0cbd-121">Dans le champ **valeur absolue** , tapez `1.1` , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="e0cbd-122">Dans **définir les seuils d’État**, dans le champ curseur de gauche (bas), tapez `1` , puis dans le champ curseur de droite (élevé), tapez `1.07` .</span><span class="sxs-lookup"><span data-stu-id="e0cbd-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="e0cbd-123">Dans **Sélectionner le style d’icône**, sélectionnez le type d’icône losange (rouge), triangle (jaune) et cercle (vert).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e0cbd-124">Notez que le champ extensible **Descriptions** apparaît sous les styles d’icône disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="e0cbd-125">Vous pouvez taper une description des différents éléments KPI afin de mieux les identifier dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="e0cbd-126">Cliquez sur **OK** pour terminer le KPI.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="e0cbd-127">Dans la grille de mesures, notez l’icône située à côté de la mesure **Internet Current Quarter Sales Performance** .</span><span class="sxs-lookup"><span data-stu-id="e0cbd-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="e0cbd-128">Cette icône indique que cette mesure sert de valeur de base à un indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="e0cbd-129">Pour créer un KPI des performances des marges Internet du trimestre en cours</span><span class="sxs-lookup"><span data-stu-id="e0cbd-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="e0cbd-130">Dans la grille de mesures pour la table **Internet Sales** , cliquez sur une cellule vide.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="e0cbd-131">Dans la barre de formule située au-dessus de la table, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="e0cbd-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="e0cbd-132">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="e0cbd-133">Dans la grille de mesures, cliquez avec le bouton droit sur la mesure **Internet Current Quarter Margin Performance** , puis cliquez sur **Créer un KPI**.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="e0cbd-134">Dans la boîte de dialogue **Indicateur de performance clé** , dans **Définir la valeur cible**, sélectionnez l’option **Valeur absolue** .</span><span class="sxs-lookup"><span data-stu-id="e0cbd-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="e0cbd-135">Dans le champ **valeur absolue** , tapez `1.25` .</span><span class="sxs-lookup"><span data-stu-id="e0cbd-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="e0cbd-136">Dans **Définir les seuils d’état**, faites glisser le secteur gauche (bas) du curseur jusqu’à ce que le champ affiche **0.8**, puis faites glisser le secteur droit (élevé) du curseur jusqu’à ce que le champ affiche **1.03**.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="e0cbd-137">Dans **Sélectionnez le style d’icône**, sélectionnez le losange (rouge), le triangle (jaune) ou le cercle (vert) comme type d’icône, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0cbd-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e0cbd-138">étape suivante</span><span class="sxs-lookup"><span data-stu-id="e0cbd-138">Next Step</span></span>  
 <span data-ttu-id="e0cbd-139">Pour continuer ce didacticiel, passez à la [Leçon 9 : Créer des perspectives](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="e0cbd-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
