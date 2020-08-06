---
title: Configurer la compression de sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614672"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="ec23f-102">Configurer la compression de sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ec23f-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="ec23f-103">À l'installation, la compression de la sauvegarde est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ec23f-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="ec23f-104">Le comportement par défaut de la compression de la sauvegarde est défini par l’option de configuration au niveau du serveur **backup compression default** (valeur par défaut de compression de la sauvegarde).</span><span class="sxs-lookup"><span data-stu-id="ec23f-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="ec23f-105">Toutefois, vous pouvez remplacer la valeur par défaut au niveau du serveur lors de la création d'une sauvegarde unique ou de la planification d'une série de sauvegardes de routine.</span><span class="sxs-lookup"><span data-stu-id="ec23f-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="ec23f-106">Pour modifier la valeur par défaut au niveau du serveur, consultez [Afficher ou configurer l’option de configuration du serveur valeur par défaut de compression de la sauvegarde](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ec23f-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="ec23f-107">Remplacer la valeur par défaut de compression de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="ec23f-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="ec23f-108">Vous pouvez modifier le comportement de compression de la sauvegarde pour une sauvegarde individuelle, un travail de sauvegarde ou une configuration de la copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="ec23f-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="ec23f-109">Pour remplacer la valeur par défaut de compression de la sauvegarde de serveur lors de la création d’une sauvegarde, utilisez WITH NO_COMPRESSION ou WITH COMPRESSION dans votre instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ec23f-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="ec23f-110">Pour une configuration de la copie des journaux de transactions, vous pouvez contrôler le comportement de compression des sauvegardes de fichiers journaux en utilisant [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ec23f-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="ec23f-111">Pour plus d’informations sur la façon d’afficher ou de configurer l’option par défaut de compression de la sauvegarde pour une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Afficher ou configurer l’option de configuration du serveur valeur par défaut de compression de la sauvegarde](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ec23f-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="ec23f-112">Vous pouvez remplacer la valeur par défaut de compression de la sauvegarde au niveau du serveur lors de la création d’une sauvegarde en spécifiant **Compresser la sauvegarde** ou **Ne pas compresser la sauvegarde** dans l’une des boîtes de dialogue suivantes :</span><span class="sxs-lookup"><span data-stu-id="ec23f-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="ec23f-113">Sauvegarder la base de données (page Options)</span><span class="sxs-lookup"><span data-stu-id="ec23f-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="ec23f-114">Lors de la sauvegarde d'une base de données, vous pouvez contrôler la compression de la sauvegarde pour une sauvegarde de base de données, de fichier ou de journal individuelle.</span><span class="sxs-lookup"><span data-stu-id="ec23f-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="ec23f-115">Utiliser l'Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="ec23f-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="ec23f-116">L'Assistant Plan de la maintenance vous permet de contrôler la compression de la sauvegarde pour chaque jeu de sauvegardes complètes ou différentielles de base de données ou de sauvegardes de fichier journal que vous planifiez.</span><span class="sxs-lookup"><span data-stu-id="ec23f-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="ec23f-117">Integration Services (SSIS) [Tâche Sauvegarder la base de données](../../integration-services/control-flow/back-up-database-task.md)</span><span class="sxs-lookup"><span data-stu-id="ec23f-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="ec23f-118">Vous pouvez contrôler le comportement de compression de la sauvegarde lors de la création d'un package pour sauvegarder une base de données unique ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="ec23f-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="ec23f-119">Paramètres de sauvegarde des journaux de transactions</span><span class="sxs-lookup"><span data-stu-id="ec23f-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="ec23f-120">Vous pouvez contrôler le comportement de compression de la sauvegarde pour les sauvegardes de journaux.</span><span class="sxs-lookup"><span data-stu-id="ec23f-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="ec23f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec23f-121">See Also</span></span>  
 [<span data-ttu-id="ec23f-122">Compression de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec23f-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
