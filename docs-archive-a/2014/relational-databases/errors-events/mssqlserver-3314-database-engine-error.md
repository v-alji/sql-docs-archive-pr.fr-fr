---
title: MSSQLSERVER_3314 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612861"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="7b6ef-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="7b6ef-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="7b6ef-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7b6ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b6ef-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7b6ef-104">Product Name</span></span>|<span data-ttu-id="7b6ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b6ef-105">SQL Server</span></span>|  
|<span data-ttu-id="7b6ef-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7b6ef-106">Event ID</span></span>|<span data-ttu-id="7b6ef-107">3314</span><span class="sxs-lookup"><span data-stu-id="7b6ef-107">3314</span></span>|  
|<span data-ttu-id="7b6ef-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7b6ef-108">Event Source</span></span>|<span data-ttu-id="7b6ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b6ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b6ef-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7b6ef-110">Component</span></span>|<span data-ttu-id="7b6ef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b6ef-111">SQLEngine</span></span>|  
|<span data-ttu-id="7b6ef-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7b6ef-112">Symbolic Name</span></span>|<span data-ttu-id="7b6ef-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="7b6ef-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="7b6ef-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7b6ef-114">Message Text</span></span>|<span data-ttu-id="7b6ef-115">Une erreur s'est produite sur l'enregistrement de journal % S_LSN en annulant une opération journalisée dans la base de données '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="7b6ef-116">En général, l'erreur spécifique est déjà journalisée dans le service de journal d'événements Windows.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="7b6ef-117">Restaurez la base de données ou le fichier à partir d'une sauvegarde, ou réparez la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b6ef-118">Explication</span><span class="sxs-lookup"><span data-stu-id="7b6ef-118">Explanation</span></span>  
 <span data-ttu-id="7b6ef-119">Il s'agit d'une erreur de cumul pour la récupération d'une annulation.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="7b6ef-120">Cette erreur a placé la base de données dans l'état SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="7b6ef-121">Le groupe de fichiers primaire et éventuellement d'autres groupes de fichiers sont suspects et peut-être endommagés.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="7b6ef-122">La base de données ne peut pas être récupérée au démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et n'est par conséquent pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="7b6ef-123">Une action est requise de la part de l'utilisateur pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="7b6ef-124">Notez que si cette erreur se produit pour **tempdb**, l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'arrête.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b6ef-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7b6ef-125">User Action</span></span>  
 <span data-ttu-id="7b6ef-126">Cette erreur peut être provoquée par une situation temporaire qui existait sur le système lors d'une tentative donnée de démarrer l'instance du serveur ou de récupérer une base de données.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="7b6ef-127">Cette erreur peut également être provoquée par un échec permanent qui se produit à chaque tentative de démarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="7b6ef-128">Pour plus d'informations sur la cause, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l'échec spécifique.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="7b6ef-129">Pour plus d'informations sur la cause de l'occurrence de l'erreur 3314, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l'échec spécifique.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="7b6ef-130">L'action utilisateur appropriée varie selon que les informations dans le Journal des événements Windows indiquent que l'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été provoquée par une condition transitoire ou un échec permanent.</span><span class="sxs-lookup"><span data-stu-id="7b6ef-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="7b6ef-131">Pour plus d'informations sur les actions utilisateur requises pour le dépannage de l'erreur 3314, consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b6ef-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6ef-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b6ef-132">See Also</span></span>  
 <span data-ttu-id="7b6ef-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b6ef-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="7b6ef-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b6ef-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="7b6ef-135">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="7b6ef-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="7b6ef-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="7b6ef-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="7b6ef-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b6ef-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
