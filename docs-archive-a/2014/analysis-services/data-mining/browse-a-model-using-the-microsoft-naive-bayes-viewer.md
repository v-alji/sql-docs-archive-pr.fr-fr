---
title: Parcourir un modèle à l’aide de Microsoft Naive Bayes Viewer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614939"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="c6cc0-102">Explorer un modèle à l'aide de la visionneuse de l'algorithme MNB (Microsoft Naive Bayes)</span><span class="sxs-lookup"><span data-stu-id="c6cc0-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="c6cc0-103">La [!INCLUDE[msCoName](../../includes/msconame-md.md)] visionneuse Naive Bayes dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] affiche les modèles d’exploration de données générés à l’aide de l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithme Bayes Naive.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="c6cc0-104">L'algorithme [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes est un algorithme de classification qui est fortement adaptable aux tâches de modélisation prédictive.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="c6cc0-105">Pour plus d’informations sur cet algorithme, consultez [Algorithme MNB (Microsoft Naive Bayes)](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="c6cc0-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="c6cc0-106">Comme l’une des principales finalités d’un modèle Naive Bayes est de fournir un moyen rapide d’explorer les données d’un dataset, la Visionneuse de l’algorithme MNB ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes) propose plusieurs méthodes d’affichage de l’interaction entre les attributs prédictibles et les attributs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6cc0-107">Si vous voulez afficher des informations détaillées sur les équations utilisées dans le modèle et les motifs détectés, vous pouvez basculer vers la visionneuse de l’arborescence de contenu générique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6cc0-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="c6cc0-108">Pour plus d’informations, consultez [Explorer un modèle à l’aide de la visionneuse de l’arborescence de contenu générique Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) ou [Visionneuse de l’arborescence de contenu générique Microsoft &#40;exploration de données&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="c6cc0-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="c6cc0-109">Onglets de la visionneuse</span><span class="sxs-lookup"><span data-stu-id="c6cc0-109">Viewer Tabs</span></span>  
 <span data-ttu-id="c6cc0-110">Lorsque vous parcourez un modèle d'exploration de données dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], le modèle s'affiche sous l'onglet **Visionneuse de modèle d'exploration de données** du Concepteur d'exploration de données, à l'aide de la visionneuse appropriée pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="c6cc0-111">La Visionneuse de l’algorithme MNB ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes) fournit les onglets suivants pour explorer les données :</span><span class="sxs-lookup"><span data-stu-id="c6cc0-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="c6cc0-112">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="c6cc0-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="c6cc0-113">Profils d'attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="c6cc0-114">Caractéristiques d’attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="c6cc0-115">Discrimination d’attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="c6cc0-116">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="c6cc0-116">Dependency Network</span></span>  
 <span data-ttu-id="c6cc0-117">L’onglet **Réseau de dépendances** affiche les dépendances entre les attributs d’entrée et les attributs prédictibles d’un modèle.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="c6cc0-118">Le curseur situé à gauche de la visionneuse agit comme un filtre lié à la force des dépendances.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="c6cc0-119">Si vous déplacez le curseur vers le bas, seuls les liens les plus forts sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="c6cc0-120">Lorsque vous sélectionnez un nœud, la visionneuse met en surbrillance les dépendances propres à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="c6cc0-121">Par exemple, si vous choisissez un nœud prévisible, la visionneuse met également en surbrillance chacun des nœuds permettant de prédire le nœud prévisible.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="c6cc0-122">La légende en bas de la visionneuse associe des codes de couleur au type de dépendance apparaissant dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="c6cc0-123">Par exemple, lorsque vous sélectionnez un nœud prévisible, le nœud prévisible est surligné en turquoise et les nœuds permettant de prédire le nœud sélectionné sont surlignés en orange.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="c6cc0-124">Retour au début</span><span class="sxs-lookup"><span data-stu-id="c6cc0-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a><span data-ttu-id="c6cc0-125">Profils d’attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-125">Attribute Profiles</span></span>  
 <span data-ttu-id="c6cc0-126">L’onglet **Profils d’attribut** affiche des histogrammes dans une grille.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="c6cc0-127">Vous pouvez utiliser cette grille pour comparer l’attribut prédictible que vous sélectionnez dans la zone **Prédictible** à tous les autres attributs figurant dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="c6cc0-128">Chaque colonne de l'onglet représente un état de l'attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="c6cc0-129">Si l’attribut prédictible possède un grand nombre d’états, vous pouvez modifier le nombre d’états affichés dans l’histogramme à l’aide de l’option **Barres de l’histogramme**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="c6cc0-130">Si le nombre que vous définissez est inférieur au nombre total d'états de l'attribut, les états sont répertoriés par ordre de prise en charge et le reste des états est regroupé dans un compartiment gris unique.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="c6cc0-131">Pour afficher une légende d’exploration de données qui associe les couleurs de l’histogramme aux états d’un attribut, cochez la case **Afficher la légende** .</span><span class="sxs-lookup"><span data-stu-id="c6cc0-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="c6cc0-132">La légende d'exploration de données affiche également la distribution des cas pour chaque paire attribut/valeur que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="c6cc0-133">Pour copier le contenu de la grille en tant que table HTML dans le Presse-papiers, cliquez avec le bouton droit sur l’onglet **Profils d’attribut** puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="c6cc0-134">Retour au début</span><span class="sxs-lookup"><span data-stu-id="c6cc0-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a> <span data-ttu-id="c6cc0-135">Caractéristiques d'attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="c6cc0-136">Pour utiliser l’onglet **Caractéristiques d’attribut** , sélectionnez un attribut prédictible dans la liste **Attribut** , puis sélectionnez un état de l’attribut sélectionné dans la liste **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="c6cc0-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="c6cc0-137">Quand vous définissez ces variables, l’onglet **Caractéristiques d’attribut** affiche les états des attributs qui sont associés au cas sélectionné de l’attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="c6cc0-138">Les attributs sont triés par ordre d'importance.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="c6cc0-139">Retour au début</span><span class="sxs-lookup"><span data-stu-id="c6cc0-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a> <span data-ttu-id="c6cc0-140">Discrimination d'attribut</span><span class="sxs-lookup"><span data-stu-id="c6cc0-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="c6cc0-141">Pour utiliser l’onglet **Discrimination d’attribut** , sélectionnez un attribut prédictible et deux de ses états dans les listes **Attribut**, **Valeur 1**et **Valeur 2** .</span><span class="sxs-lookup"><span data-stu-id="c6cc0-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="c6cc0-142">La grille de l’onglet **Discrimination d’attribut** affiche alors les informations suivantes dans des colonnes :</span><span class="sxs-lookup"><span data-stu-id="c6cc0-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="c6cc0-143">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="c6cc0-143">**Attribute**</span></span>  
 <span data-ttu-id="c6cc0-144">Répertorie les autres attributs du jeu de données contenant un état qui privilégie fortement l'un des états de l'attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="c6cc0-145">**Valeurs**</span><span class="sxs-lookup"><span data-stu-id="c6cc0-145">**Values**</span></span>  
 <span data-ttu-id="c6cc0-146">Affiche la valeur de l’attribut dans la colonne**Attribut**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="c6cc0-147">**Privilégie\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="c6cc0-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="c6cc0-148">Affiche une barre de couleur qui indique à quel degré la valeur d’attribut favorise la valeur d’attribut prédictible affichée dans **Valeur 1**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="c6cc0-149">**Privilégie\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="c6cc0-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="c6cc0-150">Affiche une barre de couleur qui indique à quel degré la valeur d’attribut favorise la valeur d’attribut prédictible affichée dans **Valeur 2**.</span><span class="sxs-lookup"><span data-stu-id="c6cc0-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="c6cc0-151">Retour au début</span><span class="sxs-lookup"><span data-stu-id="c6cc0-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="c6cc0-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6cc0-152">See Also</span></span>  
 <span data-ttu-id="c6cc0-153">[Algorithme Microsoft Naive Bayes](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="c6cc0-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="c6cc0-154">[Tâches de la visionneuse de modèle d’exploration de données et procédures](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="c6cc0-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="c6cc0-155">[Outils d’exploration de données](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c6cc0-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="c6cc0-156">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="c6cc0-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
