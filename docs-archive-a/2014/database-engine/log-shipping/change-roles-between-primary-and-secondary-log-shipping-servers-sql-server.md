---
title: Changer des rôles entre les serveurs primaire et secondaire de copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703255"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="d7562-102">Changer des rôles entre les serveurs primaire et secondaire de copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d7562-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="d7562-103">Après avoir basculé une configuration de copie des journaux de transactions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers un serveur secondaire, vous pouvez configurer votre base de données secondaire de façon à ce qu'elle agisse en tant que base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="d7562-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="d7562-104">Vous pourrez alors intervertir les bases de données primaire et secondaire en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="d7562-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="d7562-105">Exécution du changement de rôle initial</span><span class="sxs-lookup"><span data-stu-id="d7562-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="d7562-106">La première fois que vous voulez basculer vers la base de données secondaire et en faire votre base de données primaire, vous devez effectuer un ensemble d'opérations.</span><span class="sxs-lookup"><span data-stu-id="d7562-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="d7562-107">Après cela, vous pourrez intervertir facilement les rôles des bases de données primaire et secondaire.</span><span class="sxs-lookup"><span data-stu-id="d7562-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="d7562-108">Basculez manuellement de la base de données primaire vers la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="d7562-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="d7562-109">Vérifiez que vous avez sauvegardé le journal des transactions en cours sur votre serveur principal en utilisant l'option NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d7562-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="d7562-110">Pour plus d’informations, consultez [Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7562-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="d7562-111">Désactivez l'opération de copie des journaux de transaction sur le serveur principal, ainsi que les opérations de copie et de restauration sur le serveur secondaire d'origine.</span><span class="sxs-lookup"><span data-stu-id="d7562-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d7562-112">Dans la base de données secondaire (que vous voulez transformer en base de données primaire), configurez la copie des journaux de transaction au moyen de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7562-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d7562-113">Pour plus d’informations, consultez [Configurer la copie des journaux de transaction &#40;Transact-SQL&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7562-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="d7562-114">Incorporez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7562-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="d7562-115">Utilisez le même partage pour la création des sauvegardes que vous avez créées pour le serveur principal d'origine.</span><span class="sxs-lookup"><span data-stu-id="d7562-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="d7562-116">Lorsque vous ajoutez la base de données secondaire, dans la boîte de dialogue **Paramètres de base de données secondaire** , tapez le nom de la base de données primaire dans la zone **Base de données secondaire** .</span><span class="sxs-lookup"><span data-stu-id="d7562-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="d7562-117">Dans la boîte de dialogue **Paramètres de base de données secondaire** , sélectionnez **Non, la base de données secondaire est initialisée**.</span><span class="sxs-lookup"><span data-stu-id="d7562-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="d7562-118">Si l'analyse de l'envoi de journaux est activée sur la configuration de copie des journaux de transaction précédente, reconfigurez l'analyse de l'envoi de journaux pour surveiller la nouvelle configuration de copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="d7562-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="d7562-119">Exécutez les commandes suivantes, en remplaçant *nom_base_de_données* par le nom de votre base de données :</span><span class="sxs-lookup"><span data-stu-id="d7562-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="d7562-120">**Sur le nouveau serveur principal**</span><span class="sxs-lookup"><span data-stu-id="d7562-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="d7562-121">Exécutez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7562-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="d7562-122">**Sur le nouveau serveur secondaire**</span><span class="sxs-lookup"><span data-stu-id="d7562-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="d7562-123">Exécutez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7562-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="d7562-124">Interversion des rôles</span><span class="sxs-lookup"><span data-stu-id="d7562-124">Swapping Roles</span></span>  
 <span data-ttu-id="d7562-125">Une fois les opérations ci-dessus effectuées pour le changement initial des rôles, vous pouvez intervertir les rôles des bases de données primaire et secondaire en effectuant les opérations de cette section.</span><span class="sxs-lookup"><span data-stu-id="d7562-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="d7562-126">Pour changer les rôles, effectuez ces opérations générales :</span><span class="sxs-lookup"><span data-stu-id="d7562-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="d7562-127">Connectez la base de données secondaire, en sauvegardant le journal des transactions du serveur principal avec l'option NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d7562-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="d7562-128">Désactivez l'opération de copie des journaux de transaction sur le serveur principal, ainsi que les opérations de copie et de restauration sur le serveur secondaire d'origine.</span><span class="sxs-lookup"><span data-stu-id="d7562-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="d7562-129">Activez l'opération de copie des journaux de transaction sur le serveur secondaire (nouveau serveur principal, ainsi que les opérations de copie et de restauration sur le serveur principal (nouveau serveur secondaire).</span><span class="sxs-lookup"><span data-stu-id="d7562-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7562-130">Lorsque vous modifiez une base de données secondaire en base de données primaire, pour garantir une expérience cohérente aux utilisateurs et aux applications, vous devrez peut-être recréer tout ou partie des métadonnées de la base de données, telles que les connexions et les travaux, sur la nouvelle instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="d7562-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="d7562-131">Pour plus d’informations, consultez [Gérer les métadonnées durant la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="d7562-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d7562-132">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d7562-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d7562-133">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d7562-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="d7562-134">Gestion des connexions et des travaux après un basculement de rôle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d7562-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7562-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7562-135">See Also</span></span>  
 [<span data-ttu-id="d7562-136">Tables et procédures stockées liées à la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="d7562-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
