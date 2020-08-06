---
title: MSSQLSERVER_1457 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612912"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="df21d-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="df21d-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="df21d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="df21d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df21d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="df21d-104">Product Name</span></span>|<span data-ttu-id="df21d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="df21d-105">SQL Server</span></span>|  
|<span data-ttu-id="df21d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="df21d-106">Event ID</span></span>|<span data-ttu-id="df21d-107">1457</span><span class="sxs-lookup"><span data-stu-id="df21d-107">1457</span></span>|  
|<span data-ttu-id="df21d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="df21d-108">Event Source</span></span>|<span data-ttu-id="df21d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="df21d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="df21d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="df21d-110">Component</span></span>|<span data-ttu-id="df21d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="df21d-111">SQLEngine</span></span>|  
|<span data-ttu-id="df21d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="df21d-112">Symbolic Name</span></span>|<span data-ttu-id="df21d-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="df21d-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="df21d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="df21d-114">Message Text</span></span>|<span data-ttu-id="df21d-115">La synchronisation de la base de données miroir, '%.\*ls', a été interrompue : la base de données est donc dans un état incohérent.</span><span class="sxs-lookup"><span data-stu-id="df21d-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="df21d-116">La commande ALTER DATABASE a échoué.</span><span class="sxs-lookup"><span data-stu-id="df21d-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="df21d-117">Vérifiez que la base de données miroir est sauvegardée et en ligne, reconnectez l'instance de serveur miroir, puis autorisez la base de données miroir à terminer la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="df21d-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df21d-118">Explication</span><span class="sxs-lookup"><span data-stu-id="df21d-118">Explanation</span></span>  
 <span data-ttu-id="df21d-119">Ce message indique que l’instruction ALTER DATABASE *nom_base_de_données* SET PARTNER OFF a échoué.</span><span class="sxs-lookup"><span data-stu-id="df21d-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="df21d-120">L'échec de la tentative de suppression de la mise en miroir de bases de données a interrompu la synchronisation de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="df21d-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="df21d-121">La base de données est incohérente.</span><span class="sxs-lookup"><span data-stu-id="df21d-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df21d-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="df21d-122">User Action</span></span>  
 <span data-ttu-id="df21d-123">Pour résoudre cette erreur, vous pouvez effectuer l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="df21d-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="df21d-124">Rétablissez le contact entre le serveur miroir et le serveur principal pour permettre la synchronisation de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="df21d-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="df21d-125">Supprimez la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="df21d-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="df21d-126">Après avoir supprimé la base de données miroir, vous pouvez en créer une nouvelle à partir de vos sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="df21d-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df21d-127">Vous pouvez supprimer la base de données miroir lorsque la mise en miroir de bases de données est toujours activée uniquement après l'échec d'une instruction SET PARTNER OFF.</span><span class="sxs-lookup"><span data-stu-id="df21d-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df21d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df21d-128">See Also</span></span>  
 <span data-ttu-id="df21d-129">[Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="df21d-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="df21d-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="df21d-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="df21d-131">[Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="df21d-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="df21d-132">[Suppression d’une mise en miroir des bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="df21d-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="df21d-133">Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="df21d-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
