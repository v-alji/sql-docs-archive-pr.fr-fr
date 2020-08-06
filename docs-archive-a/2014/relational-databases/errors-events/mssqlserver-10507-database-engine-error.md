---
title: MSSQLSERVER_10507 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706543"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="fcc53-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="fcc53-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="fcc53-103">Détails</span><span class="sxs-lookup"><span data-stu-id="fcc53-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcc53-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="fcc53-104">Product Name</span></span>|<span data-ttu-id="fcc53-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fcc53-105">SQL Server</span></span>|  
|<span data-ttu-id="fcc53-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="fcc53-106">Event ID</span></span>|<span data-ttu-id="fcc53-107">10507</span><span class="sxs-lookup"><span data-stu-id="fcc53-107">10507</span></span>|  
|<span data-ttu-id="fcc53-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="fcc53-108">Event Source</span></span>|<span data-ttu-id="fcc53-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fcc53-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fcc53-110">Composant</span><span class="sxs-lookup"><span data-stu-id="fcc53-110">Component</span></span>|<span data-ttu-id="fcc53-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fcc53-111">SQLEngine</span></span>|  
|<span data-ttu-id="fcc53-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="fcc53-112">Symbolic Name</span></span>|<span data-ttu-id="fcc53-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="fcc53-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="fcc53-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="fcc53-114">Message Text</span></span>|<span data-ttu-id="fcc53-115">Impossible de créer le repère de plan '%.\*ls', car l’instruction spécifiée par `@stmt` et `@module_or_batch` ou par `@plan_handle` et `@statement_start_offset` ne correspond à aucune instruction dans le module ou lot spécifié.</span><span class="sxs-lookup"><span data-stu-id="fcc53-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="fcc53-116">Modifiez les valeurs pour qu'elles correspondent à une instruction dans le module ou le lot.</span><span class="sxs-lookup"><span data-stu-id="fcc53-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fcc53-117">Explication</span><span class="sxs-lookup"><span data-stu-id="fcc53-117">Explanation</span></span>  
 <span data-ttu-id="fcc53-118">Une instruction dans le module ou le lot spécifié n'a pas pu être mise en correspondance avec l'instruction ou la valeur de décalage de l'instruction spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fcc53-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fcc53-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fcc53-119">User Action</span></span>  
 <span data-ttu-id="fcc53-120">Modifiez les valeurs de paramètre spécifiées pour qu'elles correspondent à une instruction dans le module ou le lot.</span><span class="sxs-lookup"><span data-stu-id="fcc53-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc53-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcc53-121">See Also</span></span>  
 <span data-ttu-id="fcc53-122">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="fcc53-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="fcc53-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcc53-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="fcc53-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fcc53-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
