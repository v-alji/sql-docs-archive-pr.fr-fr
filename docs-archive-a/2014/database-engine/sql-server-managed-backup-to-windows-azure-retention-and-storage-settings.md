---
title: SQL Server la gestion de sauvegarde dans Azure-paramètres de rétention et de stockage | Microsoft Docs
description: Cette rubrique explique comment configurer SQL Server sauvegarde managée pour Microsoft Azure pour une base de données et configurer les paramètres par défaut de l’instance.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705404"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="90a77-103">Sauvegarde managée SQL Server sur Azure : Paramètres de conservation et de stockage</span><span class="sxs-lookup"><span data-stu-id="90a77-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="90a77-104">Cette rubrique décrit les étapes de base requises pour configurer la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une base de données, et pour configurer les paramètres par défaut de l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="90a77-105">Elle décrit également les étapes nécessaires pour interrompre et reprendre les services de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="90a77-106">Pour une procédure pas à pas complète de la configuration [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , consultez [configuration d’SQL Server la gestion de sauvegarde sur Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) et [configuration d’SQL Server sauvegarde managée sur Azure pour les groupes de disponibilité](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90a77-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="90a77-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="90a77-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="90a77-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="90a77-109">N'activez pas la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur les bases de données qui utilisent actuellement des plans de maintenance ou la copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="90a77-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="90a77-110">Pour plus d’informations sur l’interopérabilité et la coexistence avec d’autres fonctionnalités de SQL Server, consultez [SQL Server gestion de la sauvegarde vers Azure : interopérabilité et coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="90a77-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="90a77-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="90a77-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="90a77-112">SQL Server Agent ne doit pas être en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="90a77-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="90a77-113">Si SQL Server Agent est arrêté pendant une certaine période, puis est redémarré, vous pouvez constater une activité de sauvegarde accrue selon la période qui s'est écoulée entre l'arrêt et le démarrage. De plus, un journal des travaux en souffrance peut être généré, contenant les sauvegardes qui attendent d'être exécutées.</span><span class="sxs-lookup"><span data-stu-id="90a77-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="90a77-114">Pensez à configurer SQL Server Agent afin qu'il soit lancé automatiquement au démarrage.</span><span class="sxs-lookup"><span data-stu-id="90a77-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="90a77-115">Un compte de stockage Azure et des informations d’identification SQL qui stockent les informations d’authentification dans le compte de stockage doivent être créés avant d’être configurés [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90a77-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="90a77-116">Pour plus d'informations, consultez la section [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) dans la rubrique **Sauvegarde SQL Server vers une URL** et la [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="90a77-117">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] crée les conteneurs nécessaires pour stocker les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="90a77-117">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] creates the necessary containers to store the backups.</span></span> <span data-ttu-id="90a77-118">Le nom du conteneur est créé à l’aide du format « nom de l’ordinateur-nom de l’instance ».</span><span class="sxs-lookup"><span data-stu-id="90a77-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="90a77-119">Pour les groupes de disponibilité AlwaysOn, le conteneur est nommé en utilisant le GUID du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="90a77-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90a77-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="90a77-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90a77-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="90a77-121">Permissions</span></span>  
 <span data-ttu-id="90a77-122">Pour exécuter les procédures stockées qui activent [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , vous devez être `System Administrator` membre ou du rôle de base de données **db_backupoperator** avec les autorisations **ALTER ANY CREDENTIAL** , ainsi que `EXECUTE` les autorisations sur le **sp_delete_backuphistory**et les `smart_admin.sp_backup_master_switch` procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="90a77-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="90a77-123">Les procédures stockées et les fonctions utilisées pour passer en revue les paramètres existants nécessitent généralement des autorisations `Execute` sur la procédure stockée et `Select` sur la fonction, respectivement.</span><span class="sxs-lookup"><span data-stu-id="90a77-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="90a77-124">Considérations relatives à l’activation de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour les bases de données et les instances</span><span class="sxs-lookup"><span data-stu-id="90a77-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 <span data-ttu-id="90a77-125">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] peut être activée pour chaque base de données distincte ou pour la totalité de l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-125">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="90a77-126">Les choix dépendent des exigences de récupérabilité des bases de données sur l’instance, de la configuration requise pour la gestion de plusieurs bases de données et instances et de l’utilisation stratégique du stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="90a77-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="90a77-127">Activation de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="90a77-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="90a77-128">Si une base de données a des exigences de sauvegarde spécifiques et une période de rétention (SLA relatif à la récupérabilité) qui sont différentes des autres bases de données sur l'instance, configurez la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de la base de données pour cette base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="90a77-129">Les paramètres de niveau base de données remplacent les paramètres de configuration de niveau instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="90a77-130">Cependant, ces deux possibilités peuvent être utilisées ensemble sur la même instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="90a77-131">Voici une liste des avantages et des éléments à prendre en considération lorsque vous activez la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="90a77-132">Plus de granularité : paramètres de configuration distincts pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="90a77-133">Peut prendre en charge différentes périodes de rétention pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="90a77-134">Remplace les paramètres au niveau de l'instance pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="90a77-135">Peut servir à réduire les coûts de stockage en sélectionnant des bases de données individuelles pour la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="90a77-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="90a77-136">Nécessite la gestion de chaque base de données</span><span class="sxs-lookup"><span data-stu-id="90a77-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="90a77-137">Activation de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de l'instance avec des paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="90a77-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="90a77-138">Utilisez ces paramètres si la plupart des bases de données dans l'instance ont les mêmes exigences de sauvegarde et les mêmes stratégies de rétention, ou si vous souhaitez que les nouvelles instances de bases de données soient automatiquement sauvegardées à la création.</span><span class="sxs-lookup"><span data-stu-id="90a77-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="90a77-139">Les bases de données qui font exception à la stratégie peuvent être configurées individuellement.</span><span class="sxs-lookup"><span data-stu-id="90a77-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="90a77-140">Voici une liste des avantages et des éléments à prendre en considération lorsque vous activez la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="90a77-141">Automatisation au niveau de l'instance : les paramètres communs sont appliqués automatiquement aux nouvelles bases de données ajoutées par la suite.</span><span class="sxs-lookup"><span data-stu-id="90a77-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="90a77-142">Les nouvelles bases de données sont automatiquement sauvegardées après leur création dans les instances</span><span class="sxs-lookup"><span data-stu-id="90a77-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="90a77-143">Peut s'appliquer aux bases de données qui ont les mêmes périodes de rétention.</span><span class="sxs-lookup"><span data-stu-id="90a77-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="90a77-144">Vous pouvez toujours configurer les bases de données qui nécessitent une période de rétention différente même si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée au niveau de l'instance avec les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="90a77-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="90a77-145">Vous pouvez également désactiver [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour les bases de données si vous n’envisagez pas d’utiliser le stockage Azure pour les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="90a77-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="90a77-146">Activer et configurer [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une base de données</span><span class="sxs-lookup"><span data-stu-id="90a77-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="90a77-147">La procédure stockée système `smart_admin.sp_set_db_backup` est utilisée pour activer la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une base de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="90a77-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="90a77-148">Lorsque la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée pour la première fois sur la base de données, les informations suivantes doivent être spécifiées en plus de l'activation de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="90a77-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="90a77-149">Nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="90a77-150">Période de rétention.</span><span class="sxs-lookup"><span data-stu-id="90a77-150">The retention period.</span></span>  
  
-   <span data-ttu-id="90a77-151">Informations d’identification SQL utilisées pour l’authentification auprès du compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="90a77-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="90a77-152">Spécifiez de ne pas chiffrer à l’aide de \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** ou spécifiez un algorithme de chiffrement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="90a77-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="90a77-153">Pour plus d'informations sur le chiffrement, consultez [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="90a77-154">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une configuration au niveau de la base de données est prise en charge uniquement via Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="90a77-154">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="90a77-155">Une fois que la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée pour une base de données, cette information est conservée.</span><span class="sxs-lookup"><span data-stu-id="90a77-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="90a77-156">Si vous modifiez la configuration, seuls le nom de la base de données et le paramètre que vous souhaitez modifier sont requis ; la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] conserve les valeurs existantes pour les autres paramètres en l'absence d'autre indication.</span><span class="sxs-lookup"><span data-stu-id="90a77-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90a77-157">Avant de configurer la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur une base de données, il peut être utile de passer en revue la configuration existante, si elle existe.</span><span class="sxs-lookup"><span data-stu-id="90a77-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="90a77-158">Les étapes pour revoir les paramètres de configuration d'une base de données sont abordées plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="90a77-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="90a77-159">**Utilisation de Transact-SQL :**</span><span class="sxs-lookup"><span data-stu-id="90a77-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="90a77-160">Si vous activez [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour la première fois, les paramètres requis sont : \* \@ database_name*, \* \@ credential_name* \* \@ encryption_algorithm*, \* \@ enable_backup* le paramètre \* \@ storage_url\* est facultatif.</span><span class="sxs-lookup"><span data-stu-id="90a77-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="90a77-161">Si vous ne fournissez pas de valeur pour le @storage_url paramètre, la valeur est dérivée à l’aide des informations de compte de stockage des informations d’identification SQL.</span><span class="sxs-lookup"><span data-stu-id="90a77-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="90a77-162">Si vous spécifiez l'URL de stockage, vous ne devez spécifier que l'URL de la racine du compte de stockage, et vous devez faire correspondre les informations dans les informations d'identification SQL spécifiées.</span><span class="sxs-lookup"><span data-stu-id="90a77-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="90a77-163">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="90a77-164">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="90a77-165">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="90a77-166">Cet exemple active [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour la base de données « TestDB ».</span><span class="sxs-lookup"><span data-stu-id="90a77-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="90a77-167">La période de rétention est définie à 30 jours.</span><span class="sxs-lookup"><span data-stu-id="90a77-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="90a77-168">Cet exemple utilise l'option de chiffrement spécifiant l'algorithme de chiffrement et les informations du chiffreur.</span><span class="sxs-lookup"><span data-stu-id="90a77-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="90a77-169">La période de rétention peut être définie sur n'importe quelle valeur de 1 à 30 jours.</span><span class="sxs-lookup"><span data-stu-id="90a77-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="90a77-170">Pour plus d'informations sur la création d'un certificat pour le chiffrement, consultez l'étape Créer un certificat de sauvegarde dans [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="90a77-171">Pour plus d’informations sur cette procédure stockée, consultez [smart_admin. set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="90a77-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="90a77-172">Pour passer en revue les paramètres de configuration d'une base de données, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="90a77-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="90a77-173">Activer et configurer [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] les paramètres par défaut de l’instance</span><span class="sxs-lookup"><span data-stu-id="90a77-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="90a77-174">Vous pouvez activer et configurer les [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] paramètres par défaut au niveau de l’instance de deux manières : à l’aide de la procédure stockée système `smart_admin.set_instance_backup` ou **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="90a77-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="90a77-175">Les deux méthodes sont expliquées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="90a77-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="90a77-176">**smart_admin. set_instance_backup :**.</span><span class="sxs-lookup"><span data-stu-id="90a77-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="90a77-177">En spécifiant la valeur **1** pour \* \@ enable_backup\* paramètre, vous pouvez activer la sauvegarde et définir les configurations par défaut.</span><span class="sxs-lookup"><span data-stu-id="90a77-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="90a77-178">Une fois appliqués au niveau de l'instance, ces paramètres par défaut sont appliqués aux nouvelles bases de données ajoutées à cette instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="90a77-179">Lorsque la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée pour la première, les informations suivantes doivent être spécifiées en plus de l'activation de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur l'instance :</span><span class="sxs-lookup"><span data-stu-id="90a77-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="90a77-180">Période de rétention.</span><span class="sxs-lookup"><span data-stu-id="90a77-180">The retention period.</span></span>  
  
-   <span data-ttu-id="90a77-181">Informations d’identification SQL utilisées pour l’authentification auprès du compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="90a77-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="90a77-182">Option de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="90a77-182">The encryption option.</span></span> <span data-ttu-id="90a77-183">Spécifiez de ne pas chiffrer à l’aide de \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** ou spécifiez un algorithme de chiffrement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="90a77-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="90a77-184">Pour plus d'informations sur le chiffrement, consultez [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="90a77-185">Ces paramètres sont conservés après l'activation.</span><span class="sxs-lookup"><span data-stu-id="90a77-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="90a77-186">Si vous modifiez la configuration, seuls le nom de la base de données et le paramètre à modifier sont requise.</span><span class="sxs-lookup"><span data-stu-id="90a77-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> <span data-ttu-id="90a77-187">La [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] conserve les valeurs existantes en l'absence d'autre indication.</span><span class="sxs-lookup"><span data-stu-id="90a77-187">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90a77-188">Avant de configurer la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur une instance, il peut être utile de vérifier la configuration existante, si elle existe.</span><span class="sxs-lookup"><span data-stu-id="90a77-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="90a77-189">Les étapes pour revoir les paramètres de configuration d'une base de données sont abordées plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="90a77-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="90a77-190">**SQL Server Management Studio :** pour effectuer cette tâche dans SQL Server Management Studio, accédez à l'Explorateur d'objets, développez le nœud **Gestion** , puis cliquez avec le bouton droit sur **Sauvegarde managée**.</span><span class="sxs-lookup"><span data-stu-id="90a77-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="90a77-191">Sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="90a77-191">Select **Configure**.</span></span> <span data-ttu-id="90a77-192">La boîte de dialogue **Sauvegarde managée** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="90a77-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="90a77-193">Utilisez cette boîte de dialogue pour spécifier la période de rétention, les informations d'identification SQL, l'URL de stockage et les paramètres de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="90a77-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="90a77-194">Pour obtenir une aide spécifique sur cette boîte de dialogue, consultez [configurer la sauvegarde managée &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="90a77-195">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90a77-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="90a77-196">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-197">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-198">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90a77-199">La période de rétention peut être définie sur n'importe quelle valeur de 1 à 30 jours.</span><span class="sxs-lookup"><span data-stu-id="90a77-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="90a77-200">Pour plus d'informations sur la création d'un certificat pour le chiffrement, consultez l'étape Créer un certificat de sauvegarde dans [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="90a77-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="90a77-201">Pour passer en revue les paramètres de configuration par défaut d'une instance, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="90a77-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="90a77-202">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="90a77-203">Démarrer une instance PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="90a77-204">Exécutez le script suivant après l'avoir modifié en fonction de vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="90a77-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90a77-205">Lorsque vous créez une nouvelle base de données après avoir configuré les paramètres par défaut, la configuration peut prendre jusqu'à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="90a77-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="90a77-206">Cela s'applique également aux bases de données modifiées du modèle de récupération **Simple** au modèle **Full** ou **Bulk-Logged** .</span><span class="sxs-lookup"><span data-stu-id="90a77-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="90a77-207">Désactiver la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une base de données</span><span class="sxs-lookup"><span data-stu-id="90a77-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="90a77-208">Désactivez les paramètres de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] à l'aide de la procédure stockée système `sp_set_db_backup`.</span><span class="sxs-lookup"><span data-stu-id="90a77-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="90a77-209">Le \* \@ enableparameter\* est utilisé pour activer et désactiver les [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations pour une base de données spécifique, où 1 active et 0 désactive les paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="90a77-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="90a77-210">Pour désactiver la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une base de données spécifique :</span><span class="sxs-lookup"><span data-stu-id="90a77-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="90a77-211">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-212">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-213">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="90a77-214">Désactiver la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour toutes les bases de données sur l'instance</span><span class="sxs-lookup"><span data-stu-id="90a77-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="90a77-215">La procédure suivante désactive les paramètres de configuration de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur toutes les bases de données où la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est actuellement activée sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="90a77-216">Les paramètres de configuration tels que l'URL de stockage, la rétention, et les informations d'identification SQL, restent dans les métadonnées et peuvent être utilisés si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée ultérieurement pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="90a77-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="90a77-217">Si vous souhaitez simplement interrompre le service de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] temporairement, vous pouvez utiliser le commutateur principal abordé dans les sections suivantes de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="90a77-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="90a77-218">Pour désactiver la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]pour toutes les bases de données :</span><span class="sxs-lookup"><span data-stu-id="90a77-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="90a77-219">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-220">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-221">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="90a77-222">L'exemple suivant détermine si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est configurée au niveau de l'instance et identifie toutes les bases de données activées pour la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] sur l'instance, puis exécute la procédure stockée système `sp_set_db_backup` pour désactiver la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="90a77-223">Pour passer en revue les paramètres de configuration de toutes les bases de données sur l'instance, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="90a77-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="90a77-224">Désactiver les paramètres de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] par défaut pour l'instance</span><span class="sxs-lookup"><span data-stu-id="90a77-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="90a77-225">Les paramètres par défaut au niveau de l'instance sont appliqués à toutes les nouvelles bases de données créées sur cette instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="90a77-226">Si vous n'avez plus besoin des paramètres par défaut, vous pouvez désactiver cette configuration à l'aide de la procédure stockée système **smart_admin.sp_set_instance_backup** .</span><span class="sxs-lookup"><span data-stu-id="90a77-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="90a77-227">La désactivation ne supprime pas les autres paramètres de configuration, comme l'URL de stockage, le paramètre de rétention ou le nom de l'objet contenant les informations d'identification SQL.</span><span class="sxs-lookup"><span data-stu-id="90a77-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="90a77-228">Ces paramètres seront utilisés si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] est activée sur l'instance ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="90a77-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="90a77-229">Pour désactiver les paramètres de configuration par défaut de la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="90a77-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="90a77-230">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-231">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-232">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="90a77-233">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="90a77-234">Démarrer une instance PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="90a77-235">Exécutez le script suivant :</span><span class="sxs-lookup"><span data-stu-id="90a77-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="90a77-236">Interrompre la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de l'instance</span><span class="sxs-lookup"><span data-stu-id="90a77-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="90a77-237">Dans certains cas, vous pouvez souhaiter interrompre les services de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pour une courte période.</span><span class="sxs-lookup"><span data-stu-id="90a77-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="90a77-238">La procédure stockée système `smart_admin.sp_backup_master_switch` vous permet de désactiver le service de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="90a77-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="90a77-239">La même procédure est utilisée pour reprendre la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="90a77-240">Le paramètre @state est utilisé pour déterminer si la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] doit être désactivée ou activée.</span><span class="sxs-lookup"><span data-stu-id="90a77-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="90a77-241">Pour interrompre les services de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] à l'aide de Transact-SQL :</span><span class="sxs-lookup"><span data-stu-id="90a77-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="90a77-242">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-243">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-244">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur`Execute`</span><span class="sxs-lookup"><span data-stu-id="90a77-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="90a77-245">Pour interrompre la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="90a77-246">Démarrer une instance PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="90a77-247">Exécutez le script suivant après l'avoir modifié en fonction de vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="90a77-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="90a77-248">Pour reprendre la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90a77-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="90a77-249">Connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a77-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90a77-250">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90a77-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90a77-251">Copiez et collez l’exemple suivant dans la fenêtre de requête, puis cliquez sur `Execute` .</span><span class="sxs-lookup"><span data-stu-id="90a77-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="90a77-252">Pour reprendre la [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="90a77-253">Démarrer une instance PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a77-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="90a77-254">Exécutez le script suivant après l'avoir modifié en fonction de vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="90a77-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
