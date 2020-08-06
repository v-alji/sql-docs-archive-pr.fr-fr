---
title: MSSQLSERVER_10532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707583"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="530f8-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="530f8-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="530f8-103">Détails</span><span class="sxs-lookup"><span data-stu-id="530f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="530f8-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="530f8-104">Product Name</span></span>|<span data-ttu-id="530f8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="530f8-105">SQL Server</span></span>|  
|<span data-ttu-id="530f8-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="530f8-106">Event ID</span></span>|<span data-ttu-id="530f8-107">10532</span><span class="sxs-lookup"><span data-stu-id="530f8-107">10532</span></span>|  
|<span data-ttu-id="530f8-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="530f8-108">Event Source</span></span>|<span data-ttu-id="530f8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="530f8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="530f8-110">Composant</span><span class="sxs-lookup"><span data-stu-id="530f8-110">Component</span></span>|<span data-ttu-id="530f8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="530f8-111">SQLEngine</span></span>|  
|<span data-ttu-id="530f8-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="530f8-112">Symbolic Name</span></span>|<span data-ttu-id="530f8-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="530f8-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="530f8-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="530f8-114">Message Text</span></span>|<span data-ttu-id="530f8-115">Impossible de créer le repère de plan ’%.\*ls’, car le module ou lot spécifié par `@plan_handle` ne contient pas d’instruction éligible pour un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="530f8-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="530f8-116">Indiquez une autre valeur pour `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="530f8-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="530f8-117">Explication</span><span class="sxs-lookup"><span data-stu-id="530f8-117">Explanation</span></span>  
 <span data-ttu-id="530f8-118">Le module ou lot spécifié par `@plan_handle` ne contient pas d'instruction éligible pour un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="530f8-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="530f8-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="530f8-119">User Action</span></span>  
 <span data-ttu-id="530f8-120">Indiquez une autre valeur pour `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="530f8-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530f8-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="530f8-121">See Also</span></span>  
 <span data-ttu-id="530f8-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="530f8-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="530f8-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="530f8-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="530f8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="530f8-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
