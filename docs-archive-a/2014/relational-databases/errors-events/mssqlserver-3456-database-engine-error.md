---
title: MSSQLSERVER_3456 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701244"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="bf1c1-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="bf1c1-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="bf1c1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bf1c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf1c1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bf1c1-104">Product Name</span></span>|<span data-ttu-id="bf1c1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf1c1-105">SQL Server</span></span>|  
|<span data-ttu-id="bf1c1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bf1c1-106">Event ID</span></span>|<span data-ttu-id="bf1c1-107">3456</span><span class="sxs-lookup"><span data-stu-id="bf1c1-107">3456</span></span>|  
|<span data-ttu-id="bf1c1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bf1c1-108">Event Source</span></span>|<span data-ttu-id="bf1c1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bf1c1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bf1c1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bf1c1-110">Component</span></span>|<span data-ttu-id="bf1c1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bf1c1-111">SQLEngine</span></span>|  
|<span data-ttu-id="bf1c1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bf1c1-112">Symbolic Name</span></span>|<span data-ttu-id="bf1c1-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="bf1c1-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="bf1c1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bf1c1-114">Message Text</span></span>|<span data-ttu-id="bf1c1-115">Impossible de rétablir l'enregistrement du journal %S_LSN, pour l'ID de transaction %S_XID, à la page %S_PGID, base de données '%.\*ls' (ID de base de données %d).</span><span class="sxs-lookup"><span data-stu-id="bf1c1-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="bf1c1-116">Page : LSN = %S_LSN, type = %ld.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="bf1c1-117">Log : OpCode = %ld, contexte %ld, PrevPageLSN : %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="bf1c1-118">Effectuez une restauration à partir d'une sauvegarde de la base de données ou réparez la base de données.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf1c1-119">Explication</span><span class="sxs-lookup"><span data-stu-id="bf1c1-119">Explanation</span></span>  
 <span data-ttu-id="bf1c1-120">L'opération de restauration n'a pas pu rétablir le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="bf1c1-121">Cette erreur a placé la base de données dans l'état SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="bf1c1-122">Le groupe de fichiers primaire et éventuellement d'autres groupes de fichiers sont suspects et peut-être endommagés.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="bf1c1-123">La base de données ne peut pas être récupérée au démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et n'est par conséquent pas disponible.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="bf1c1-124">Une action est requise de la part de l'utilisateur pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="bf1c1-125">Notez que si cette erreur se produit pour **tempdb**, l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'arrête.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf1c1-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bf1c1-126">User Action</span></span>  
 <span data-ttu-id="bf1c1-127">Cette erreur peut être provoquée par une situation temporaire qui existait sur le système lors d'une tentative donnée de démarrer l'instance du serveur ou de récupérer une base de données.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="bf1c1-128">Cette erreur peut également être provoquée par un échec permanent qui se produit à chaque tentative de démarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="bf1c1-129">Pour plus d'informations sur la cause, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l'échec spécifique.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="bf1c1-130">Pour plus d’informations sur la cause de l’occurrence de l’erreur 3456, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l’échec spécifique.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="bf1c1-131">L'action utilisateur appropriée varie selon que les informations dans le Journal des événements Windows indiquent que l'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été provoquée par une condition transitoire ou un échec permanent.</span><span class="sxs-lookup"><span data-stu-id="bf1c1-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="bf1c1-132">Pour plus d’informations sur les actions utilisateur requises pour le dépannage de l’erreur 3456, consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf1c1-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1c1-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf1c1-133">See Also</span></span>  
 <span data-ttu-id="bf1c1-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf1c1-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="bf1c1-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf1c1-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="bf1c1-136">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="bf1c1-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="bf1c1-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="bf1c1-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="bf1c1-138">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bf1c1-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
