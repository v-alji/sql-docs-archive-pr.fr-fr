---
title: MSSQLSERVER_10531 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699744"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="fc556-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="fc556-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="fc556-103">Détails</span><span class="sxs-lookup"><span data-stu-id="fc556-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc556-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="fc556-104">Product Name</span></span>|<span data-ttu-id="fc556-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc556-105">SQL Server</span></span>|  
|<span data-ttu-id="fc556-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="fc556-106">Event ID</span></span>|<span data-ttu-id="fc556-107">10531</span><span class="sxs-lookup"><span data-stu-id="fc556-107">10531</span></span>|  
|<span data-ttu-id="fc556-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="fc556-108">Event Source</span></span>|<span data-ttu-id="fc556-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fc556-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fc556-110">Composant</span><span class="sxs-lookup"><span data-stu-id="fc556-110">Component</span></span>|<span data-ttu-id="fc556-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fc556-111">SQLEngine</span></span>|  
|<span data-ttu-id="fc556-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="fc556-112">Symbolic Name</span></span>|<span data-ttu-id="fc556-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="fc556-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="fc556-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="fc556-114">Message Text</span></span>|<span data-ttu-id="fc556-115">Impossible de créer le repère de plan '%.\*ls' à partir du cache, car l'utilisateur ne dispose pas des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="fc556-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="fc556-116">Accordez l'autorisation VIEW SERVER STATE à l'utilisateur qui crée le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="fc556-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fc556-117">Explication</span><span class="sxs-lookup"><span data-stu-id="fc556-117">Explanation</span></span>  
 <span data-ttu-id="fc556-118">L'utilisateur ne dispose pas des autorisations adéquates pour créer le repère de plan spécifié à partir du cache du plan.</span><span class="sxs-lookup"><span data-stu-id="fc556-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc556-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fc556-119">User Action</span></span>  
 <span data-ttu-id="fc556-120">Accordez l’autorisation VIEW SERVER STATE à l’utilisateur qui crée le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="fc556-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc556-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc556-121">See Also</span></span>  
 <span data-ttu-id="fc556-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="fc556-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="fc556-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc556-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="fc556-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fc556-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
