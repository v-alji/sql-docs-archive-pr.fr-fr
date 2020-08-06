---
title: Changer la sécurité des transactions dans une session de mise en miroir de bases de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603032"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="eecca-102">Modifier la sécurité des transactions dans une session de mise en miroir de bases de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eecca-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="eecca-103">La sécurité des transactions est l'attribut qui contrôle le mode de fonctionnement de la session.</span><span class="sxs-lookup"><span data-stu-id="eecca-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="eecca-104">Le propriétaire de la base de données peut toutefois modifier à tout moment la sécurité des transactions.</span><span class="sxs-lookup"><span data-stu-id="eecca-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="eecca-105">Par défaut, le niveau de sécurité est FULL (mode synchrone).</span><span class="sxs-lookup"><span data-stu-id="eecca-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="eecca-106">La désactivation de la sécurité des transactions fait passer la session en mode asynchrone, ce qui optimise les performances.</span><span class="sxs-lookup"><span data-stu-id="eecca-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="eecca-107">Si l'instance principale devient non disponible, le miroir s'arrête mais reste accessible en tant que secours semi-automatique (le basculement impose un service forcé avec une possibilité de perte de données).</span><span class="sxs-lookup"><span data-stu-id="eecca-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="eecca-108">Pour activer la sécurité des transactions</span><span class="sxs-lookup"><span data-stu-id="eecca-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="eecca-109">Connectez-vous au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="eecca-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="eecca-110">Émettez l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="eecca-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="eecca-111">où *\<database>* est le nom de la base de données mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="eecca-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="eecca-112">Pour désactiver la sécurité des transactions</span><span class="sxs-lookup"><span data-stu-id="eecca-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="eecca-113">Connectez-vous au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="eecca-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="eecca-114">Émettez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="eecca-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="eecca-115">où *\<database>* est la base de données mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="eecca-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eecca-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eecca-116">See Also</span></span>  
 <span data-ttu-id="eecca-117">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="eecca-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="eecca-118">Modes de fonctionnement de la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="eecca-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
