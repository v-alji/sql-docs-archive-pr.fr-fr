---
title: Filtrer un jeu d’éléments dans un modèle de règles d’association | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- filtering itemsets [Analysis Services]
- Mining Model Viewer [Analysis Services], itemsets
ms.assetid: 3ed919ea-8598-45d2-a4a0-b1b3357a4ab1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f841280a6dd39a5f824f2e6a10975b0f80ed0761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601169"
---
# <a name="filter-an-itemset-in-an-association-rules-model"></a><span data-ttu-id="61803-102">Filtrer un jeu d'éléments dans un modèle de règles d'association</span><span class="sxs-lookup"><span data-stu-id="61803-102">Filter an Itemset in an Association Rules Model</span></span>
  <span data-ttu-id="61803-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous pouvez filtrer les jeux d’éléments affichés sous l’onglet **Jeux d’éléments** de la visionneuse de l’algorithme MAR ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules).</span><span class="sxs-lookup"><span data-stu-id="61803-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can filter the itemsets that are displayed in the **Itemsets** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer.</span></span>  
  
### <a name="to-filter-an-itemset"></a><span data-ttu-id="61803-104">Pour filtrer un jeu d'éléments</span><span class="sxs-lookup"><span data-stu-id="61803-104">To filter an itemset</span></span>  
  
1.  <span data-ttu-id="61803-105">Sous l’onglet **Visionneuse de modèle d’exploration de données** du Concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur l’onglet **Jeux d’éléments** de la **Visionneuse de l’algorithme MAR (Microsoft Association Rules)**.</span><span class="sxs-lookup"><span data-stu-id="61803-105">On the **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Itemsets** tab of the **Association Rules Viewer**.</span></span>  
  
2.  <span data-ttu-id="61803-106">Entrez une condition de règle dans la zone **Filtrer le jeu d’éléments** .</span><span class="sxs-lookup"><span data-stu-id="61803-106">Enter a rule condition in the **Filter itemset** box.</span></span> <span data-ttu-id="61803-107">Par exemple, une condition de règle pourrait être « Touring-1000 = existing ».</span><span class="sxs-lookup"><span data-stu-id="61803-107">For example, a rule condition might be "Touring-1000 = existing"</span></span>  
  
3.  <span data-ttu-id="61803-108">Cliquez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="61803-108">Click **Enter**.</span></span>  
  
 <span data-ttu-id="61803-109">Les jeux d'éléments sont filtrés pour afficher uniquement ceux qui contiennent les éléments sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="61803-109">The itemsets are now filtered to display only those itemsets that contain the selected items.</span></span> <span data-ttu-id="61803-110">La zone ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="61803-110">The box is not case-sensitive.</span></span> <span data-ttu-id="61803-111">Les filtres sont stockés en mémoire pour vous permettre de sélectionner un ancien filtre dans la liste.</span><span class="sxs-lookup"><span data-stu-id="61803-111">Filters are stored in memory so that you can select an old filter from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61803-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61803-112">See Also</span></span>  
 [<span data-ttu-id="61803-113">Tâches de la visionneuse de modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="61803-113">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
