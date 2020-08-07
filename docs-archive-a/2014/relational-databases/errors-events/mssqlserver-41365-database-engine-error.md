---
title: MSSQLSERVER_41365 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611096"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="afb80-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="afb80-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="afb80-103">Détails</span><span class="sxs-lookup"><span data-stu-id="afb80-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="afb80-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="afb80-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="afb80-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="afb80-105">Event ID</span></span>|<span data-ttu-id="afb80-106">41365</span><span class="sxs-lookup"><span data-stu-id="afb80-106">41365</span></span>|  
|<span data-ttu-id="afb80-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="afb80-107">Event Source</span></span>|<span data-ttu-id="afb80-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="afb80-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="afb80-109">Composant</span><span class="sxs-lookup"><span data-stu-id="afb80-109">Component</span></span>|<span data-ttu-id="afb80-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="afb80-110">SQLEngine</span></span>|  
|<span data-ttu-id="afb80-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="afb80-111">Symbolic Name</span></span>|<span data-ttu-id="afb80-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="afb80-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="afb80-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="afb80-113">Message Text</span></span>|<span data-ttu-id="afb80-114">La demande de fusion de la plage des transactions [%d, %d] dans la base de données %.\*ls n'a pas été planifiée.</span><span class="sxs-lookup"><span data-stu-id="afb80-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="afb80-115">Les fichiers de point de contrôle représentant la plage sont soit indisponibles pour la fusion, soit ils font partie d'une fusion en cours.</span><span class="sxs-lookup"><span data-stu-id="afb80-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="afb80-116">Explication</span><span class="sxs-lookup"><span data-stu-id="afb80-116">Explanation</span></span>  
 <span data-ttu-id="afb80-117">Les fichiers de point de contrôle représentant la plage sont soit indisponibles pour la fusion, soit ils font partie d'une fusion en cours.</span><span class="sxs-lookup"><span data-stu-id="afb80-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="afb80-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="afb80-118">User Action</span></span>  
 <span data-ttu-id="afb80-119">Optimisez la plage de transactions pour les opérations de fusion/attente avant de réexécuter la même demande.</span><span class="sxs-lookup"><span data-stu-id="afb80-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="afb80-120">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="afb80-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb80-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afb80-121">See Also</span></span>  
 [<span data-ttu-id="afb80-122">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="afb80-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
