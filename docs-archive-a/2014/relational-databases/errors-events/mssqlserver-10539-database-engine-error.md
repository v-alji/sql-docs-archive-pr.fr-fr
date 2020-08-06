---
title: MSSQLSERVER_10539 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699713"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="4f1a3-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="4f1a3-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="4f1a3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4f1a3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f1a3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4f1a3-104">Product Name</span></span>|<span data-ttu-id="4f1a3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f1a3-105">SQL Server</span></span>|  
|<span data-ttu-id="4f1a3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4f1a3-106">Event ID</span></span>|<span data-ttu-id="4f1a3-107">10539</span><span class="sxs-lookup"><span data-stu-id="4f1a3-107">10539</span></span>|  
|<span data-ttu-id="4f1a3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4f1a3-108">Event Source</span></span>|<span data-ttu-id="4f1a3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4f1a3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4f1a3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4f1a3-110">Component</span></span>|<span data-ttu-id="4f1a3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4f1a3-111">SQLEngine</span></span>|  
|<span data-ttu-id="4f1a3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4f1a3-112">Symbolic Name</span></span>|<span data-ttu-id="4f1a3-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="4f1a3-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="4f1a3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4f1a3-114">Message Text</span></span>|<span data-ttu-id="4f1a3-115">Impossible de créer le repère de plan '%.\*ls' à partir du cache, car aucun plan de requête n'est disponible pour l'instruction avec l'offset de démarrage %d.</span><span class="sxs-lookup"><span data-stu-id="4f1a3-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="4f1a3-116">Ce problème peut se produire si l'instruction dépend des objets de base de données qui n'ont pas encore été créés.</span><span class="sxs-lookup"><span data-stu-id="4f1a3-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="4f1a3-117">Assurez-vous que tous les objets de base de données nécessaires existent, puis exécutez l'instruction avant de créer le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="4f1a3-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4f1a3-118">Explication</span><span class="sxs-lookup"><span data-stu-id="4f1a3-118">Explanation</span></span>  
 <span data-ttu-id="4f1a3-119">Aucun plan de requête n'est disponible dans le cache du plan pour l'instruction avec l'offset de démarrage spécifié.</span><span class="sxs-lookup"><span data-stu-id="4f1a3-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f1a3-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4f1a3-120">User Action</span></span>  
 <span data-ttu-id="4f1a3-121">Assurez-vous que tous les objets de base de données nécessaires existent, puis exécutez l'instruction avant de créer le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="4f1a3-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1a3-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f1a3-122">See Also</span></span>  
 [<span data-ttu-id="4f1a3-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f1a3-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
