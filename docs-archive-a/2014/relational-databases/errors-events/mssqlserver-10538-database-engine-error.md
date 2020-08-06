---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699720"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="7d043-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="7d043-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="7d043-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7d043-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d043-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7d043-104">Product Name</span></span>|<span data-ttu-id="7d043-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d043-105">SQL Server</span></span>|  
|<span data-ttu-id="7d043-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7d043-106">Event ID</span></span>|<span data-ttu-id="7d043-107">10538</span><span class="sxs-lookup"><span data-stu-id="7d043-107">10538</span></span>|  
|<span data-ttu-id="7d043-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7d043-108">Event Source</span></span>|<span data-ttu-id="7d043-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d043-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d043-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7d043-110">Component</span></span>|<span data-ttu-id="7d043-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7d043-111">SQLEngine</span></span>|  
|<span data-ttu-id="7d043-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7d043-112">Symbolic Name</span></span>|<span data-ttu-id="7d043-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="7d043-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="7d043-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7d043-114">Message Text</span></span>|<span data-ttu-id="7d043-115">Impossible de trouver le repère de plan, car l'ID du repère de plan spécifié a la valeur Null ou n'est pas valide, ou vous n'avez pas d'autorisation sur l'objet référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="7d043-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="7d043-116">Vérifiez que l’ID du repère de plan est valide, que la session active est définie en fonction du contexte de base de données approprié et que vous disposez de l’autorisation ALTER ou de l’autorisation ALTER DATABASE sur l’objet référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="7d043-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d043-117">Explication</span><span class="sxs-lookup"><span data-stu-id="7d043-117">Explanation</span></span>  
 <span data-ttu-id="7d043-118">L'ID du repère de plan spécifié est Null ou n'est pas valide, ou vous n'avez pas d'autorisation sur l'objet référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="7d043-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d043-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7d043-119">User Action</span></span>  
 <span data-ttu-id="7d043-120">Vérifiez que l'ID du repère de plan est valide, que la session active est définie en fonction du contexte de base de données approprié et que vous disposez de l'autorisation ALTER ou de l'autorisation ALTER DATABASE sur l'objet référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="7d043-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d043-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d043-121">See Also</span></span>  
 <span data-ttu-id="7d043-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7d043-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="7d043-123">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="7d043-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="7d043-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d043-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
