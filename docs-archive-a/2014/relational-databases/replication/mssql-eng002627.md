---
title: MSSQL_ENG002627 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709163"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="fa660-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="fa660-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="fa660-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="fa660-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa660-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="fa660-104">Product Name</span></span>|<span data-ttu-id="fa660-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa660-105">SQL Server</span></span>|  
|<span data-ttu-id="fa660-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="fa660-106">Event ID</span></span>|<span data-ttu-id="fa660-107">2627</span><span class="sxs-lookup"><span data-stu-id="fa660-107">2627</span></span>|  
|<span data-ttu-id="fa660-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="fa660-108">Event Source</span></span>|<span data-ttu-id="fa660-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fa660-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fa660-110">Composant</span><span class="sxs-lookup"><span data-stu-id="fa660-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="fa660-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="fa660-111">Symbolic Name</span></span>|<span data-ttu-id="fa660-112">N/A</span><span class="sxs-lookup"><span data-stu-id="fa660-112">N/A</span></span>|  
|<span data-ttu-id="fa660-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="fa660-113">Message Text</span></span>|<span data-ttu-id="fa660-114">Violation de la contrainte% ls'%. \* ls'.</span><span class="sxs-lookup"><span data-stu-id="fa660-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="fa660-115">Impossible d’insérer une clé en double dans l’objet '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="fa660-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa660-116">Explication</span><span class="sxs-lookup"><span data-stu-id="fa660-116">Explanation</span></span>  
 <span data-ttu-id="fa660-117">C'est une erreur générale qui peut être déclenchée qu'une base de données soit répliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="fa660-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="fa660-118">Dans les bases de données répliquées, l'erreur est généralement déclenchée car les clés primaires n'ont pas été gérés de manière appropriée à travers la topologie.</span><span class="sxs-lookup"><span data-stu-id="fa660-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="fa660-119">Dans un environnement distribué, il est primordial de s'assurer que la même valeur n'est pas insérée dans une colonne de clé primaire ou toute autre colonne unique sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="fa660-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="fa660-120">Les raisons peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa660-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="fa660-121">Les insertions et mises à jour sur une ligne se produisent sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="fa660-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="fa660-122">La réplication de fusion et les abonnements pouvant être mis à jour pour la réplication transactionnelle permettent tous deux la détection et la résolution des conflits, mais il est quand même préférable de n'insérer ou de ne mettre à jour une ligne donnée que sur un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="fa660-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="fa660-123">La réplication transactionnelle d'égal à égal ne permet pas la détection et la résolution des conflits, elle nécessite que les insertions et mises à jour soient partitionnées.</span><span class="sxs-lookup"><span data-stu-id="fa660-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="fa660-124">Une ligne a été insérée sur un abonné qui devrait être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa660-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="fa660-125">Les abonnés aux publications d'instantanés, ainsi que les abonnés au publications transactionnelles devraient être traités comme étant en lecture seule à moins d'utiliser des abonnements pouvant être mis à jour ou la réplication transactionnelle d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="fa660-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="fa660-126">Une table avec une colonne d'identité est utilisée, mais la colonne n'est par gérée de façon appropriée.</span><span class="sxs-lookup"><span data-stu-id="fa660-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa660-127">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fa660-127">User Action</span></span>  
 <span data-ttu-id="fa660-128">L'action requise dépend de la raison du déclenchement de l'erreur :</span><span class="sxs-lookup"><span data-stu-id="fa660-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="fa660-129">Les insertions et mises à jour sur une ligne se produisent sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="fa660-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="fa660-130">Quel que soit le type de réplication utilisé, il est recommandé de partitionner les insertions et mises à jour chaque fois que cela est possible, car cela réduit le traitement nécessaire pour la détection et la résolution des conflits.</span><span class="sxs-lookup"><span data-stu-id="fa660-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="fa660-131">Pour la réplication transactionnelle d'égal à égal, le partitionnement d'insertions et de mises à jour est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fa660-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="fa660-132">Pour plus d'informations, consultez [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="fa660-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="fa660-133">Une ligne a été insérée sur un abonné qui devrait être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa660-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="fa660-134">N'insérez pas ou ne mettez pas à jour de lignes sur l'Abonné à moins d'utiliser la réplication de fusion, la réplication transactionnelle avec abonnements pouvant être mis à jour ou la réplication transactionnelle d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="fa660-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="fa660-135">Une table avec une colonne d'identité est utilisée, mais la colonne n'est par gérée de façon appropriée.</span><span class="sxs-lookup"><span data-stu-id="fa660-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="fa660-136">Pour la réplication de fusion et la réplication transactionnelle avec abonnements pouvant être mis à jour, les colonnes d'identité doivent être gérées automatiquement par la réplication.</span><span class="sxs-lookup"><span data-stu-id="fa660-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="fa660-137">Pour la réplication transactionnelle d'égal à égal, elles doivent être gérées manuellement.</span><span class="sxs-lookup"><span data-stu-id="fa660-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="fa660-138">Pour plus d’informations, consultez [ Répliquer des colonnes d’identité](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="fa660-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa660-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa660-139">See Also</span></span>  
 <span data-ttu-id="fa660-140">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fa660-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="fa660-141">[Réplication de fusion](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fa660-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="fa660-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fa660-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="fa660-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="fa660-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
