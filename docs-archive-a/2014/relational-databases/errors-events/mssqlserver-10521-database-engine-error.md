---
title: MSSQLSERVER_10521 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699749"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="cb0a4-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="cb0a4-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="cb0a4-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cb0a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb0a4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cb0a4-104">Product Name</span></span>|<span data-ttu-id="cb0a4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb0a4-105">SQL Server</span></span>|  
|<span data-ttu-id="cb0a4-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cb0a4-106">Event ID</span></span>|<span data-ttu-id="cb0a4-107">10521</span><span class="sxs-lookup"><span data-stu-id="cb0a4-107">10521</span></span>|  
|<span data-ttu-id="cb0a4-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cb0a4-108">Event Source</span></span>|<span data-ttu-id="cb0a4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb0a4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb0a4-110">Composant</span><span class="sxs-lookup"><span data-stu-id="cb0a4-110">Component</span></span>|<span data-ttu-id="cb0a4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cb0a4-111">SQLEngine</span></span>|  
|<span data-ttu-id="cb0a4-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cb0a4-112">Symbolic Name</span></span>|<span data-ttu-id="cb0a4-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="cb0a4-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="cb0a4-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cb0a4-114">Message Text</span></span>|<span data-ttu-id="cb0a4-115">Impossible de créer le repère de plan '%.\*ls', car `@type` a été spécifié en tant que '%ls' et le paramètre '%ls' a la valeur Null.</span><span class="sxs-lookup"><span data-stu-id="cb0a4-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="cb0a4-116">Ce type requiert une valeur autre que Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="cb0a4-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="cb0a4-117">Spécifiez une valeur autre que Null pour le paramètre ou remplacez le type par un type qui autorise une valeur Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="cb0a4-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb0a4-118">Explication</span><span class="sxs-lookup"><span data-stu-id="cb0a4-118">Explanation</span></span>  
 <span data-ttu-id="cb0a4-119">Le type spécifié dans `@type` requiert une valeur non Null pour le paramètre spécifié ; toutefois, une valeur Null a été fournie.</span><span class="sxs-lookup"><span data-stu-id="cb0a4-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb0a4-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cb0a4-120">User Action</span></span>  
 <span data-ttu-id="cb0a4-121">Spécifiez une valeur autre que Null pour le paramètre ou remplacez le type par un type qui autorise une valeur Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="cb0a4-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0a4-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb0a4-122">See Also</span></span>  
 <span data-ttu-id="cb0a4-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cb0a4-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="cb0a4-124">[Repères de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="cb0a4-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="cb0a4-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb0a4-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
