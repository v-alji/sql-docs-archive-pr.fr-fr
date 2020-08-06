---
title: Attachement et détachement de bases de données DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602312"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="902d6-102">Attachement et détachement de bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="902d6-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="902d6-103">Cette rubrique explique comment attacher et détacher les bases de données DQS.</span><span class="sxs-lookup"><span data-stu-id="902d6-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="902d6-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="902d6-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="902d6-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="902d6-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="902d6-106">Pour obtenir la liste des limitations et restrictions, consultez [Attacher et détacher une base de données &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="902d6-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="902d6-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="902d6-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="902d6-108">Vérifiez qu'aucune activité ou aucun processus n'est en cours d'exécution dans DQS.</span><span class="sxs-lookup"><span data-stu-id="902d6-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="902d6-109">Pour ce faire, utilisez l'écran **Analyse des activités** .</span><span class="sxs-lookup"><span data-stu-id="902d6-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="902d6-110">Pour plus d'informations sur l'utilisation de cet écran, consultez [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="902d6-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="902d6-111">Assurez-vous qu'aucun utilisateur n'est connecté au [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902d6-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="902d6-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="902d6-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="902d6-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="902d6-113">Permissions</span></span>  
  
-   <span data-ttu-id="902d6-114">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe db_owner dans l'instance SQL Server pour pouvoir détacher des bases de données DQS.</span><span class="sxs-lookup"><span data-stu-id="902d6-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="902d6-115">Votre compte d'utilisateur Windows doit disposer d'une autorisation CREATE DATABASE, CREATE ANY DATABASE ou ALTER ANY DATABASE pour pouvoir attacher une base de données.</span><span class="sxs-lookup"><span data-stu-id="902d6-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="902d6-116">Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour mettre fin à toutes les activités en cours d'exécution ou arrêter tous les processus en cours d'exécution dans DQS.</span><span class="sxs-lookup"><span data-stu-id="902d6-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="902d6-117">Détacher des bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="902d6-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="902d6-118">Lorsque vous détachez une base de données DQS à l'aide de SQL Server Management Studio, les fichiers détachés restent sur votre ordinateur et peuvent être rattachés à la même instance de SQL Server ou être déplacés vers un autre serveur et être attachés à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="902d6-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="902d6-119">Les fichiers de base de données DQS sont généralement disponibles à l’emplacement suivant sur votre ordinateur Data Quality Services : C:\Program Files\Microsoft SQL Server\MSSQL12. *<Instance_Name>* \MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="902d6-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="902d6-120">Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.</span><span class="sxs-lookup"><span data-stu-id="902d6-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="902d6-121">Dans l'Explorateur d'objets, développez le nœud **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="902d6-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="902d6-122">Cliquez avec le bouton droit sur la base de données **DQS_MAIN** , pointez sur **Tâches**, puis sélectionnez **Détacher**.</span><span class="sxs-lookup"><span data-stu-id="902d6-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="902d6-123">La boîte de dialogue **Détacher la base de données** apparaît.</span><span class="sxs-lookup"><span data-stu-id="902d6-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="902d6-124">Activez la case à cocher sous la colonne **Supprimer** , puis cliquez sur **OK** pour détacher la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="902d6-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="902d6-125">Répétez les étapes 3 et 4 avec les bases de données DQS_PROJECTS et DQS_STAGING_DATA afin de les détacher.</span><span class="sxs-lookup"><span data-stu-id="902d6-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="902d6-126">Vous pouvez également détacher les bases de données DQS à l'aide d'instructions Transact-SQL avec la procédure stockée sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="902d6-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="902d6-127">Pour plus d'informations sur le détachement de bases de données à l'aide d'instructions Transact-SQL, consultez [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) dans [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="902d6-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="902d6-128">Attacher des bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="902d6-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="902d6-129">Utilisez les instructions suivantes pour attacher une base de données DQS à la même instance SQL Server (depuis laquelle vous avez procédé au détachement) ou à une autre instance de SQL Server où [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="902d6-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="902d6-130">Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.</span><span class="sxs-lookup"><span data-stu-id="902d6-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="902d6-131">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur **Bases de données**, puis sélectionnez **Attacher**.</span><span class="sxs-lookup"><span data-stu-id="902d6-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="902d6-132">La boîte de dialogue **Attacher des bases de données** apparaît.</span><span class="sxs-lookup"><span data-stu-id="902d6-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="902d6-133">Pour spécifier la base de données à attacher, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="902d6-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="902d6-134">La boîte de dialogue **Rechercher les fichiers de base de données** apparaît.</span><span class="sxs-lookup"><span data-stu-id="902d6-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="902d6-135">Sélectionnez l'unité de disque contenant la base de données et développez l'arborescence du répertoire pour rechercher et sélectionner le fichier .mdf de la base de données.</span><span class="sxs-lookup"><span data-stu-id="902d6-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="902d6-136">Par exemple, pour la base de données DQS_MAIN :</span><span class="sxs-lookup"><span data-stu-id="902d6-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="902d6-137">Le volet (inférieur) des **détails de la base de données** affiche les noms des fichiers à attacher.</span><span class="sxs-lookup"><span data-stu-id="902d6-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="902d6-138">Pour vérifier ou changer le nom du chemin d’accès d’un fichier, cliquez sur le bouton **Parcourir** ( ... ).</span><span class="sxs-lookup"><span data-stu-id="902d6-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="902d6-139">Cliquez sur **OK** pour attacher la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="902d6-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="902d6-140">Répétez les étapes 2 à 6 pour les bases de données DQS_PROJECTS et DQS_STAGING_DATA afin de les attacher.</span><span class="sxs-lookup"><span data-stu-id="902d6-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="902d6-141">Vous devez également exécuter les instructions Transact-SQL à l'étape suivante après la restauration de la base de données DQS_MAIN ; sinon, un message d'erreur s'affiche lorsque vous tentez de vous connecter à Data Quality Server à l'aide de l'application Data Quality Client et que vous ne pouvez pas vous connecter.</span><span class="sxs-lookup"><span data-stu-id="902d6-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="902d6-142">Toutefois, vous n'avez pas besoin de suivre les étapes 9 et 10 si vous venez d'attacher la base de données DQS_PROJECTS ou DQS_STAGING_DATA, et non DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="902d6-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="902d6-143">Pour exécuter les instructions Transact-SQL, dans l'Explorateur d'objets, cliquez avec le bouton droit sur le serveur et sélectionnez **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="902d6-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="902d6-144">Dans la fenêtre Éditeur de requête, copiez les instructions SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="902d6-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="902d6-145">Appuyez sur F5 pour exécuter les instructions.</span><span class="sxs-lookup"><span data-stu-id="902d6-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="902d6-146">Consultez le volet de résultats pour vérifier que les instructions ont été correctement exécutées.</span><span class="sxs-lookup"><span data-stu-id="902d6-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="902d6-147">Vous recevrez le message suivant : `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="902d6-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="902d6-148">Connectez-vous à Data Quality Server à l'aide de l'application Data Quality Client afin de vérifier que vous pouvez vous connecter correctement.</span><span class="sxs-lookup"><span data-stu-id="902d6-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="902d6-149">Vous pouvez également attacher des bases de données DQS à l'aide d'instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="902d6-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="902d6-150">Pour plus d'informations sur l'attachement de bases de données à l'aide d'instructions Transact-SQL, consultez [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) dans [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="902d6-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902d6-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="902d6-151">See Also</span></span>  
 [<span data-ttu-id="902d6-152">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="902d6-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
