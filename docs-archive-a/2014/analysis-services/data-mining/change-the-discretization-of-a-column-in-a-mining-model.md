---
title: Modifier la discrétisation d’une colonne dans un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613230"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="13705-102">Modifier la discrétisation d'une colonne dans un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="13705-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="13705-103">discrétise automatiquement les valeurs, autrement dit, il place les données dans une colonne numérique, dans certains scénarios.</span><span class="sxs-lookup"><span data-stu-id="13705-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="13705-104">Par exemple, si vos données contiennent des données numériques continues et que vous créez un modèle d'arbre de décision, chaque colonne de données continues est intégrée automatiquement, selon la distribution des données.</span><span class="sxs-lookup"><span data-stu-id="13705-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="13705-105">Si vous souhaitez contrôler la discrétisation des données, vous devez modifier les propriétés de la colonne de structure d'exploration de données, qui contrôle l'utilisation des données dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="13705-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="13705-106">Pour obtenir des informations générales sur la façon de définir des propriétés dans un modèle d’exploration de données, consultez [Colonnes de modèle d’exploration de données](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="13705-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="13705-107">Pour afficher les propriétés d'une colonne de modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="13705-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="13705-108">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur l’en-tête de colonne contenant le nom du modèle d’exploration de données ou sur la ligne dans la grille qui contient le nom de l’algorithme d’exploration de données, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="13705-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="13705-109">La fenêtre **Propriétés** affiche les propriétés associées au modèle d'exploration de données dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="13705-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="13705-110">Dans la colonne **Structure** près du côté gauche de l'écran, cliquez sur la colonne qui contient les données numériques continues que vous souhaitez discrétiser.</span><span class="sxs-lookup"><span data-stu-id="13705-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="13705-111">L'affichage de la fenêtre **Propriétés** se modifie et affiche uniquement les propriétés associées à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="13705-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="13705-112">Pour modifier la méthode de discrétisation</span><span class="sxs-lookup"><span data-stu-id="13705-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="13705-113">Dans la fenêtre **propriétés d’exploration de données** , cliquez sur la zone de texte en regard de **contenu**, puis sélectionnez `Discretized` dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13705-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="13705-114">La fenêtre <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> et <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> sont maintenant activées.</span><span class="sxs-lookup"><span data-stu-id="13705-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="13705-115">Dans la fenêtre **Propriétés** , cliquez sur la zone de texte en regard de <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> et sélectionnez l’une des valeurs suivantes : `Automatic` , `EqualAreas` ou `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="13705-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13705-116">Si l’utilisation de la colonne est définie sur `Ignore` , la fenêtre **Propriétés** de la colonne est vide.</span><span class="sxs-lookup"><span data-stu-id="13705-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="13705-117">La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="13705-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="13705-118">Sous l’onglet **Propriétés** , cliquez sur la zone de texte en regard de <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> et tapez une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="13705-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13705-119">Si vous modifiez ces propriétés, la structure doit être traitée à nouveau, avec tous les modèles auxquels s'applique le nouveau paramètre.</span><span class="sxs-lookup"><span data-stu-id="13705-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13705-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13705-120">See Also</span></span>  
 [<span data-ttu-id="13705-121">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="13705-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
