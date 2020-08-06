---
title: Abonnement, commandes non distribuées (abonnement transactionnel, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699444"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="275f0-102">Abonnement, Commandes non distribuées (Abonnement transactionnel, SQL Server 2005 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="275f0-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="275f0-103">L'onglet **Commandes non distribuées** contient des informations sur le nombre de commandes de la base de données de distribution qui n'ont pas été distribuées à l'abonné sélectionné, ainsi que le délai estimé de distribution de ces commandes.</span><span class="sxs-lookup"><span data-stu-id="275f0-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="275f0-104">Pour plus d’informations sur l’affichage des commandes dans la base de données de distribution, consultez [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="275f0-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="275f0-105">Options</span><span class="sxs-lookup"><span data-stu-id="275f0-105">Options</span></span>  
 <span data-ttu-id="275f0-106">**Nombre de commandes dans la base de données de distribution attendant d'être appliquées à cet abonné.**</span><span class="sxs-lookup"><span data-stu-id="275f0-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="275f0-107">Nombre de commandes dans la base de données de distribution qui n'ont pas été distribuées à l'abonné sélectionné.</span><span class="sxs-lookup"><span data-stu-id="275f0-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="275f0-108">Une commande est constituée d'une instruction DML (Data Manipulation Language) Transact-SQL ou d'une instruction DDL (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="275f0-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="275f0-109">**Temps estimé pour appliquer ces commandes, sur base des performances passées**</span><span class="sxs-lookup"><span data-stu-id="275f0-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="275f0-110">Délai estimé de distribution des commandes à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="275f0-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="275f0-111">Si cette valeur est supérieure au délai nécessaire pour générer et appliquer un instantané à l'Abonné, réinitialisez l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="275f0-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="275f0-112">Pour plus d’informations, consultez [Réinitialiser des abonnements](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="275f0-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275f0-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="275f0-113">See Also</span></span>  
 <span data-ttu-id="275f0-114">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="275f0-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="275f0-115">[Surveiller les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="275f0-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="275f0-116">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="275f0-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
