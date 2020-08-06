---
title: Réduire une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695691"
---
# <a name="shrink-a-database"></a><span data-ttu-id="4f40d-102">Réduire une base de données</span><span class="sxs-lookup"><span data-stu-id="4f40d-102">Shrink a Database</span></span>
  <span data-ttu-id="4f40d-103">Cette rubrique explique comment réduire une base de données au moyen de l'Explorateur d'objets dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f40d-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f40d-104">La réduction des fichiers de données permet de récupérer de l'espace en déplaçant des pages de données de la fin du fichier vers un espace inoccupé plus proche de l'avant du fichier.</span><span class="sxs-lookup"><span data-stu-id="4f40d-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="4f40d-105">Quand une quantité d'espace libre suffisante est créée à la fin du fichier, des pages de données à la fin du fichier peuvent être désallouées et retournées au système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4f40d-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f40d-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4f40d-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4f40d-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4f40d-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4f40d-108">La base de données ne peut pas être réduite à une taille inférieure à la taille minimale de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4f40d-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="4f40d-109">La taille minimale d'une base de données correspond à la taille spécifiée lors de sa création ou lors de la dernière définition de taille explicite lors d'une opération de modification de taille, notamment au moyen de DBCC SHRINKFILE.</span><span class="sxs-lookup"><span data-stu-id="4f40d-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="4f40d-110">Par exemple, la plus petite taille que pourrait avoir une base de données de 10 Mo initialement et de 100 Mo avant réduction, même si toutes les données qu'elle contient ont été supprimées, est de 10 Mo après réduction.</span><span class="sxs-lookup"><span data-stu-id="4f40d-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="4f40d-111">Vous ne pouvez pas réduire la taille d'une base de données en cours de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4f40d-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="4f40d-112">Inversement, vous ne pouvez pas sauvegarder une base de données alors qu'elle fait l'objet d'une opération de réduction.</span><span class="sxs-lookup"><span data-stu-id="4f40d-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="4f40d-113">DBCC SHRINKDATABASE échoue lorsqu'il rencontre un index columnstore optimisé en mémoire xVelocity.</span><span class="sxs-lookup"><span data-stu-id="4f40d-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="4f40d-114">Le travail effectué avant de rencontrer l'index columnstore réussit, de sorte que la base de données peut être plus petite.</span><span class="sxs-lookup"><span data-stu-id="4f40d-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="4f40d-115">Pour exécuter DBCC SHRINKDATABASE, désactivez tous les index columnstore avant d'exécuter DBCC SHRINKDATABASE, puis reconstruisez les index.</span><span class="sxs-lookup"><span data-stu-id="4f40d-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4f40d-116">Recommandations</span><span class="sxs-lookup"><span data-stu-id="4f40d-116">Recommendations</span></span>  
  
