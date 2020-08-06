---
title: Définir un message d’absence de données pour une région de données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697548"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="abca5-102">Définir un message d'absence de données pour une région de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="abca5-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="abca5-103">Quand vous souhaitez qu’un texte s’affiche dans le rapport rendu à la place d’une région de données ne contenant pas de données, vous devez définir la propriété NoRowsMessage de la région de données de table, de matrice ou de liste souhaitée, la propriété NoDataMessage de la région de données de graphique et la propriété NoDataText de l’échelle de couleurs de la carte.</span><span class="sxs-lookup"><span data-stu-id="abca5-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="abca5-104">Au moment de l'exécution, le processeur de rapports exécute la requête pour chaque dataset d'un rapport et la requête de dataset peut ne produire aucun jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="abca5-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="abca5-105">Pour une région de données liée à un dataset vide, vous pouvez spécifier le texte à afficher à la place de la région de données vide.</span><span class="sxs-lookup"><span data-stu-id="abca5-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="abca5-106">Vous pouvez également définir la propriété NoRowsMessage pour un sous-rapport quand aucun dataset de ce dernier ne contient de données au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="abca5-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="abca5-107">Pour définir la propriété NoRowsMessage d'une table, matrice ou liste spécifique</span><span class="sxs-lookup"><span data-stu-id="abca5-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="abca5-108">En mode Conception, sur l'aire de conception, cliquez sur la table, la matrice, la région de données de type liste ou le sous-rapport souhaité pour sélectionner celle-ci / celui-ci.</span><span class="sxs-lookup"><span data-stu-id="abca5-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="abca5-109">Le volet Propriétés affiche les propriétés de l'élément que vous venez de sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="abca5-110">Dans le volet Propriétés, tapez le texte que vous souhaitez afficher en tant que message dans le `NoRowsMessage` champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="abca5-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="abca5-111">Vous pouvez également cliquer sur l’option **Expression** de la liste déroulante pour ouvrir la boîte de dialogue **Expression** et créer l’expression souhaitée.</span><span class="sxs-lookup"><span data-stu-id="abca5-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="abca5-112">Pour définir la propriété NoDataMessage d'un graphique</span><span class="sxs-lookup"><span data-stu-id="abca5-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="abca5-113">En mode Conception, sur l'aire de conception, cliquez sur le graphique souhaité pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="abca5-114">Le volet Propriétés affiche les propriétés de l'élément que vous venez de sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="abca5-115">Dans le volet Propriétés, développez le nœud pour `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="abca5-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="abca5-116">Dans **légende**, tapez le texte que vous souhaitez afficher en tant que message dans le `NoDataMessage` champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="abca5-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="abca5-117">Vous pouvez également cliquer sur l’option **Expression** de la liste déroulante pour ouvrir la boîte de dialogue **Expression** et créer l’expression souhaitée.</span><span class="sxs-lookup"><span data-stu-id="abca5-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="abca5-118">Pour définir la propriété NoRowsMessage d'un sous-rapport</span><span class="sxs-lookup"><span data-stu-id="abca5-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="abca5-119">En mode Conception, sur l'aire de conception, cliquez sur le sous-rapport souhaité pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="abca5-120">Le volet Propriétés affiche les propriétés de l'élément que vous venez de sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="abca5-121">Dans le volet Propriétés, tapez le texte que vous souhaitez afficher en tant que message dans le `NoRowsMessage` champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="abca5-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="abca5-122">Vous pouvez également cliquer sur l’option **Expression** de la liste déroulante pour ouvrir la boîte de dialogue **Expression** et créer l’expression souhaitée.</span><span class="sxs-lookup"><span data-stu-id="abca5-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="abca5-123">Pour définir la propriété NoDataText de l'échelle de couleurs d'une carte</span><span class="sxs-lookup"><span data-stu-id="abca5-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="abca5-124">En mode Conception, cliquez sur l'échelle de couleurs de la carte pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="abca5-125">Le volet Propriétés affiche les propriétés de l'élément que vous venez de sélectionner.</span><span class="sxs-lookup"><span data-stu-id="abca5-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="abca5-126">Dans le volet Propriétés, dans `NoDataText` , tapez le texte que vous souhaitez afficher en tant qu’étiquette pour les couleurs sans valeur de données.</span><span class="sxs-lookup"><span data-stu-id="abca5-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="abca5-127">Vous pouvez également cliquer sur l’option **Expression** de la liste déroulante pour ouvrir la boîte de dialogue **Expression** et créer l’expression souhaitée.</span><span class="sxs-lookup"><span data-stu-id="abca5-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abca5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abca5-128">See Also</span></span>  
 <span data-ttu-id="abca5-129">[Sous-rapports &#40;Générateur de rapports et SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="abca5-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="abca5-130">[Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="abca5-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="abca5-131">[Graphiques &#40;Générateur de rapports et SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="abca5-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="abca5-132">[Cartes &#40;Générateur de rapports et SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="abca5-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="abca5-133">Sous-rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="abca5-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
