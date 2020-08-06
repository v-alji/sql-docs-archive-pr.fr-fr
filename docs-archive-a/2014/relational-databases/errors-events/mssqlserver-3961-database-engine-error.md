---
title: MSSQLSERVER_3961 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613470"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="6cad3-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="6cad3-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="6cad3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="6cad3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cad3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6cad3-104">Product Name</span></span>|<span data-ttu-id="6cad3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6cad3-105">SQL Server</span></span>|  
|<span data-ttu-id="6cad3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="6cad3-106">Event ID</span></span>|<span data-ttu-id="6cad3-107">3961</span><span class="sxs-lookup"><span data-stu-id="6cad3-107">3961</span></span>|  
|<span data-ttu-id="6cad3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="6cad3-108">Event Source</span></span>|<span data-ttu-id="6cad3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6cad3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6cad3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="6cad3-110">Component</span></span>|<span data-ttu-id="6cad3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6cad3-111">SQLEngine</span></span>|  
|<span data-ttu-id="6cad3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="6cad3-112">Symbolic Name</span></span>|<span data-ttu-id="6cad3-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="6cad3-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="6cad3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="6cad3-114">Message Text</span></span>|<span data-ttu-id="6cad3-115">La transaction d'isolement d'instantané a échoué dans la base de données '%.\*ls' car l'objet auquel l'instruction a eu accès a été modifié par une instruction DDL dans une autre transaction simultanée depuis le début de cette transaction.</span><span class="sxs-lookup"><span data-stu-id="6cad3-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="6cad3-116">Elle est rejetée, car les métadonnées ne font pas l’objet d’une gestion des versions.</span><span class="sxs-lookup"><span data-stu-id="6cad3-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="6cad3-117">Une mise à jour simultanée des métadonnées peut provoquer des incohérences si elle est combinée avec un isolement d’instantané.</span><span class="sxs-lookup"><span data-stu-id="6cad3-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6cad3-118">Explication</span><span class="sxs-lookup"><span data-stu-id="6cad3-118">Explanation</span></span>  
 <span data-ttu-id="6cad3-119">Cette erreur peut se produire si vous interrogez des métadonnées avec isolement d’instantané et s’il existe une instruction DDL simultanée qui met à jour les métadonnées faisant l’objet d’un accès avec isolement d’instantané.</span><span class="sxs-lookup"><span data-stu-id="6cad3-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6cad3-120">ne prend pas en charge le contrôle de version des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="6cad3-120">does not support versioning of metadata.</span></span> <span data-ttu-id="6cad3-121">Pour cette raison, des restrictions existent sur les opérations DDL qui peuvent être effectuées dans une transaction explicite exécutée avec isolement d’instantané.</span><span class="sxs-lookup"><span data-stu-id="6cad3-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="6cad3-122">Par définition, une transaction implicite est une instruction unique qui permet d’appliquer la sémantique de l’isolement d’instantané même avec des instructions DDL.</span><span class="sxs-lookup"><span data-stu-id="6cad3-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="6cad3-123">Les instructions DDL suivantes ne sont pas autorisées en isolement d’instantanée après une instruction BEGIN TRANSACTION : ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME ou toute instruction DDL CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="6cad3-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="6cad3-124">Ces instructions sont autorisées quand vous utilisez l’isolement d’instantané au sein de transactions implicites.</span><span class="sxs-lookup"><span data-stu-id="6cad3-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="6cad3-125">Par définition, une transaction implicite est une instruction unique qui permet d’appliquer la sémantique de l’isolement d’instantané même avec des instructions DDL.</span><span class="sxs-lookup"><span data-stu-id="6cad3-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cad3-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6cad3-126">User Action</span></span>  
 <span data-ttu-id="6cad3-127">Modifiez le niveau d'isolement de capture instantanée en le remplaçant par un niveau d'isolement qui n'est pas de capture instantanée, tel que la lecture validée, avant l'interrogation des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="6cad3-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
