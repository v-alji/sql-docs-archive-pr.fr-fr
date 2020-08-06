---
title: Créer et gérer des mesures (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603659"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="0d6a1-102">Créer et gérer des mesures (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="0d6a1-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="0d6a1-103">Une mesure est une formule créée pour être utilisée dans un rapport ou un tableau croisé dynamique (ou un graphique croisé dynamique) Excel.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="0d6a1-104">Les mesures peuvent reposer sur des fonctions d'agrégation standard, comme COUNT ou SUM, ou vous pouvez définir votre propre formule à l'aide de DAX.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="0d6a1-105">Les tâches de cette rubrique décrivent comment créer et gérer des mesures à l’aide de la grille de mesures d’une table.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="0d6a1-106">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d6a1-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="0d6a1-107">Pour créer une mesure qui utilise une formule d'agrégation standard</span><span class="sxs-lookup"><span data-stu-id="0d6a1-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="0d6a1-108">Pour créer une mesure à l’aide d’une formule personnalisée</span><span class="sxs-lookup"><span data-stu-id="0d6a1-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="0d6a1-109">Pour modifier les propriétés de mesure</span><span class="sxs-lookup"><span data-stu-id="0d6a1-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="0d6a1-110">Pour renommer une mesure</span><span class="sxs-lookup"><span data-stu-id="0d6a1-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="0d6a1-111">Pour supprimer une mesure</span><span class="sxs-lookup"><span data-stu-id="0d6a1-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="0d6a1-112">Tâches</span><span class="sxs-lookup"><span data-stu-id="0d6a1-112">Tasks</span></span>  
 <span data-ttu-id="0d6a1-113">Pour créer et gérer des mesures, vous allez utiliser la grille de mesures d’une table.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="0d6a1-114">Vous pouvez afficher la grille de mesures pour une table dans le générateur de modèles dans la vue de données uniquement.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="0d6a1-115">Vous ne pouvez pas créer de mesures ni afficher la grille de mesures dans la vue de diagramme ; toutefois, vous pouvez afficher des mesures existantes dans la vue de diagramme.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="0d6a1-116">Pour afficher la grille de mesures d'une table, cliquez sur le menu **Table** , puis sur **Afficher la grille de mesures**.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="0d6a1-117">Pour créer une mesure à l’aide d’une formule d’agrégation standard</span><span class="sxs-lookup"><span data-stu-id="0d6a1-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="0d6a1-118">Cliquez sur la colonne pour laquelle vous souhaitez créer la mesure, puis dans le menu **Colonne** , pointez sur **Somme automatique**, puis cliquez sur un type d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="0d6a1-119">La mesure est créée automatiquement avec un nom par défaut, suivi de la formule dans la première cellule de la grille de mesures directement sous la colonne.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="0d6a1-120">Pour créer une mesure qui utilise une formule personnalisée</span><span class="sxs-lookup"><span data-stu-id="0d6a1-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="0d6a1-121">Dans la grille de mesures, sous la colonne pour laquelle vous souhaitez créer la mesure, cliquez sur une cellule, puis dans la barre de formule, tapez un nom, suivi de deux-points (:), d’un signe égal (=) et de la formule.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="0d6a1-122">Appuyez sur Entrée pour accepter la formule.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a><span data-ttu-id="0d6a1-123">Pour modifier des propriétés de mesures</span><span class="sxs-lookup"><span data-stu-id="0d6a1-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="0d6a1-124">Dans la grille de mesures, cliquez sur une mesure, puis dans la fenêtre **Propriétés** , tapez ou sélectionnez une valeur de propriété différente.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a><span data-ttu-id="0d6a1-125">Pour renommer une mesure</span><span class="sxs-lookup"><span data-stu-id="0d6a1-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="0d6a1-126">Dans la grille de mesures, cliquez sur une mesure, puis dans la fenêtre **Propriétés** , dans **Nom de la mesure**, tapez un nouveau nom et cliquez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="0d6a1-127">Vous pouvez également renommer une mesure dans la barre de formule.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="0d6a1-128">Le nom de la mesure précède la formule, suivi de deux-points.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="0d6a1-129">Pour supprimer une mesure</span><span class="sxs-lookup"><span data-stu-id="0d6a1-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="0d6a1-130">Dans la grille de mesures, cliquez avec le bouton droit sur une mesure, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6a1-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d6a1-131">See Also</span></span>  
 <span data-ttu-id="0d6a1-132">[Mesures &#40;&#41;tabulaire SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="0d6a1-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="0d6a1-133">[KPI &#40;&#41;tabulaires SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="0d6a1-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="0d6a1-134">Colonnes calculées &#40;SSAS tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="0d6a1-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
