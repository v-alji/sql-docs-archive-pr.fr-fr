---
title: MSSQL_ENG003165 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1702588ba6ac1beeb33b87a7afc7fc330271559
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599929"
---
# <a name="mssql_eng003165"></a><span data-ttu-id="330ee-102">MSSQL_ENG003165</span><span class="sxs-lookup"><span data-stu-id="330ee-102">MSSQL_ENG003165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="330ee-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="330ee-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="330ee-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="330ee-104">Product Name</span></span>|<span data-ttu-id="330ee-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="330ee-105">SQL Server</span></span>|  
|<span data-ttu-id="330ee-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="330ee-106">Event ID</span></span>|<span data-ttu-id="330ee-107">3165</span><span class="sxs-lookup"><span data-stu-id="330ee-107">3165</span></span>|  
|<span data-ttu-id="330ee-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="330ee-108">Event Source</span></span>|<span data-ttu-id="330ee-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="330ee-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="330ee-110">Composant</span><span class="sxs-lookup"><span data-stu-id="330ee-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="330ee-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="330ee-111">Symbolic Name</span></span>||  
|<span data-ttu-id="330ee-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="330ee-112">Message Text</span></span>|<span data-ttu-id="330ee-113">La base de données « %ls » a été restaurée, cependant, une erreur a été rencontrée pendant la restauration/suppression de la réplication.</span><span class="sxs-lookup"><span data-stu-id="330ee-113">Database '%ls' was restored; however, an error was encountered while replication was being restored/removed.</span></span> <span data-ttu-id="330ee-114">La base de données est restée hors ligne.</span><span class="sxs-lookup"><span data-stu-id="330ee-114">The database has been left offline.</span></span> <span data-ttu-id="330ee-115">Consultez la rubrique MSSQL_ENG003165 dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="330ee-115">See the topic MSSQL_ENG003165 in SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="330ee-116">Explication</span><span class="sxs-lookup"><span data-stu-id="330ee-116">Explanation</span></span>  
 <span data-ttu-id="330ee-117">Cette erreur est déclenchée si un problème se produit lors de la restauration d'une sauvegarde d'un base de données répliquée :</span><span class="sxs-lookup"><span data-stu-id="330ee-117">This error is raised if a problem occurs restoring a backup of a replicated database:</span></span>  
  
-   <span data-ttu-id="330ee-118">Si la sauvegarde est restaurée sur la même base de données et sur le même serveur sur laquelle elle a été effectuée, l'erreur indique que les paramètres de la réplication n'ont pas pu être restaurés correctement.</span><span class="sxs-lookup"><span data-stu-id="330ee-118">If the backup is being restored to the same database and server on which it was taken, the error indicates that replication settings could not be restored properly.</span></span>  
  
-   <span data-ttu-id="330ee-119">Si la sauvegarde est restaurée sur une base de données ou un serveur différent, l'erreur indique que les paramètres de la réplication n'ont pas pu être supprimés correctement (par défaut, les paramètres de la réplication sont supprimés si la base de données ou le serveur est différent).</span><span class="sxs-lookup"><span data-stu-id="330ee-119">If the backup is being restored to a different database or server, the error indicates that replication settings could not be removed properly (by default, replication settings are removed if the database or server is different).</span></span>  
  
 <span data-ttu-id="330ee-120">L'erreur résulte probablement d'une incompatibilité entre l'état de la base de données restaurée et une ou plusieurs bases de données système contenant des métadonnées de réplication : **msdb**, **master**, ou la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="330ee-120">The error is probably the result of a mismatch between the state of the restored database and one or more system databases that contain replication metadata: **msdb**, **master**, or the distribution database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="330ee-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="330ee-121">User Action</span></span>  
 <span data-ttu-id="330ee-122">Pour résoudre ce problème :</span><span class="sxs-lookup"><span data-stu-id="330ee-122">To resolve this issue:</span></span>  
  
1.  <span data-ttu-id="330ee-123">Exécutez ALTER DATABASE pour mettre en ligne la base de données, par exemple : `ALTER DATABASE AdventureWorks SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="330ee-123">Execute ALTER DATABASE to bring the database online; for example: `ALTER DATABASE AdventureWorks SET ONLINE`.</span></span> <span data-ttu-id="330ee-124">Pour plus d’informations, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="330ee-124">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span> <span data-ttu-id="330ee-125">Si vous souhaitez conserver les paramètres de la réplication, passez à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="330ee-125">If you want to preserve replication settings, go to step 2.</span></span> <span data-ttu-id="330ee-126">Sinon, passez à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="330ee-126">If not, go to step 3.</span></span>  
  
2.  <span data-ttu-id="330ee-127">Exécutez [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="330ee-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span></span> <span data-ttu-id="330ee-128">Si cette procédure stockée s'exécute avec succès, la restauration est terminée.</span><span class="sxs-lookup"><span data-stu-id="330ee-128">If this stored procedure executes successfully, the restore is complete.</span></span> <span data-ttu-id="330ee-129">Dans le cas contraire, passez à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="330ee-129">If it does not execute successfully, go to step 3.</span></span>  
  
3.  <span data-ttu-id="330ee-130">Exécutez [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) pour supprimer tous les paramètres de la réplication.</span><span class="sxs-lookup"><span data-stu-id="330ee-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove all replication settings.</span></span>  
  
     <span data-ttu-id="330ee-131">Reconfigurez la réplication si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="330ee-131">Reconfigure replication if necessary.</span></span> <span data-ttu-id="330ee-132">Si la topologie de réplication a fait l'objet d'un script comme il a été recommandé, utilisez des scripts pour reconfigurer la topologie.</span><span class="sxs-lookup"><span data-stu-id="330ee-132">If you have scripted the replication topology as recommended, use scripts to reconfigure the topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330ee-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="330ee-133">See Also</span></span>  
 <span data-ttu-id="330ee-134">[Sauvegarde et restauration des bases de données SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="330ee-134">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="330ee-135">[Sauvegarder et restaurer des bases de données répliquées](administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="330ee-135">[Back Up and Restore Replicated Databases](administration/back-up-and-restore-replicated-databases.md) </span></span>  
 [<span data-ttu-id="330ee-136">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="330ee-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
