---
title: Concepts liés aux procédures stockées système de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709212"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="a40ee-102">Concepts liés aux procédures stockées système de réplication</span><span class="sxs-lookup"><span data-stu-id="a40ee-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="a40ee-103">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'accès par programme à toutes les fonctionnalités d'une topologie de réplication configurables par l'utilisateur est opéré par les procédures stockées système.</span><span class="sxs-lookup"><span data-stu-id="a40ee-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="a40ee-104">Bien que les procédures stockées puissent être exécutées individuellement à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de l'utilitaire en ligne de commande sqlcmd, il peut être judicieux d'écrire des fichiers de script [!INCLUDE[tsql](../../../includes/tsql-md.md)] qui peuvent être exécutés pour effectuer une séquence logique de tâches de réplication.</span><span class="sxs-lookup"><span data-stu-id="a40ee-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="a40ee-105">La génération de scripts pour des tâches de réplication offre les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="a40ee-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="a40ee-106">conservation d'une copie définitive des étapes utilisées pour déployer votre topologie de réplication ;</span><span class="sxs-lookup"><span data-stu-id="a40ee-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="a40ee-107">utilisation d'un même script pour configurer plusieurs abonnés ;</span><span class="sxs-lookup"><span data-stu-id="a40ee-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="a40ee-108">formation rapide des nouveaux administrateurs de base de données en leur permettant d'évaluer, de comprendre et de modifier le code, ou de résoudre des problèmes liés au code.</span><span class="sxs-lookup"><span data-stu-id="a40ee-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a40ee-109">Les scripts peuvent causer des failles de sécurité ; ils peuvent appeler des fonctions système sans que l'utilisateur le sache ou intervienne. En outre, ils sont susceptibles de contenir des informations d'identification de sécurité sous forme de texte brut.</span><span class="sxs-lookup"><span data-stu-id="a40ee-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="a40ee-110">Examinez les scripts pour détecter d'éventuels problèmes de sécurité avant de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="a40ee-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="a40ee-111">Création de scripts de réplication</span><span class="sxs-lookup"><span data-stu-id="a40ee-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="a40ee-112">Du point de la réplication, un script consiste en une série d'instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)], chacune exécutant une procédure stockée de réplication.</span><span class="sxs-lookup"><span data-stu-id="a40ee-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="a40ee-113">Les scripts sont des fichiers texte, souvent dotés d'une extension de fichier .sql, qui peuvent être exécutés à l'aide de l'utilitaire sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="a40ee-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="a40ee-114">Lorsqu'un fichier de script est exécuté, l'utilitaire exécute les instructions SQL stockées dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="a40ee-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="a40ee-115">De même, un script peut être stocké sous la forme d’un objet de requête dans un projet [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a40ee-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="a40ee-116">Les méthodes suivantes peuvent être employées pour créer des scripts de réplication :</span><span class="sxs-lookup"><span data-stu-id="a40ee-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="a40ee-117">création manuelle du script ;</span><span class="sxs-lookup"><span data-stu-id="a40ee-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="a40ee-118">utilisation des fonctionnalités de génération de script fournies dans les Assistants de réplication ou</span><span class="sxs-lookup"><span data-stu-id="a40ee-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="a40ee-119">.</span><span class="sxs-lookup"><span data-stu-id="a40ee-119">.</span></span> <span data-ttu-id="a40ee-120">Pour plus d'informations, voir [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a40ee-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="a40ee-121">utilisation de Replication Management Objects pour générer le script par programme et créer un objet RMO.</span><span class="sxs-lookup"><span data-stu-id="a40ee-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="a40ee-122">Lorsque vous créez des scripts de réplication manuellement, gardez à l'esprit les points suivants :</span><span class="sxs-lookup"><span data-stu-id="a40ee-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   <span data-ttu-id="a40ee-123">Les scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] comportent un ou plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="a40ee-123">[!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts have one or more batches.</span></span> <span data-ttu-id="a40ee-124">La commande GO signale la fin d'un lot.</span><span class="sxs-lookup"><span data-stu-id="a40ee-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="a40ee-125">Si un script [!INCLUDE[tsql](../../../includes/tsql-md.md)] ne comporte pas de commande GO, il est exécuté comme un lot isolé.</span><span class="sxs-lookup"><span data-stu-id="a40ee-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="a40ee-126">Lors de l'exécution de plusieurs procédures stockées de réplication dans un lot unique, après la première procédure, toutes les procédures suivantes du lot doivent être précédées du mot clé EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="a40ee-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="a40ee-127">Toutes les procédures stockées d'un lot doivent être compilées pour que le lot puisse être exécuté.</span><span class="sxs-lookup"><span data-stu-id="a40ee-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="a40ee-128">Toutefois, lorsque le lot a été compilé et qu'un plan d'exécution a été créé, une erreur d'exécution peut éventuellement se produire.</span><span class="sxs-lookup"><span data-stu-id="a40ee-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="a40ee-129">Lorsque vous créez des scripts pour configurer la réplication, vous devez utiliser l'authentification Windows de sorte que les informations d'identification de sécurité ne soient pas stockées dans le fichier de script.</span><span class="sxs-lookup"><span data-stu-id="a40ee-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="a40ee-130">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="a40ee-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="a40ee-131">Exemple de script de réplication</span><span class="sxs-lookup"><span data-stu-id="a40ee-131">Sample Replication Script</span></span>  
 <span data-ttu-id="a40ee-132">Le script suivant peut être exécuté pour configurer la publication et la distribution sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="a40ee-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="a40ee-133">Ce script peut ensuite être enregistré localement sous le nom `instdistpub.sql` afin d'être exécuté ou réexécuté en cas de besoin.</span><span class="sxs-lookup"><span data-stu-id="a40ee-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="a40ee-134">Le script précédent inclut des variables de script **sqlcmd**, lesquelles sont utilisées dans de nombreux exemples de code de réplication dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a40ee-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="a40ee-135">Les variables de script sont définies à l’aide de la syntaxe `$(MyVariable)`.</span><span class="sxs-lookup"><span data-stu-id="a40ee-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="a40ee-136">Les valeurs des variables peuvent être transmises à un script sur la ligne de commande ou dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a40ee-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a40ee-137">Pour plus d'informations, consultez la section suivante de cette rubrique, « Exécution de scripts de réplication ».</span><span class="sxs-lookup"><span data-stu-id="a40ee-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="a40ee-138">Exécution de scripts de réplication</span><span class="sxs-lookup"><span data-stu-id="a40ee-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="a40ee-139">Une fois qu'un script de réplication a été créé, il est possible d'utiliser l'une des méthodes suivantes pour l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="a40ee-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="a40ee-140">Création d'un fichier de requête SQL dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a40ee-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="a40ee-141">Il est possible de créer un fichier de script [!INCLUDE[tsql](../../../includes/tsql-md.md)] de réplication sous la forme d’un fichier de requête SQL dans un projet [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a40ee-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="a40ee-142">Après l'écriture du script, une connexion à la base de données peut être établie pour ce fichier de requête, et le script peut être exécuté.</span><span class="sxs-lookup"><span data-stu-id="a40ee-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="a40ee-143">Pour plus d’informations sur la création de [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts à l’aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , consultez [éditeurs de requêtes et de texte &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="a40ee-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="a40ee-144">Pour utiliser un script qui inclut des variables de script, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] doit s’exécuter en mode **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="a40ee-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="a40ee-145">En mode **sqlcmd**, l’éditeur de requête accepte une syntaxe supplémentaire spécifique à **sqlcmd**, par exemple `:setvar`, qui est utilisée pour fournir une valeur à une variable.</span><span class="sxs-lookup"><span data-stu-id="a40ee-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="a40ee-146">Pour plus d’informations sur le mode **sqlcmd**, consultez [Modifier des scripts SQLCMD à l’aide de l’Éditeur de requête](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a40ee-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="a40ee-147">Dans le script suivant, la syntaxe `:setvar` est utilisée afin de fournir une valeur pour la variable `$(DistPubServer)`.</span><span class="sxs-lookup"><span data-stu-id="a40ee-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="a40ee-148">Utilisation de l'utilitaire sqlcmd à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="a40ee-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="a40ee-149">L’exemple suivant montre comment la ligne de commande est utilisée pour exécuter le fichier de script `instdistpub.sql` à l’aide de l’[utilitaire sqlcmd](../../../tools/sqlcmd-utility.md):</span><span class="sxs-lookup"><span data-stu-id="a40ee-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="a40ee-150">Dans cet exemple, le commutateur `-E` indique que l'authentification Windows est employée lors de la connexion à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a40ee-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a40ee-151">Avec l'authentification Windows, il est inutile de stocker un nom d'utilisateur et un mot de passe dans le fichier de script.</span><span class="sxs-lookup"><span data-stu-id="a40ee-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="a40ee-152">Le nom et le chemin d'accès du fichier de script sont spécifiés par le commutateur `-i`, et le nom du fichier de sortie est spécifié par le commutateur `-o` (la sortie de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est écrite dans ce fichier et non dans la console lorsque ce commutateur est utilisé).</span><span class="sxs-lookup"><span data-stu-id="a40ee-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="a40ee-153">L'utilitaire `sqlcmd` vous permet de passer des variables de script à un script [!INCLUDE[tsql](../../../includes/tsql-md.md)] lors de l'exécution, à l'aide du commutateur `-v`.</span><span class="sxs-lookup"><span data-stu-id="a40ee-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="a40ee-154">Dans cet exemple, `sqlcmd` remplace chaque instance de `$(DistPubServer)` dans le script par la valeur `N'MyDistributorAndPublisher'` avant l’exécution.</span><span class="sxs-lookup"><span data-stu-id="a40ee-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a40ee-155">Le commutateur `-X` désactive les variables de script.</span><span class="sxs-lookup"><span data-stu-id="a40ee-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="a40ee-156">Automatisation des tâches dans un fichier de commandes</span><span class="sxs-lookup"><span data-stu-id="a40ee-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="a40ee-157">Le recours à un fichier de commandes permet d'automatiser les tâches d'administration et de synchronisation de la réplication, entre autres, dans le même fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="a40ee-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="a40ee-158">Le fichier de commandes suivant utilise l’utilitaire **sqlcmd** pour supprimer la base de données d’abonnement et la recréer, ainsi que pour ajouter un abonnement de fusion par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="a40ee-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="a40ee-159">Le fichier appelle ensuite l'agent de fusion pour synchroniser le nouvel abonnement :</span><span class="sxs-lookup"><span data-stu-id="a40ee-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="a40ee-160">Génération de scripts pour les tâches de réplication courantes</span><span class="sxs-lookup"><span data-stu-id="a40ee-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="a40ee-161">Les tâches de réplication les plus courantes pour lesquelles il est possible de générer des scripts à l'aide de procédures stockées système sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a40ee-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="a40ee-162">Configuration de la publication et de la distribution</span><span class="sxs-lookup"><span data-stu-id="a40ee-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="a40ee-163">Modification des propriétés d'un serveur de distribution et d'un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="a40ee-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="a40ee-164">Désactivation de la publication et de la distribution</span><span class="sxs-lookup"><span data-stu-id="a40ee-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="a40ee-165">Création de publications et définition d'articles</span><span class="sxs-lookup"><span data-stu-id="a40ee-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="a40ee-166">Suppression de publications et d'articles</span><span class="sxs-lookup"><span data-stu-id="a40ee-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="a40ee-167">Création d'un abonnement par extraction de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="a40ee-168">Modification d'un abonnement par extraction de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="a40ee-169">Suppression d'un abonnement par extraction de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="a40ee-170">Création d'un abonnement par émission de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="a40ee-171">Modification d'un abonnement par émission de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="a40ee-172">Suppression d'un abonnement par émission de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="a40ee-173">Synchronisation d'un abonnement par extraction de données</span><span class="sxs-lookup"><span data-stu-id="a40ee-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40ee-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a40ee-174">See Also</span></span>  
 <span data-ttu-id="a40ee-175">[Concepts de programmation en matière de réplication](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="a40ee-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="a40ee-176">[Procédures stockées de réplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a40ee-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="a40ee-177">Création de scripts de réplication</span><span class="sxs-lookup"><span data-stu-id="a40ee-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
