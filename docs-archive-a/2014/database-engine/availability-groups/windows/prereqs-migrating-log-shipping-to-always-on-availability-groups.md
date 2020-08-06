---
title: Conditions préalables à la migration de la copie des journaux de session vers groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703292"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="71e08-102">Conditions préalables requises pour la migration de la copie des journaux de transaction vers les groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71e08-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="71e08-103">Cette rubrique décrit les conditions requises pour convertir une base de données principale pour la copie des journaux de transaction avec une ou plusieurs de ses bases de données secondaires en base de données principale AlwaysOn et ses bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="71e08-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71e08-104">Vous pouvez configurer une base de données principale ou secondaire (éventuellement accessible en lecture) dans un groupe de disponibilité en tant que base de données principale de copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="71e08-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="71e08-105">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="71e08-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="71e08-106">Conditions préalables requises pour les groupes de disponibilité</span><span class="sxs-lookup"><span data-stu-id="71e08-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="71e08-107">Conditions préalables requises pour la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="71e08-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="71e08-108">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="71e08-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="71e08-109">Contenu connexe</span><span class="sxs-lookup"><span data-stu-id="71e08-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="71e08-110">Conditions préalables pour le groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="71e08-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="71e08-111">Pour permettre aux travaux de sauvegarde de s'exécuter sur le réplica principal du groupe de disponibilité, utilisez les paramètres de sauvegarde de groupes de disponibilité AlwaysOn suivants :</span><span class="sxs-lookup"><span data-stu-id="71e08-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="71e08-112">Propriété</span><span class="sxs-lookup"><span data-stu-id="71e08-112">Property</span></span>|<span data-ttu-id="71e08-113">Paramètre</span><span class="sxs-lookup"><span data-stu-id="71e08-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="71e08-114">Préférence de sauvegarde automatisée du groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="71e08-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="71e08-115">Uniquement sur le réplica principal</span><span class="sxs-lookup"><span data-stu-id="71e08-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="71e08-116">Priorité de sauvegarde du réplica principal.</span><span class="sxs-lookup"><span data-stu-id="71e08-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="71e08-117">>0</span><span class="sxs-lookup"><span data-stu-id="71e08-117">>0</span></span>|  
  
 <span data-ttu-id="71e08-118">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="71e08-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="71e08-119">Afficher les propriétés d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="71e08-120">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a><span data-ttu-id="71e08-121">Conditions préalables pour l’envoi de journaux</span><span class="sxs-lookup"><span data-stu-id="71e08-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="71e08-122">La base de données principale pour la copie des journaux de transaction doit résider sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica principal initial/actuel du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="71e08-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="71e08-123">Pour qu'une base de données secondaire pour la copie des journaux de transaction soit convertie en base de données secondaire AlwaysOn, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e08-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="71e08-124">Utilisez le même nom que celui de la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="71e08-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="71e08-125">Choisissez un emplacement sur une instance de serveur qui héberge un réplica secondaire pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="71e08-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="71e08-126">Une fois que le travail de sauvegarde a été exécuté sur la base de données principale, désactivez-le. Dès que le travail de restauration a été exécuté sur une base de données secondaire donnée, désactivez-le.</span><span class="sxs-lookup"><span data-stu-id="71e08-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="71e08-127">Après avoir créé toutes les bases de données secondaires pour le groupe de disponibilité, si vous souhaitez effectuer des sauvegardes sur des réplicas secondaires, vous devez reconfigurer la préférence de sauvegarde automatisée du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="71e08-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="71e08-128">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="71e08-128">**For more information:**</span></span>  
  
 <span data-ttu-id="71e08-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (Conversion d’une configuration de copie de journaux de transaction en groupe de disponibilité - blog SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71e08-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="71e08-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="71e08-130">Related Tasks</span></span>  
 <span data-ttu-id="71e08-131">**Copie des journaux de transaction**</span><span class="sxs-lookup"><span data-stu-id="71e08-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="71e08-132">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="71e08-133">Supprimer la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="71e08-134">**Groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="71e08-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="71e08-135">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="71e08-136">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="71e08-137">Créer un groupe de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="71e08-138">Créer un groupe de disponibilité &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="71e08-139">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="71e08-140">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="71e08-141">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="71e08-141">Related Content</span></span>  
  
-   <span data-ttu-id="71e08-142">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="71e08-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="71e08-143">Conversion d'une configuration de copie de journaux de transaction en groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="71e08-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="71e08-144">Ajouter une base de données primaire de copie des journaux de transaction et une base de données secondaire à un groupe de disponibilité existant</span><span class="sxs-lookup"><span data-stu-id="71e08-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="71e08-145">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="71e08-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="71e08-146">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="71e08-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="71e08-147">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="71e08-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="71e08-148">Guide de migration : Migration vers les groupes de disponibilité AlwaysOn à partir des déploiements antérieurs combinant la mise en miroir de bases de données et la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="71e08-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="71e08-149">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="71e08-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="71e08-150">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="71e08-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="71e08-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71e08-151">See Also</span></span>  
 <span data-ttu-id="71e08-152">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71e08-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="71e08-153">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71e08-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="71e08-154">Surveillance des groupes de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71e08-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
