---
title: Modification des mesures | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612590"
---
# <a name="modifying-measures"></a><span data-ttu-id="10708-102">Modification des mesures</span><span class="sxs-lookup"><span data-stu-id="10708-102">Modifying Measures</span></span>
  <span data-ttu-id="10708-103">Vous pouvez utiliser la propriété **FormatString** pour définir des paramètres de mise en forme qui contrôlent comment les mesures sont affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="10708-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="10708-104">Au cours de cette tâche, vous allez spécifier des propriétés de formatage pour les mesures relatives aux devises et aux pourcentages dans le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10708-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="10708-105">Pour modifier les mesures du cube</span><span class="sxs-lookup"><span data-stu-id="10708-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="10708-106">Affichez l’onglet **Structure de cube** du Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , développez le groupe de mesures **Internet Sales** dans le volet **Mesures** , cliquez avec le bouton droit sur **Order Quantity**, puis choisissez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="10708-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="10708-107">Dans la fenêtre des propriétés, cliquez sur l'icône en forme de punaise **Masquer automatiquement** pour épingler la fenêtre des propriétés.</span><span class="sxs-lookup"><span data-stu-id="10708-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="10708-108">Il est plus facile de modifier les propriétés de plusieurs éléments à la fois dans le cube lorsque la fenêtre des propriétés reste ouverte.</span><span class="sxs-lookup"><span data-stu-id="10708-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="10708-109">Dans la fenêtre Propriétés, cliquez sur la liste **FormatString** , puis tapez **#,#**.</span><span class="sxs-lookup"><span data-stu-id="10708-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="10708-110">Dans la barre d'outils de l'onglet **Structure de cube** , cliquez sur l'icône **Afficher la grille de mesures** à gauche.</span><span class="sxs-lookup"><span data-stu-id="10708-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="10708-111">L'affichage de la grille permet de sélectionner plusieurs mesures en même temps.</span><span class="sxs-lookup"><span data-stu-id="10708-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="10708-112">Sélectionnez l'une des mesures suivantes.</span><span class="sxs-lookup"><span data-stu-id="10708-112">Select the following measures.</span></span> <span data-ttu-id="10708-113">Vous pouvez sélectionner plusieurs mesures en cliquant sur chacune d'elles tout en maintenant enfoncée la touche CTRL :</span><span class="sxs-lookup"><span data-stu-id="10708-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="10708-114">**Unit Price**</span><span class="sxs-lookup"><span data-stu-id="10708-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="10708-115">**Extended Amount**</span><span class="sxs-lookup"><span data-stu-id="10708-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="10708-116">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="10708-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="10708-117">**Product Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="10708-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="10708-118">**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="10708-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="10708-119">**Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="10708-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="10708-120">**Tax Amt**</span><span class="sxs-lookup"><span data-stu-id="10708-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="10708-121">**Freight**</span><span class="sxs-lookup"><span data-stu-id="10708-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="10708-122">Dans la fenêtre des propriétés, dans la liste **FormatString** , sélectionnez **Currency**.</span><span class="sxs-lookup"><span data-stu-id="10708-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="10708-123">Dans la zone de liste déroulante en haut de la fenêtre des propriétés (sous la barre de titre), sélectionnez la mesure **Unit Price Discount Pct**, puis sélectionnez **Percent** dans la liste **FormatString** .</span><span class="sxs-lookup"><span data-stu-id="10708-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="10708-124">Dans la Fenêtre Propriétés, remplacez la valeur de la propriété **Name** de la mesure **Unit Price discount PCT** par `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="10708-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="10708-125">Dans le volet **mesures** , cliquez sur **Tax AMT** et remplacez le nom de cette mesure par `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="10708-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="10708-126">Dans la fenêtre des propriétés, cliquez sur l'icône **Masquer automatiquement** pour masquer la fenêtre des propriétés, puis cliquez sur **Afficher l'arborescence de mesures** dans la barre d'outils de l'onglet **Structure de cube** .</span><span class="sxs-lookup"><span data-stu-id="10708-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="10708-127">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="10708-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="10708-128">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="10708-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="10708-129">Modification de la dimension Customer</span><span class="sxs-lookup"><span data-stu-id="10708-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="10708-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10708-130">See Also</span></span>  
 <span data-ttu-id="10708-131">[Définir des dimensions de base de données](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="10708-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="10708-132">Configurer des propriétés de mesure</span><span class="sxs-lookup"><span data-stu-id="10708-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
