---
title: Supprimer un filtre d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601777"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="b4d59-102">Supprimer un filtre d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b4d59-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="b4d59-103">Lorsque vous créez un filtre sur un modèle d'exploration de données, vous pouvez créer des modèles sur un sous-ensemble des données contenues dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="b4d59-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="b4d59-104">Les filtres sont également utiles pour tester la précision du modèle sur un sous-ensemble des données d'origine.</span><span class="sxs-lookup"><span data-stu-id="b4d59-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="b4d59-105">Toutefois, vous devez supprimer le filtre si vous souhaitez réafficher l'intégralité des cas.</span><span class="sxs-lookup"><span data-stu-id="b4d59-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="b4d59-106">Cette procédure décrit comment supprimer des conditions sur un filtre ou supprimer complètement le filtre.</span><span class="sxs-lookup"><span data-stu-id="b4d59-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="b4d59-107">Pour supprimer une condition d'un filtre sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b4d59-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="b4d59-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans l'Explorateur de solutions, cliquez sur la structure d'exploration de données qui contient le modèle d'exploration de données à filtrer.</span><span class="sxs-lookup"><span data-stu-id="b4d59-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="b4d59-109">Cliquez sur l'onglet **Modèles d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="b4d59-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="b4d59-110">Sélectionnez le modèle et cliquez avec le bouton droit pour ouvrir le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="b4d59-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="b4d59-111">-ou-</span><span class="sxs-lookup"><span data-stu-id="b4d59-111">-or-</span></span>  
  
     <span data-ttu-id="b4d59-112">Sélectionnez le modèle.</span><span class="sxs-lookup"><span data-stu-id="b4d59-112">Select the model.</span></span> <span data-ttu-id="b4d59-113">Dans le menu **Modèle d'exploration de données** , sélectionnez **Définir le filtre de modèle**.</span><span class="sxs-lookup"><span data-stu-id="b4d59-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="b4d59-114">Dans la boîte de dialogue **Filtre de modèle** , cliquez avec le bouton droit sur la ligne dans la grille qui contient la condition que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b4d59-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="b4d59-115">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b4d59-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="b4d59-116">Pour effacer le filtre sur un modèle d'exploration de données dans la boîte de dialogue Éditeur de filtre</span><span class="sxs-lookup"><span data-stu-id="b4d59-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="b4d59-117">Dans la boîte de dialogue **Éditeur de filtre** , cliquez avec le bouton droit sur n’importe quelle ligne de la grille et sélectionnez **Supprimer tout**.</span><span class="sxs-lookup"><span data-stu-id="b4d59-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="b4d59-118">Utilisation des filtres de modèle à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="b4d59-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="b4d59-119">Si vous souhaitez supprimer le filtre entier, vous n'avez pas besoin d'ouvrir les boîtes de dialogue de l'Éditeur de filtre.</span><span class="sxs-lookup"><span data-stu-id="b4d59-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="b4d59-120">Les conditions de filtre que vous avez créées sont disponibles dans la propriété `Filter` du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b4d59-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4d59-121">Vous pouvez afficher les propriétés d'un modèle d'exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], mais pas dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4d59-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="b4d59-122">Pour effacer le filtre sur un modèle d'exploration de données dans l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="b4d59-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="b4d59-123">Dans l'Explorateur de solutions, cliquez sur le modèle d'exploration de données qui contient le filtre.</span><span class="sxs-lookup"><span data-stu-id="b4d59-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="b4d59-124">Dans la fenêtre **Propriétés** , cliquez avec le bouton droit sur le texte de filtre dans la `Filter` propriété, puis sélectionnez **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="b4d59-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="b4d59-125">Appuyez sur la touche Retour arrière ou Suppr.</span><span class="sxs-lookup"><span data-stu-id="b4d59-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d59-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4d59-126">See Also</span></span>  
 <span data-ttu-id="b4d59-127">[Extraction des données de cas à partir d’un modèle d’exploration de données](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="b4d59-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="b4d59-128">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="b4d59-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="b4d59-129">Filtres pour les modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="b4d59-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
