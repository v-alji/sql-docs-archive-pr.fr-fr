---
title: Gestion des caches (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604223"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="9a08b-102">Gestion des caches (XMLA)</span><span class="sxs-lookup"><span data-stu-id="9a08b-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="9a08b-103">Vous pouvez utiliser la commande [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) dans XML for Analysis (XMLA) pour effacer le cache d’une dimension ou d’une partition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9a08b-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="9a08b-104">L’effacement du cache force [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à reconstruire le cache pour cet objet.</span><span class="sxs-lookup"><span data-stu-id="9a08b-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="9a08b-105">Spécification d'objets</span><span class="sxs-lookup"><span data-stu-id="9a08b-105">Specifying Objects</span></span>  
 <span data-ttu-id="9a08b-106">La propriété [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) de la `ClearCache` commande peut contenir une référence d’objet uniquement pour l’un des objets suivants.</span><span class="sxs-lookup"><span data-stu-id="9a08b-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="9a08b-107">Si une référence d'objet désigne un objet différent de ceux mentionnés ci-dessous, une erreur se produit :</span><span class="sxs-lookup"><span data-stu-id="9a08b-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="9a08b-108">Base de données</span><span class="sxs-lookup"><span data-stu-id="9a08b-108">Database</span></span>  
 <span data-ttu-id="9a08b-109">Efface le cache pour l'ensemble des dimensions et des partitions contenues dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9a08b-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="9a08b-110">Dimension</span><span class="sxs-lookup"><span data-stu-id="9a08b-110">Dimension</span></span>  
 <span data-ttu-id="9a08b-111">Efface le cache pour la dimension spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9a08b-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="9a08b-112">Cube</span><span class="sxs-lookup"><span data-stu-id="9a08b-112">Cube</span></span>  
 <span data-ttu-id="9a08b-113">Efface le cache pour l'ensemble des partitions contenues dans les groupes de mesures du cube.</span><span class="sxs-lookup"><span data-stu-id="9a08b-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="9a08b-114">Groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="9a08b-114">Measure group</span></span>  
 <span data-ttu-id="9a08b-115">Efface le cache pour l'ensemble des partitions contenues dans le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="9a08b-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="9a08b-116">Partition</span><span class="sxs-lookup"><span data-stu-id="9a08b-116">Partition</span></span>  
 <span data-ttu-id="9a08b-117">Efface le cache pour la partition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9a08b-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a08b-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a08b-118">See Also</span></span>  
 [<span data-ttu-id="9a08b-119">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9a08b-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
