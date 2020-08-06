---
title: MSSQL_ENG002601 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708192"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="e2073-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="e2073-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e2073-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="e2073-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2073-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e2073-104">Product Name</span></span>|<span data-ttu-id="e2073-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2073-105">SQL Server</span></span>|  
|<span data-ttu-id="e2073-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2073-106">Event ID</span></span>|<span data-ttu-id="e2073-107">2601</span><span class="sxs-lookup"><span data-stu-id="e2073-107">2601</span></span>|  
|<span data-ttu-id="e2073-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e2073-108">Event Source</span></span>|<span data-ttu-id="e2073-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e2073-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e2073-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e2073-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e2073-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e2073-111">Symbolic Name</span></span>|<span data-ttu-id="e2073-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e2073-112">N/A</span></span>|  
|<span data-ttu-id="e2073-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e2073-113">Message Text</span></span>|<span data-ttu-id="e2073-114">Impossible d’insérer une ligne de clé en double dans l’objet '%1!' \*avec un index unique '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="e2073-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e2073-115">Explication</span><span class="sxs-lookup"><span data-stu-id="e2073-115">Explanation</span></span>  
 <span data-ttu-id="e2073-116">C'est une erreur générale qui peut être déclenchée qu'une base de données soit répliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="e2073-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="e2073-117">Dans les bases de données répliquées, l'erreur est généralement déclenchée car les clés primaires n'ont pas été gérés de manière appropriée à travers la topologie.</span><span class="sxs-lookup"><span data-stu-id="e2073-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="e2073-118">Dans un environnement distribué, il est primordial de s'assurer que la même valeur n'est pas insérée dans une colonne de clé primaire ou toute autre colonne unique sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="e2073-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="e2073-119">Les raisons peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2073-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="e2073-120">Les insertions et mises à jour sur une ligne se produisent sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="e2073-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="e2073-121">La réplication de fusion et les abonnements pouvant être mis à jour pour la réplication transactionnelle permettent tous deux la détection et la résolution des conflits, mais il est quand même préférable de n'insérer ou de ne mettre à jour une ligne donnée que sur un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="e2073-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="e2073-122">La réplication transactionnelle d'égal à égal ne permet pas la détection et la résolution des conflits, elle nécessite que les insertions et mises à jour soient partitionnées.</span><span class="sxs-lookup"><span data-stu-id="e2073-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="e2073-123">Une ligne a été insérée sur un abonné qui devrait être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2073-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="e2073-124">Les abonnés aux publications d'instantanés, ainsi que les abonnés au publications transactionnelles devraient être traités comme étant en lecture seule à moins d'utiliser des abonnements pouvant être mis à jour ou la réplication transactionnelle d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="e2073-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="e2073-125">Une table avec une colonne d'identité est utilisée, mais la colonne n'est par gérée de façon appropriée.</span><span class="sxs-lookup"><span data-stu-id="e2073-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="e2073-126">Dans la réplication de fusion, cette erreur peut également se produite lors d'une insertion dans une table système **MSmerge_contents**; l'erreur déclenchée est similaire à : impossible d'insérer une ligne de clé dupliquée dans l'objet « MSmerge_contents » d'index unique « ucl1SycContents ».</span><span class="sxs-lookup"><span data-stu-id="e2073-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2073-127">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e2073-127">User Action</span></span>  
 <span data-ttu-id="e2073-128">L'action requise dépend de la raison du déclenchement de l'erreur :</span><span class="sxs-lookup"><span data-stu-id="e2073-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="e2073-129">Les insertions et mises à jour sur une ligne se produisent sur plus d'un seul nœud.</span><span class="sxs-lookup"><span data-stu-id="e2073-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="e2073-130">Quel que soit le type de réplication utilisé, il est recommandé de partitionner les insertions et mises à jour chaque fois que cela est possible, car cela réduit le traitement nécessaire pour la détection et la résolution des conflits.</span><span class="sxs-lookup"><span data-stu-id="e2073-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="e2073-131">Pour la réplication transactionnelle d'égal à égal, le partitionnement d'insertions et de mises à jour est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e2073-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="e2073-132">Pour plus d'informations, consultez [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e2073-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="e2073-133">Une ligne a été insérée sur un abonné qui devrait être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2073-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="e2073-134">N'insérez pas ou ne mettez pas à jour de lignes sur l'Abonné à moins d'utiliser la réplication de fusion, la réplication transactionnelle avec abonnements pouvant être mis à jour ou la réplication transactionnelle d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="e2073-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="e2073-135">Une table avec une colonne d'identité est utilisée, mais la colonne n'est par gérée de façon appropriée.</span><span class="sxs-lookup"><span data-stu-id="e2073-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="e2073-136">Pour la réplication de fusion et la réplication transactionnelle avec abonnements pouvant être mis à jour, les colonnes d'identité doivent être gérées automatiquement par la réplication.</span><span class="sxs-lookup"><span data-stu-id="e2073-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="e2073-137">Pour la réplication transactionnelle d'égal à égal, elles doivent être gérées manuellement.</span><span class="sxs-lookup"><span data-stu-id="e2073-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="e2073-138">Pour plus d’informations, consultez [ Répliquer des colonnes d’identité](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e2073-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="e2073-139">L'erreur se produit pendant l'insertion dans une table système **MSmerge_contents**.</span><span class="sxs-lookup"><span data-stu-id="e2073-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="e2073-140">Cette erreur peut se produire en raison d'une valeur incorrecte pour la propriété du filtre de jointure **join_unique_key**.</span><span class="sxs-lookup"><span data-stu-id="e2073-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="e2073-141">Cette propriété doit être définie avec la valeur TRUE seulement si la colonne de jointure dans la table parente est unique.</span><span class="sxs-lookup"><span data-stu-id="e2073-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="e2073-142">Si la propriété est définie avec la valeur TRUE mais que la colonne n'est pas unique, cette erreur est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="e2073-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="e2073-143">Pour plus d'informations sur la définition de cette propriété, consultez [Définir et modifier un filtre de jointure entre des articles de fusion](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="e2073-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2073-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2073-144">See Also</span></span>  
 [<span data-ttu-id="e2073-145">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="e2073-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
