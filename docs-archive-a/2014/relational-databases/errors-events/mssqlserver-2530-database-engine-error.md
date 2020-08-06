---
title: MSSQLSERVER_2530 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600978"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="7806b-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="7806b-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="7806b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7806b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7806b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7806b-104">Product Name</span></span>|<span data-ttu-id="7806b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7806b-105">SQL Server</span></span>|  
|<span data-ttu-id="7806b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7806b-106">Event ID</span></span>|<span data-ttu-id="7806b-107">2530</span><span class="sxs-lookup"><span data-stu-id="7806b-107">2530</span></span>|  
|<span data-ttu-id="7806b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7806b-108">Event Source</span></span>|<span data-ttu-id="7806b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7806b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7806b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7806b-110">Component</span></span>|<span data-ttu-id="7806b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7806b-111">SQLEngine</span></span>|  
|<span data-ttu-id="7806b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7806b-112">Symbolic Name</span></span>|<span data-ttu-id="7806b-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="7806b-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="7806b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7806b-114">Message Text</span></span>|<span data-ttu-id="7806b-115">L’index "%.\*ls" sur la table "%.\*ls" est désactivé.</span><span class="sxs-lookup"><span data-stu-id="7806b-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7806b-116">Explication</span><span class="sxs-lookup"><span data-stu-id="7806b-116">Explanation</span></span>  
 <span data-ttu-id="7806b-117">L'instruction DBCC ne peut pas continuer, car l'index spécifié est désactivé.</span><span class="sxs-lookup"><span data-stu-id="7806b-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="7806b-118">Lorsqu'un index est désactivé, il reste dans cet état tant qu'il n'est pas reconstruit, ou supprimé et recréé.</span><span class="sxs-lookup"><span data-stu-id="7806b-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7806b-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7806b-119">User Action</span></span>  
  
1.  <span data-ttu-id="7806b-120">Activez l'index désactivé à l'aide de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7806b-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="7806b-121">Instruction ALTER INDEX avec la clause REBUILD</span><span class="sxs-lookup"><span data-stu-id="7806b-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="7806b-122">Instruction CREATE INDEX avec la clause DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="7806b-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="7806b-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="7806b-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="7806b-124">Réexécutez l'instruction DBCC.</span><span class="sxs-lookup"><span data-stu-id="7806b-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7806b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7806b-125">See Also</span></span>  
 <span data-ttu-id="7806b-126">[Activer les index et les contraintes](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="7806b-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="7806b-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7806b-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="7806b-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7806b-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="7806b-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7806b-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
