---
title: Mise en miroir et instantanés de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603023"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="9816c-102">Mise en miroir et instantanés de bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9816c-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="9816c-103">Une base de données miroir maintenue à des fins de disponibilité peut être utilisée dans le but de décharger la création de rapports.</span><span class="sxs-lookup"><span data-stu-id="9816c-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="9816c-104">Pour utiliser une base de données miroir à des fins de création de rapports, créez un instantané de base de données sur la base de données miroir et redirigez les requêtes de connexions clientes vers l'instantané le plus récent.</span><span class="sxs-lookup"><span data-stu-id="9816c-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="9816c-105">Un instantané de base de données est une image – statique, en lecture seule et cohérente par rapport aux transactions – de sa base de données source telle qu'elle existait au moment de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="9816c-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="9816c-106">Pour créer un instantané de base de données dans une base de données miroir, la base de données doit être dans un état de mise en miroir synchronisée.</span><span class="sxs-lookup"><span data-stu-id="9816c-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="9816c-107">Contrairement à la base de données miroir, un instantané de base de données est accessible à tous les clients.</span><span class="sxs-lookup"><span data-stu-id="9816c-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="9816c-108">Tant que le serveur miroir communique avec le serveur principal, vous pouvez demander aux clients sources des rapports de se connecter à un instantané.</span><span class="sxs-lookup"><span data-stu-id="9816c-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="9816c-109">Notez qu'un instantané de base de données étant statique, les nouvelles données ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="9816c-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="9816c-110">Pour que les utilisateurs puissent accéder aux données relativement récentes, un instantané de base de données doit être créé régulièrement et les applications doivent diriger les connexions clientes entrantes vers ce nouvel instantané.</span><span class="sxs-lookup"><span data-stu-id="9816c-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="9816c-111">Un nouvel instantané de base de données est pratiquement vide mais, au fil du temps, il grossit à mesure qu'un nombre croissant de pages de base de données sont mises à jour pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="9816c-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="9816c-112">Du fait de ce mode de croissance incrémentielle des instantanés dans une base de données, chaque instantané consomme autant de ressources qu'une base de données classique.</span><span class="sxs-lookup"><span data-stu-id="9816c-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="9816c-113">Selon les configurations du serveur miroir et du serveur principal, la présence d'un nombre excessif d'instantanés dans une base de données miroir peut réduire les performances dans la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="9816c-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="9816c-114">Nous vous recommandons donc de conserver uniquement quelques instantanés relativement récents dans vos bases de données miroir.</span><span class="sxs-lookup"><span data-stu-id="9816c-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="9816c-115">Normalement, une fois que vous avez créé un instantané de remplacement, vous devez rediriger les requêtes entrantes vers le nouvel instantané et supprimer l'instantané antérieur après avoir exécuté toutes les requêtes en cours.</span><span class="sxs-lookup"><span data-stu-id="9816c-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9816c-116">Pour plus d’informations sur les instantanés de base de données, consultez [Instantanés de base de données &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9816c-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="9816c-117">S'il se produit un basculement de rôle, la base de données et ses instantanés sont redémarrés, ce qui entraîne une déconnexion temporaire des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9816c-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="9816c-118">Ensuite, les instantanés de base de données demeurent sur l'instance de serveur où ils ont été créés et qui est devenue la nouvelle base de données principale.</span><span class="sxs-lookup"><span data-stu-id="9816c-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="9816c-119">Les utilisateurs peuvent continuer à utiliser ces instantanés après le basculement.</span><span class="sxs-lookup"><span data-stu-id="9816c-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="9816c-120">Cependant, il s'ensuit une charge supplémentaire sur le nouveau serveur principal.</span><span class="sxs-lookup"><span data-stu-id="9816c-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="9816c-121">Si les performances constituent l'une de vos préoccupations majeures, nous vous recommandons de créer un instantané sur la nouvelle base de données miroir dès qu'elle est disponible, de rediriger les clients vers le nouvel instantané et de supprimer de la base de données miroir précédente l'ensemble des instantanés de base de données.</span><span class="sxs-lookup"><span data-stu-id="9816c-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9816c-122">Pour une solution de création de rapports dotée d'une bonne capacité de déploiement horizontal, envisagez la réplication.</span><span class="sxs-lookup"><span data-stu-id="9816c-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="9816c-123">Pour plus d’informations, consultez [Réplication SQL Server](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9816c-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9816c-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="9816c-124">Example</span></span>  
 <span data-ttu-id="9816c-125">Cet exemple créé des instantanés de bases de données sur une base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="9816c-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="9816c-126">Imaginons que la base de données d'une session de mise en miroir de base de données soit la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9816c-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="9816c-127">Cet exemple crée trois instantanés de base de données sur la copie miroir de la base de données `AdventureWorks` qui réside sur le lecteur `F` .</span><span class="sxs-lookup"><span data-stu-id="9816c-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="9816c-128">Les noms des instantanés sont `AdventureWorks_0600`, `AdventureWorks_1200`et `AdventureWorks_1800` ; ils identifient les heures de création approximatives des captures.</span><span class="sxs-lookup"><span data-stu-id="9816c-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="9816c-129">Créez le premier instantané de base de données sur le miroir de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9816c-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="9816c-130">Créez le deuxième instantané de base de données sur le miroir de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9816c-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="9816c-131">Les utilisateurs qui se servent encore de `AdventureWorks_0600` peuvent continuer à le faire.</span><span class="sxs-lookup"><span data-stu-id="9816c-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="9816c-132">À ce stade, les nouvelles connexions clientes peuvent être orientées, par programme, vers l'instantané le plus récent.</span><span class="sxs-lookup"><span data-stu-id="9816c-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="9816c-133">Créez le troisième instantané de base de données sur le miroir de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9816c-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="9816c-134">Les utilisateurs qui se servent encore de `AdventureWorks_0600` ou de `AdventureWorks_1200` peuvent continuer à le faire.</span><span class="sxs-lookup"><span data-stu-id="9816c-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="9816c-135">À ce stade, les nouvelles connexions clientes peuvent être orientées, par programme, vers l'instantané le plus récent.</span><span class="sxs-lookup"><span data-stu-id="9816c-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9816c-136">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9816c-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9816c-137">Créer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9816c-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="9816c-138">Afficher un instantané de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9816c-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="9816c-139">Supprimer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9816c-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="9816c-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9816c-140">See Also</span></span>  
 <span data-ttu-id="9816c-141">[Instantanés de base de données &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9816c-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="9816c-142">Connecter des clients à une session de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9816c-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
