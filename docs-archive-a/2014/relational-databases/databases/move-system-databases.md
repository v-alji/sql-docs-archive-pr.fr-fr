---
title: Déplacer des bases de données système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710688"
---
# <a name="move-system-databases"></a><span data-ttu-id="c32e2-102">Déplacer des bases de données système</span><span class="sxs-lookup"><span data-stu-id="c32e2-102">Move System Databases</span></span>
  <span data-ttu-id="c32e2-103">Cette rubrique décrit comment déplacer des bases de données système dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c32e2-104">Le déplacement des bases de données système peut être utile dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="c32e2-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="c32e2-105">Récupération après défaillance.</span><span class="sxs-lookup"><span data-stu-id="c32e2-105">Failure recovery.</span></span> <span data-ttu-id="c32e2-106">Par exemple, la base de données est en mode suspect ou a été fermée en raison d'une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="c32e2-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="c32e2-107">Déplacement prévu.</span><span class="sxs-lookup"><span data-stu-id="c32e2-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="c32e2-108">Déplacement en vue d'une maintenance de disque planifiée.</span><span class="sxs-lookup"><span data-stu-id="c32e2-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="c32e2-109">Les procédures ci-dessous s'appliquent au déplacement des fichiers de base de données au sein de la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c32e2-110">Pour déplacer une base de données vers une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou vers un autre serveur, utilisez les opérations de [sauvegarde et restauration](../backup-restore/back-up-and-restore-of-sql-server-databases.md) ou de [détachement et attachement](move-a-database-using-detach-and-attach-transact-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="c32e2-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="c32e2-111">Les procédures de cette rubrique requièrent le nom logique des fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="c32e2-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="c32e2-112">Pour obtenir ce nom, interrogez la colonne name dans l’affichage catalogue [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c32e2-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c32e2-113">Si vous déplacez une base de données système et que vous recréez ultérieurement la base de données master, vous devez redéplacer la base de données système car l'opération de recréation installe toutes les bases de données système à leur emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="c32e2-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a> <span data-ttu-id="c32e2-114">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c32e2-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="c32e2-115">Procédure de réadressage planifié et de maintenance de disque planifiée</span><span class="sxs-lookup"><span data-stu-id="c32e2-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="c32e2-116">Procédure de récupération d’erreur</span><span class="sxs-lookup"><span data-stu-id="c32e2-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="c32e2-117">Déplacement de la base de données Master</span><span class="sxs-lookup"><span data-stu-id="c32e2-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="c32e2-118">Déplacement de la base de données Resource</span><span class="sxs-lookup"><span data-stu-id="c32e2-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="c32e2-119">Suivi : après le déplacement de toutes les bases de données système</span><span class="sxs-lookup"><span data-stu-id="c32e2-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="c32e2-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="c32e2-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="c32e2-121">Procédure de réadressage planifié et de maintenance de disque planifiée</span><span class="sxs-lookup"><span data-stu-id="c32e2-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="c32e2-122">Pour déplacer des données ou un fichier journal d'une base de données système dans le cadre d'un réadressage planifié ou d'une opération de maintenance planifiée, suivez la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c32e2-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="c32e2-123">Cette procédure s'applique à toutes les bases de données système à l'exception des bases de données master et Resource.</span><span class="sxs-lookup"><span data-stu-id="c32e2-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="c32e2-124">Pour chaque fichier à déplacer, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="c32e2-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="c32e2-125">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou éteignez le système pour que la maintenance ait lieu.</span><span class="sxs-lookup"><span data-stu-id="c32e2-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="c32e2-126">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer les services SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="c32e2-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="c32e2-127">Déplacez le ou les fichiers vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="c32e2-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="c32e2-128">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou le serveur.</span><span class="sxs-lookup"><span data-stu-id="c32e2-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="c32e2-129">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer les services SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="c32e2-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="c32e2-130">Vérifiez le changement de fichier en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="c32e2-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="c32e2-131">Si la base de données msdb est déplacée et si l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configurée pour la [messagerie de base de données](../database-mail/database-mail.md), effectuez ces opérations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c32e2-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="c32e2-132">Assurez-vous que [!INCLUDE[ssSB](../../../includes/sssb-md.md)] est activé pour la base de données msdb en exécutant la requête ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c32e2-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="c32e2-133">Pour plus d’informations sur l’activation de [!INCLUDE[ssSB](../../../includes/sssb-md.md)], consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c32e2-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="c32e2-134">Vérifiez le bon fonctionnement de la messagerie de base de données en envoyant un message électronique de test.</span><span class="sxs-lookup"><span data-stu-id="c32e2-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="c32e2-135">Procédure de récupération après défaillance</span><span class="sxs-lookup"><span data-stu-id="c32e2-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="c32e2-136">Si un fichier doit être déplacé dans un nouvel emplacement en raison d'une défaillance matérielle, suivez la procédure décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c32e2-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="c32e2-137">Cette procédure s'applique à toutes les bases de données système à l'exception des bases de données master et Resource.</span><span class="sxs-lookup"><span data-stu-id="c32e2-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c32e2-138">Si la base de données ne démarre pas – elle est en mode suspect ou dans un état de non récupération, seuls les membres du rôle fixe sysadmin peuvent déplacer le fichier.</span><span class="sxs-lookup"><span data-stu-id="c32e2-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="c32e2-139">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si elle est démarrée.</span><span class="sxs-lookup"><span data-stu-id="c32e2-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="c32e2-140">Démarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode de récupération de la base de données master uniquement en tapant une des commandes suivantes à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="c32e2-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="c32e2-141">Les paramètres spécifiés dans ces commandes respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="c32e2-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="c32e2-142">Les commandes échouent lorsque les paramètres ne sont pas spécifiés comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="c32e2-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="c32e2-143">Dans le cas d'une instance par défaut (MSSQLSERVER), exécutez la commande ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c32e2-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="c32e2-144">Dans le cas d'une instance nommée, exécutez la commande ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c32e2-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="c32e2-145">Pour plus d'informations, consultez [Démarrer, arrêter, suspendre, reprendre, redémarrer les services SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="c32e2-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="c32e2-146">Pour chaque fichier à déplacer, utilisez les commandes **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pour exécuter l’instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="c32e2-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="c32e2-147">Pour plus d’informations sur l’utilisation de l’utilitaire **sqlcmd** , consultez [Utiliser l’utilitaire sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c32e2-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="c32e2-148">Quittez l’utilitaire **sqlcmd** ou [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="c32e2-149">Arrêtez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c32e2-150">Par exemple, exécutez `NET STOP MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="c32e2-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="c32e2-151">Déplacez le ou les fichiers vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="c32e2-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="c32e2-152">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c32e2-153">Par exemple, exécutez `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="c32e2-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="c32e2-154">Vérifiez le changement de fichier en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="c32e2-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="c32e2-155">Déplacement de la base de données master</span><span class="sxs-lookup"><span data-stu-id="c32e2-155">Moving the master Database</span></span>  
 <span data-ttu-id="c32e2-156">Pour déplacer la base de données master, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c32e2-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="c32e2-157">Dans le menu **Démarrer** , pointez successivement sur **Tous les programmes**, sur **Microsoft SQL Server**et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="c32e2-158">Dans le nœud **Services SQL Server** , cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (par exemple, **SQL Server (MSSQLSERVER)** ), puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="c32e2-159">Dans la boîte de dialogue \*\*Propriétés de SQL Server ( \*\*\*nom_instance \***)** , cliquez sur l’onglet **Paramètres de démarrage** .</span><span class="sxs-lookup"><span data-stu-id="c32e2-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="c32e2-160">Dans la zone **Paramètres existants**, sélectionnez le paramètre -d pour déplacer le fichier de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="c32e2-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="c32e2-161">Cliquez sur **Mettre à jour** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="c32e2-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="c32e2-162">Dans la zone **Spécifiez un paramètre de démarrage** , modifiez le paramètre par le nouveau chemin d’accès de la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="c32e2-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="c32e2-163">Dans la zone **Paramètres existants**, sélectionnez le paramètre -l pour déplacer le fichier journal MASTER.</span><span class="sxs-lookup"><span data-stu-id="c32e2-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="c32e2-164">Cliquez sur **Mettre à jour** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="c32e2-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="c32e2-165">Dans la zone **Spécifiez un paramètre de démarrage** , modifiez le paramètre par le nouveau chemin d’accès de la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="c32e2-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="c32e2-166">La valeur du paramètre pour le fichier de données doit suivre le paramètre `-d` et la valeur pour le fichier journal doit suivre le paramètre `-l` .</span><span class="sxs-lookup"><span data-stu-id="c32e2-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="c32e2-167">L’exemple suivant montre les valeurs des paramètres pour l’emplacement par défaut des fichiers de données de la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="c32e2-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="c32e2-168">Si le nouvel emplacement planifié pour les fichiers de données de la base de données MASTER correspond à `E:\SQLData`, les valeurs des paramètres sont modifiées comme suit :</span><span class="sxs-lookup"><span data-stu-id="c32e2-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="c32e2-169">Arrêtez l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cliquant avec le bouton droit sur le nom d’instance et en choisissant **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="c32e2-170">Déplacez les fichiers master.mdf et mastlog.ldf vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="c32e2-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="c32e2-171">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="c32e2-172">Vérifiez que la modification des fichiers a bien eu lieu pour la base de données master en exécutant la requête ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c32e2-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="c32e2-173">Déplacement de la base de données Resources</span><span class="sxs-lookup"><span data-stu-id="c32e2-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="c32e2-174">L'emplacement de la base de données est \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*><>\MSSQL\Binn\\\ .</span><span class="sxs-lookup"><span data-stu-id="c32e2-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="c32e2-175">La base de données ne peut pas être déplacée.</span><span class="sxs-lookup"><span data-stu-id="c32e2-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="c32e2-176">Suivi : Après le déplacement de toutes les bases de données système</span><span class="sxs-lookup"><span data-stu-id="c32e2-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="c32e2-177">Si vous avez déplacé toutes les bases de données système vers un même lecteur ou volume ou vers un autre serveur utilisant une lettre de lecteur différente, effectuez les mises à jour suivantes.</span><span class="sxs-lookup"><span data-stu-id="c32e2-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="c32e2-178">Modifiez le chemin d'accès du journal de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c32e2-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="c32e2-179">Si vous ne mettez pas à jour ce chemin d'accès, l'Agent SQL Server ne démarre pas.</span><span class="sxs-lookup"><span data-stu-id="c32e2-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="c32e2-180">Modifiez l'emplacement par défaut de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c32e2-180">Change the database default location.</span></span> <span data-ttu-id="c32e2-181">La création d'une base de données peut échouer si la lettre de lecteur et le chemin d'accès spécifiés comme emplacement par défaut n'existent pas.</span><span class="sxs-lookup"><span data-stu-id="c32e2-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="c32e2-182">Modifier le chemin d'accès du journal de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="c32e2-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="c32e2-183">Dans SQL Server Management Studio, dans l'Explorateur d'objets, développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="c32e2-184">Cliquez avec le bouton droit sur **Journaux d’erreurs** , puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="c32e2-185">Dans la boîte de dialogue **Configurer les journaux d'erreurs de l'Agent SQL Server** , spécifiez le nouvel emplacement du fichier SQLAGENT.OUT.</span><span class="sxs-lookup"><span data-stu-id="c32e2-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="c32e2-186">L’emplacement par défaut est C:\Program Files\Microsoft SQL Server\MSSQL12. <instance_name> \MSSQL\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="c32e2-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="c32e2-187">Modifier l'emplacement par défaut de la base de données</span><span class="sxs-lookup"><span data-stu-id="c32e2-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="c32e2-188">Dans SQL Server Management Studio, dans l’Explorateur d’objets, cliquez avec le bouton droit sur le serveur SQL Server, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c32e2-189">Dans la boîte de dialogue **Propriétés du serveur** , sélectionnez **Paramètres de base de données**.</span><span class="sxs-lookup"><span data-stu-id="c32e2-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="c32e2-190">Sous **Emplacements de la base de données par défaut**, accédez au nouvel emplacement des fichiers de données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="c32e2-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="c32e2-191">Arrêtez et démarrez le service SQL Server pour terminer la modification.</span><span class="sxs-lookup"><span data-stu-id="c32e2-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="c32e2-192">Exemples</span><span class="sxs-lookup"><span data-stu-id="c32e2-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="c32e2-193">R.</span><span class="sxs-lookup"><span data-stu-id="c32e2-193">A.</span></span> <span data-ttu-id="c32e2-194">Déplacement de la base de données tempdb</span><span class="sxs-lookup"><span data-stu-id="c32e2-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="c32e2-195">Dans l'exemple suivant, les fichiers de données et les fichiers journaux de la base de données `tempdb` sont déplacés vers un nouvel emplacement dans le cadre d'une opération planifiée.</span><span class="sxs-lookup"><span data-stu-id="c32e2-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c32e2-196">Dans la mesure où la base de données tempdb est recréée à chaque démarrage de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous n'avez pas à déplacer physiquement les fichiers de données et les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="c32e2-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="c32e2-197">Les fichiers sont créés au nouvel emplacement lorsque le service est redémarré à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="c32e2-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="c32e2-198">Tant que le service n'a pas redémarré, tempdb continue à utiliser les fichiers de données et les fichiers journaux situés à l'emplacement existant.</span><span class="sxs-lookup"><span data-stu-id="c32e2-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="c32e2-199">Déterminez les noms de fichiers logiques de la base de données `tempdb` et leur emplacement actuel sur le disque.</span><span class="sxs-lookup"><span data-stu-id="c32e2-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="c32e2-200">Modifiez l'emplacement de chaque fichier à l'aide de `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="c32e2-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="c32e2-201">Arrêtez et redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32e2-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="c32e2-202">Vérifiez que la modification des fichiers a bien eu lieu.</span><span class="sxs-lookup"><span data-stu-id="c32e2-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="c32e2-203">Supprimez les fichiers `tempdb.mdf` et `templog.ldf` de l'emplacement d'origine.</span><span class="sxs-lookup"><span data-stu-id="c32e2-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32e2-204">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c32e2-204">See Also</span></span>  
 <span data-ttu-id="c32e2-205">[Base de données Resource](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="c32e2-206">[Base de données tempdb](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="c32e2-207">[Base de données master](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="c32e2-208">[Base de données msdb](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="c32e2-209">[Base de données model](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="c32e2-210">[Déplacer des bases de données utilisateur](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="c32e2-211">[Déplacer des fichiers de bases de données](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="c32e2-212">[Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="c32e2-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="c32e2-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c32e2-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="c32e2-214">Reconstruire des bases de données système</span><span class="sxs-lookup"><span data-stu-id="c32e2-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
