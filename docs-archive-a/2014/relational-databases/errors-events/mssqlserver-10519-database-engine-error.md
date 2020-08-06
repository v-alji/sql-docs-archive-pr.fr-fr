---
title: MSSQLSERVER_10519 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705152"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="6d707-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="6d707-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="6d707-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6d707-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d707-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6d707-104">Product Name</span></span>|<span data-ttu-id="6d707-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d707-105">SQL Server</span></span>|  
|<span data-ttu-id="6d707-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6d707-106">Event ID</span></span>|<span data-ttu-id="6d707-107">10519</span><span class="sxs-lookup"><span data-stu-id="6d707-107">10519</span></span>|  
|<span data-ttu-id="6d707-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6d707-108">Event Source</span></span>|<span data-ttu-id="6d707-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6d707-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6d707-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6d707-110">Component</span></span>|<span data-ttu-id="6d707-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6d707-111">SQLEngine</span></span>|  
|<span data-ttu-id="6d707-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6d707-112">Symbolic Name</span></span>|<span data-ttu-id="6d707-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="6d707-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="6d707-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6d707-114">Message Text</span></span>|<span data-ttu-id="6d707-115">Impossible de créer le repère de plan '%.\*ls', car les indicateurs spécifiés dans `@hints` ne peuvent pas être appliqués à l’instruction spécifiée par `@stmt` ou `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="6d707-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="6d707-116">Vérifiez que les indicateurs peuvent être appliqués à l'instruction.</span><span class="sxs-lookup"><span data-stu-id="6d707-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d707-117">Explication</span><span class="sxs-lookup"><span data-stu-id="6d707-117">Explanation</span></span>  
 <span data-ttu-id="6d707-118">Les indicateurs spécifiés dans `@hints` ne peuvent pas être appliqués à l'instruction spécifiée par `@stmt` ou `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="6d707-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d707-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d707-119">User Action</span></span>  
 <span data-ttu-id="6d707-120">Spécifiez des indicateurs qui peuvent être appliqués à l'instruction.</span><span class="sxs-lookup"><span data-stu-id="6d707-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d707-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d707-121">See Also</span></span>  
 <span data-ttu-id="6d707-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d707-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="6d707-123">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="6d707-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="6d707-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6d707-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
