---
title: MSSQLSERVER_10502 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600992"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="96a5d-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="96a5d-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="96a5d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="96a5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96a5d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="96a5d-104">Product Name</span></span>|<span data-ttu-id="96a5d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="96a5d-105">SQL Server</span></span>|  
|<span data-ttu-id="96a5d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="96a5d-106">Event ID</span></span>|<span data-ttu-id="96a5d-107">10502</span><span class="sxs-lookup"><span data-stu-id="96a5d-107">10502</span></span>|  
|<span data-ttu-id="96a5d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="96a5d-108">Event Source</span></span>|<span data-ttu-id="96a5d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="96a5d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="96a5d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="96a5d-110">Component</span></span>|<span data-ttu-id="96a5d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="96a5d-111">SQLEngine</span></span>|  
|<span data-ttu-id="96a5d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="96a5d-112">Symbolic Name</span></span>|<span data-ttu-id="96a5d-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="96a5d-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="96a5d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="96a5d-114">Message Text</span></span>|<span data-ttu-id="96a5d-115">Impossible de créer le repère de plan '%.\*ls', car l’instruction spécifiée par @stmt et @module_or_batch ou par @plan_handle et @statement_start_offset correspond au repère de plan existant '%.\*ls' dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="96a5d-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="96a5d-116">Supprimez le repère de plan existant avant de créer le nouveau.</span><span class="sxs-lookup"><span data-stu-id="96a5d-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96a5d-117">Explication</span><span class="sxs-lookup"><span data-stu-id="96a5d-117">Explanation</span></span>  
 <span data-ttu-id="96a5d-118">Un repère de plan existe pour l'instruction spécifiée.</span><span class="sxs-lookup"><span data-stu-id="96a5d-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96a5d-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="96a5d-119">User Action</span></span>  
 <span data-ttu-id="96a5d-120">Supprimez le repère de plan existant avant de créer le nouveau.</span><span class="sxs-lookup"><span data-stu-id="96a5d-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a5d-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96a5d-121">See Also</span></span>  
 <span data-ttu-id="96a5d-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="96a5d-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="96a5d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96a5d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="96a5d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96a5d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
