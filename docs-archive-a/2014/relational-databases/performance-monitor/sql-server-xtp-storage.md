---
title: Stockage XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610627"
---
# <a name="xtp-storage"></a><span data-ttu-id="06a55-102">Storage XTP</span><span class="sxs-lookup"><span data-stu-id="06a55-102">XTP Storage</span></span>
  <span data-ttu-id="06a55-103">L'objet de performance XTP Storage contient des compteurs associés au stockage XTP dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06a55-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="06a55-104">Ce tableau décrit les compteurs **XTP Storage**.</span><span class="sxs-lookup"><span data-stu-id="06a55-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="06a55-105">Compteur</span><span class="sxs-lookup"><span data-stu-id="06a55-105">Counter</span></span>|<span data-ttu-id="06a55-106">Description</span><span class="sxs-lookup"><span data-stu-id="06a55-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06a55-107">**Points de contrôle fermés**</span><span class="sxs-lookup"><span data-stu-id="06a55-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="06a55-108">Nombre de points de contrôle fermés effectués par l'agent en ligne.</span><span class="sxs-lookup"><span data-stu-id="06a55-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="06a55-109">**Points de contrôle terminés**</span><span class="sxs-lookup"><span data-stu-id="06a55-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="06a55-110">Nombre de points de contrôle traités par le thread de point de contrôle hors connexion.</span><span class="sxs-lookup"><span data-stu-id="06a55-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="06a55-111">**Fusions principales terminées**</span><span class="sxs-lookup"><span data-stu-id="06a55-111">**Core Merges Completed**</span></span>|<span data-ttu-id="06a55-112">Nombre de fusions principale exécutées par le thread de travail de fusion.</span><span class="sxs-lookup"><span data-stu-id="06a55-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="06a55-113">Ces fusions ne sont pas encore installées.</span><span class="sxs-lookup"><span data-stu-id="06a55-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="06a55-114">**Évaluations de la stratégie de fusion**</span><span class="sxs-lookup"><span data-stu-id="06a55-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="06a55-115">Nombre d'évaluations de la stratégie de fusion depuis le démarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="06a55-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="06a55-116">**Demandes de fusion en attente**</span><span class="sxs-lookup"><span data-stu-id="06a55-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="06a55-117">Nombre de demandes de fusion en attente depuis le démarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="06a55-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="06a55-118">**Fusions abandonnées**</span><span class="sxs-lookup"><span data-stu-id="06a55-118">**Merges Abandoned**</span></span>|<span data-ttu-id="06a55-119">Nombre de fusions abandonnées en raison d'un échec.</span><span class="sxs-lookup"><span data-stu-id="06a55-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="06a55-120">**Fusions installées**</span><span class="sxs-lookup"><span data-stu-id="06a55-120">**Merges Installed**</span></span>|<span data-ttu-id="06a55-121">Nombre de fusions correctement installées.</span><span class="sxs-lookup"><span data-stu-id="06a55-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="06a55-122">**Fichiers totaux fusionnés**</span><span class="sxs-lookup"><span data-stu-id="06a55-122">**Total Files Merged**</span></span>|<span data-ttu-id="06a55-123">Nombre total de fichiers sources fusionnés.</span><span class="sxs-lookup"><span data-stu-id="06a55-123">The total number of source files merged.</span></span> <span data-ttu-id="06a55-124">Ce nombre peut être utilisé pour rechercher le nombre moyen de fichiers sources dans la fusion.</span><span class="sxs-lookup"><span data-stu-id="06a55-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06a55-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06a55-125">See Also</span></span>  
 [<span data-ttu-id="06a55-126">Les compteurs de performances de l’OLTP en mémoire &#40;de XTP&#41;</span><span class="sxs-lookup"><span data-stu-id="06a55-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
