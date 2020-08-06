---
title: Suppression de la mise en miroir de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701795"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="71b75-102">Suppression d'une mise en miroir des bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71b75-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="71b75-103">Le propriétaire de la base de données peut arrêter manuellement une session de mise en miroir de base de données à tout moment et sur n'importe quel serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="71b75-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="71b75-104">Impact de la suppression d'une mise en mémoire</span><span class="sxs-lookup"><span data-stu-id="71b75-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="71b75-105">Lorsqu'une mise en miroir est supprimée, les événements suivants se produisent :</span><span class="sxs-lookup"><span data-stu-id="71b75-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="71b75-106">Les relations qui existaient éventuellement entre les serveurs partenaires d'une part et entre chaque serveur partenaire et le serveur témoin d'autre part sont rompues définitivement.</span><span class="sxs-lookup"><span data-stu-id="71b75-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="71b75-107">Si les serveurs partenaires communiquaient entre eux lorsque la session a été arrêtée, leur relation est immédiatement rompue sur les deux ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="71b75-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="71b75-108">Si les serveurs partenaires ne communiquaient pas (la base de données présentait alors l'état DISCONNECTED au moment de l'arrêt), la relation est rompue immédiatement sur le serveur partenaire à partir duquel la mise en miroir a été arrêtée ; lorsque l'autre serveur partenaire essaie de se reconnecter, il découvre que la session de mise en miroir est terminée.</span><span class="sxs-lookup"><span data-stu-id="71b75-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="71b75-109">Les informations sur la session de mise en miroir sont supprimées, ce qui n'est pas le cas lorsqu'une session est suspendue.</span><span class="sxs-lookup"><span data-stu-id="71b75-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="71b75-110">La mise en miroir est supprimée de la base de données principale et de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="71b75-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="71b75-111">Dans **sys.databases**, la colonne **mirroring_state** et toutes les autres colonnes de mise en miroir indiquent la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="71b75-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="71b75-112">Pour plus d’informations, consultez [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="71b75-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="71b75-113">L'instance de chaque serveur partenaire conserve une copie distincte de la base de données.</span><span class="sxs-lookup"><span data-stu-id="71b75-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="71b75-114">La base de données miroir conserve l’état RESTORING (consultez la colonne **state** de **sys.databases**), car elle a été créée par le biais de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="71b75-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="71b75-115">À ce stade, vous pouvez soit supprimer l'ancienne base de données miroir, soit la restaurer avec WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="71b75-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="71b75-116">Après avoir récupéré la base de données, vous constatez qu'elle est différente de l'ancienne base de données principale. Cela s'explique par le fait que l'opération de récupération débute un nouveau branchement de récupération.</span><span class="sxs-lookup"><span data-stu-id="71b75-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71b75-117">Pour continuer la mise en miroir après l'arrêt d'une session, vous devez établir une nouvelle session de mise en miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="71b75-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="71b75-118">Si vous créez une sauvegarde de fichier journal après l'arrêt de la mise en miroir, vous devez l'appliquer à la base de données miroir avant de redémarrer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="71b75-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="71b75-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="71b75-119">Related Tasks</span></span>  
 <span data-ttu-id="71b75-120">**Pour supprimer une mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="71b75-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="71b75-121">Supprimer une mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71b75-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="71b75-122">**Pour démarrer la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="71b75-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="71b75-123">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="71b75-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="71b75-124">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71b75-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="71b75-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71b75-125">See Also</span></span>  
 <span data-ttu-id="71b75-126">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="71b75-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="71b75-127">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71b75-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="71b75-128">[Suspension et reprise de la mise en miroir de bases de données &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71b75-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="71b75-129">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71b75-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
