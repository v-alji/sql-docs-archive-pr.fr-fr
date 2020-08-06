---
title: MSSQLSERVER_10535 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699731"
---
# <a name="mssqlserver_10535"></a><span data-ttu-id="b209b-102">MSSQLSERVER_10535</span><span class="sxs-lookup"><span data-stu-id="b209b-102">MSSQLSERVER_10535</span></span>
    
## <a name="details"></a><span data-ttu-id="b209b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b209b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b209b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b209b-104">Product Name</span></span>|<span data-ttu-id="b209b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b209b-105">SQL Server</span></span>|  
|<span data-ttu-id="b209b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b209b-106">Event ID</span></span>|<span data-ttu-id="b209b-107">10535</span><span class="sxs-lookup"><span data-stu-id="b209b-107">10535</span></span>|  
|<span data-ttu-id="b209b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b209b-108">Event Source</span></span>|<span data-ttu-id="b209b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b209b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b209b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b209b-110">Component</span></span>|<span data-ttu-id="b209b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b209b-111">SQLEngine</span></span>|  
|<span data-ttu-id="b209b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b209b-112">Symbolic Name</span></span>|<span data-ttu-id="b209b-113">PG_NO_PLAN</span><span class="sxs-lookup"><span data-stu-id="b209b-113">PG_NO_PLAN</span></span>|  
|<span data-ttu-id="b209b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b209b-114">Message Text</span></span>|<span data-ttu-id="b209b-115">Impossible de créer le repère de plan '%.\*ls', car aucun plan n'a été trouvé dans le cache du plan qui correspond au handle de plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="b209b-115">Cannot create plan guide '%.\*ls' because a plan was not found in the plan cache that corresponds to the specified plan handle.</span></span> <span data-ttu-id="b209b-116">Indiquez un handle de plan mis en cache.</span><span class="sxs-lookup"><span data-stu-id="b209b-116">Specify a cached plan handle.</span></span> <span data-ttu-id="b209b-117">Pour obtenir la liste des handles de plan mis en cache, interrogez la vue de gestion dynamique sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="b209b-117">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b209b-118">Explication</span><span class="sxs-lookup"><span data-stu-id="b209b-118">Explanation</span></span>  
 <span data-ttu-id="b209b-119">Aucun plan correspondant au handle de plan spécifié n'a été trouvé dans le cache du plan.</span><span class="sxs-lookup"><span data-stu-id="b209b-119">A plan was not found in the plan cache that corresponds to the specified plan handle.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b209b-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b209b-120">User Action</span></span>  
 <span data-ttu-id="b209b-121">Indiquez un handle de plan mis en cache.</span><span class="sxs-lookup"><span data-stu-id="b209b-121">Specify a cached plan handle.</span></span> <span data-ttu-id="b209b-122">Pour obtenir la liste des handles de plan mis en cache, interrogez la vue de gestion dynamique sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="b209b-122">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b209b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b209b-123">See Also</span></span>  
 <span data-ttu-id="b209b-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b209b-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 [<span data-ttu-id="b209b-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b209b-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
