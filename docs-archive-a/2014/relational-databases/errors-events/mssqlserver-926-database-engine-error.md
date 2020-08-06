---
title: MSSQLSERVER_926 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604490"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="74667-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="74667-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="74667-103">Détails</span><span class="sxs-lookup"><span data-stu-id="74667-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74667-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="74667-104">Product Name</span></span>|<span data-ttu-id="74667-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74667-105">SQL Server</span></span>|  
|<span data-ttu-id="74667-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="74667-106">Event ID</span></span>|<span data-ttu-id="74667-107">926</span><span class="sxs-lookup"><span data-stu-id="74667-107">926</span></span>|  
|<span data-ttu-id="74667-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="74667-108">Event Source</span></span>|<span data-ttu-id="74667-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74667-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74667-110">Composant</span><span class="sxs-lookup"><span data-stu-id="74667-110">Component</span></span>|<span data-ttu-id="74667-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="74667-111">SQLEngine</span></span>|  
|<span data-ttu-id="74667-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="74667-112">Symbolic Name</span></span>|<span data-ttu-id="74667-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="74667-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="74667-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="74667-114">Message Text</span></span>|<span data-ttu-id="74667-115">La base de données '%.\*ls' ne peut pas être ouverte.</span><span class="sxs-lookup"><span data-stu-id="74667-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="74667-116">Elle a été marquée SUSPECT lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="74667-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="74667-117">Pour plus d’informations, consultez le journal des erreurs SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74667-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74667-118">Explication</span><span class="sxs-lookup"><span data-stu-id="74667-118">Explanation</span></span>  
 <span data-ttu-id="74667-119">La base de données est marquée comme étant suspecte, car le processus de récupération visant à amener la base de données dans un état transactionnel cohérent a échoué.</span><span class="sxs-lookup"><span data-stu-id="74667-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="74667-120">Cela peut se produire durant les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="74667-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="74667-121">Démarrage d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74667-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="74667-122">Attachement d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="74667-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="74667-123">Utilisation de la base de données RESTORE ou de procédures RESTORE LOG.</span><span class="sxs-lookup"><span data-stu-id="74667-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74667-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="74667-124">User Action</span></span>  
 <span data-ttu-id="74667-125">Inspectez le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et déterminez la cause de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="74667-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="74667-126">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été redémarré depuis l'échec de la récupération, regardez dans les journaux des erreurs précédents de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin de voir pourquoi la récupération a échoué.</span><span class="sxs-lookup"><span data-stu-id="74667-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="74667-127">Si la récupération a échoué en raison d'une erreur d'E/S permanente, d'une page endommagée ou d'un autre problème matériel, résolvez le problème matériel sous-jacent et restaurez la base de données en utilisant une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="74667-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="74667-128">Si aucune sauvegarde n'est disponible, utilisez les options de réparation de DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="74667-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="74667-129">Si vous n'arrivez pas à résoudre ce problème, contactez votre fournisseur d'assistance principal.</span><span class="sxs-lookup"><span data-stu-id="74667-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="74667-130">Fournissez-lui le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin qu'il puisse l'examiner.</span><span class="sxs-lookup"><span data-stu-id="74667-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74667-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74667-131">See Also</span></span>  
 <span data-ttu-id="74667-132">[Sauvegarde et restauration des bases de données SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="74667-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="74667-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74667-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="74667-134">[Bases de donnéessys.sys&#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74667-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="74667-135">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74667-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
