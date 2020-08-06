---
title: MSSQLSERVER_10537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702960"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="a1eb5-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="a1eb5-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="a1eb5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a1eb5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1eb5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a1eb5-104">Product Name</span></span>|<span data-ttu-id="a1eb5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1eb5-105">SQL Server</span></span>|  
|<span data-ttu-id="a1eb5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a1eb5-106">Event ID</span></span>|<span data-ttu-id="a1eb5-107">10537</span><span class="sxs-lookup"><span data-stu-id="a1eb5-107">10537</span></span>|  
|<span data-ttu-id="a1eb5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a1eb5-108">Event Source</span></span>|<span data-ttu-id="a1eb5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a1eb5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a1eb5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a1eb5-110">Component</span></span>|<span data-ttu-id="a1eb5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a1eb5-111">SQLEngine</span></span>|  
|<span data-ttu-id="a1eb5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a1eb5-112">Symbolic Name</span></span>|<span data-ttu-id="a1eb5-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a1eb5-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="a1eb5-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a1eb5-114">Message Text</span></span>|<span data-ttu-id="a1eb5-115">Impossible d’activer le repère de plan '%.\*ls', car le repère de plan activé '%.\*ls' contient les mêmes étendue et valeur de décalage de départ que l’instruction.</span><span class="sxs-lookup"><span data-stu-id="a1eb5-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="a1eb5-116">Désactivez le repère de plan existant avant d'activer le repère de plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="a1eb5-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a1eb5-117">Explication</span><span class="sxs-lookup"><span data-stu-id="a1eb5-117">Explanation</span></span>  
 <span data-ttu-id="a1eb5-118">Un repère de plan existant contient les mêmes étendue et valeur de décalage de départ que l'instruction du repère de plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="a1eb5-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a1eb5-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a1eb5-119">User Action</span></span>  
 <span data-ttu-id="a1eb5-120">Désactivez le repère de plan existant avant d'activer le repère de plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="a1eb5-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1eb5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1eb5-121">See Also</span></span>  
 <span data-ttu-id="a1eb5-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a1eb5-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="a1eb5-123">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="a1eb5-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="a1eb5-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1eb5-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
