---
title: Créer un instantané de base de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709584"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="dfaf7-102">Créer un instantané de base de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="dfaf7-103">Pour créer un instantané de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez impérativement utiliser [!INCLUDE[tsql](../../includes/tsql-md.md)]+.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="dfaf7-104">ne prend pas en charge la création d'instantanés de base de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="dfaf7-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dfaf7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dfaf7-106">Composants requis</span><span class="sxs-lookup"><span data-stu-id="dfaf7-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="dfaf7-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dfaf7-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="dfaf7-108">Bonne pratique : Dénomination des instantanés de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="dfaf7-109">**Pour créer un instantané de base de données, avec :**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dfaf7-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dfaf7-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dfaf7-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dfaf7-111">Prerequisites</span></span>  
 <span data-ttu-id="dfaf7-112">La base de données source, qui peut utiliser n'importe quel mode de récupération, doit respecter les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="dfaf7-113">L’instance de serveur doit exécuter une édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui prend en charge l’instantané de base de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="dfaf7-114">Pour plus d’informations sur la prise en charge des instantanés de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="dfaf7-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="dfaf7-115">La base de données source doit être en ligne, à moins que la base de données soit une base de données miroir au sein d'une session de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="dfaf7-116">Pour créer un instantané de base de données dans une base de données miroir, la base de données doit être dans l’[état de mise en miroir](../../database-engine/database-mirroring/mirroring-states-sql-server.md)synchronisé.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="dfaf7-117">La base de données source ne peut pas être configurée en tant que base de données partagée évolutive.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dfaf7-118">Pour plus d’informations sur d’autres considérations importantes, consultez [Instantanés de base de données &#40;SQL Server&#41;](database-snapshots-sql-server.md)+.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="dfaf7-119">Recommandations</span><span class="sxs-lookup"><span data-stu-id="dfaf7-119">Recommendations</span></span>  
 <span data-ttu-id="dfaf7-120">Cette section présente les recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="dfaf7-121">Bonne pratique : Dénomination des instantanés de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="dfaf7-122">Bonne pratique : Limitation du nombre d’instantanés de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="dfaf7-123">Bonne pratique : Connexions clientes à un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="dfaf7-124">Bonne pratique : Dénomination des instantanés de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="dfaf7-125">Avant de créer des instantanés, il est important de déterminer comment ils seront nommés.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="dfaf7-126">Chaque instantané de base de données nécessite un nom de base de données unique.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="dfaf7-127">Pour faciliter l'administration, le nom de l'instantané peut intégrer des informations identifiant la base de données, telles que :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="dfaf7-128">Nom de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="dfaf7-129">Une indication que le nouveau nom désigne un instantané.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="dfaf7-130">La date et l'heure de création de l'instantané, un numéro de séquence ou d'autres informations pour distinguer les instantanés consécutifs sur une base de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="dfaf7-131">Par exemple, envisageons une série d'instantanés de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dfaf7-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="dfaf7-132">Trois instantanés quotidiens sont créés à des intervalles de 6 heures, entre 6h00</span><span class="sxs-lookup"><span data-stu-id="dfaf7-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="dfaf7-133">et 18h00.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="dfaf7-134">Chaque instantané quotidien est conservé pendant 24 heures avant d'être supprimé et remplacé par un nouvel instantané du même nom.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="dfaf7-135">Notez que chaque instantané indique l'heure, mais non le jour :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="dfaf7-136">Si l'heure de création de ces instantanés quotidiens varie selon les jours, une convention de dénomination moins précise peut être préférable, par exemple :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="dfaf7-137">Bonne pratique : Limitation du nombre d’instantanés de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="dfaf7-138">La création d'une série d'instantanés dans le temps fournit des instantanés consécutifs de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="dfaf7-139">Chaque instantané est conservé jusqu'à ce qu'il soit explicitement supprimé.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="dfaf7-140">Chaque instantané continuant à grandir au fur et à mesure que les pages d'origine sont mises à jour, vous voudrez peut-être conserver de l'espace disque en supprimant un instantané plus ancien après en avoir créé un nouveau.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfaf7-141">Si vous souhaitez revenir à un instantané de base de données, vous devez supprimer tous les autres instantanés de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="dfaf7-142">Bonne pratique : Connexions clientes à un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="dfaf7-143">Pour utiliser un instantané de base de données, les clients ont besoin de savoir où il se trouve.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="dfaf7-144">Les utilisateurs peuvent lire un instantané de base de données pendant qu'un autre instantané est créé ou supprimé.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="dfaf7-145">Cependant, lorsque vous substituez un nouvel instantané de base de données à un instantané existant, vous devez rediriger les clients vers le nouvel instantané.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="dfaf7-146">Les utilisateurs peuvent se connecter manuellement à un instantané de base de données à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfaf7-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="dfaf7-147">Cependant, pour prendre en charge un environnement de production, vous devez créer une solution de programmation qui dirige de façon transparente les clients écrivant des rapports vers le dernier instantané de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dfaf7-148">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dfaf7-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dfaf7-149">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dfaf7-149">Permissions</span></span>  
 <span data-ttu-id="dfaf7-150">Tout utilisateur ayant la possibilité de créer une base de données peut également créer un instantané de base de données. Toutefois, pour créer un instantané d’une base de données miroir, vous devez être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="dfaf7-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dfaf7-151">Comment créer un instantané de base de données (en utilisant Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="dfaf7-152">**Pour créer un instantané de base de données**</span><span class="sxs-lookup"><span data-stu-id="dfaf7-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfaf7-153">Pour obtenir un exemple de cette procédure, consultez [Exemples (Transact-SQL)](#TsqlExample)plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="dfaf7-154">En vous basant sur la taille actuelle de la base de données source, vérifiez que votre disque dispose de suffisamment d'espace pour en accueillir un instantané.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="dfaf7-155">La taille maximale d'un instantané est la taille de la base de données source au moment où l'instantané est créé.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="dfaf7-156">Pour plus d’informations, consultez [Afficher la taille du fichier partiellement alloué d’un instantané de base de données &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dfaf7-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="dfaf7-157">Exécutez une instruction CREATE DATABASE sur les fichiers en utilisant la clause AS SNAPSHOT OF.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="dfaf7-158">Pour créer un instantané, vous devez spécifier le nom logique de chaque fichier de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="dfaf7-159">La syntaxe est la suivante :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="dfaf7-160">CREATE DATABASE *nom_capture_instantanée_base_de_données*</span><span class="sxs-lookup"><span data-stu-id="dfaf7-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="dfaf7-161">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="dfaf7-161">ON</span></span>  
  
     <span data-ttu-id="dfaf7-162">(</span><span class="sxs-lookup"><span data-stu-id="dfaf7-162">(</span></span>  
  
     <span data-ttu-id="dfaf7-163">NAME =*nom_fichier_logique*,</span><span class="sxs-lookup"><span data-stu-id="dfaf7-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="dfaf7-164">FILENAME =’*nom_fichier_se*’</span><span class="sxs-lookup"><span data-stu-id="dfaf7-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="dfaf7-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="dfaf7-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="dfaf7-166">AS SNAPSHOT OF *nom_base_de_données_source*</span><span class="sxs-lookup"><span data-stu-id="dfaf7-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="dfaf7-167">[;]</span><span class="sxs-lookup"><span data-stu-id="dfaf7-167">[;]</span></span>  
  
     <span data-ttu-id="dfaf7-168">Où *nom_base_de_données_\*\*source* représente la base de données source, *nom_fichier_logique* le nom logique utilisé dans SQL Server pour référencer le fichier, *nom_fichier_se* le chemin et le nom de fichier utilisés par le système d’exploitation quand vous créez le fichier, et *nom_capture_instantanée_base_de_données* le nom de la capture instantanée à laquelle vous souhaitez restaurer la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="dfaf7-169">Pour obtenir une description complète de cette syntaxe, consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)+.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfaf7-170">Lorsque vous créez un instantané de base de données, les fichiers journaux, les fichiers hors connexion, les fichiers de restauration et les anciens fichiers ne sont pas autorisés dans l'instruction CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="dfaf7-171">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfaf7-172">L'extension `.ss` utilisée dans les exemples est arbitraire.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="dfaf7-173">Cette section contient les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="dfaf7-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="dfaf7-174">R.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-174">A.</span></span> [<span data-ttu-id="dfaf7-175">Création d'un instantané sur la base de données AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="dfaf7-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="dfaf7-176">B.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-176">B.</span></span> [<span data-ttu-id="dfaf7-177">Création d'un instantané sur la base de données Sales (Ventes)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="dfaf7-178">A.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-178">A.</span></span> <span data-ttu-id="dfaf7-179">Création d'un instantané sur la base de données AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="dfaf7-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="dfaf7-180">Cet exemple montre comment créer un instantané de base de données sur la base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="dfaf7-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="dfaf7-181">Le nom de l'instantané, `AdventureWorks_dbss_1800`, et le nom de son fichier partiellement alloué, `AdventureWorks_data_1800.ss`, précisent l'heure de création, 6H00 du soir (18 heures).</span><span class="sxs-lookup"><span data-stu-id="dfaf7-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="dfaf7-182">B.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-182">B.</span></span> <span data-ttu-id="dfaf7-183">Création d'un instantané sur la base de données Sales (Ventes)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="dfaf7-184">Cet exemple montre comment créer un instantané de base de données, `sales_snapshot1200`, sur la base de données `Sales` .</span><span class="sxs-lookup"><span data-stu-id="dfaf7-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="dfaf7-185">Cette base de données a été créée dans l’exemple « création d’une base de données qui a des groupes de fichiers » dans [Create database &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfaf7-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dfaf7-186">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="dfaf7-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="dfaf7-187">Afficher un instantané de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dfaf7-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="dfaf7-188">Rétablir une base de données dans l’état d’un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="dfaf7-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="dfaf7-189">Supprimer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfaf7-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="dfaf7-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dfaf7-190">See Also</span></span>  
 <span data-ttu-id="dfaf7-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dfaf7-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="dfaf7-192">Instantanés de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dfaf7-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
