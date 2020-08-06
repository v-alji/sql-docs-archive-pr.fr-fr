---
title: Modifier les propriétés d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601179"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="f3276-102">Modifier les propriétés d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f3276-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="f3276-103">Certaines propriétés du modèle d'exploration de données s'appliquent au modèle dans son ensemble, et d'autres propriétés de modèle s'appliquent à des colonnes individuelles.</span><span class="sxs-lookup"><span data-stu-id="f3276-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="f3276-104">La propriété `Drillthrough`, qui spécifie si les données de cas doivent être disponibles pour l'interrogation, et la propriété `Description` sont des exemples de propriétés qui s'appliquent à l'ensemble du modèle.</span><span class="sxs-lookup"><span data-stu-id="f3276-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="f3276-105">Les propriétés qui s'appliquent à la colonne incluent `Usage` et `ModelingFlags`, qui contrôlent l'utilisation des données de la colonne dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="f3276-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="f3276-106">Les propriétés de modèle suivantes ont des éditeurs avancés que vous pouvez utiliser pour créer des expressions ou pour configurer les propriétés de modèle complexes.</span><span class="sxs-lookup"><span data-stu-id="f3276-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="f3276-107">Les propriétés suivantes fournissent :</span><span class="sxs-lookup"><span data-stu-id="f3276-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="f3276-108">`Filter`propriété : ouvre la [boîte de dialogue filtre de jeu de données ou filtre de modèle](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f3276-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="f3276-109">`AlgorithmParameters`propriété : ouvre la [boîte de dialogue Paramètres d’algorithme &#40;vue modèles d’exploration de données&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="f3276-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="f3276-110">Pour plus d’informations sur la définition des propriétés dans un modèle d’exploration, consultez [Colonnes de modèle d’exploration de données](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f3276-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="f3276-111">Pour modifier les propriétés d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f3276-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="f3276-112">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur l’en-tête de colonne contenant le nom du modèle d’exploration de données ou sur la ligne de la grille qui contient le nom de l’algorithme d’exploration de données, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f3276-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f3276-113">Dans la fenêtre **Propriétés** à droite de l’écran, mettez en surbrillance la valeur qui correspond à la propriété à modifier, puis entrez la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="f3276-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="f3276-114">La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="f3276-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="f3276-115">Pour modifier les propriétés d'une colonne de modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f3276-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="f3276-116">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur la cellule de la grille à l’intersection de la colonne de la structure d’exploration de données et du modèle d’exploration de données, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f3276-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f3276-117">Dans la fenêtre **Propriétés** à droite de l’écran, mettez en surbrillance la valeur qui correspond à la propriété à modifier, puis entrez la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="f3276-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3276-118">Si l’utilisation de la colonne est définie sur `Ignore` , la fenêtre **Propriétés** de la colonne est vide.</span><span class="sxs-lookup"><span data-stu-id="f3276-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="f3276-119">La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="f3276-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3276-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3276-120">See Also</span></span>  
 [<span data-ttu-id="f3276-121">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="f3276-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