-   <span data-ttu-id="4f40d-117">Pour visualiser la quantité d'espace actuellement libre (non allouée) dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4f40d-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="4f40d-118">Pour plus d'informations, consultez [Afficher les informations sur l'espace occupé par les données et par le journal d'une base de données](display-data-and-log-space-information-for-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="4f40d-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="4f40d-119">Prenez en compte les informations suivantes lorsque vous envisagez de réduire une base de données :</span><span class="sxs-lookup"><span data-stu-id="4f40d-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="4f40d-120">Une opération de réduction de taille de fichier est plus efficace après l'exécution d'une opération qui crée une grande quantité d'espace inutilisé, telle qu'une troncature de table ou une suppression de table.</span><span class="sxs-lookup"><span data-stu-id="4f40d-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="4f40d-121">Un certain espace libre doit exister pour les opérations quotidiennes courantes pour la plupart des bases de données.</span><span class="sxs-lookup"><span data-stu-id="4f40d-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="4f40d-122">Si vous réduisez plusieurs fois la taille d'une base de données et que vous constatez que la taille augmente de nouveau, cela indique que l'espace qui a été réduit est nécessaire pour les opérations courantes.</span><span class="sxs-lookup"><span data-stu-id="4f40d-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="4f40d-123">Dans ce cas, la réduction de la taille de la base de données ne sert à rien.</span><span class="sxs-lookup"><span data-stu-id="4f40d-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="4f40d-124">Une opération de réduction ne conserve pas l'état de fragmentation des index de la base de données, et augmente généralement la fragmentation.</span><span class="sxs-lookup"><span data-stu-id="4f40d-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="4f40d-125">Il s'agit là d'une raison supplémentaire pour ne pas réduire la taille de la base de données de manière répétitive.</span><span class="sxs-lookup"><span data-stu-id="4f40d-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="4f40d-126">Sauf en cas de besoin précis, n'attribuez pas la valeur ON à l'option de base de données AUTO_SHRINK.</span><span class="sxs-lookup"><span data-stu-id="4f40d-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f40d-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4f40d-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f40d-128">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4f40d-128">Permissions</span></span>  
 <span data-ttu-id="4f40d-129">Nécessite l’appartenance au rôle de serveur fixe **sysadmin** ou au rôle de base de données fixe **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="4f40d-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f40d-130">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f40d-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="4f40d-131">Pour réduire une base de données</span><span class="sxs-lookup"><span data-stu-id="4f40d-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="4f40d-132">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="4f40d-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4f40d-133">Développez **Bases de données**, puis cliquez avec le bouton droit sur la base de données à réduire.</span><span class="sxs-lookup"><span data-stu-id="4f40d-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="4f40d-134">Pointez sur **Tâches**puis sur **Réduire**, puis cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="4f40d-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="4f40d-135">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="4f40d-135">**Database**</span></span>  
     <span data-ttu-id="4f40d-136">Affiche le nom de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4f40d-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="4f40d-137">**Espace actuellement alloué**</span><span class="sxs-lookup"><span data-stu-id="4f40d-137">**Current allocated space**</span></span>  
     <span data-ttu-id="4f40d-138">Affiche l'espace total, utilisé et non utilisé, pour la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4f40d-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="4f40d-139">**Espace libre disponible**</span><span class="sxs-lookup"><span data-stu-id="4f40d-139">**Available free space**</span></span>  
     <span data-ttu-id="4f40d-140">Affiche la totalité de l'espace disponible dans les fichiers de données et les fichiers journaux de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4f40d-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="4f40d-141">**Réorganiser les fichiers avant de libérer de l'espace inutilisé**</span><span class="sxs-lookup"><span data-stu-id="4f40d-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="4f40d-142">Activer cette option équivaut à exécuter DBCC SHRINKDATABASE en spécifiant une option de pourcentage cible.</span><span class="sxs-lookup"><span data-stu-id="4f40d-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="4f40d-143">Désactiver cette option équivaut à exécuter DBCC SHRINKDATABASE avec l'option TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="4f40d-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="4f40d-144">Par défaut, cette option n'est pas sélectionnée à l'ouverture de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4f40d-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="4f40d-145">Si cette option est sélectionnée, l'utilisateur doit spécifier une option de pourcentage cible.</span><span class="sxs-lookup"><span data-stu-id="4f40d-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="4f40d-146">**Espace libre maximal dans les fichiers après réduction**</span><span class="sxs-lookup"><span data-stu-id="4f40d-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="4f40d-147">Entrez le pourcentage maximal d'espace disponible à conserver dans les fichiers de base de données après la réduction de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4f40d-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="4f40d-148">Les valeurs autorisées sont comprises entre 0 et 99.</span><span class="sxs-lookup"><span data-stu-id="4f40d-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="4f40d-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f40d-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f40d-150">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f40d-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="4f40d-151">Pour réduire une base de données</span><span class="sxs-lookup"><span data-stu-id="4f40d-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="4f40d-152">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f40d-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f40d-153">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4f40d-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f40d-154">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4f40d-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4f40d-155">L'exemple suivant utilise [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) pour diminuer la taille des fichiers de données et journaux de la base de données utilisateur `UserDB` pour obtenir `10` % d'espace libre dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4f40d-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="4f40d-156">Suivi : Après avoir réduit une base de données</span><span class="sxs-lookup"><span data-stu-id="4f40d-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="4f40d-157">Les données qui sont déplacées pour réduire un fichier peuvent être dispersées à n'importe quel emplacement disponible dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="4f40d-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="4f40d-158">Cela provoque la fragmentation de l'index et peut ralentir les performances des requêtes qui recherchent une plage de l'index.</span><span class="sxs-lookup"><span data-stu-id="4f40d-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="4f40d-159">Pour éliminer la fragmentation, reconstruisez les index dans le fichier après réduction.</span><span class="sxs-lookup"><span data-stu-id="4f40d-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f40d-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f40d-160">See Also</span></span>  
 <span data-ttu-id="4f40d-161">[Réduire un fichier](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="4f40d-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="4f40d-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f40d-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="4f40d-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f40d-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="4f40d-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f40d-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="4f40d-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f40d-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="4f40d-166">Groupes de fichiers et fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="4f40d-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
