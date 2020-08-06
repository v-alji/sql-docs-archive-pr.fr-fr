---
title: Extensions à AdventureWorks pour présenter l’OLTP en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707787"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="ed257-102">Extensions à AdventureWorks pour présenter l'OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="ed257-103">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ed257-103">Overview</span></span>  
 <span data-ttu-id="ed257-104">Cet exemple présente les nouvelles fonctionnalités d' [!INCLUDE[hek_2](../includes/hek-2-md.md)] , qui fait partie de [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ed257-105">Il présente les tables optimisées en mémoire et les procédures stockées compilées en mode natif, et illustre les performances d' [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed257-106">Pour afficher cette rubrique pour SQL Server 2016, consultez [Extensions à AdventureWorks pour présenter l’OLTP en mémoire](https://msdn.microsoft.com/library/mt465764.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed257-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="ed257-107">Dans l'exemple, 5 tables de la base de données AdventureWorks sont migrées vers des tables optimisées en mémoire, et une charge de travail de démonstration est incluse pour le traitement des commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="ed257-108">Utilisez cette charge de travail de démonstration pour voir le gain de performances obtenu en utilisant [!INCLUDE[hek_2](../includes/hek-2-md.md)] sur votre serveur.</span><span class="sxs-lookup"><span data-stu-id="ed257-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="ed257-109">Dans la description de l'exemple, nous aborderons les différents facteurs à prendre en compte lors de la migration des tables vers [!INCLUDE[hek_2](../includes/hek-2-md.md)] , notamment les fonctionnalités qui ne sont pas encore prises en charge pour les tables optimisées en mémoire dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="ed257-110">La documentation de l'exemple est structurée comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed257-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="ed257-111">[Configuration requise](#Prerequisites) pour installer l'exemple et exécuter la charge de travail de démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="ed257-112">Instructions pour [Installation de l’exemple In-Memory OLTP basé sur AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="ed257-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="ed257-113">[Description des exemples de tables et de procédures](#Descriptionofthesampletablesandprocedures) : il s’agit des descriptions des tables et des procédures ajoutées à AdventureWorks par l' [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemple, ainsi que des considérations relatives à la migration de certaines tables AdventureWorks d’origine vers des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="ed257-114">Instructions pour effectuer des [Mesures de performance à l’aide de la charge de travail de démonstration](#PerformanceMeasurementsusingtheDemoWorkload) : inclut des instructions pour installer et exécuter Ostress, un outil de pilotage de la charge de travail, et pour exécuter la charge de travail de démonstration elle-même</span><span class="sxs-lookup"><span data-stu-id="ed257-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="ed257-115">Utilisation de la mémoire et de l’espace disque dans l’exemple</span><span class="sxs-lookup"><span data-stu-id="ed257-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ed257-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ed257-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="ed257-117">RTM-version d’évaluation, Developer ou Enterprise</span><span class="sxs-lookup"><span data-stu-id="ed257-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="ed257-118">Pour tester les performances, un serveur avec des caractéristiques semblables dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="ed257-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="ed257-119">Pour cet exemple spécifique, vous devez disposer d'au moins 16 Go de mémoire disponible sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ed257-120">Pour obtenir des recommandations générales sur [!INCLUDE[hek_2](../includes/hek-2-md.md)] le matériel pour, consultez le billet de blog suivant :[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="ed257-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a><span data-ttu-id="ed257-121">Installation de l' [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemple basé sur AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="ed257-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="ed257-122">Procédez comme suit pour installer l'exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="ed257-123">Téléchargez l'archive pour la sauvegarde complète de la base de données AdventureWorks2014 :</span><span class="sxs-lookup"><span data-stu-id="ed257-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="ed257-124">Ouvrez la commande suivante : [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="ed257-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="ed257-125">À l'invite, enregistrez le fichier dans un dossier local.</span><span class="sxs-lookup"><span data-stu-id="ed257-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="ed257-126">Extrayez le fichier **AdventureWorks2014.bak** dans un dossier local, par exemple 'c:\temp'.</span><span class="sxs-lookup"><span data-stu-id="ed257-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="ed257-127">Restaurez la sauvegarde de la base de données à l'aide de [!INCLUDE[tsql](../includes/tsql-md.md)] ou [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ed257-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="ed257-128">Identifiez le dossier cible et le nom du fichier de données, par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="ed257-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span><span class="sxs-lookup"><span data-stu-id="ed257-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="ed257-130">Identifiez le dossier cible et le nom du fichier journal, par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="ed257-131">'i:\DATA\AdventureWorks2014_log.ldf'</span><span class="sxs-lookup"><span data-stu-id="ed257-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="ed257-132">Le fichier journal doit être placé sur un lecteur différent du fichier de données, idéalement un lecteur à faible latence tel qu'un stockage sur disque SSD ou PCIe, pour des performances maximales.</span><span class="sxs-lookup"><span data-stu-id="ed257-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="ed257-133">Exemple de script T-SQL :</span><span class="sxs-lookup"><span data-stu-id="ed257-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="ed257-134">Remplacez le propriétaire de base de données par une connexion sur votre serveur, en exécutant la commande suivante dans la fenêtre de requête de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ed257-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="ed257-135">Téléchargez l’exemple de script « [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL » à partir de l' [exemple d’OLTP en mémoire SQL Server 2014 RTM](https://go.microsoft.com/fwlink/?LinkID=396372) dans un dossier local.</span><span class="sxs-lookup"><span data-stu-id="ed257-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="ed257-136">Mettez à jour la valeur de la variable « checkpoint_files_location » dans le script « [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL » pour pointer vers l’emplacement cible des [!INCLUDE[hek_2](../includes/hek-2-md.md)] fichiers de point de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ed257-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="ed257-137">Les fichiers de point de contrôle doivent être placés sur un lecteur avec de bonnes performances d'E/S séquentielles.</span><span class="sxs-lookup"><span data-stu-id="ed257-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="ed257-138">Mettez à jour la valeur pour la variable 'database_name' afin qu'elle pointe vers la base de données AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="ed257-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="ed257-139">Veillez à inclure la barre oblique inverse « \' en tant que partie du nom du chemin d’accès</span><span class="sxs-lookup"><span data-stu-id="ed257-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="ed257-140">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="ed257-141">Exécutez l'exemple de script, de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed257-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="ed257-142">En utilisant l'utilitaire de ligne de commande sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="ed257-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="ed257-143">Par exemple, en exécutant la commande suivante à partir de l'invite de ligne de commande dans le dossier qui contient le script :</span><span class="sxs-lookup"><span data-stu-id="ed257-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="ed257-144">En utilisant Management Studio :</span><span class="sxs-lookup"><span data-stu-id="ed257-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="ed257-145">Ouvrez le script « [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL » dans une fenêtre de requête</span><span class="sxs-lookup"><span data-stu-id="ed257-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="ed257-146">Connectez-vous au serveur cible qui contient la base de données AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="ed257-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="ed257-147">Activez le mode SQLCMD en cliquant sur « Query-> SQLCMD mode »</span><span class="sxs-lookup"><span data-stu-id="ed257-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="ed257-148">Cliquez sur le bouton « Exécuter » pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="ed257-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="ed257-149">Description des exemples de tables et de procédures</span><span class="sxs-lookup"><span data-stu-id="ed257-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="ed257-150">L'exemple crée de nouvelles tables pour les produits et les commandes, selon les tables existantes dans AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ed257-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="ed257-151">Le schéma des nouvelles tables est similaire à celui des tables existantes, avec quelques différences, comme expliqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ed257-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="ed257-152">Les nouvelles tables à mémoire optimisée ont le suffixe « _inmem ».</span><span class="sxs-lookup"><span data-stu-id="ed257-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="ed257-153">L’exemple inclut également les tables correspondantes avec le suffixe « _ondisk » : ces tables peuvent être utilisées pour effectuer une comparaison un-à-un entre les performances des tables à mémoire optimisée et des tables sur disque de votre système.</span><span class="sxs-lookup"><span data-stu-id="ed257-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="ed257-154">Notez que les tables optimisées en mémoire utilisées dans la charge de travail pour la comparaison de performances sont entièrement durables et entièrement journalisées.</span><span class="sxs-lookup"><span data-stu-id="ed257-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="ed257-155">Elles ne sacrifient pas la durabilité ou la fiabilité pour atteindre les gains de performance.</span><span class="sxs-lookup"><span data-stu-id="ed257-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="ed257-156">La charge de travail cible pour cet exemple est le traitement des commandes, comprenant également des informations sur les produits et les remises.</span><span class="sxs-lookup"><span data-stu-id="ed257-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="ed257-157">À cet effet, il utilise les tables SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, et SpecialOfferProduct.</span><span class="sxs-lookup"><span data-stu-id="ed257-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="ed257-158">Deux nouvelles procédures stockées, Sales.usp_InsertSalesOrder_inmem et Sales.usp_UpdateSalesOrderShipInfo_inmem, sont utilisées pour insérer les commandes et pour mettre à jour les informations d'expédition d'une commande client spécifique.</span><span class="sxs-lookup"><span data-stu-id="ed257-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="ed257-159">Le nouveau schéma « Demo » contient les tables d'assistance et les procédures stockées pour effectuer une charge de travail de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="ed257-160">Concrètement, l'exemple d' [!INCLUDE[hek_2](../includes/hek-2-md.md)] ajoute les objets suivants dans AdventureWorks :</span><span class="sxs-lookup"><span data-stu-id="ed257-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="ed257-161">Tables ajoutées par l'exemple</span><span class="sxs-lookup"><span data-stu-id="ed257-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="ed257-162">Nouvelles tables</span><span class="sxs-lookup"><span data-stu-id="ed257-162">The New Tables</span></span>  
 <span data-ttu-id="ed257-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="ed257-164">Informations sur les en-têtes des commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-164">Header information about sales orders.</span></span> <span data-ttu-id="ed257-165">Chaque commande possède une ligne dans cette table.</span><span class="sxs-lookup"><span data-stu-id="ed257-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="ed257-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="ed257-167">Détails des commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-167">Details of sales orders.</span></span> <span data-ttu-id="ed257-168">À chaque article d'une commande correspond une ligne dans cette table.</span><span class="sxs-lookup"><span data-stu-id="ed257-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="ed257-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ed257-170">Informations sur les offres spéciales, y compris le pourcentage de remise associé à chaque offre spéciale.</span><span class="sxs-lookup"><span data-stu-id="ed257-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="ed257-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="ed257-172">Table de référence qui relie les offres spéciales et les produits.</span><span class="sxs-lookup"><span data-stu-id="ed257-172">Reference table between special offers and products.</span></span> <span data-ttu-id="ed257-173">Chaque offre spéciale peut contenir zéro ou plusieurs produits, et chaque produit peut être associé à zéro ou plusieurs offres spéciales.</span><span class="sxs-lookup"><span data-stu-id="ed257-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="ed257-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="ed257-175">Informations sur les produits, notamment leur prix catalogue.</span><span class="sxs-lookup"><span data-stu-id="ed257-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="ed257-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ed257-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="ed257-177">Utilisé dans la charge de travail de démonstration pour construire des exemples de commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="ed257-178">Variations sur disque des tables :</span><span class="sxs-lookup"><span data-stu-id="ed257-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="ed257-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="ed257-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="ed257-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="ed257-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="ed257-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="ed257-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="ed257-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="ed257-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="ed257-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="ed257-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="ed257-184">Différences entre les tables sur disque d'origine et les nouvelles tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="ed257-185">Pour la plupart, les nouvelles tables de cet exemple utilisent les mêmes colonnes et les mêmes types de données que les tables d'origine.</span><span class="sxs-lookup"><span data-stu-id="ed257-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="ed257-186">Toutefois, il existe quelques différences.</span><span class="sxs-lookup"><span data-stu-id="ed257-186">However, there are a few differences.</span></span> <span data-ttu-id="ed257-187">Nous les avons répertoriées ci-dessous, avec le raisonnement sous-jacent au changement.</span><span class="sxs-lookup"><span data-stu-id="ed257-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="ed257-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="ed257-189">Les*contraintes par défaut* sont prises en charge pour les tables optimisées en mémoire, et la plupart des contraintes par défaut ont été migrées en l’état.</span><span class="sxs-lookup"><span data-stu-id="ed257-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="ed257-190">Toutefois, la table d'origine Sales.SalesOrderHeader contient plusieurs contraintes par défaut qui récupèrent la date actuelle, pour les colonnes OrderDate et ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="ed257-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="ed257-191">Dans une charge de travail de traitement des commandes à haut débit, avec de nombreuses concurrences, n'importe quelle ressource globale peut devenir un point de contention.</span><span class="sxs-lookup"><span data-stu-id="ed257-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="ed257-192">L'heure système est l'une de ces ressources globales, et nous avons observé qu'elle peut devenir un goulot d'étranglement lorsqu'une charge de travail [!INCLUDE[hek_2](../includes/hek-2-md.md)] qui insère des commandes client est exécutée, en particulier si l'heure système doit être extraite pour plusieurs colonnes dans l'en-tête de la commande, ainsi que pour ses détails.</span><span class="sxs-lookup"><span data-stu-id="ed257-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="ed257-193">Le problème est résolu dans cet exemple en récupérant l'heure système une seule fois pour chaque commande client insérée, puis en utilisant cette valeur pour les colonnes datetime dans SalesOrderHeader_inmem et SalesOrderDetail_inmem, dans la procédure stockée Sales.usp_InsertSalesOrder_inmem.</span><span class="sxs-lookup"><span data-stu-id="ed257-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="ed257-194">*Types définis par l’utilisateur (UDT) alias* : la table d’origine utilise deux types définis par l’utilisateur (UDT) alias : dbo.OrderNumber et dbo.AccountNumber, pour les colonnes PurchaseOrderNumber et AccountNumber, respectivement.</span><span class="sxs-lookup"><span data-stu-id="ed257-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] <span data-ttu-id="ed257-195">ne prend pas en charge le type défini par l’utilisateur alias pour les tables optimisées en mémoire, par conséquent les nouvelles tables utilisent les types de données système nvarchar(25) et nvarchar(15), respectivement.</span><span class="sxs-lookup"><span data-stu-id="ed257-195">does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="ed257-196">*Colonnes autorisant des valeurs NULL dans l’index* : dans la table d’origine, la colonne SalesPersonID autorise les valeurs NULL, tandis que dans les nouvelles tables, la colonne n’accepte pas les valeurs NULL et a une contrainte par défaut avec la valeur (-1).</span><span class="sxs-lookup"><span data-stu-id="ed257-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="ed257-197">Cela est dû au fait que les index des tables optimisées en mémoire ne peuvent pas avoir de colonnes autorisant des valeurs NULL dans la clé d'index ; -1 est un substitut de la valeur NULL dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="ed257-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="ed257-198">*Colonnes calculées[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] : les colonnes calculées SalesOrderNumber et TotalDue sont omises, car* ne prend pas en charge les colonnes calculées dans les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ed257-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="ed257-199">La nouvelle vue Sales.vSalesOrderHeader_extended_inmem reflète les colonnes SalesOrderNumber et TotalDue.</span><span class="sxs-lookup"><span data-stu-id="ed257-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="ed257-200">Par conséquent, vous pouvez utiliser cette vue si ces colonnes sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ed257-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="ed257-201">Les*contraintes de clé étrangère* ne sont pas prises en charge pour les tables optimisées en mémoire dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ed257-202">En outre, SalesOrderHeader_inmem est une table très sollicitée dans l'exemple de charge de travail, et les contraintes de clé étrangère nécessitent un traitement supplémentaire pour toutes les opérations DML, avec des recherches dans les autres tables référencées dans ces contraintes.</span><span class="sxs-lookup"><span data-stu-id="ed257-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="ed257-203">Par conséquent, on formule l'hypothèse que l'application garantit l'intégrité référentielle, et celle-ci n'est pas validée lorsque des lignes sont insérées.</span><span class="sxs-lookup"><span data-stu-id="ed257-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="ed257-204">L'intégrité référentielle des données de cette table peut être vérifiée à l'aide de la procédure stockée dbo.usp_ValidateIntegrity, en utilisant le script suivant :</span><span class="sxs-lookup"><span data-stu-id="ed257-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ed257-205">Les*contraintes de validation* ne sont pas prises en charge pour les tables optimisées en mémoire dans SQ Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ed257-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="ed257-206">L'intégrité du domaine est validée avec l'intégrité référentielle en utilisant ce script :</span><span class="sxs-lookup"><span data-stu-id="ed257-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ed257-207">*Rowguid* : la colonne ROWGUID est omise.</span><span class="sxs-lookup"><span data-stu-id="ed257-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ed257-208">Alors que uniqueidentifier est pris en charge pour les tables optimisées en mémoire, l'option ROWGUIDCOL n'est pas prise en charge dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ed257-209">Les colonnes de ce type sont généralement utilisées pour la réplication de fusion ou pour des tables qui possèdent des colonnes FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ed257-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="ed257-210">Cet exemple ne comporte aucun de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="ed257-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="ed257-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="ed257-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="ed257-212">*Contraintes par défaut* : similairement à SalesOrderHeader, la contrainte par défaut qui exige la date/l’heure système n’est pas migrée. En revanche, la procédure stockée d’insertion des commandes prend soin d’insérer la date et l’heure système actuelles à la première insertion.</span><span class="sxs-lookup"><span data-stu-id="ed257-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="ed257-213">*Colonnes calculées* : la colonne calculée LineTotal n’a pas été migrée, car les colonnes calculées ne sont pas prises en charge par les tables à mémoire optimisée dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed257-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ed257-214">Pour accéder à cette colonne, utilisez la vue Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="ed257-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="ed257-215">*Rowguid* : la colonne ROWGUID est omise.</span><span class="sxs-lookup"><span data-stu-id="ed257-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ed257-216">Pour plus d'informations consultez la description de la table SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ed257-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="ed257-217">Pour les contraintes *de validation* et *de clé étrangère* consultez la description de SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ed257-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="ed257-218">Le script suivant peut être utilisé pour vérifier l'intégrité du domaine et l'intégrité référentielle de cette table :</span><span class="sxs-lookup"><span data-stu-id="ed257-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="ed257-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="ed257-219">Production.Product</span></span>  
  
-   <span data-ttu-id="ed257-220">*Types définis par l’utilisateur (UDT) alias* : la table d’origine utilise le type de données défini par l’utilisateur dbo.Flag, qui est équivalent au bit de type de données système.</span><span class="sxs-lookup"><span data-stu-id="ed257-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="ed257-221">La table migrée utilise le type de données bit à la place.</span><span class="sxs-lookup"><span data-stu-id="ed257-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="ed257-222">*Classement BIN2* : les colonnes Name et ProductNumber sont incluses dans les clés d’index, et doivent donc avoir des classements BIN2 dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed257-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="ed257-223">Ici, l'hypothèse est que l'application ne tient pas compte des spécificités du classement, comme le non-respect de la casse.</span><span class="sxs-lookup"><span data-stu-id="ed257-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="ed257-224">*Rowguid* : la colonne ROWGUID est omise.</span><span class="sxs-lookup"><span data-stu-id="ed257-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ed257-225">Pour plus d'informations consultez la description de la table SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ed257-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="ed257-226">Les contraintes*uniques*, *de validation* et *de clé étrangère* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem et Product.usp_DeleteProduct_inmem can be used to insert et delete products; these procedures validate domain et referential integrity, et will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="ed257-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ed257-227">En outre, le script suivant peut être utilisé pour valider l'intégrité du domaine et l'intégrité référentielle, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed257-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="ed257-228">Notez que les procédures stockées usp_InsertProduct_inmem et usp_DeleteProduct_inmem tiennent compte uniquement des clés étrangères entre les tables migrées.</span><span class="sxs-lookup"><span data-stu-id="ed257-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="ed257-229">Les références aux autres tables ProductModel, ProductSubcategory, et UnitMeasure ne sont pas prises en compte.</span><span class="sxs-lookup"><span data-stu-id="ed257-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="ed257-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="ed257-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="ed257-231">Les contraintes*de validation* et *de clé étrangère* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem et Sales.usp_DeleteSpecialOffer_inmem can be used to insert et delete special offers; these procedures validate domain et referential integrity, et will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="ed257-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ed257-232">En outre, le script suivant peut être utilisé pour valider l'intégrité du domaine et l'intégrité référentielle, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed257-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ed257-233">*Rowguid* : la colonne ROWGUID est omise.</span><span class="sxs-lookup"><span data-stu-id="ed257-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ed257-234">Pour plus d'informations consultez la description de la table SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ed257-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="ed257-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="ed257-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="ed257-236">Les contraintes*de clé étrangère* sont prises en compte de deux façons : la procédure stockée Sales.usp_InsertSpecialOfferProduct_inmem peut être utilisée pour insérer des relations entre des offres spéciales et des produits ; cette procédure valide l'intégrité référentielle, et échoue si l'intégrité est violée.</span><span class="sxs-lookup"><span data-stu-id="ed257-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="ed257-237">En outre, le script suivant peut être utilisé pour valider l'intégrité référentielle, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed257-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="ed257-238">*Rowguid* : la colonne ROWGUID est omise.</span><span class="sxs-lookup"><span data-stu-id="ed257-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="ed257-239">Pour plus d'informations consultez la description de la table SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="ed257-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="ed257-240">Observations sur les index des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="ed257-241">L'index de base des tables optimisées en mémoire est l'index non cluster, qui prend en charge les recherches de point (recherche d'index dans le prédicat d'égalité), les analyses de plage (recherche d'index dans l'attribut d'inégalité), les analyses d'index complet, et les analyses triées.</span><span class="sxs-lookup"><span data-stu-id="ed257-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="ed257-242">En outre, les index non cluster prennent en charge la recherche dans les colonnes de début de la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="ed257-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="ed257-243">En fait, les index non cluster optimisés en mémoire autorisent toutes les opérations prises en charge par les index non cluster sur disque, à la seule exception des analyses ascendantes.</span><span class="sxs-lookup"><span data-stu-id="ed257-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="ed257-244">Par conséquent, l'utilisation des index non cluster est un choix sûr pour les index.</span><span class="sxs-lookup"><span data-stu-id="ed257-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="ed257-245">Les index HASH peuvent être utilisés pour optimiser davantage la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="ed257-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="ed257-246">Ils sont particulièrement optimisés pour les recherches de point et les insertions de ligne.</span><span class="sxs-lookup"><span data-stu-id="ed257-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="ed257-247">Toutefois, il faut considérer qu'ils ne prennent pas en charge les analyses de plage, les analyses triées, ou la recherche sur les colonnes clés d'index.</span><span class="sxs-lookup"><span data-stu-id="ed257-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="ed257-248">Par conséquent, leur utilisation est plus délicate.</span><span class="sxs-lookup"><span data-stu-id="ed257-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="ed257-249">En outre, il est nécessaire de spécifier le bucket_count lors de la création.</span><span class="sxs-lookup"><span data-stu-id="ed257-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="ed257-250">Celui-ci doit généralement correspondre à une valeur comprise entre le nombre de valeurs de clé d'index et son double, mais il peut généralement être surestimé.</span><span class="sxs-lookup"><span data-stu-id="ed257-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="ed257-251">Consultez la documentation en ligne pour plus de détails sur les [instructions d’index](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) et pour les recommandations concernant le [choix du bon bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ed257-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="ed257-252">Les index des tables migrées ont été paramétrés pour la charge de travail de traitement des commandes de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="ed257-253">La charge de travail repose sur les insertions et les recherches de point dans les tables Sales.SalesOrderHeader_inmem et Sales.SalesOrderDetail_inmem, elle porte également sur les recherches de point sur les colonnes clés primaires dans les tables Production.Product_inmem et Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="ed257-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="ed257-254">Sales.SalesOrderHeader_inmem a trois index, qui sont tous des index HASH pour des raisons de performances, et aucune recherche triée ou de plage n'est nécessaire pour la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="ed257-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="ed257-255">Index HASH sur (SalesOrderID) : le bucket_count est dimensionné à 10 millions (arrondi à 16 millions), car le nombre estimé de commandes est 10 millions.</span><span class="sxs-lookup"><span data-stu-id="ed257-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="ed257-256">Index HASH sur (SalesPersonID) : le bucket_count est 1 million.</span><span class="sxs-lookup"><span data-stu-id="ed257-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="ed257-257">Le jeu de données fourni ne contient pas beaucoup de commerciaux, mais il permet une croissance future ; de plus, les performances ne sont pas affectées par les recherches de point si le bucket_count est surdimensionné.</span><span class="sxs-lookup"><span data-stu-id="ed257-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="ed257-258">Index HASH sur (CustomerID) : le bucket_count est 1 million.</span><span class="sxs-lookup"><span data-stu-id="ed257-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="ed257-259">Le jeu de données fourni ne contient pas beaucoup de clients, mais il permet une croissance future.</span><span class="sxs-lookup"><span data-stu-id="ed257-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="ed257-260">Sales.SalesOrderDetail_inmem a trois index, qui sont tous des index HASH pour des raisons de performances, et aucune recherche triée ou de plage n'est nécessaire pour la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="ed257-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="ed257-261">Index HASH sur (SalesOrderID, SalesOrderDetailID) : il s'agit de l'index de clé primaire, et bien que les recherches sur (SalesOrderID, SalesOrderDetailID) soient rares, l'utilisation d'un index de hachage pour la clé accélère les insertions de lignes.</span><span class="sxs-lookup"><span data-stu-id="ed257-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="ed257-262">Le bucket_count est dimensionné à 50 millions (arrondi à 67 millions) : le nombre estimé de commandes est 10 millions, valeur dimensionnée pour une moyenne de 5 articles par commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="ed257-263">Index HASH sur (SalesOrderID) : les recherches par commande sont fréquentes : vous souhaitez rechercher tous les articles correspondant à une commande unique.</span><span class="sxs-lookup"><span data-stu-id="ed257-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="ed257-264">Le Index bucket_count est dimensionné à 10 millions (arrondi à 16 millions), car le nombre estimé de commandes est 10 millions.</span><span class="sxs-lookup"><span data-stu-id="ed257-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="ed257-265">Index HASH sur (ProductID) : le bucket_count est 1 million.</span><span class="sxs-lookup"><span data-stu-id="ed257-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="ed257-266">Le jeu de données fourni ne contient pas beaucoup de produits, mais il permet une croissance future.</span><span class="sxs-lookup"><span data-stu-id="ed257-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="ed257-267">Production.Product_inmem a trois index.</span><span class="sxs-lookup"><span data-stu-id="ed257-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="ed257-268">Index HASH sur (ProductID) : les recherches sur ProductID sont critiques pour la charge de travail de démonstration, c'est pourquoi il s'agit d'un index de hachage.</span><span class="sxs-lookup"><span data-stu-id="ed257-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="ed257-269">Index non cluster sur (Name) : il permet les analyses triées par noms de produit.</span><span class="sxs-lookup"><span data-stu-id="ed257-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="ed257-270">Index non cluster sur (ProductNumber) : il permet les analyses triées par numéros de produit.</span><span class="sxs-lookup"><span data-stu-id="ed257-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="ed257-271">Sales.SpecialOffer_inmem a un index HASH sur (SpecialOfferID) : les recherches de point pour des offres spéciales sont critiques pour la charge de travail de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="ed257-272">Le bucket_count est dimensionné à 1 million pour permettre la croissance future.</span><span class="sxs-lookup"><span data-stu-id="ed257-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="ed257-273">Sales.SpecialOfferProduct_inmem n’est pas référencé dans la charge de travail de démonstration, et il n’est donc pas nécessaire d’utiliser les index de hachage de cette table pour optimiser la charge de travail ; les index sur (SpecialOfferID, ProductID) et (ProductID) sont NONCLUSTERED.</span><span class="sxs-lookup"><span data-stu-id="ed257-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="ed257-274">Notez que ci-dessus, certains bucket_counts sont surdimensionnés, mais pas les bucket_counts des index sur SalesOrderHeader_inmem et SalesOrderDetail_inmem qui sont dimensionnés uniquement à 10 millions de commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="ed257-275">Cela a pour but de permettre l'installation de l'exemple sur des systèmes avec une faible disponibilité de mémoire ; cependant dans ces cas, la charge de travail de démonstration échoue pour conditions de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="ed257-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="ed257-276">Si vous voulez dimensionner au-delà de 10 millions de commandes, augmentez le nombre de compartiments en conséquence.</span><span class="sxs-lookup"><span data-stu-id="ed257-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="ed257-277">Observations sur l'utilisation de la mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="ed257-278">L'utilisation de la mémoire dans la base de données d'exemple, avant et après l'exécution de la charge de travail de démonstration, est décrite dans la section [Utilisation de la mémoire pour les tables optimisées en mémoire](#Memoryutilizationforthememory-optimizedtables).</span><span class="sxs-lookup"><span data-stu-id="ed257-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="ed257-279">Procédures stockées ajoutées par l'exemple</span><span class="sxs-lookup"><span data-stu-id="ed257-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="ed257-280">Les deux procédures stockées clés d'insertion des commandes et de mise à jour des informations d'expédition sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed257-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="ed257-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="ed257-282">Insère une nouvelle commande dans la base de données et génère le SalesOrderID pour cette commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="ed257-283">Comme paramètres d'entrée, elle récupère les détails de l'en-tête de la commande client, ainsi que les articles de la commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="ed257-284">Paramètre de sortie :</span><span class="sxs-lookup"><span data-stu-id="ed257-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="ed257-285">@SalesOrderID int : SalesOrderID de la commande qui vient d’être insérée</span><span class="sxs-lookup"><span data-stu-id="ed257-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="ed257-286">Paramètres d'entrée (obligatoires) :</span><span class="sxs-lookup"><span data-stu-id="ed257-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="ed257-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="ed257-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="ed257-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="ed257-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="ed257-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem : paramètre table qui contient les articles de la commande</span><span class="sxs-lookup"><span data-stu-id="ed257-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="ed257-293">Paramètres d'entrée (facultatifs) :</span><span class="sxs-lookup"><span data-stu-id="ed257-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="ed257-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="ed257-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="ed257-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="ed257-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="ed257-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="ed257-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="ed257-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="ed257-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="ed257-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="ed257-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="ed257-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="ed257-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="ed257-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="ed257-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="ed257-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="ed257-305">Met à jour les informations d'expédition d'une commande client spécifique.</span><span class="sxs-lookup"><span data-stu-id="ed257-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="ed257-306">Met également à jour les informations d'expédition de tous les articles de la commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="ed257-307">Il s'agit d'une procédure wrapper pour les procédures stockées compilées en mode natif Sales.usp_UpdateSalesOrderShipInfo_native avec la logique de nouvelle tentative permettant de traiter les conflits potentiels (inattendus) avec des transactions simultanées qui mettent à jour la même commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="ed257-308">Pour plus d'informations sur la logique de nouvelle tentative, consultez la rubrique de la documentation en ligne [ici](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ed257-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="ed257-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="ed257-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="ed257-310">Il s'agit de la procédure stockée compilée en mode natif qui traite effectivement la mise à jour des informations d'expédition.</span><span class="sxs-lookup"><span data-stu-id="ed257-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="ed257-311">Elle doit être appelée à partir de la procédure stockée wrapper Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="ed257-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="ed257-312">Si le client peut traiter les échecs et implémente la logique de nouvelle tentative, vous pouvez appeler cette procédure directement, au lieu d'utiliser la procédure stockée wrapper.</span><span class="sxs-lookup"><span data-stu-id="ed257-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="ed257-313">La procédure stockée suivante est utilisée pour la charge de travail de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="ed257-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="ed257-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="ed257-315">Réinitialise la démonstration en vidant et en réamorçant les tables SalesOrderHeader et SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="ed257-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="ed257-316">Les procédures stockées suivantes sont utilisées pour insérer et supprimer des tables optimisées en mémoire tout en garantissant l'intégrité du domaine et l'intégrité référentielle.</span><span class="sxs-lookup"><span data-stu-id="ed257-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="ed257-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="ed257-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="ed257-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ed257-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="ed257-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="ed257-322">Enfin, la procédure stockée suivante est utilisée pour vérifier l'intégrité du domaine et l'intégrité référentielle.</span><span class="sxs-lookup"><span data-stu-id="ed257-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="ed257-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="ed257-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="ed257-324">Paramètre facultatif : @object_id - ID de l’objet dont l’intégrité doit être validée</span><span class="sxs-lookup"><span data-stu-id="ed257-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="ed257-325">Cette procédure s’appuie sur les tables dbo.DomainIntegrity, dbo.ReferentialIntegrity et dbo.UniqueIntegrity pour les règles d’intégrité qui doivent être vérifiées. L’exemple remplit ces tables en fonction des contraintes de validation, de clé étrangère et uniques qui existent pour les tables d’origine dans la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ed257-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="ed257-326">Elle repose sur les procédures d'assistance dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, et dbo.GenerateUQCheck pour générer l'instruction T-SQL nécessaire pour effectuer les vérifications d'intégrité.</span><span class="sxs-lookup"><span data-stu-id="ed257-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="ed257-327">Mesures de performance à l'aide de la charge de travail de démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="ed257-328">Ostress est un outil de ligne de commande qui a été développé par l'équipe de support technique de [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed257-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="ed257-329">Cet outil peut être utilisé pour exécuter des requêtes ou des procédures stockées distantes en parallèle.</span><span class="sxs-lookup"><span data-stu-id="ed257-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="ed257-330">Vous pouvez configurer le nombre de threads pour exécuter une instruction T-SQL donnée en parallèle et spécifier combien de fois l'instruction doit être exécutée sur ce thread. Ostress assemblera les threads et exécutera l'instruction sur tous les threads en parallèle.</span><span class="sxs-lookup"><span data-stu-id="ed257-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="ed257-331">Lorsque l'exécution est terminée pour tous les threads, Ostress indique le temps qu'il a fallu pour terminer l'exécution sur tous les threads.</span><span class="sxs-lookup"><span data-stu-id="ed257-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="ed257-332">Installation d'Ostress</span><span class="sxs-lookup"><span data-stu-id="ed257-332">Installing ostress</span></span>  
 <span data-ttu-id="ed257-333">Ostress est installé avec les utilitaires RML ; il n'y a aucune installation autonome pour Ostress.</span><span class="sxs-lookup"><span data-stu-id="ed257-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="ed257-334">Étapes d'installation :</span><span class="sxs-lookup"><span data-stu-id="ed257-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="ed257-335">Téléchargez et exécutez le package d’installation x64 pour les utilitaires RML à partir de la page suivante :[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed257-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="ed257-336">Si une boîte de dialogue indique que certains fichiers sont en cours d’utilisation, cliquez sur « Continuer »</span><span class="sxs-lookup"><span data-stu-id="ed257-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="ed257-337">Exécution d'Ostress</span><span class="sxs-lookup"><span data-stu-id="ed257-337">Running ostress</span></span>  
 <span data-ttu-id="ed257-338">Ostress s'exécute à partir de l'invite de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="ed257-339">Il est plus pratique d'exécuter l'outil à partir de l'« invite de commandes RML », qui est installé avec les Utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="ed257-340">Pour ouvrir l'invite de commandes RML exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="ed257-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="ed257-341">Dans Windows Server 2012 R2 et dans Windows 8 et 8.1, ouvrez le menu de démarrage en cliquant sur la touche Windows, et tapez « rml ».</span><span class="sxs-lookup"><span data-stu-id="ed257-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="ed257-342">Cliquez sur l’« invite de commandes RML », qui apparaît dans la liste de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="ed257-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="ed257-343">Vérifiez que l'invite de commandes se trouve dans le dossier d'installation des utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="ed257-344">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="ed257-345">Les options de ligne de commande d'Ostress s'affichent en exécutant simplement ostress.exe, sans besoin d'aucune option de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="ed257-346">Les options principales à prendre en compte pour exécuter Ostress avec cet exemple sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed257-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="ed257-347">-S Nom de l’instance [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à laquelle se connecter</span><span class="sxs-lookup"><span data-stu-id="ed257-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="ed257-348">-E utiliser l’authentification Windows pour se connecter (par défaut); Si vous utilisez l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentification, utilisez les options-u et-P pour spécifier le nom d’utilisateur et le mot de passe, respectivement.</span><span class="sxs-lookup"><span data-stu-id="ed257-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="ed257-349">-d Nom de la base de données, pour cet exemple AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="ed257-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="ed257-350">-Q Instruction T-SQL à exécuter</span><span class="sxs-lookup"><span data-stu-id="ed257-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="ed257-351">-n Nombre de connexions qui traitent chaque fichier d'entrée/requête</span><span class="sxs-lookup"><span data-stu-id="ed257-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="ed257-352">-r Nombre d'itérations pour chaque connexion qui exécute chaque fichier d'entrée/requête</span><span class="sxs-lookup"><span data-stu-id="ed257-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="ed257-353">Charge de travail de démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-353">Demo Workload</span></span>  
 <span data-ttu-id="ed257-354">La procédure stockée principale utilisée dans la charge de travail de démonstration est Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="ed257-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="ed257-355">Le script ci-dessous construit un paramètre table (TVP) avec des exemples de données, puis appelle la procédure pour insérer une commande avec 5 articles.</span><span class="sxs-lookup"><span data-stu-id="ed257-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="ed257-356">L'outil Ostress permet d'exécuter des appels de procédure stockée en parallèle, pour simuler des clients insérant des commandes simultanément.</span><span class="sxs-lookup"><span data-stu-id="ed257-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="ed257-357">Réinitialisez la démonstration après chaque exécution contrainte exécutant Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="ed257-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="ed257-358">Cette procédure supprime les lignes des tables optimisées en mémoire, tronque les tables sur disque, et exécute un point de contrôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="ed257-359">Le script suivant est exécuté simultanément pour simuler une charge de travail de traitement des commandes :</span><span class="sxs-lookup"><span data-stu-id="ed257-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="ed257-360">Avec ce script, chaque exemple de commande construite est inséré 20 fois, via 20 procédures stockées exécutées dans une boucle WHILE.</span><span class="sxs-lookup"><span data-stu-id="ed257-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="ed257-361">La boucle est utilisée pour tenir compte du fait que la base de données est utilisée pour construire l'exemple de commande.</span><span class="sxs-lookup"><span data-stu-id="ed257-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="ed257-362">Dans des environnements de production standard, l'application de niveau intermédiaire construira la commande à insérer.</span><span class="sxs-lookup"><span data-stu-id="ed257-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="ed257-363">Le script ci-dessus insère des commandes dans les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ed257-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="ed257-364">Le script pour insérer des commandes dans les tables sur disque est dérivé en remplaçant les deux occurrences de « _inmem » par « _ondisk ».</span><span class="sxs-lookup"><span data-stu-id="ed257-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="ed257-365">Nous utiliserons l'outil Ostress pour exécuter des scripts utilisant plusieurs connexions simultanées.</span><span class="sxs-lookup"><span data-stu-id="ed257-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="ed257-366">Nous utiliserons le paramètre « -n » pour contrôler le nombre de connexions, et le paramètre « r » pour contrôler le nombre de fois où le script est exécuté sur chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="ed257-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="ed257-367">Validation fonctionnelle de la charge de travail</span><span class="sxs-lookup"><span data-stu-id="ed257-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="ed257-368">Pour vérifier que tout fonctionne, nous allons commencer par un exemple de test, en utilisant 10 connexions simultanées et 5 itérations, en insérant un total de 10 \* 5 \* 20 = 1000 commande client.</span><span class="sxs-lookup"><span data-stu-id="ed257-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="ed257-369">Dans la commande ci-dessous, nous supposons que l'instance par défaut est utilisée sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="ed257-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="ed257-370">Si vous utilisez une instance nommée ou un serveur distant, remplacez le nom du serveur en conséquence, en utilisant le paramètre -S.</span><span class="sxs-lookup"><span data-stu-id="ed257-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="ed257-371">Insérez 1000 commandes dans les tables optimisées en mémoire en utilisant la commande suivante dans l'invite de commandes RML :</span><span class="sxs-lookup"><span data-stu-id="ed257-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="ed257-372">Cliquez sur le bouton correspondant pour copier la commande, et collez-la dans l'invite de commandes des utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ed257-373">Si tout fonctionne comme prévu, votre fenêtre de commande devrait ressembler à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="ed257-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="ed257-374">Aucun message d'erreur ne devrait apparaître.</span><span class="sxs-lookup"><span data-stu-id="ed257-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="ed257-375">Vérifiez également que la charge de travail fonctionne comme prévu pour les tables sur disque en exécutant la commande suivante à l'invite de commandes RML :</span><span class="sxs-lookup"><span data-stu-id="ed257-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="ed257-376">Cliquez sur le bouton correspondant pour copier la commande, et collez-la dans l'invite de commandes des utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="ed257-377">Exécution de la charge de travail</span><span class="sxs-lookup"><span data-stu-id="ed257-377">Running the Workload</span></span>  
 <span data-ttu-id="ed257-378">Pour tester à l'échelle, nous insérons 10 millions de commandes, à l'aide de 100 connexions.</span><span class="sxs-lookup"><span data-stu-id="ed257-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="ed257-379">Ce test peut être exécuté aisément sur un serveur de taille moyenne (par exemple, 8 noyaux physiques, et 16 noyaux logiques), et un stockage SSD de base pour le journal.</span><span class="sxs-lookup"><span data-stu-id="ed257-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="ed257-380">Si le test ne fonctionne pas correctement sur votre matériel, consultez la section [Dépannage des tests lents](#Troubleshootingslow-runningtests). Si vous voulez réduire le niveau d’extraction pour le test, réduisez le nombre de connexions en modifiant le paramètre « -n ».</span><span class="sxs-lookup"><span data-stu-id="ed257-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="ed257-381">Par exemple, pour réduire le nombre de connexions à 40, remplacez le paramètre « -n100 » par « -n40 ».</span><span class="sxs-lookup"><span data-stu-id="ed257-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="ed257-382">Comme mesure de performances pour la charge de travail, nous utilisons le temps écoulé tel qu'indiqué par ostress.exe après avoir exécuté la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="ed257-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="ed257-383">Tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="ed257-384">Nous allons commencer par exécuter la charge de travail sur les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ed257-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="ed257-385">La commande suivante ouvre 100 threads, chacun exécuté pour 5 000 itérations.</span><span class="sxs-lookup"><span data-stu-id="ed257-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="ed257-386">Chaque itération insère 20 commandes dans des transactions séparées.</span><span class="sxs-lookup"><span data-stu-id="ed257-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="ed257-387">Il y a 20 insertions par itération pour compenser le fait que la base de données est utilisée pour générer les données à insérer.</span><span class="sxs-lookup"><span data-stu-id="ed257-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="ed257-388">Cela donne un total de 20 \* 5 000 \* 100 = 10 000 000 commandes insérées.</span><span class="sxs-lookup"><span data-stu-id="ed257-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="ed257-389">Ouvrez l'invite de commandes RML et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ed257-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="ed257-390">Cliquez sur le bouton correspondant pour copier la commande, et collez-la dans l'invite de commandes des utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ed257-391">Sur un serveur de test avec un nombre total de 8 noyaux physiques (16 logiques), ceci a nécessité 2 minutes et 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="ed257-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="ed257-392">Sur un second serveur de test avec 24 noyaux physiques (48 logiques), ceci a nécessité 1 minute et 0 secondes.</span><span class="sxs-lookup"><span data-stu-id="ed257-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="ed257-393">Observez l'utilisation de l'UC pendant que la charge de travail est exécutée, par exemple via le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="ed257-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="ed257-394">Vous constaterez que l'utilisation de l'UC est proche de 100 %.</span><span class="sxs-lookup"><span data-stu-id="ed257-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="ed257-395">Dans le cas contraire, vous avez un goulot d'étranglement d'E/S du journal. Consultez [Dépannage des tests lents](#Troubleshootingslow-runningtests).</span><span class="sxs-lookup"><span data-stu-id="ed257-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="ed257-396">Tables sur disque</span><span class="sxs-lookup"><span data-stu-id="ed257-396">Disk-based tables</span></span>  
 <span data-ttu-id="ed257-397">La commande suivante exécute la charge de travail sur les tables sur disque.</span><span class="sxs-lookup"><span data-stu-id="ed257-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="ed257-398">Notez que l'exécution de cette charge de travail peut prendre du temps, principalement à cause d'une contention de verrous internes dans le système.</span><span class="sxs-lookup"><span data-stu-id="ed257-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="ed257-399">Les tables optimisées en mémoire n'ont pas de verrous et ne sont pas concernées par ce problème.</span><span class="sxs-lookup"><span data-stu-id="ed257-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="ed257-400">Ouvrez l'invite de commandes RML et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ed257-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="ed257-401">Cliquez sur le bouton correspondant pour copier la commande, et collez-la dans l'invite de commandes des utilitaires RML.</span><span class="sxs-lookup"><span data-stu-id="ed257-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="ed257-402">Sur un serveur de test avec un nombre total de 8 noyaux physiques (16 logiques), ceci a nécessité 41 minutes et 25 secondes.</span><span class="sxs-lookup"><span data-stu-id="ed257-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="ed257-403">Sur un second serveur de test avec 24 noyaux physiques (48 logiques), ceci a nécessité 52 minutes et 16 secondes.</span><span class="sxs-lookup"><span data-stu-id="ed257-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="ed257-404">La raison principale de la différence de performances entre les tables optimisées en mémoire et les tables sur disque pendant ce test, est que lorsque vous utilisez des tables sur disque, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] n'utilise pas entièrement l'UC.</span><span class="sxs-lookup"><span data-stu-id="ed257-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="ed257-405">Cela est dû à une contention de verrou : les transactions simultanées tentent d'écrire dans la même page de données ; les verrous sont utilisés pour garantir qu'une seule transaction à la fois écrit sur une page.</span><span class="sxs-lookup"><span data-stu-id="ed257-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="ed257-406">Le moteur d' [!INCLUDE[hek_2](../includes/hek-2-md.md)] n'a pas de verrous, et les lignes de données ne sont pas organisées en pages.</span><span class="sxs-lookup"><span data-stu-id="ed257-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="ed257-407">Par conséquent, les transactions simultanées ne bloquent pas les insertions réciproques, ce qui permet [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à d’utiliser pleinement l’UC.</span><span class="sxs-lookup"><span data-stu-id="ed257-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="ed257-408">Observez l'utilisation de l'UC pendant que la charge de travail est exécutée, par exemple via le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="ed257-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="ed257-409">Vous verrez qu'avec les tables sur disque, l'utilisation de l'UC est loin d'être de 100 %.</span><span class="sxs-lookup"><span data-stu-id="ed257-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="ed257-410">Dans une configuration de test avec 16 processeurs logiques, l'utilisation serait d'environ 24 %.</span><span class="sxs-lookup"><span data-stu-id="ed257-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="ed257-411">Éventuellement, vous pouvez afficher le nombre d’attentes de verrous par seconde à l’aide de l’analyseur de performances, avec le compteur de performance « \SQL Server:Latches\Latch Waits/sec ».</span><span class="sxs-lookup"><span data-stu-id="ed257-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="ed257-412">Réinitialisation de la démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-412">Resetting the demo</span></span>  
 <span data-ttu-id="ed257-413">Pour réinitialiser la démonstration, ouvrez l'invite de commandes RML et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ed257-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="ed257-414">Selon le matériel, l'exécution peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="ed257-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="ed257-415">Nous vous recommandons de réinitialiser après chaque exécution de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="ed257-416">Étant donné que cette charge de travail est réservée à l'insertion, chaque exécution consommera plus de mémoire, c'est pourquoi une réinitialisation est requise afin d'éviter des conditions de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="ed257-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="ed257-417">La quantité de mémoire consommée après une exécution est décrite dans la section [Utilisation de la mémoire après avoir exécuté la charge de travail](#Memoryutilizationafterrunningtheworkload).</span><span class="sxs-lookup"><span data-stu-id="ed257-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="ed257-418">Dépannage des tests lents</span><span class="sxs-lookup"><span data-stu-id="ed257-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="ed257-419">Les résultats des tests varient généralement selon le matériel, mais aussi selon le niveau de concurrence utilisé dans l'exécution du test.</span><span class="sxs-lookup"><span data-stu-id="ed257-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="ed257-420">Voici quelques pistes à explorer, si les résultats ne sont pas tels que prévu :</span><span class="sxs-lookup"><span data-stu-id="ed257-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="ed257-421">Nombre de transactions simultanées : lors de l'exécution de la charge de travail sur un seul thread, le gain de performances avec [!INCLUDE[hek_2](../includes/hek-2-md.md)] sera probablement inférieur à 2X.</span><span class="sxs-lookup"><span data-stu-id="ed257-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="ed257-422">La contention de verrou n'est un problème que si le niveau de concurrence est élevé.</span><span class="sxs-lookup"><span data-stu-id="ed257-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="ed257-423">Nombre faible de noyaux disponibles pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: cela signifie qu'il y aura un niveau de concurrence faible dans le système, car il ne peut y avoir qu'autant de transactions simultanée en cours d'exécution qu'il y a de noyaux disponibles pour SQL.</span><span class="sxs-lookup"><span data-stu-id="ed257-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="ed257-424">Symptôme : si l'utilisation de l'UC est élevée lors de l'exécution de la charge de travail sur les tables sur disque, cela signifie qu'il n'y a pas beaucoup de contentions, et donc qu'il n'y a pas de concurrence.</span><span class="sxs-lookup"><span data-stu-id="ed257-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="ed257-425">Vitesse du lecteur de journal : si le lecteur de journal n’arrive pas à suivre le débit des transactions dans le système, la charge de travail devient un goulot d’étranglement dans les E/S du journal.</span><span class="sxs-lookup"><span data-stu-id="ed257-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="ed257-426">Bien que la journalisation soit plus efficace avec [!INCLUDE[hek_2](../includes/hek-2-md.md)], si le journal des E/S est congestionné, le gain de performance potentiel est limité.</span><span class="sxs-lookup"><span data-stu-id="ed257-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="ed257-427">Symptôme : si l'utilisation de l'UC n'est pas proche de 100 % ou varie beaucoup pendant l'exécution de la charge de travail sur les tables optimisées en mémoire, il est possible qu'il existe un goulot d'étranglement du journal des E/S.</span><span class="sxs-lookup"><span data-stu-id="ed257-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="ed257-428">Cela peut être vérifié en ouvrant le moniteur de ressource et en examinant la longueur de la file d'attente du lecteur de journalisation.</span><span class="sxs-lookup"><span data-stu-id="ed257-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="ed257-429">Utilisation de la mémoire et de l’espace disque dans l’exemple</span><span class="sxs-lookup"><span data-stu-id="ed257-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="ed257-430">Vous trouverez ci-dessous la description de ce à quoi vous devez vous attendre en termes d'utilisation de la mémoire et de l'espace disque pour l'exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="ed257-431">Nous présentons également les résultats obtenus pour un serveur de test avec 16 noyaux logiques.</span><span class="sxs-lookup"><span data-stu-id="ed257-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="ed257-432">Utilisation de la mémoire pour les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="ed257-433">Utilisation générale de la base de données</span><span class="sxs-lookup"><span data-stu-id="ed257-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="ed257-434">La requête suivante peut être utilisée pour obtenir l'utilisation totale de mémoire pour [!INCLUDE[hek_2](../includes/hek-2-md.md)] dans le système.</span><span class="sxs-lookup"><span data-stu-id="ed257-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="ed257-435">Instantané de la base de données juste après sa création :</span><span class="sxs-lookup"><span data-stu-id="ed257-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-436">**type**</span><span class="sxs-lookup"><span data-stu-id="ed257-436">**type**</span></span>|<span data-ttu-id="ed257-437">**name**</span><span class="sxs-lookup"><span data-stu-id="ed257-437">**name**</span></span>|<span data-ttu-id="ed257-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ed257-438">**pages_MB**</span></span>|  
|<span data-ttu-id="ed257-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-440">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-440">Default</span></span>|<span data-ttu-id="ed257-441">94</span><span class="sxs-lookup"><span data-stu-id="ed257-441">94</span></span>|  
|<span data-ttu-id="ed257-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ed257-443">DB_ID_5</span></span>|<span data-ttu-id="ed257-444">877</span><span class="sxs-lookup"><span data-stu-id="ed257-444">877</span></span>|  
|<span data-ttu-id="ed257-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-446">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-446">Default</span></span>|<span data-ttu-id="ed257-447">0</span><span class="sxs-lookup"><span data-stu-id="ed257-447">0</span></span>|  
|<span data-ttu-id="ed257-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-449">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-449">Default</span></span>|<span data-ttu-id="ed257-450">0</span><span class="sxs-lookup"><span data-stu-id="ed257-450">0</span></span>|  
  
 <span data-ttu-id="ed257-451">Les régisseurs de mémoire par défaut contiennent les structures de mémoire à l'échelle du système et sont relativement petits.</span><span class="sxs-lookup"><span data-stu-id="ed257-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="ed257-452">Le régisseur de mémoire de la base de données utilisateur, dans ce cas la base de données dont l'ID est 5, a une taille d'environ 900 Mo.</span><span class="sxs-lookup"><span data-stu-id="ed257-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="ed257-453">Utilisation de la mémoire par table</span><span class="sxs-lookup"><span data-stu-id="ed257-453">Memory utilization per table</span></span>  
 <span data-ttu-id="ed257-454">La requête suivante peut être utilisée pour explorer l'utilisation de la mémoire des différentes tables et de leurs index :</span><span class="sxs-lookup"><span data-stu-id="ed257-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="ed257-455">L'exemple suivant indique les résultats de cette requête pour une nouvelle installation de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-456">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="ed257-456">**Table Name**</span></span>|<span data-ttu-id="ed257-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="ed257-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="ed257-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="ed257-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="ed257-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="ed257-460">64</span><span class="sxs-lookup"><span data-stu-id="ed257-460">64</span></span>|<span data-ttu-id="ed257-461">3840</span><span class="sxs-lookup"><span data-stu-id="ed257-461">3840</span></span>|  
|<span data-ttu-id="ed257-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="ed257-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="ed257-463">1984</span><span class="sxs-lookup"><span data-stu-id="ed257-463">1984</span></span>|<span data-ttu-id="ed257-464">5504</span><span class="sxs-lookup"><span data-stu-id="ed257-464">5504</span></span>|  
|<span data-ttu-id="ed257-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="ed257-466">15316</span><span class="sxs-lookup"><span data-stu-id="ed257-466">15316</span></span>|<span data-ttu-id="ed257-467">663552</span><span class="sxs-lookup"><span data-stu-id="ed257-467">663552</span></span>|  
|<span data-ttu-id="ed257-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ed257-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="ed257-469">64</span><span class="sxs-lookup"><span data-stu-id="ed257-469">64</span></span>|<span data-ttu-id="ed257-470">10432</span><span class="sxs-lookup"><span data-stu-id="ed257-470">10432</span></span>|  
|<span data-ttu-id="ed257-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="ed257-472">3</span><span class="sxs-lookup"><span data-stu-id="ed257-472">3</span></span>|<span data-ttu-id="ed257-473">8 192</span><span class="sxs-lookup"><span data-stu-id="ed257-473">8192</span></span>|  
|<span data-ttu-id="ed257-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="ed257-475">7168</span><span class="sxs-lookup"><span data-stu-id="ed257-475">7168</span></span>|<span data-ttu-id="ed257-476">147456</span><span class="sxs-lookup"><span data-stu-id="ed257-476">147456</span></span>|  
|<span data-ttu-id="ed257-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-477">Product_inmem</span></span>|<span data-ttu-id="ed257-478">124</span><span class="sxs-lookup"><span data-stu-id="ed257-478">124</span></span>|<span data-ttu-id="ed257-479">12352</span><span class="sxs-lookup"><span data-stu-id="ed257-479">12352</span></span>|  
  
 <span data-ttu-id="ed257-480">Comme vous pouvez le voir, les tables sont assez petites : SalesOrderHeader_inmem a une taille d'environ 7 Mo, et SalesOrderDetail_inmem a une taille d'environ 15 Mo.</span><span class="sxs-lookup"><span data-stu-id="ed257-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="ed257-481">Ce qui est frappant ici est la taille de la mémoire allouée aux index, par rapport à la taille des données de table.</span><span class="sxs-lookup"><span data-stu-id="ed257-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="ed257-482">Cela est dû au fait que les index de hachage de l'exemple sont prédimensionnés pour contenir plus de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="ed257-483">Notez que les index de hachage ont une taille fixe, par conséquent, leur taille n'augmente pas selon la taille des données de la table.</span><span class="sxs-lookup"><span data-stu-id="ed257-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="ed257-484">Utilisation de la mémoire après avoir exécuté la charge de travail</span><span class="sxs-lookup"><span data-stu-id="ed257-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="ed257-485">Après l'insertion de 10 millions de commandes, l'utilisation globale de la mémoire devrait s'apparenter à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ed257-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-486">**type**</span><span class="sxs-lookup"><span data-stu-id="ed257-486">**type**</span></span>|<span data-ttu-id="ed257-487">**name**</span><span class="sxs-lookup"><span data-stu-id="ed257-487">**name**</span></span>|<span data-ttu-id="ed257-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ed257-488">**pages_MB**</span></span>|  
|<span data-ttu-id="ed257-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-490">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-490">Default</span></span>|<span data-ttu-id="ed257-491">146</span><span class="sxs-lookup"><span data-stu-id="ed257-491">146</span></span>|  
|<span data-ttu-id="ed257-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ed257-493">DB_ID_5</span></span>|<span data-ttu-id="ed257-494">7374</span><span class="sxs-lookup"><span data-stu-id="ed257-494">7374</span></span>|  
|<span data-ttu-id="ed257-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-496">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-496">Default</span></span>|<span data-ttu-id="ed257-497">0</span><span class="sxs-lookup"><span data-stu-id="ed257-497">0</span></span>|  
|<span data-ttu-id="ed257-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-499">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-499">Default</span></span>|<span data-ttu-id="ed257-500">0</span><span class="sxs-lookup"><span data-stu-id="ed257-500">0</span></span>|  
  
 <span data-ttu-id="ed257-501">Comme vous pouvez le voir, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilise un bit sous 8 Go pour les tables optimisées en mémoire et les index dans l'exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="ed257-502">Voici l'utilisation de la mémoire détaillée par table après l'exécution d'un exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-503">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="ed257-503">**Table Name**</span></span>|<span data-ttu-id="ed257-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="ed257-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="ed257-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="ed257-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="ed257-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="ed257-507">5113761</span><span class="sxs-lookup"><span data-stu-id="ed257-507">5113761</span></span>|<span data-ttu-id="ed257-508">663552</span><span class="sxs-lookup"><span data-stu-id="ed257-508">663552</span></span>|  
|<span data-ttu-id="ed257-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="ed257-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="ed257-510">64</span><span class="sxs-lookup"><span data-stu-id="ed257-510">64</span></span>|<span data-ttu-id="ed257-511">10368</span><span class="sxs-lookup"><span data-stu-id="ed257-511">10368</span></span>|  
|<span data-ttu-id="ed257-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="ed257-513">2</span><span class="sxs-lookup"><span data-stu-id="ed257-513">2</span></span>|<span data-ttu-id="ed257-514">8 192</span><span class="sxs-lookup"><span data-stu-id="ed257-514">8192</span></span>|  
|<span data-ttu-id="ed257-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="ed257-516">1575679</span><span class="sxs-lookup"><span data-stu-id="ed257-516">1575679</span></span>|<span data-ttu-id="ed257-517">147456</span><span class="sxs-lookup"><span data-stu-id="ed257-517">147456</span></span>|  
|<span data-ttu-id="ed257-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-518">Product_inmem</span></span>|<span data-ttu-id="ed257-519">111</span><span class="sxs-lookup"><span data-stu-id="ed257-519">111</span></span>|<span data-ttu-id="ed257-520">12032</span><span class="sxs-lookup"><span data-stu-id="ed257-520">12032</span></span>|  
|<span data-ttu-id="ed257-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="ed257-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="ed257-522">64</span><span class="sxs-lookup"><span data-stu-id="ed257-522">64</span></span>|<span data-ttu-id="ed257-523">3712</span><span class="sxs-lookup"><span data-stu-id="ed257-523">3712</span></span>|  
|<span data-ttu-id="ed257-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="ed257-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="ed257-525">1984</span><span class="sxs-lookup"><span data-stu-id="ed257-525">1984</span></span>|<span data-ttu-id="ed257-526">5504</span><span class="sxs-lookup"><span data-stu-id="ed257-526">5504</span></span>|  
  
 <span data-ttu-id="ed257-527">Nous pouvons voir un total d'environ 6,5 Go de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="ed257-528">Notez que la taille des index sur la table SalesOrderHeader_inmem et SalesOrderDetail_inmem est la même que la taille des index avant d'insérer les commandes.</span><span class="sxs-lookup"><span data-stu-id="ed257-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="ed257-529">La taille de l'index n'a pas changé car les deux tables utilisent des index de hachage, qui sont statiques.</span><span class="sxs-lookup"><span data-stu-id="ed257-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="ed257-530">Après la réinitialisation de la démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-530">After demo reset</span></span>  
 <span data-ttu-id="ed257-531">La procédure stockée Demo.usp_DemoReset peut être utilisée pour réinitialiser la démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="ed257-532">Elle supprime les données dans les tables SalesOrderHeader_inmem et SalesOrderDetail_inmem, puis réinsère les données à partir des tables d'origine SalesOrderHeader et SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="ed257-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="ed257-533">Cependant, même si les lignes des tables ont été supprimées, cela ne signifie pas pour autant que la mémoire est immédiatement récupérée.</span><span class="sxs-lookup"><span data-stu-id="ed257-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="ed257-534">récupère la mémoire des lignes supprimées dans les tables optimisées en mémoire en arrière-plan, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ed257-534">reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="ed257-535">Vous verrez qu'immédiatement après la réinitialisation de la démonstration, sans charge de travail transactionnelle sur le système, la mémoire des lignes supprimées n'est pas encore récupérée :</span><span class="sxs-lookup"><span data-stu-id="ed257-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-536">**type**</span><span class="sxs-lookup"><span data-stu-id="ed257-536">**type**</span></span>|<span data-ttu-id="ed257-537">**name**</span><span class="sxs-lookup"><span data-stu-id="ed257-537">**name**</span></span>|<span data-ttu-id="ed257-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ed257-538">**pages_MB**</span></span>|  
|<span data-ttu-id="ed257-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-540">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-540">Default</span></span>|<span data-ttu-id="ed257-541">2261</span><span class="sxs-lookup"><span data-stu-id="ed257-541">2261</span></span>|  
|<span data-ttu-id="ed257-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ed257-543">DB_ID_5</span></span>|<span data-ttu-id="ed257-544">7396</span><span class="sxs-lookup"><span data-stu-id="ed257-544">7396</span></span>|  
|<span data-ttu-id="ed257-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-546">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-546">Default</span></span>|<span data-ttu-id="ed257-547">0</span><span class="sxs-lookup"><span data-stu-id="ed257-547">0</span></span>|  
|<span data-ttu-id="ed257-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-549">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-549">Default</span></span>|<span data-ttu-id="ed257-550">0</span><span class="sxs-lookup"><span data-stu-id="ed257-550">0</span></span>|  
  
 <span data-ttu-id="ed257-551">C'est le comportement attendu : la mémoire est récupérée lorsque la charge de travail transactionnelle s'exécute.</span><span class="sxs-lookup"><span data-stu-id="ed257-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="ed257-552">Si vous démarrez une deuxième exécution de la charge de travail de démonstration, vous verrez que l'utilisation de la mémoire diminue au début, au fur et à mesure que les lignes précédemment supprimées sont nettoyées.</span><span class="sxs-lookup"><span data-stu-id="ed257-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="ed257-553">À un certain moment, la taille de la mémoire augmentera de nouveau, jusqu'à ce que la charge de travail soit terminée.</span><span class="sxs-lookup"><span data-stu-id="ed257-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="ed257-554">Une fois que les 10 millions de lignes ont été insérées après la réinitialisation de la démonstration, l'utilisation de la mémoire sera très similaire à l'utilisation après la première exécution.</span><span class="sxs-lookup"><span data-stu-id="ed257-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="ed257-555">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="ed257-556">**type**</span><span class="sxs-lookup"><span data-stu-id="ed257-556">**type**</span></span>|<span data-ttu-id="ed257-557">**name**</span><span class="sxs-lookup"><span data-stu-id="ed257-557">**name**</span></span>|<span data-ttu-id="ed257-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="ed257-558">**pages_MB**</span></span>|  
|<span data-ttu-id="ed257-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-560">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-560">Default</span></span>|<span data-ttu-id="ed257-561">1863</span><span class="sxs-lookup"><span data-stu-id="ed257-561">1863</span></span>|  
|<span data-ttu-id="ed257-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="ed257-563">DB_ID_5</span></span>|<span data-ttu-id="ed257-564">7390</span><span class="sxs-lookup"><span data-stu-id="ed257-564">7390</span></span>|  
|<span data-ttu-id="ed257-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-566">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-566">Default</span></span>|<span data-ttu-id="ed257-567">0</span><span class="sxs-lookup"><span data-stu-id="ed257-567">0</span></span>|  
|<span data-ttu-id="ed257-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="ed257-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="ed257-569">Default</span><span class="sxs-lookup"><span data-stu-id="ed257-569">Default</span></span>|<span data-ttu-id="ed257-570">0</span><span class="sxs-lookup"><span data-stu-id="ed257-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="ed257-571">Utilisation du disque pour les tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="ed257-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="ed257-572">La taille globale sur disque des fichiers de point de contrôle d'une base de données à un moment donné peut être récupérée à l'aide de la requête :</span><span class="sxs-lookup"><span data-stu-id="ed257-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="ed257-573">InitialState</span><span class="sxs-lookup"><span data-stu-id="ed257-573">Initial state</span></span>  
 <span data-ttu-id="ed257-574">Quand les exemples de groupe de fichiers et de tables à mémoire optimisée sont initialement créés, un certain nombre de fichiers de point de contrôle sont créés au préalable et le système commence à les remplir. Le nombre de fichiers de point de contrôle créés au préalable dépend du nombre de processeurs logiques dans le système.</span><span class="sxs-lookup"><span data-stu-id="ed257-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="ed257-575">Étant donné que cet exemple a une taille très petite au début, les fichiers créés au préalable seront vides après la création initiale.</span><span class="sxs-lookup"><span data-stu-id="ed257-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="ed257-576">Voici la taille initiale sur disque de l'exemple sur un ordinateur doté de 16 processeurs logiques :</span><span class="sxs-lookup"><span data-stu-id="ed257-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ed257-577">**Taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ed257-578">2312</span><span class="sxs-lookup"><span data-stu-id="ed257-578">2312</span></span>|  
  
 <span data-ttu-id="ed257-579">Comme vous pouvez le voir, il y a un grand écart entre la taille sur disque des fichiers de point de contrôle, qui est de 2,3 Go, et la taille réelle des données, proche de 30 Mo.</span><span class="sxs-lookup"><span data-stu-id="ed257-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="ed257-580">Pour analyser de plus près la raison de l'utilisation de l'espace disque, vous pouvez utiliser la requête suivante,</span><span class="sxs-lookup"><span data-stu-id="ed257-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="ed257-581">La taille du disque retournée par cette requête est approximative pour les fichiers ayant l'état 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE) ou 7 (TOMBSTONE).</span><span class="sxs-lookup"><span data-stu-id="ed257-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="ed257-582">Pour l'état initial de l'exemple, le résultat sera similaire à ce qui suit pour un serveur avec 16 processeurs logiques :</span><span class="sxs-lookup"><span data-stu-id="ed257-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ed257-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-583">**state_desc**</span></span>|<span data-ttu-id="ed257-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-584">**file_type_desc**</span></span>|<span data-ttu-id="ed257-585">**count**</span><span class="sxs-lookup"><span data-stu-id="ed257-585">**count**</span></span>|<span data-ttu-id="ed257-586">**taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ed257-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-587">PRECREATED</span></span>|<span data-ttu-id="ed257-588">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-588">DATA</span></span>|<span data-ttu-id="ed257-589">16</span><span class="sxs-lookup"><span data-stu-id="ed257-589">16</span></span>|<span data-ttu-id="ed257-590">2 048</span><span class="sxs-lookup"><span data-stu-id="ed257-590">2048</span></span>|  
|<span data-ttu-id="ed257-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-591">PRECREATED</span></span>|<span data-ttu-id="ed257-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-592">DELTA</span></span>|<span data-ttu-id="ed257-593">16</span><span class="sxs-lookup"><span data-stu-id="ed257-593">16</span></span>|<span data-ttu-id="ed257-594">128</span><span class="sxs-lookup"><span data-stu-id="ed257-594">128</span></span>|  
|<span data-ttu-id="ed257-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-596">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-596">DATA</span></span>|<span data-ttu-id="ed257-597">1</span><span class="sxs-lookup"><span data-stu-id="ed257-597">1</span></span>|<span data-ttu-id="ed257-598">128</span><span class="sxs-lookup"><span data-stu-id="ed257-598">128</span></span>|  
|<span data-ttu-id="ed257-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-600">DELTA</span></span>|<span data-ttu-id="ed257-601">1</span><span class="sxs-lookup"><span data-stu-id="ed257-601">1</span></span>|<span data-ttu-id="ed257-602">8</span><span class="sxs-lookup"><span data-stu-id="ed257-602">8</span></span>|  
  
 <span data-ttu-id="ed257-603">Comme vous pouvez le voir, la majeure partie de l'espace est utilisé par les fichiers de données et delta précréés.</span><span class="sxs-lookup"><span data-stu-id="ed257-603">As you can see, most of the space is used by precreated data and delta files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="ed257-604">créé au préalable une paire de fichiers (données, delta) par processeur logique.</span><span class="sxs-lookup"><span data-stu-id="ed257-604">pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="ed257-605">En outre, les fichiers de données ont une taille prédimensionnée de 128 Mo, et les fichiers delta de 8 Mo, afin d'optimiser l'insertion des données dans ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="ed257-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="ed257-606">Les données réelles dans les tables optimisées en mémoire se trouvent dans un seul fichier de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="ed257-607">Après l'exécution de la charge de travail</span><span class="sxs-lookup"><span data-stu-id="ed257-607">After running the workload</span></span>  
 <span data-ttu-id="ed257-608">Après une seule exécution de test qui insère 10 millions de commandes, la taille totale sur disque ressemble à ce qui suit (pour un serveur de test avec 16 noyaux) :</span><span class="sxs-lookup"><span data-stu-id="ed257-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ed257-609">**Taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ed257-610">8828</span><span class="sxs-lookup"><span data-stu-id="ed257-610">8828</span></span>|  
  
 <span data-ttu-id="ed257-611">La taille sur disque est proche de 9 Go, ce qui est proche de la taille en mémoire des données.</span><span class="sxs-lookup"><span data-stu-id="ed257-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="ed257-612">Analysons plus en détail les tailles des fichiers de point de contrôle entre les différents états :</span><span class="sxs-lookup"><span data-stu-id="ed257-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ed257-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-613">**state_desc**</span></span>|<span data-ttu-id="ed257-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-614">**file_type_desc**</span></span>|<span data-ttu-id="ed257-615">**count**</span><span class="sxs-lookup"><span data-stu-id="ed257-615">**count**</span></span>|<span data-ttu-id="ed257-616">**taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ed257-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-617">PRECREATED</span></span>|<span data-ttu-id="ed257-618">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-618">DATA</span></span>|<span data-ttu-id="ed257-619">16</span><span class="sxs-lookup"><span data-stu-id="ed257-619">16</span></span>|<span data-ttu-id="ed257-620">2 048</span><span class="sxs-lookup"><span data-stu-id="ed257-620">2048</span></span>|  
|<span data-ttu-id="ed257-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-621">PRECREATED</span></span>|<span data-ttu-id="ed257-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-622">DELTA</span></span>|<span data-ttu-id="ed257-623">16</span><span class="sxs-lookup"><span data-stu-id="ed257-623">16</span></span>|<span data-ttu-id="ed257-624">128</span><span class="sxs-lookup"><span data-stu-id="ed257-624">128</span></span>|  
|<span data-ttu-id="ed257-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-626">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-626">DATA</span></span>|<span data-ttu-id="ed257-627">1</span><span class="sxs-lookup"><span data-stu-id="ed257-627">1</span></span>|<span data-ttu-id="ed257-628">128</span><span class="sxs-lookup"><span data-stu-id="ed257-628">128</span></span>|  
|<span data-ttu-id="ed257-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-630">DELTA</span></span>|<span data-ttu-id="ed257-631">1</span><span class="sxs-lookup"><span data-stu-id="ed257-631">1</span></span>|<span data-ttu-id="ed257-632">8</span><span class="sxs-lookup"><span data-stu-id="ed257-632">8</span></span>|  
  
 <span data-ttu-id="ed257-633">Nous avons toujours 16 paires de fichiers précréés, prêtes au fur et à mesure que les points de contrôle se ferment.</span><span class="sxs-lookup"><span data-stu-id="ed257-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="ed257-634">Il y a une paire en cours de création, utilisée tant que le point de contrôle actif n'est pas fermé.</span><span class="sxs-lookup"><span data-stu-id="ed257-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="ed257-635">Avec les fichiers de point de contrôle en cours d'utilisation, cela donne environ 6,5 Go d'utilisation du disque pour 6,5 Go de données en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ed257-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="ed257-636">N'oubliez pas que les index ne sont pas conservés sur le disque, donc, dans ce cas, la taille globale sur le disque est plus petite que la taille de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="ed257-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="ed257-637">Après la réinitialisation de la démonstration</span><span class="sxs-lookup"><span data-stu-id="ed257-637">After demo reset</span></span>  
 <span data-ttu-id="ed257-638">Après la réinitialisation de la démonstration, l'espace disque n'est pas libéré immédiatement s'il n'y a pas de charge de travail transactionnelle sur le système, et s'il n'y a pas de points de contrôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed257-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="ed257-639">Pour que les fichiers de point de contrôle passent par les différentes étapes et soient inévitablement supprimés, plusieurs points de contrôle et événements de troncation du journal doivent se produire, pour initialiser la fusion des fichiers de point de contrôle, ainsi que pour initialiser le garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ed257-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="ed257-640">Cela se produit automatiquement si vous avez une charge de travail transactionnelle dans le système (et si vous effectuez des sauvegardes de journaux régulières, dans le cas où vous utilisez le mode de restauration complète), mais pas lorsque le système est inactif, comme dans un scénario de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="ed257-641">Dans l'exemple, après la réinitialisation de la démonstration, vous obtiendrez un résultat similaire au suivant.</span><span class="sxs-lookup"><span data-stu-id="ed257-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="ed257-642">**Taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="ed257-643">11839</span><span class="sxs-lookup"><span data-stu-id="ed257-643">11839</span></span>|  
  
 <span data-ttu-id="ed257-644">À presque 12 Go, la taille dépasse manifestement les 9 Go que nous avions avant le réinitialisation de la démonstration.</span><span class="sxs-lookup"><span data-stu-id="ed257-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="ed257-645">Cela est dû au fait que certaines fusions de fichiers de point de contrôle ont commencé, tandis que certaines cibles de fusion n'ont pas encore été installées, et que certains fichiers sources de fusion n'ont pas encore été nettoyés, comme vous pouvez le voir à partir des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ed257-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ed257-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-646">**state_desc**</span></span>|<span data-ttu-id="ed257-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-647">**file_type_desc**</span></span>|<span data-ttu-id="ed257-648">**count**</span><span class="sxs-lookup"><span data-stu-id="ed257-648">**count**</span></span>|<span data-ttu-id="ed257-649">**taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ed257-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-650">PRECREATED</span></span>|<span data-ttu-id="ed257-651">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-651">DATA</span></span>|<span data-ttu-id="ed257-652">16</span><span class="sxs-lookup"><span data-stu-id="ed257-652">16</span></span>|<span data-ttu-id="ed257-653">2 048</span><span class="sxs-lookup"><span data-stu-id="ed257-653">2048</span></span>|  
|<span data-ttu-id="ed257-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-654">PRECREATED</span></span>|<span data-ttu-id="ed257-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-655">DELTA</span></span>|<span data-ttu-id="ed257-656">16</span><span class="sxs-lookup"><span data-stu-id="ed257-656">16</span></span>|<span data-ttu-id="ed257-657">128</span><span class="sxs-lookup"><span data-stu-id="ed257-657">128</span></span>|  
|<span data-ttu-id="ed257-658">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ed257-658">ACTIVE</span></span>|<span data-ttu-id="ed257-659">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-659">DATA</span></span>|<span data-ttu-id="ed257-660">38</span><span class="sxs-lookup"><span data-stu-id="ed257-660">38</span></span>|<span data-ttu-id="ed257-661">5152</span><span class="sxs-lookup"><span data-stu-id="ed257-661">5152</span></span>|  
|<span data-ttu-id="ed257-662">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ed257-662">ACTIVE</span></span>|<span data-ttu-id="ed257-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-663">DELTA</span></span>|<span data-ttu-id="ed257-664">38</span><span class="sxs-lookup"><span data-stu-id="ed257-664">38</span></span>|<span data-ttu-id="ed257-665">1331</span><span class="sxs-lookup"><span data-stu-id="ed257-665">1331</span></span>|  
|<span data-ttu-id="ed257-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="ed257-666">MERGE TARGET</span></span>|<span data-ttu-id="ed257-667">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-667">DATA</span></span>|<span data-ttu-id="ed257-668">7</span><span class="sxs-lookup"><span data-stu-id="ed257-668">7</span></span>|<span data-ttu-id="ed257-669">896</span><span class="sxs-lookup"><span data-stu-id="ed257-669">896</span></span>|  
|<span data-ttu-id="ed257-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="ed257-670">MERGE TARGET</span></span>|<span data-ttu-id="ed257-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-671">DELTA</span></span>|<span data-ttu-id="ed257-672">7</span><span class="sxs-lookup"><span data-stu-id="ed257-672">7</span></span>|<span data-ttu-id="ed257-673">56</span><span class="sxs-lookup"><span data-stu-id="ed257-673">56</span></span>|  
|<span data-ttu-id="ed257-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="ed257-674">MERGED SOURCE</span></span>|<span data-ttu-id="ed257-675">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-675">DATA</span></span>|<span data-ttu-id="ed257-676">13</span><span class="sxs-lookup"><span data-stu-id="ed257-676">13</span></span>|<span data-ttu-id="ed257-677">1772</span><span class="sxs-lookup"><span data-stu-id="ed257-677">1772</span></span>|  
|<span data-ttu-id="ed257-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="ed257-678">MERGED SOURCE</span></span>|<span data-ttu-id="ed257-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-679">DELTA</span></span>|<span data-ttu-id="ed257-680">13</span><span class="sxs-lookup"><span data-stu-id="ed257-680">13</span></span>|<span data-ttu-id="ed257-681">455</span><span class="sxs-lookup"><span data-stu-id="ed257-681">455</span></span>|  
  
 <span data-ttu-id="ed257-682">Les cibles de fusion sont installées et la source fusionnée est nettoyée au fur et à mesure que l'activité transactionnelle s'exécute dans le système.</span><span class="sxs-lookup"><span data-stu-id="ed257-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="ed257-683">Après une deuxième exécution de la charge de travail de démonstration, et l'insertion de 10 millions de commandes client après la réinitialisation de la démonstration, vous constaterez que les fichiers construits lors de la première exécution de la charge de travail ont été nettoyés.</span><span class="sxs-lookup"><span data-stu-id="ed257-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="ed257-684">Si vous exécutez la requête ci-dessus plusieurs fois pendant que la charge de travail s'exécute, vous verrez les fichiers de point de contrôle passer à travers les différentes étapes.</span><span class="sxs-lookup"><span data-stu-id="ed257-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="ed257-685">Après la deuxième exécution de la charge de travail et l'insertion de 10 millions de commandes, vous verrez que l'utilisation du disque est très similaire, mais pas nécessairement identique, à celle constatée après la première exécution, car le système est dynamique par nature.</span><span class="sxs-lookup"><span data-stu-id="ed257-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="ed257-686">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed257-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ed257-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-687">**state_desc**</span></span>|<span data-ttu-id="ed257-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="ed257-688">**file_type_desc**</span></span>|<span data-ttu-id="ed257-689">**count**</span><span class="sxs-lookup"><span data-stu-id="ed257-689">**count**</span></span>|<span data-ttu-id="ed257-690">**taille sur disque en Mo**</span><span class="sxs-lookup"><span data-stu-id="ed257-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="ed257-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-691">PRECREATED</span></span>|<span data-ttu-id="ed257-692">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-692">DATA</span></span>|<span data-ttu-id="ed257-693">16</span><span class="sxs-lookup"><span data-stu-id="ed257-693">16</span></span>|<span data-ttu-id="ed257-694">2 048</span><span class="sxs-lookup"><span data-stu-id="ed257-694">2048</span></span>|  
|<span data-ttu-id="ed257-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="ed257-695">PRECREATED</span></span>|<span data-ttu-id="ed257-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-696">DELTA</span></span>|<span data-ttu-id="ed257-697">16</span><span class="sxs-lookup"><span data-stu-id="ed257-697">16</span></span>|<span data-ttu-id="ed257-698">128</span><span class="sxs-lookup"><span data-stu-id="ed257-698">128</span></span>|  
|<span data-ttu-id="ed257-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-700">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-700">DATA</span></span>|<span data-ttu-id="ed257-701">2</span><span class="sxs-lookup"><span data-stu-id="ed257-701">2</span></span>|<span data-ttu-id="ed257-702">268</span><span class="sxs-lookup"><span data-stu-id="ed257-702">268</span></span>|  
|<span data-ttu-id="ed257-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="ed257-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="ed257-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-704">DELTA</span></span>|<span data-ttu-id="ed257-705">2</span><span class="sxs-lookup"><span data-stu-id="ed257-705">2</span></span>|<span data-ttu-id="ed257-706">16</span><span class="sxs-lookup"><span data-stu-id="ed257-706">16</span></span>|  
|<span data-ttu-id="ed257-707">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ed257-707">ACTIVE</span></span>|<span data-ttu-id="ed257-708">DATA</span><span class="sxs-lookup"><span data-stu-id="ed257-708">DATA</span></span>|<span data-ttu-id="ed257-709">41</span><span class="sxs-lookup"><span data-stu-id="ed257-709">41</span></span>|<span data-ttu-id="ed257-710">5608</span><span class="sxs-lookup"><span data-stu-id="ed257-710">5608</span></span>|  
|<span data-ttu-id="ed257-711">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="ed257-711">ACTIVE</span></span>|<span data-ttu-id="ed257-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="ed257-712">DELTA</span></span>|<span data-ttu-id="ed257-713">41</span><span class="sxs-lookup"><span data-stu-id="ed257-713">41</span></span>|<span data-ttu-id="ed257-714">328</span><span class="sxs-lookup"><span data-stu-id="ed257-714">328</span></span>|  
  
 <span data-ttu-id="ed257-715">Dans ce cas, il existe deux paires de fichiers de point de contrôle avec l’état « under construction », signifiant que plusieurs paires de fichiers ont été déplacées vers l’état « under construction », probablement en raison du haut niveau de concurrence dans la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="ed257-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="ed257-716">Plusieurs threads simultanés ont nécessité une nouvelle paire de fichiers en même temps ; par conséquent, une paire est passée de l’état « precreated » à l’état « under construction ».</span><span class="sxs-lookup"><span data-stu-id="ed257-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed257-717">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed257-717">See Also</span></span>  
 [<span data-ttu-id="ed257-718">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="ed257-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
