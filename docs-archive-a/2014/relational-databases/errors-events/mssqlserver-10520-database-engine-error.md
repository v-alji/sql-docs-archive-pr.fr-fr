---
title: MSSQLSERVER_10520 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699755"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="e969d-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="e969d-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="e969d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e969d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e969d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e969d-104">Product Name</span></span>|<span data-ttu-id="e969d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e969d-105">SQL Server</span></span>|  
|<span data-ttu-id="e969d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e969d-106">Event ID</span></span>|<span data-ttu-id="e969d-107">10520</span><span class="sxs-lookup"><span data-stu-id="e969d-107">10520</span></span>|  
|<span data-ttu-id="e969d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e969d-108">Event Source</span></span>|<span data-ttu-id="e969d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e969d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e969d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e969d-110">Component</span></span>|<span data-ttu-id="e969d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e969d-111">SQLEngine</span></span>|  
|<span data-ttu-id="e969d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e969d-112">Symbolic Name</span></span>|<span data-ttu-id="e969d-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="e969d-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="e969d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e969d-114">Message Text</span></span>|<span data-ttu-id="e969d-115">Impossible de créer le repère de plan ’%.ls’, car @type a été spécifié comme ’%ls’ et une valeur autre que Null est spécifiée pour le paramètre ’%ls’.</span><span class="sxs-lookup"><span data-stu-id="e969d-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="e969d-116">Ce type requiert une valeur Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="e969d-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="e969d-117">Spécifiez la valeur Null pour le paramètre ou remplacez le type par un type qui autorise une valeur autre que Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="e969d-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e969d-118">Explication</span><span class="sxs-lookup"><span data-stu-id="e969d-118">Explanation</span></span>  
 <span data-ttu-id="e969d-119">Le type spécifié dans @type nécessite une valeur Null pour le paramètre spécifié, mais une valeur non Null a été fournie.</span><span class="sxs-lookup"><span data-stu-id="e969d-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e969d-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e969d-120">User Action</span></span>  
 <span data-ttu-id="e969d-121">Spécifiez la valeur Null pour le paramètre ou remplacez le type par un type qui autorise une valeur autre que Null pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="e969d-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e969d-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e969d-122">See Also</span></span>  
 <span data-ttu-id="e969d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e969d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="e969d-124">Repères de plan</span><span class="sxs-lookup"><span data-stu-id="e969d-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
