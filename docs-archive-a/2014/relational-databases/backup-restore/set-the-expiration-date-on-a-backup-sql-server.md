---
title: Définir la date d’expiration d’une sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603559"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="658cf-102">Définir la date d'expiration d'une sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="658cf-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="658cf-103">Cette rubrique explique comment définir la date d'expiration d'une sauvegarde dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="658cf-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="658cf-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="658cf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="658cf-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="658cf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="658cf-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="658cf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="658cf-107">**Pour définir la date d'expiration d'une sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="658cf-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="658cf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="658cf-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="658cf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658cf-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="658cf-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="658cf-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="658cf-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="658cf-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="658cf-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="658cf-112">Permissions</span></span>  
 <span data-ttu-id="658cf-113">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="658cf-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="658cf-114">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="658cf-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="658cf-115">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="658cf-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="658cf-116">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="658cf-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="658cf-117">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="658cf-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="658cf-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="658cf-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="658cf-119">Pour définir la date d'expiration d'une sauvegarde</span><span class="sxs-lookup"><span data-stu-id="658cf-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="658cf-120">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="658cf-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="658cf-121">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="658cf-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="658cf-122">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="658cf-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="658cf-123">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="658cf-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="658cf-124">Dans la page **Général** , pour l'option **Expiration du jeu de sauvegarde**, spécifiez une date d'expiration indiquant à quel moment la sauvegarde définie peut être remplacée par une autre sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="658cf-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="658cf-125">Pour que le jeu de sauvegarde expire au bout d’un nombre de jours spécifique, cliquez sur **Après** (option par défaut) et entrez le nombre de jours souhaité pour l’expiration du jeu après sa création.</span><span class="sxs-lookup"><span data-stu-id="658cf-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="658cf-126">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="658cf-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="658cf-127">La valeur par défaut est définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** de la boîte de dialogue **Propriétés du serveur** (page**Paramètres de base de données** ).</span><span class="sxs-lookup"><span data-stu-id="658cf-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="658cf-128">Pour y accéder, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et sélectionnez les propriétés. Ensuite, sélectionnez la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="658cf-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="658cf-129">Pour que le jeu de sauvegarde expire à une date spécifique, cliquez sur **Le**et entrez la date d'expiration souhaitée.</span><span class="sxs-lookup"><span data-stu-id="658cf-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="658cf-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="658cf-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="658cf-131">Pour définir la date d'expiration d'une sauvegarde</span><span class="sxs-lookup"><span data-stu-id="658cf-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="658cf-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="658cf-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="658cf-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="658cf-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="658cf-134">Dans l'instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) , spécifiez l'option EXPIREDATE ou RETAINDAYS afin de déterminer quand le [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] peut remplacer la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="658cf-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="658cf-135">Si aucune de ces options n'est spécifiée, la date d'expiration est déterminée par le paramètre de configuration serveur [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) (rétention du support).</span><span class="sxs-lookup"><span data-stu-id="658cf-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="658cf-136">Cet exemple utilise l'option `EXPIREDATE` pour spécifier une date d'expiration fixée au 30 juin 2015 (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="658cf-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="658cf-137"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="658cf-137">See Also</span></span>  
 <span data-ttu-id="658cf-138">[Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="658cf-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="658cf-139">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="658cf-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="658cf-140">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="658cf-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="658cf-141">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="658cf-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
