---
title: Définir les filtres | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601387"
---
# <a name="define-filters"></a><span data-ttu-id="a0dc6-102">Définir les filtres</span><span class="sxs-lookup"><span data-stu-id="a0dc6-102">Define Filters</span></span>
  <span data-ttu-id="a0dc6-103">La boîte de dialogue **Définir les filtres** vous permet de définir les filtres que vous appliquerez aux conflits de données afin d'afficher un sous-ensemble de conflits dans la grille.</span><span class="sxs-lookup"><span data-stu-id="a0dc6-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="a0dc6-104">Pour définir un filtre, choisissez un opérateur dans la zone de liste déroulante **Opérateur** , puis entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a0dc6-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="a0dc6-105">Par exemple, pour afficher uniquement les conflits dans lesquels le perdant du conflit est le serveur **ReplTest1**, sélectionnez **Égal à** dans la zone de liste déroulante **Opérateur** et entrez **ReplTest1** dans la première colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="a0dc6-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0dc6-106">Options</span><span class="sxs-lookup"><span data-stu-id="a0dc6-106">Options</span></span>  
 <span data-ttu-id="a0dc6-107">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="a0dc6-107">**Operator**</span></span>  
 <span data-ttu-id="a0dc6-108">Sélectionnez un opérateur pour le filtre, ex. : **Inférieur ou Égal à**.</span><span class="sxs-lookup"><span data-stu-id="a0dc6-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="a0dc6-109">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="a0dc6-109">**Value**</span></span>  
 <span data-ttu-id="a0dc6-110">Entrez une valeur pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="a0dc6-110">Enter a value for the filter.</span></span> <span data-ttu-id="a0dc6-111">La plupart des opérateurs nécessitent uniquement la saisie d'une valeur dans la première colonne **Valeur** , mais les opérateurs **Entre** et **Non compris entre** nécessitent une valeur dans les deux colonnes **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="a0dc6-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="a0dc6-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="a0dc6-112">**Clear**</span></span>  
 <span data-ttu-id="a0dc6-113">Cliquez sur ce bouton pour effacer tous les filtres précédemment définis.</span><span class="sxs-lookup"><span data-stu-id="a0dc6-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0dc6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0dc6-114">See Also</span></span>  
 <span data-ttu-id="a0dc6-115">[Visionneuse des conflits de réplication de Microsoft &#40;réplication de fusion&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a0dc6-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="a0dc6-116">Visionneuse des conflits de réplication de Microsoft &#40;réplication transactionnelle&#41;</span><span class="sxs-lookup"><span data-stu-id="a0dc6-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
