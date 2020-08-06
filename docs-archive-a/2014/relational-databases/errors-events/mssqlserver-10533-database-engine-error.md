---
title: MSSQLSERVER_10533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10533 (Database Engine error)
ms.assetid: cc2fbdab-7b90-415f-a1f9-066824344283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccef25bc8f594cb6ea0b60aefab838ef27cda6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605507"
---
# <a name="mssqlserver_10533"></a><span data-ttu-id="9f778-102">MSSQLSERVER_10533</span><span class="sxs-lookup"><span data-stu-id="9f778-102">MSSQLSERVER_10533</span></span>
    
## <a name="details"></a><span data-ttu-id="9f778-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9f778-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f778-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9f778-104">Product Name</span></span>|<span data-ttu-id="9f778-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f778-105">SQL Server</span></span>|  
|<span data-ttu-id="9f778-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9f778-106">Event ID</span></span>|<span data-ttu-id="9f778-107">10533</span><span class="sxs-lookup"><span data-stu-id="9f778-107">10533</span></span>|  
|<span data-ttu-id="9f778-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9f778-108">Event Source</span></span>|<span data-ttu-id="9f778-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f778-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f778-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9f778-110">Component</span></span>|<span data-ttu-id="9f778-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9f778-111">SQLEngine</span></span>|  
|<span data-ttu-id="9f778-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9f778-112">Symbolic Name</span></span>|<span data-ttu-id="9f778-113">PG_NAME_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="9f778-113">PG_NAME_TOO_BIG</span></span>|  
|<span data-ttu-id="9f778-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9f778-114">Message Text</span></span>|<span data-ttu-id="9f778-115">Impossible de créer le repère de plan '%.\*ls', car le nom du repère de plan dépasse 124, le nombre maximal de caractères autorisé.</span><span class="sxs-lookup"><span data-stu-id="9f778-115">Cannot create plan guide '%.\*ls' because the plan guide name exceeds 124 characters, the maximum number allowed.</span></span> <span data-ttu-id="9f778-116">Indiquez un nom qui contient moins de 125 caractères.</span><span class="sxs-lookup"><span data-stu-id="9f778-116">Specify a name that contains fewer than 125 characters.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f778-117">Explication</span><span class="sxs-lookup"><span data-stu-id="9f778-117">Explanation</span></span>  
 <span data-ttu-id="9f778-118">Le nom du repère de plan dépasse 124 caractères, le nombre maximal autorisé.</span><span class="sxs-lookup"><span data-stu-id="9f778-118">The plan guide name exceeds 124 characters, the maximum number allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f778-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9f778-119">User Action</span></span>  
 <span data-ttu-id="9f778-120">Indiquez un nom qui contient moins de 125 caractères.</span><span class="sxs-lookup"><span data-stu-id="9f778-120">Specify a name that contains fewer than 125 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f778-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f778-121">See Also</span></span>  
 <span data-ttu-id="9f778-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="9f778-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="9f778-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9f778-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="9f778-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f778-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
