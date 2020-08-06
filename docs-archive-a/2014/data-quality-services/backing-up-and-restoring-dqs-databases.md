---
title: Sauvegarde et restauration de bases de données DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3091f62-2234-4a80-a615-cf14c2a1da85
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 489664d8c64a99d1ea4dcec79b93e5b01b28f649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601721"
---
# <a name="backing-up-and-restoring-dqs-databases"></a><span data-ttu-id="5d76a-102">Sauvegarde et restauration de bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="5d76a-102">Backing Up and Restoring DQS Databases</span></span>
  <span data-ttu-id="5d76a-103">Cette rubrique explique comment sauvegarder et restaurer les bases de données DQS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-103">This topic describes how to back up and restore the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d76a-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5d76a-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5d76a-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5d76a-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="5d76a-106">Vous devez connaître ou mémoriser le mot de passe de la clé principale de base de données que vous avez fournie pendant l'installation du serveur DQS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-106">You must know or remember the password for the database master key that you provided during the DQS server installation.</span></span>  
  
-   <span data-ttu-id="5d76a-107">Vérifiez qu'aucune activité ou aucun processus n'est en cours d'exécution dans DQS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-107">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="5d76a-108">Pour ce faire, utilisez l'écran **Analyse des activités** .</span><span class="sxs-lookup"><span data-stu-id="5d76a-108">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="5d76a-109">Pour plus d'informations sur l'utilisation de cet écran, consultez [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="5d76a-109">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="5d76a-110">Assurez-vous qu'aucun utilisateur n'est connecté au serveur DQS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-110">Ensure that there are no users logged on the DQS server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d76a-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5d76a-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d76a-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5d76a-112">Permissions</span></span>  
  
-   <span data-ttu-id="5d76a-113">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe sysadmin dans l'instance de SQL Server pour effectuer les opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="5d76a-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to perform the backup and restore operations.</span></span>  
  
-   <span data-ttu-id="5d76a-114">Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour mettre fin à toutes les activités en cours d'exécution ou arrêter tous les processus en cours d'exécution dans DQS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-114">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="backup-and-restore-dqs-databases"></a><a name="BackupRestore"></a><span data-ttu-id="5d76a-115">Sauvegarder et restaurer des bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="5d76a-115">Backup and Restore DQS Databases</span></span>  
  
1.  <span data-ttu-id="5d76a-116">Démarrez Microsoft SQL Server Management Studio et connectez-vous à l'instance de SQL Server appropriée.</span><span class="sxs-lookup"><span data-stu-id="5d76a-116">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="5d76a-117">Dans l'Explorateur d'objets, développez le nœud **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="5d76a-117">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="5d76a-118">Sauvegardez la base de données DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="5d76a-118">Back up the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="5d76a-119">Pour obtenir des instructions pas à pas sur la sauvegarde d’une base de données SQL Server, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5d76a-119">For step-by-step instructions for backing a SQL Server database, see [Create a Full Database Backup &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="5d76a-120">Sauvegardez la base de données DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-120">Back up the DQS_PROJECTS database.</span></span>  
  
5.  <span data-ttu-id="5d76a-121">Sauvegardez la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="5d76a-121">Back up the DQS_MAIN database.</span></span>  
  
6.  <span data-ttu-id="5d76a-122">Déconnectez-vous de l'instance actuelle de SQL Server, et connectez-vous à l'instance de SQL Server où vous voulez restaurer ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="5d76a-122">Disconnect from the current instance of SQL Server, and connect to the SQL Server instance where you want to restore these databases.</span></span>  
  
7.  <span data-ttu-id="5d76a-123">Restaurez la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="5d76a-123">Restore DQS_MAIN database.</span></span> <span data-ttu-id="5d76a-124">Pour obtenir des instructions pas à pas sur la restauration d’une base de données SQL Server, consultez [restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="5d76a-124">For step-by-step instructions to restore a SQL Server database, see [Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span></span>  
  
8.  <span data-ttu-id="5d76a-125">Restaurez la base de données DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="5d76a-125">Restore the DQS_PROJECTS database.</span></span>  
  
9. <span data-ttu-id="5d76a-126">Restaurez la base de données DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="5d76a-126">Restore the DQS_STAGING_DATA database.</span></span>  
  
10. <span data-ttu-id="5d76a-127">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur le serveur, puis cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5d76a-127">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
11. <span data-ttu-id="5d76a-128">Dans la fenêtre de l’éditeur de requête, copiez les instructions SQL suivantes et remplacez *\<PASSWORD>* par le mot de passe que vous avez fourni pendant l’installation de DQS pour la clé principale de base de données :</span><span class="sxs-lookup"><span data-stu-id="5d76a-128">In the Query Editor window, copy the following SQL statements, and replace *\<PASSWORD>* with the password that you provided during the DQS installation for the database master key:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    EXECUTE [internal_core].[RestoreDQDatabases] '<PASSWORD>'  
    GO  
    ```  
  
12. <span data-ttu-id="5d76a-129">Appuyez sur F5 pour exécuter les instructions.</span><span class="sxs-lookup"><span data-stu-id="5d76a-129">Press F5 to execute the statements.</span></span> <span data-ttu-id="5d76a-130">Vérifiez le volet **résultats** pour vérifier que les instructions ont été exécutées avec succès.</span><span class="sxs-lookup"><span data-stu-id="5d76a-130">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d76a-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d76a-131">See Also</span></span>  
 [<span data-ttu-id="5d76a-132">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="5d76a-132">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
