---
title: Afficher les propriétés et le contenu d’une unité de sauvegarde logique (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702996"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="3a615-102">Afficher les propriétés et le contenu d'une unité de sauvegarde logique (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3a615-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="3a615-103">Cette rubrique explique comment afficher les propriétés et le contenu d'une unité de sauvegarde logique dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a615-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3a615-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="3a615-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a615-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="3a615-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a615-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3a615-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3a615-107">**Pour afficher les propriétés et le contenu d'une unité de sauvegarde logique, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="3a615-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="3a615-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a615-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3a615-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a615-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a615-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3a615-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a615-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3a615-111">Security</span></span>  
 <span data-ttu-id="3a615-112">Pour plus d’informations sur la sécurité, consultez [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a615-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a615-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3a615-113">Permissions</span></span>  
 <span data-ttu-id="3a615-114">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures, l'obtention d'informations relatives à un jeu de sauvegarde ou une unité de sauvegarde requiert l'autorisation CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3a615-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="3a615-115">Pour plus d’informations, consultez [GRANT – octroi d’autorisations de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a615-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a615-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a615-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="3a615-117">Pour afficher les propriétés et le contenu d'une unité de sauvegarde logique</span><span class="sxs-lookup"><span data-stu-id="3a615-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="3a615-118">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="3a615-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3a615-119">Développez **Objets serveur**, puis **Unités de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="3a615-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="3a615-120">Cliquez sur l’unité, puis cliquez avec le bouton droit sur **Propriétés**; la boîte de dialogue **Unité de sauvegarde** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="3a615-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="3a615-121">La page **Général** affiche le nom de l'unité et la destination, soit un périphérique à bandes, soit un chemin de fichier.</span><span class="sxs-lookup"><span data-stu-id="3a615-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="3a615-122">Dans le volet **Sélectionner une page** , cliquez sur **Contenu du support**.</span><span class="sxs-lookup"><span data-stu-id="3a615-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="3a615-123">Le volet de droite affiche les volets de propriétés suivants :</span><span class="sxs-lookup"><span data-stu-id="3a615-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="3a615-124">**Média**</span><span class="sxs-lookup"><span data-stu-id="3a615-124">**Media**</span></span>  
  
         <span data-ttu-id="3a615-125">Informations sur la séquence du support (le numéro de la séquence du support et de la famille, et l'identificateur du miroir, s'il existe) et la date et l'heure de la création du support.</span><span class="sxs-lookup"><span data-stu-id="3a615-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="3a615-126">**Support de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="3a615-126">**Media set**</span></span>  
  
         <span data-ttu-id="3a615-127">Informations sur le support de sauvegarde : nom et description du support, s'ils existent, et nombre de familles dans ce support.</span><span class="sxs-lookup"><span data-stu-id="3a615-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="3a615-128">La grille **Jeux de sauvegarde** affiche des informations sur le contenu du support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="3a615-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a615-129">Pour plus d’informations, consultez [Page Contenu du support](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="3a615-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3a615-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a615-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="3a615-131">Pour afficher les propriétés et le contenu d'une unité de sauvegarde logique</span><span class="sxs-lookup"><span data-stu-id="3a615-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="3a615-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a615-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a615-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="3a615-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a615-134">Utilisez l'instruction [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3a615-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="3a615-135">Cet exemple retourne des informations sur l'unité de sauvegarde logique `AdvWrks2008R2Backup` .</span><span class="sxs-lookup"><span data-stu-id="3a615-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a615-136"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a615-136">See Also</span></span>  
 <span data-ttu-id="3a615-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="3a615-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="3a615-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="3a615-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="3a615-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="3a615-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a615-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="3a615-143">Unités de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3a615-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
