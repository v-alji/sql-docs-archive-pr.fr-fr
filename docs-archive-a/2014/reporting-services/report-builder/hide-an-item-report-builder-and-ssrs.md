---
title: Masquer un élément (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603286"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="d33f4-102">Masquer un élément (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="d33f4-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d33f4-103">Définissez la visibilité d'un élément de rapport lorsque vous souhaitez masquer de façon conditionnelle un élément en fonction d'un paramètre de rapport ou d'une autre expression que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="d33f4-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="d33f4-104">Vous pouvez également concevoir un rapport afin de permettre aux utilisateurs d'activer ou de désactiver la visibilité des éléments de rapport en fonction de clics sur des zones de texte dans le rapport, par exemple pour un rapport d'exploration.</span><span class="sxs-lookup"><span data-stu-id="d33f4-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="d33f4-105">Pour plus d’informations, consultez [Ajouter une action Développer ou Réduire à un élément &#40;Générateur de rapports et SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d33f4-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="d33f4-106">Les procédures suivantes décrivent comment afficher ou masquer un élément de rapport dans un rapport rendu en fonction d'une constante ou d'une expression.</span><span class="sxs-lookup"><span data-stu-id="d33f4-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="d33f4-107">Pour masquer un élément de rapport</span><span class="sxs-lookup"><span data-stu-id="d33f4-107">To hide a report item</span></span>

1.  <span data-ttu-id="d33f4-108">En mode création de rapport, cliquez avec le bouton droit sur l’élément de rapport et ouvrez sa page **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="d33f4-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d33f4-109">Pour sélectionner l’intégralité d’une région de données de table ou de matrice, cliquez dans la région de données pour la sélectionner, cliquez avec le bouton droit sur une ligne, une colonne ou une poignée d’angle, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="d33f4-110">Cliquez sur **visibilité.**</span><span class="sxs-lookup"><span data-stu-id="d33f4-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="d33f4-111">Dans **Lors de la première exécution du rapport**, spécifiez s’il faut masquer ou non l’élément quand le rapport est affiché pour la première fois :</span><span class="sxs-lookup"><span data-stu-id="d33f4-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="d33f4-112">Pour afficher l’élément, cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="d33f4-113">Pour masquer l’élément, cliquez sur **Masquer**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="d33f4-114">Pour spécifier une expression qui est évaluée au moment de l’exécution, cliquez sur **Afficher ou masquer en fonction d’une expression**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="d33f4-115">Tapez l’expression ou cliquez sur le bouton Expression (**fx**) pour créer l’expression dans la boîte de dialogue **Expression** .</span><span class="sxs-lookup"><span data-stu-id="d33f4-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="d33f4-116">Quand vous spécifiez une expression de visibilité, vous définissez la propriété Hidden de l’élément de rapport, comment indiqué dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="d33f4-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="d33f4-117">L'expression évaluée affiche l'élément de rapport lorsque la valeur est False et le masque lorsque la valeur est True.</span><span class="sxs-lookup"><span data-stu-id="d33f4-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="d33f4-118">![Boîte de dialogue de visibilité de propriétés et propriété masquée](../media/hiddenproperty-propertiesvisibility.png "Boîte de dialogue de visibilité de propriétés et propriété masquée")</span><span class="sxs-lookup"><span data-stu-id="d33f4-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="d33f4-119">Cliquez deux fois sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="d33f4-120">Pour masquer des lignes statiques dans une table, une matrice ou une liste</span><span class="sxs-lookup"><span data-stu-id="d33f4-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="d33f4-121">En mode création de rapport, cliquez sur la table, la matrice ou la liste afin d'afficher les handles de ligne et de colonne.</span><span class="sxs-lookup"><span data-stu-id="d33f4-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="d33f4-122">Cliquez avec le bouton droit sur le handle de ligne, puis cliquez sur **Visibilité de ligne**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="d33f4-123">La boîte de dialogue **Visibilité de ligne** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="d33f4-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="d33f4-124">Pour définir la visibilité, effectuez les étapes 3 et 4 de la première procédure.</span><span class="sxs-lookup"><span data-stu-id="d33f4-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="d33f4-125">Pour masquer des colonnes statiques dans une table, une matrice ou une liste</span><span class="sxs-lookup"><span data-stu-id="d33f4-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="d33f4-126">En mode Conception, sélectionnez la table, la matrice ou la liste afin d'afficher les handles de ligne et de colonne.</span><span class="sxs-lookup"><span data-stu-id="d33f4-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="d33f4-127">Cliquez avec le bouton droit sur le handle de colonne, puis cliquez sur **Visibilité de la colonne**.</span><span class="sxs-lookup"><span data-stu-id="d33f4-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="d33f4-128">Dans la boîte de dialogue **Visibilité de la colonne** , effectuez les étapes 3 et 4 de la première procédure.</span><span class="sxs-lookup"><span data-stu-id="d33f4-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33f4-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d33f4-129">See Also</span></span>
 <span data-ttu-id="d33f4-130">[Action d’exploration &#40;générateur de rapports et ssrs&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Ajouter une action développer ou réduire à un élément &#40;générateur de rapports et des expressions de&#41;SSRS](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) &#40;générateur de rapports [et SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="d33f4-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


