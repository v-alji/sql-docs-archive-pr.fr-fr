---
title: Basculer manuellement une session de mise en miroir de bases de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601644"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="f30aa-102">Basculer manuellement une session de mise en miroir de bases de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f30aa-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="f30aa-103">Lorsque la base de données en miroir est synchronisée (que son état est SYNCHRONIZED), le propriétaire de la base de données peut initier un basculement manuel vers le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="f30aa-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="f30aa-104">Le basculement manuel ne peut être lancé qu'à partir du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="f30aa-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="f30aa-105">Pour basculer manuellement une session de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="f30aa-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="f30aa-106">Connectez-vous au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="f30aa-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="f30aa-107">Définissez la base de données **master** comme contexte de la base de données :</span><span class="sxs-lookup"><span data-stu-id="f30aa-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="f30aa-108">Exécutez l'instruction suivante sur le serveur principal :</span><span class="sxs-lookup"><span data-stu-id="f30aa-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="f30aa-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, où *database_name* est la base de données mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="f30aa-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="f30aa-110">Cela lance une transition immédiate du serveur miroir vers le rôle de principal.</span><span class="sxs-lookup"><span data-stu-id="f30aa-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="f30aa-111">Sur l'ancien principal, les clients sont déconnectés de la base de données et les transactions en cours sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="f30aa-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f30aa-112">Les transactions qui ont été préparées à l'aide du service MSDTC ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) mais qui ne sont toujours pas validées au moment du basculement, sont considérés abandonnées après le basculement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f30aa-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30aa-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f30aa-113">See Also</span></span>  
 <span data-ttu-id="f30aa-114">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="f30aa-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="f30aa-115">[Basculer manuellement une session de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f30aa-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="f30aa-116">Basculement de rôle durant une session de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f30aa-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
