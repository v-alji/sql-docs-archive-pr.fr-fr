---
title: Résoudre les problèmes liés à l’échec d’une opération d’ajout de fichier (groupes de disponibilité AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708631"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="dea80-102">Résoudre une opération d'ajout de fichier ayant échoué (groupes de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="dea80-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="dea80-103">Pour certains déploiements de groupes de disponibilité AlwaysOn, les chemins d'accès aux fichiers varient entre le système qui héberge le réplica principal et les systèmes qui hébergent un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="dea80-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="dea80-104">Si le chemin d'accès aux fichiers d'une opération d'ajout de fichier n'existe pas sur le réplica secondaire, l'opération d'ajout de fichier réussit sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="dea80-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="dea80-105">Cependant, l'opération d'ajout e fichier entraîne l'interruption de la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="dea80-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="dea80-106">Par voie de conséquence, le réplica secondaire passe à l'état NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="dea80-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dea80-107">Nous recommandons, si possible, que le chemin d'accès au fichier (y compris la lettre de lecteur) d'une base de données secondaire donnée soit identique au chemin d'accès de la base de données primaire correspondante.</span><span class="sxs-lookup"><span data-stu-id="dea80-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="dea80-108">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="dea80-108">Problem Resolution</span></span>  
 <span data-ttu-id="dea80-109">Pour résoudre ce problème, le propriétaire de la base de données doit effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dea80-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="dea80-110">Supprimer la base de données secondaire du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="dea80-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="dea80-111">Pour plus d’informations, consultez [Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dea80-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="dea80-112">Sur la base de données secondaire existante, restaurer une sauvegarde complète du groupe de fichiers contenant le fichier ajouté à la base de données secondaire à l'aide de WITH NORECOVERY et de WITH MOVE (en spécifiant le chemin d'accès au fichier sur l'instance de serveur qui héberge le réplica secondaire).</span><span class="sxs-lookup"><span data-stu-id="dea80-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="dea80-113">Pour plus d’informations, consultez [Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dea80-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="dea80-114">Sauvegarder le journal des transactions qui contient l'opération d'ajout de fichier sur la base de données primaire, puis restaurer manuellement la sauvegarde du journal sur la base de données secondaire à l'aide de WITH NORECOVERY et de WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="dea80-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="dea80-115">Préparer la base de données secondaire pour rejoindre le groupe de disponibilité, en restaurant, à l'aide de WITH NORECOVERY, toutes les autres sauvegardes de journal en attente de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="dea80-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="dea80-116">Réintégrer la base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="dea80-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="dea80-117">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dea80-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea80-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dea80-118">See Also</span></span>  
 <span data-ttu-id="dea80-119">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dea80-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="dea80-120">[Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dea80-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="dea80-121">[Dépanner des utilisateurs orphelins &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dea80-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="dea80-122">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;supprimé</span><span class="sxs-lookup"><span data-stu-id="dea80-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
