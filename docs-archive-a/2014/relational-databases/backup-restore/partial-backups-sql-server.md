---
title: Sauvegardes partielles (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612433"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="5660a-102">Sauvegardes partielles (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5660a-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="5660a-103">Tous les modes de récupération de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent en charge les sauvegardes partielles ; par conséquent, cette rubrique concerne toutes les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5660a-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="5660a-104">Toutefois, les sauvegardes partielles sont conçues pour le mode de récupération simple et permettent d'améliorer la souplesse des sauvegardes de bases de données très volumineuses qui contiennent un ou plusieurs groupes de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5660a-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="5660a-105">Les sauvegardes partielles sont utiles à chaque fois que vous souhaitez exclure des groupes de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5660a-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="5660a-106">Une *sauvegarde partielle* s’apparente à une sauvegarde complète de base de données, mais la première ne contient pas tous les groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5660a-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="5660a-107">En revanche, pour une base de données accessible en lecture/écriture, une sauvegarde partielle contient toutes les données du groupe de fichiers primaire, de chaque groupe de fichiers en lecture/écriture et, éventuellement, d'un ou de plusieurs fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5660a-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="5660a-108">La sauvegarde partielle d'une base de données en lecture seule contient uniquement le groupe de fichiers primaire.</span><span class="sxs-lookup"><span data-stu-id="5660a-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5660a-109">Si la base de données en lecture seule est convertie ensuite en base de données en lecture-écriture après une sauvegarde partielle, des groupes de fichiers secondaires en lecture-écriture peuvent ne pas figurer dans la sauvegarde partielle.</span><span class="sxs-lookup"><span data-stu-id="5660a-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="5660a-110">Dans ce cas, si vous tentez d'effectuer une sauvegarde partielle différentielle, la sauvegarde échoue.</span><span class="sxs-lookup"><span data-stu-id="5660a-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="5660a-111">Pour pouvoir créer une sauvegarde partielle différentielle de la base de données, vous devez créer une autre sauvegarde partielle.</span><span class="sxs-lookup"><span data-stu-id="5660a-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="5660a-112">La nouvelle sauvegarde partielle contient tous les groupes de fichiers secondaires en lecture-écriture qui peuvent servir de base pour les sauvegardes partielles différentielles.</span><span class="sxs-lookup"><span data-stu-id="5660a-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="5660a-113">Des sauvegardes de fichiers de groupes de fichiers en lecture seule peuvent être associées à des sauvegardes partielles.</span><span class="sxs-lookup"><span data-stu-id="5660a-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="5660a-114">Pour plus d’informations sur les sauvegardes de fichiers, consultez [Sauvegardes de fichiers complètes &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5660a-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="5660a-115">Une sauvegarde partielle peut servir de *base différentielle* pour des sauvegardes partielles différentielles.</span><span class="sxs-lookup"><span data-stu-id="5660a-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="5660a-116">Pour plus d’informations, consultez [Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5660a-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5660a-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5660a-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5660a-118">Les sauvegardes partielles ne sont pas prises en charge par [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou par l'Assistant Plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="5660a-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="5660a-119">**Pour créer une sauvegarde partielle**</span><span class="sxs-lookup"><span data-stu-id="5660a-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="5660a-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS ; option FILEGROUP, si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="5660a-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="5660a-121">**Pour utiliser une sauvegarde partielle dans une séquence de restauration**</span><span class="sxs-lookup"><span data-stu-id="5660a-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="5660a-122">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="5660a-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5660a-123">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="5660a-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="5660a-124"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5660a-124">See Also</span></span>  
 <span data-ttu-id="5660a-125">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5660a-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5660a-126">[Restaurations de fichiers &#40;mode de récupération simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="5660a-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="5660a-127">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5660a-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
