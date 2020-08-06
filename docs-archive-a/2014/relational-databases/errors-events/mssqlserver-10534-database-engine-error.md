---
title: MSSQLSERVER_10534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10534 (Database Engine error)
ms.assetid: e65bb118-99d5-4fdb-b1d5-0ec70f0a677b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 793bb0bf5048e30624d9566f65e7c6752bd14386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699738"
---
# <a name="mssqlserver_10534"></a><span data-ttu-id="d7ac2-102">MSSQLSERVER_10534</span><span class="sxs-lookup"><span data-stu-id="d7ac2-102">MSSQLSERVER_10534</span></span>
    
## <a name="details"></a><span data-ttu-id="d7ac2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d7ac2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7ac2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d7ac2-104">Product Name</span></span>|<span data-ttu-id="d7ac2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7ac2-105">SQL Server</span></span>|  
|<span data-ttu-id="d7ac2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d7ac2-106">Event ID</span></span>|<span data-ttu-id="d7ac2-107">10534</span><span class="sxs-lookup"><span data-stu-id="d7ac2-107">10534</span></span>|  
|<span data-ttu-id="d7ac2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d7ac2-108">Event Source</span></span>|<span data-ttu-id="d7ac2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d7ac2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d7ac2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d7ac2-110">Component</span></span>|<span data-ttu-id="d7ac2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d7ac2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d7ac2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d7ac2-112">Symbolic Name</span></span>|<span data-ttu-id="d7ac2-113">PG_INVALID_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d7ac2-113">PG_INVALID_PARAMS</span></span>|  
|<span data-ttu-id="d7ac2-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d7ac2-114">Message Text</span></span>|<span data-ttu-id="d7ac2-115">Impossible de créer le repère de plan '%.\*ls', car la valeur spécifiée pour `@params` n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-115">Cannot create plan guide '%.\*ls' because the value specified for `@params` is invalid.</span></span> <span data-ttu-id="d7ac2-116">Indiquez la valeur sous la forme *nom_paramètre type_paramètre* ou spécifiez Null.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-116">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d7ac2-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d7ac2-117">Explanation</span></span>  
 <span data-ttu-id="d7ac2-118">La valeur spécifiée pour `@params` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-118">The value specified for `@params` is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7ac2-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d7ac2-119">User Action</span></span>  
 <span data-ttu-id="d7ac2-120">Indiquez la valeur sous la forme *nom_paramètre type_paramètre* ou spécifiez Null.</span><span class="sxs-lookup"><span data-stu-id="d7ac2-120">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ac2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7ac2-121">See Also</span></span>  
 <span data-ttu-id="d7ac2-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="d7ac2-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="d7ac2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d7ac2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="d7ac2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d7ac2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
