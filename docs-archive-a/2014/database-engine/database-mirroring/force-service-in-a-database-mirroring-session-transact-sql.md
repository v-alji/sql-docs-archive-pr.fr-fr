---
title: Forcer le service dans une session de mise en miroir de bases de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709928"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="c5869-102">Forcer le service dans une session de mise en miroir de bases de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c5869-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="c5869-103">En mode haute performance et en mode haute sécurité sans basculement automatique, si le serveur principal tombe en panne alors que le serveur miroir est disponible, le propriétaire de la base de données peut rendre la base de données disponible en imposant le basculement (avec d'éventuelles pertes de données) vers la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="c5869-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="c5869-104">Cette option est disponible uniquement si toutes les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="c5869-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="c5869-105">Le serveur principal est hors service.</span><span class="sxs-lookup"><span data-stu-id="c5869-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="c5869-106">WITNESS est défini à OFF ou est connecté au serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5869-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c5869-107">Le service forcé constitue strictement une méthode de récupération après sinistre.</span><span class="sxs-lookup"><span data-stu-id="c5869-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="c5869-108">Le basculement forcé peut impliquer une perte de données.</span><span class="sxs-lookup"><span data-stu-id="c5869-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="c5869-109">Par conséquent, ne forcez le basculement que si vous acceptez le risque d'une perte de données afin de restaurer immédiatement l'accès à la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5869-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="c5869-110">Dans le cas où un service forcé risque d'entraîner des pertes de données importantes, nous vous recommandons d'arrêter la mise en miroir et de resynchroniser manuellement les bases de données.</span><span class="sxs-lookup"><span data-stu-id="c5869-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="c5869-111">Pour plus d’informations sur les risques de forcer le service, consultez [Modes de fonctionnement de la mise en miroir de bases de données](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="c5869-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="c5869-112">Un service forcé suspend la session et démarre un nouveau branchement de récupération.</span><span class="sxs-lookup"><span data-stu-id="c5869-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="c5869-113">L'effet d'un service forcé est similaire à la suppression d'une mise en miroir et la récupération de la base de données principale initiale.</span><span class="sxs-lookup"><span data-stu-id="c5869-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="c5869-114">Cependant, un service forcé facilite la resynchronisation des bases de données (avec possibilité de perte de données) à la reprise de la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5869-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="c5869-115">Pour forcer le basculement dans une session de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="c5869-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="c5869-116">Connectez-vous au serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="c5869-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="c5869-117">Émettez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="c5869-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="c5869-118">ALTER DATABASE *<nom_base_de_données>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="c5869-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="c5869-119">où *nom_base_de_données* spécifie la base de données mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c5869-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="c5869-120">Le serveur miroir devient immédiatement le serveur principal et la mise en miroir est suspendue.</span><span class="sxs-lookup"><span data-stu-id="c5869-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5869-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5869-121">See Also</span></span>  
 <span data-ttu-id="c5869-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5869-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="c5869-123">Modes de fonctionnement de la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="c5869-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
