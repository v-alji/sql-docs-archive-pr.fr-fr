---
title: Spécifier la taille d’un indicateur à l’aide d’une expression (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600512"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="e81c3-102">Spécifier la taille d'un indicateur à l'aide d'une expression (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e81c3-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e81c3-103">Outre la couleur, la direction et la forme, vous pouvez utiliser la taille pour optimiser l'impact visuel des indicateurs.</span><span class="sxs-lookup"><span data-stu-id="e81c3-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="e81c3-104">Un indicateur a une collection d’états nommée IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e81c3-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="e81c3-105">La collection IndicatorStates a en général plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="e81c3-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="e81c3-106">Chaque état est un membre de la collection et est représenté par une icône.</span><span class="sxs-lookup"><span data-stu-id="e81c3-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="e81c3-107">Ensemble, les états constituent la collection IndicatorsStates.</span><span class="sxs-lookup"><span data-stu-id="e81c3-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="e81c3-108">Pour configurer dynamiquement les tailles des icônes, vous définissez les propriétés des membres de la collection IndicatorsStates dans le volet Propriétés du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e81c3-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="e81c3-109">Si le volet **Propriétés** n'est pas visible, sélectionnez **Propriétés** sous l'onglet **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="e81c3-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e81c3-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vous utilisez la fenêtre de **Propriétés** pour définir les propriétés de membre.</span><span class="sxs-lookup"><span data-stu-id="e81c3-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="e81c3-111">Si la fenêtre **Propriétés** n'est pas ouverte, appuyez sur la touche F4.</span><span class="sxs-lookup"><span data-stu-id="e81c3-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="e81c3-112">Le volet **Propriétés** fournit l’accès aux propriétés de la collection IndicatorStates d’un indicateur.</span><span class="sxs-lookup"><span data-stu-id="e81c3-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="e81c3-113">Vous configurez des icônes de différentes tailles en définissant la propriété ScaleFactor des membres de collection IndicatorStates à l’aide d’une expression.</span><span class="sxs-lookup"><span data-stu-id="e81c3-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="e81c3-114">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e81c3-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e81c3-115">L’expression utilisée dans cette procédure a également été utilisée pour créer le rapport avec différentes tailles d’indicateurs, illustré dans [Indicateurs &#40;Générateur de rapports et SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e81c3-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="e81c3-116">Pour spécifier la taille de l'icône d'indicateur à l'aide d'une expression</span><span class="sxs-lookup"><span data-stu-id="e81c3-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="e81c3-117">Cliquez sur l'indicateur que vous souhaitez changer.</span><span class="sxs-lookup"><span data-stu-id="e81c3-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="e81c3-118">Dans le volet Propriétés, repérez la propriété IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e81c3-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="e81c3-119">Si le volet Propriétés est organisé par catégorie, vous trouverez IndicatorStates dans la catégorie **States** .</span><span class="sxs-lookup"><span data-stu-id="e81c3-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="e81c3-120">Cliquez sur le bouton de sélection **(...)** en regard d’IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="e81c3-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="e81c3-121">La boîte de dialogue relative à l' **Éditeur de collections IndicatorState** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="e81c3-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="e81c3-122">Sélectionnez tous les membres de la collection.</span><span class="sxs-lookup"><span data-stu-id="e81c3-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="e81c3-123">Dans la liste **Sélectionner plusieurs propriétés** , cliquez sur la flèche vers le bas en regard de ScaleFactor, puis sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="e81c3-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="e81c3-124">Dans la boîte de dialogue **Expression** , écrivez l'expression.</span><span class="sxs-lookup"><span data-stu-id="e81c3-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="e81c3-125">L'exemple d'expression suivant crée une icône de taille différente selon la valeur du champ **SalesYTD** .</span><span class="sxs-lookup"><span data-stu-id="e81c3-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="e81c3-126">Pour plus d’informations, consultez [Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e81c3-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e81c3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e81c3-127">See Also</span></span>  
 [<span data-ttu-id="e81c3-128">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e81c3-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
