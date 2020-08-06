---
title: Déplacer une base de données à l’aide de la méthode de détachement et d’attachement (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614619"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="00828-102">Déplacer une base de données à l'aide de la méthode de détachement et d'attachement (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="00828-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="00828-103">Cette rubrique explique comment déplacer une base de données détachée vers un autre emplacement puis la rattacher à la même instance de serveur ou à une instance différente dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00828-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="00828-104">Toutefois, nous vous recommandons de déplacer les bases de données à l'aide de la procédure de déplacement planifié ALTER DATABASE, plutôt qu'à l'aide de la méthode de détachement et d'attachement.</span><span class="sxs-lookup"><span data-stu-id="00828-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="00828-105">Pour plus d’informations, consultez [Déplacer des bases de données utilisateur](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="00828-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="00828-106">Nous vous recommandons de ne pas attacher ni restaurer de bases de données provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="00828-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="00828-107">Ces bases de données peuvent contenir du code malveillant susceptible d'exécuter du code [!INCLUDE[tsql](../../includes/tsql-md.md)] indésirable ou de provoquer des erreurs en modifiant le schéma ou la structure physique des bases de données.</span><span class="sxs-lookup"><span data-stu-id="00828-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="00828-108">Avant d’utiliser une base de données issue d’une source inconnue ou non approuvée, exécutez [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données sur un serveur autre qu’un serveur de production et examinez également le code, notamment les procédures stockées ou le code défini par l’utilisateur, de la base de données.</span><span class="sxs-lookup"><span data-stu-id="00828-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="00828-109">Procédure</span><span class="sxs-lookup"><span data-stu-id="00828-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="00828-110">Pour déplacer une base de données à l'aide des opérations de détachement et d'attachement</span><span class="sxs-lookup"><span data-stu-id="00828-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="00828-111">Détachez la base de données.</span><span class="sxs-lookup"><span data-stu-id="00828-111">Detach the database.</span></span> <span data-ttu-id="00828-112">Pour plus d’informations, consultez [Détacher une base de données](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="00828-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="00828-113">Dans une fenêtre de l'Explorateur Windows ou de l'invite de commandes Windows, déplacez les fichiers journaux et les fichiers de base de données détachés à l'emplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="00828-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00828-114">Pour déplacer une base de données composée d'un seul fichier, vous pouvez utiliser la messagerie électronique si la taille du fichier le permet.</span><span class="sxs-lookup"><span data-stu-id="00828-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="00828-115">Vous devez déplacer les fichiers journaux, même si vous envisagez d'en créer de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="00828-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="00828-116">Dans certains cas, le rattachement d'une base de données nécessite ses fichiers journaux existants.</span><span class="sxs-lookup"><span data-stu-id="00828-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="00828-117">Par conséquent, conservez toujours tous les fichiers journaux détachés jusqu'à ce que la base de données ait été attachée avec succès sans eux.</span><span class="sxs-lookup"><span data-stu-id="00828-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00828-118">Si vous tentez d'attacher la base de données sans spécifier le fichier journal, l'opération attach recherche le fichier journal à son emplacement d'origine.</span><span class="sxs-lookup"><span data-stu-id="00828-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="00828-119">Si une copie du journal existe toujours à l'emplacement d'origine, elle est attachée.</span><span class="sxs-lookup"><span data-stu-id="00828-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="00828-120">Pour éviter d'utiliser le fichier journal d'origine, spécifiez le chemin d'accès au nouveau fichier journal ou supprimez la copie d'origine du fichier journal (après l'avoir copiée au nouvel emplacement).</span><span class="sxs-lookup"><span data-stu-id="00828-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="00828-121">Attachez les fichiers copiés.</span><span class="sxs-lookup"><span data-stu-id="00828-121">Attach the copied files.</span></span> <span data-ttu-id="00828-122">Pour plus d’informations, consultez [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="00828-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00828-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="00828-123">Example</span></span>  
 <span data-ttu-id="00828-124">L’exemple suivant crée une copie des [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instructions qui sont exécutées dans une fenêtre de l’éditeur de requête connectée à l’instance de serveur à laquelle est attaché.</span><span class="sxs-lookup"><span data-stu-id="00828-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="00828-125">Détachez les [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instructions :</span><span class="sxs-lookup"><span data-stu-id="00828-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="00828-126">À l'aide de la méthode de votre choix, copiez les fichiers de base de données dventureWorks208R2_Data.mdf et AdventureWorks208R2_log) vers : C:\MySQLServer\AdventureWorks208R2_Data.mdf et C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectivement.</span><span class="sxs-lookup"><span data-stu-id="00828-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="00828-127">Dans le cas d'une base de données de production, placez la base de données et le journal des transactions sur des disques distincts.</span><span class="sxs-lookup"><span data-stu-id="00828-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="00828-128">Pour copier des fichiers via le réseau sur le disque d'un ordinateur distant, utilisez le nom UNC (Universal Naming Convention) de l'emplacement distant.</span><span class="sxs-lookup"><span data-stu-id="00828-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="00828-129">Un nom UNC se présente sous la forme **\\\\** _Servername_ **\\** _Sharename_ **\\** _Path_ **\\** _Filename_.</span><span class="sxs-lookup"><span data-stu-id="00828-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="00828-130">Comme lors de l'écriture de fichiers sur le disque dur local, les autorisations appropriées nécessaires à la lecture et à l'écriture d'un fichier sur le disque distant doivent être accordées au compte d'utilisateur utilisé par l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00828-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="00828-131">Attachez la base de données déplacée et si vous le souhaitez, son journal, en exécutant les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="00828-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="00828-132">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], une base de données nouvellement attachée n'est pas immédiatement visible dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="00828-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="00828-133">Pour visualiser la base de données, dans l'Explorateur d'objets, cliquez sur **Affichage** puis sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="00828-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="00828-134">Si le nœud **Bases de données** est développé dans l'Explorateur d'objets, la base de données récemment attachée apparaît dans la liste des bases de données.</span><span class="sxs-lookup"><span data-stu-id="00828-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00828-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00828-135">See Also</span></span>  
 [<span data-ttu-id="00828-136">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00828-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
