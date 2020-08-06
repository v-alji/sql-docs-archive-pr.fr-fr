---
title: MSSQLSERVER_17065 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17065 (Database Engine error)
ms.assetid: 63c2ba5a-be34-461e-bee1-03c25b396cd2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47aebfa29b60a1c2ae50c6699946312996d26e6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612897"
---
# <a name="mssqlserver_17065"></a><span data-ttu-id="c1368-102">MSSQLSERVER_17065</span><span class="sxs-lookup"><span data-stu-id="c1368-102">MSSQLSERVER_17065</span></span>
    
## <a name="details"></a><span data-ttu-id="c1368-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c1368-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1368-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c1368-104">Product Name</span></span>|<span data-ttu-id="c1368-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1368-105">SQL Server</span></span>|  
|<span data-ttu-id="c1368-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c1368-106">Event ID</span></span>|<span data-ttu-id="c1368-107">17065</span><span class="sxs-lookup"><span data-stu-id="c1368-107">17065</span></span>|  
|<span data-ttu-id="c1368-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c1368-108">Event Source</span></span>|<span data-ttu-id="c1368-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c1368-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c1368-110">Composant</span><span class="sxs-lookup"><span data-stu-id="c1368-110">Component</span></span>|<span data-ttu-id="c1368-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c1368-111">SQLEngine</span></span>|  
|<span data-ttu-id="c1368-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c1368-112">Symbolic Name</span></span>|<span data-ttu-id="c1368-113">SQLASSERT_BOTH</span><span class="sxs-lookup"><span data-stu-id="c1368-113">SQLASSERT_BOTH</span></span>|  
|<span data-ttu-id="c1368-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c1368-114">Message Text</span></span>|<span data-ttu-id="c1368-115">Assertion SQL Server : Fichier : \<%s>, ligne = %d Échec d’assertion = '%s' %s.</span><span class="sxs-lookup"><span data-stu-id="c1368-115">SQL Server Assertion: File: \<%s>, line = %d Failed Assertion = '%s' %s.</span></span> <span data-ttu-id="c1368-116">Cette erreur est éventuellement liée à un délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="c1368-116">This error may be timing-related.</span></span> <span data-ttu-id="c1368-117">Si l'erreur persiste après une nouvelle exécution de l'instruction, utilisez DBCC CHECKDB pour vérifier l'intégrité structurelle de la base de données ou redémarrez le serveur pour vous assurer que les structures de données en mémoire ne sont pas corrompues.</span><span class="sxs-lookup"><span data-stu-id="c1368-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c1368-118">Explication</span><span class="sxs-lookup"><span data-stu-id="c1368-118">Explanation</span></span>  
 <span data-ttu-id="c1368-119">Cette erreur peut être provoquée par des erreurs temporaires liées à un délai d'attente ou par une corruption des données en mémoire ou sur disque.</span><span class="sxs-lookup"><span data-stu-id="c1368-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1368-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c1368-120">User Action</span></span>  
 <span data-ttu-id="c1368-121">Réexécutez l'instruction qui a provoqué le déclenchement de l'exception.</span><span class="sxs-lookup"><span data-stu-id="c1368-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="c1368-122">Si l'erreur a été provoquée par un événement lié à un délai d'attente, elle peut ne pas se reproduire.</span><span class="sxs-lookup"><span data-stu-id="c1368-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="c1368-123">Si le problème persiste, exécutez DBCC CHECKDB pour rechercher une corruption sur disque.</span><span class="sxs-lookup"><span data-stu-id="c1368-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="c1368-124">Redémarrez le serveur pour vérifier que les structures de données en mémoire ne sont pas endommagées.</span><span class="sxs-lookup"><span data-stu-id="c1368-124">Restart the server to ensure the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1368-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1368-125">See Also</span></span>  
 [<span data-ttu-id="c1368-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c1368-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
