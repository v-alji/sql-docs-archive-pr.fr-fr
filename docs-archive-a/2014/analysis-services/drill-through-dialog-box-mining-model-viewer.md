---
title: Boîte de dialogue Extraire (visionneuse de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613202"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="875af-102">Boîte de dialogue Extraire (Visionneuse de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="875af-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="875af-103">Quand vous affichez un modèle d’exploration de données sous l’onglet **Visionneuse de modèle d’exploration de données** du concepteur de modèle d’exploration de données, vous pouvez extraire les détails des données de cas, à condition que l’extraction ait été activée sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="875af-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="875af-104">De plus, si l'extraction a été activée sur la structure d'exploration de données sous-jacente, vous pouvez aussi afficher les colonnes dans la structure d'exploration de données, même si ces colonnes n'ont pas été incluses dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="875af-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="875af-105">Dans la liste de colonnes, les colonnes de structure portent un préfixe par l’étiquette</span><span class="sxs-lookup"><span data-stu-id="875af-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="875af-106">« Structure. ».</span><span class="sxs-lookup"><span data-stu-id="875af-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="875af-107">Vous ne pouvez pas activer l'extraction sur une structure d'exploration de données existante.</span><span class="sxs-lookup"><span data-stu-id="875af-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="875af-108">Au lieu de cela, vous devez recréer la structure d'exploration de données et activer l'extraction au cours du processus de création.</span><span class="sxs-lookup"><span data-stu-id="875af-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="875af-109">Pour plus d’informations sur l’accès aux données de cas à partir de chacune des visionneuses de modèles d’exploration de données qui prennent en charge l’extraction, **consultez** [Extraire des données de cas à partir d’un modèle d’exploration de données](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="875af-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="875af-110">Options</span><span class="sxs-lookup"><span data-stu-id="875af-110">Options</span></span>  
 <span data-ttu-id="875af-111">**Cas classés dans**</span><span class="sxs-lookup"><span data-stu-id="875af-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="875af-112">Affiche la définition de la règle, le jeu d'éléments et le cluster qui sont contenus dans le nœud sélectionné.</span><span class="sxs-lookup"><span data-stu-id="875af-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="875af-113">**Liste des colonnes**</span><span class="sxs-lookup"><span data-stu-id="875af-113">**Column list**</span></span>  
 <span data-ttu-id="875af-114">Affiche les colonnes dans le modèle, suivies des colonnes de structure.</span><span class="sxs-lookup"><span data-stu-id="875af-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="875af-115">**Remarque** Les colonnes de structure sont affichées uniquement si l’extraction est activée sur la structure d’exploration de données et si vous avez sélectionné l’option **Colonnes de structure et de modèle**.</span><span class="sxs-lookup"><span data-stu-id="875af-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="875af-116">De plus, vous devez posséder des autorisations d'extraction à la fois sur le modèle d'exploration de données et sur la structure d'exploration de données pour afficher les colonnes.</span><span class="sxs-lookup"><span data-stu-id="875af-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="875af-117">Les colonnes de structure qui ne sont pas incluses dans le modèle apparaissent en tant que \*\*structure. \<column name> \*\*</span><span class="sxs-lookup"><span data-stu-id="875af-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="875af-118">Vous pouvez cliquer avec le bouton droit n’importe où dans la grille de colonnes et sélectionner **Copier tout** pour copier les données d’extraction, au format séparé par des tabulations, dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="875af-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="875af-119">Les données copiées comprennent uniquement les données de cas, et non la définition du nœud.</span><span class="sxs-lookup"><span data-stu-id="875af-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="875af-120">**Lire**</span><span class="sxs-lookup"><span data-stu-id="875af-120">**Play**</span></span>  
 <span data-ttu-id="875af-121">Cliquez sur le bouton fléché vert pour actualiser les données.</span><span class="sxs-lookup"><span data-stu-id="875af-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875af-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="875af-122">See Also</span></span>  
 <span data-ttu-id="875af-123">[Requêtes d’extraction &#40;l’exploration de données&#41;](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="875af-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="875af-124">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="875af-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="875af-125">Tâches de la visionneuse de modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="875af-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
