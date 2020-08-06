---
title: Onglet matrice de classification (vue graphique d’analyse de précision de l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602523"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="3884e-102">Onglet Matrice de classification (vue Graphique d'analyse de précision de l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="3884e-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="3884e-103">L’onglet **matrice de classification** affiche une matrice de classification pour chaque modèle sélectionné dans la grille modèles sous l’onglet Mappage de **colonnes** . La matrice de classification est disponible uniquement si la colonne prévisible sélectionnée dans l’onglet **mappage de colonnes** n’est pas continue.</span><span class="sxs-lookup"><span data-stu-id="3884e-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="3884e-104">Pour une description plus détaillée de l’onglet **Matrice de classification** , consultez [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3884e-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3884e-105">Options</span><span class="sxs-lookup"><span data-stu-id="3884e-105">Options</span></span>  
 <span data-ttu-id="3884e-106">**Copier**</span><span class="sxs-lookup"><span data-stu-id="3884e-106">**Copy**</span></span>  
 <span data-ttu-id="3884e-107">Copie le contenu de chaque matrice de classification dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="3884e-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="3884e-108">**Compte pour \<model> sur\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="3884e-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="3884e-109">Affiche une matrice de classification pour chaque modèle d'exploration de données de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="3884e-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="3884e-110">La matrice contient les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3884e-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="3884e-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="3884e-111">Value</span></span>|<span data-ttu-id="3884e-112">Description</span><span class="sxs-lookup"><span data-stu-id="3884e-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3884e-113">**Prédite**</span><span class="sxs-lookup"><span data-stu-id="3884e-113">**Predicted**</span></span>|<span data-ttu-id="3884e-114">Contient une ligne pour chaque état de la colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="3884e-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="3884e-115">**\<states>réel**</span><span class="sxs-lookup"><span data-stu-id="3884e-115">**\<states> (actual)**</span></span>|<span data-ttu-id="3884e-116">Colonne pour chaque état de la colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="3884e-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="3884e-117">Si l'état de la ligne et de la colonne correspond, la cellule représente le nombre réel de fois où l'état existe dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3884e-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="3884e-118">S'il ne correspond pas, la cellule représente l'erreur de la prévision.</span><span class="sxs-lookup"><span data-stu-id="3884e-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3884e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3884e-119">See Also</span></span>  
 <span data-ttu-id="3884e-120">[Concepteur graphique d’analyse de précision de l’exploration de données &#40;&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3884e-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="3884e-121">[Tâches de test et de validation et &#40;d’exploration de données&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3884e-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="3884e-122">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3884e-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
