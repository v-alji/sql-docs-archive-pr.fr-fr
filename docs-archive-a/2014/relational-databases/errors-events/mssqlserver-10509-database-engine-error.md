---
title: MSSQLSERVER_10509 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10509 (Database Engine error)
ms.assetid: e9dd5357-ee3d-420a-9a89-d12ab5404e73
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73194c7da553bf27acb78d8c4e7d71bc93f457d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708420"
---
# <a name="mssqlserver_10509"></a><span data-ttu-id="961f2-102">MSSQLSERVER_10509</span><span class="sxs-lookup"><span data-stu-id="961f2-102">MSSQLSERVER_10509</span></span>
    
## <a name="details"></a><span data-ttu-id="961f2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="961f2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="961f2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="961f2-104">Product Name</span></span>|<span data-ttu-id="961f2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="961f2-105">SQL Server</span></span>|  
|<span data-ttu-id="961f2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="961f2-106">Event ID</span></span>|<span data-ttu-id="961f2-107">10509</span><span class="sxs-lookup"><span data-stu-id="961f2-107">10509</span></span>|  
|<span data-ttu-id="961f2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="961f2-108">Event Source</span></span>|<span data-ttu-id="961f2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="961f2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="961f2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="961f2-110">Component</span></span>|<span data-ttu-id="961f2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="961f2-111">SQLEngine</span></span>|  
|<span data-ttu-id="961f2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="961f2-112">Symbolic Name</span></span>|<span data-ttu-id="961f2-113">PG_INVALID_STMT</span><span class="sxs-lookup"><span data-stu-id="961f2-113">PG_INVALID_STMT</span></span>|  
|<span data-ttu-id="961f2-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="961f2-114">Message Text</span></span>|<span data-ttu-id="961f2-115">Impossible de créer le repère de plan '%.\*ls', car l’instruction spécifiée par `@stmt` ou `@statement_start_offset` contient une erreur de syntaxe ou n’est pas éligible pour le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="961f2-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span> <span data-ttu-id="961f2-116">Fournissez une seule instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] valide ou une position de départ de l'instruction valide dans le lot.</span><span class="sxs-lookup"><span data-stu-id="961f2-116">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="961f2-117">Pour obtenir une position de départ valide, interrogez la colonne statement_start_offset de la fonction de gestion dynamique sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="961f2-117">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="961f2-118">Explication</span><span class="sxs-lookup"><span data-stu-id="961f2-118">Explanation</span></span>  
 <span data-ttu-id="961f2-119">L'instruction spécifiée par `@stmt` ou `@statement_start_offset` contient une erreur de syntaxe ou n'est pas éligible pour une utilisation dans un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="961f2-119">The statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="961f2-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="961f2-120">User Action</span></span>  
 <span data-ttu-id="961f2-121">Fournissez une seule instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] valide ou une position de départ de l'instruction valide dans le lot.</span><span class="sxs-lookup"><span data-stu-id="961f2-121">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="961f2-122">Pour obtenir une position de départ valide, interrogez la colonne statement_start_offset de la fonction de gestion dynamique sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="961f2-122">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961f2-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="961f2-123">See Also</span></span>  
 <span data-ttu-id="961f2-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="961f2-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="961f2-125">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="961f2-125">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="961f2-126">[sys. dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="961f2-126">[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span></span>  
 [<span data-ttu-id="961f2-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="961f2-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
