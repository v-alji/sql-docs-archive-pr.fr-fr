---
title: Interroger des serveurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611491"
---
# <a name="poll-servers"></a><span data-ttu-id="cf607-102">Interroger des serveurs</span><span class="sxs-lookup"><span data-stu-id="cf607-102">Poll Servers</span></span>
  <span data-ttu-id="cf607-103">Lorsqu'une administration multiserveur est mise en œuvre, les serveurs cibles contactent périodiquement le serveur maître pour transférer des informations sur les travaux ayant été exécutés et pour télécharger de nouveaux travaux.</span><span class="sxs-lookup"><span data-stu-id="cf607-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="cf607-104">Le processus de contact du serveur maître se nomme *interrogation de serveur* et intervient selon *une fréquence d’interrogation*spécifique.</span><span class="sxs-lookup"><span data-stu-id="cf607-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="cf607-105">Fréquences d'interrogation</span><span class="sxs-lookup"><span data-stu-id="cf607-105">Polling Intervals</span></span>  
 <span data-ttu-id="cf607-106">La fréquence d'interrogation (une minute par défaut) contrôle à quelle fréquence le serveur cible se connecte au serveur maître pour télécharger des instructions et transférer les résultats d'exécution d'un travail.</span><span class="sxs-lookup"><span data-stu-id="cf607-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="cf607-107">Quand un serveur cible interroge le serveur maître, il lit les opérations attribuées au serveur cible à partir de la table **sysdownloadlist** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="cf607-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="cf607-108">Ces opérations contrôlent les travaux multiserveur et différents aspects du comportement du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="cf607-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="cf607-109">La suppression, l'insertion, le démarrage d'un travail et la mise à jour de la fréquence d'interrogation du serveur cible sont des exemples d'opérations.</span><span class="sxs-lookup"><span data-stu-id="cf607-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="cf607-110">Les opérations sont publiées dans la table **sysdownloadlist** de l’une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf607-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="cf607-111">Explicitement au moyen de la procédure stockée **sp_post_msx_operation**</span><span class="sxs-lookup"><span data-stu-id="cf607-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="cf607-112">Implicitement au moyen d'autres procédures stockées de travail</span><span class="sxs-lookup"><span data-stu-id="cf607-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="cf607-113">Si vous utilisez des procédures stockées de travail pour modifier les planifications ou les étapes d'un travail multiserveur, ou bien des objets SQL-DMO pour contrôler des travaux multiserveur, vous devez soumettre la commande suivante après la modification des planifications ou des étapes d'un travail multiserveur :</span><span class="sxs-lookup"><span data-stu-id="cf607-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="cf607-114">La soumission de cette commande maintient les serveurs cibles synchronisés avec la définition du travail en cours.</span><span class="sxs-lookup"><span data-stu-id="cf607-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="cf607-115">Il n'est pas nécessaire de publier les opérations de manière explicite si vous utilisez :</span><span class="sxs-lookup"><span data-stu-id="cf607-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="cf607-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour contrôler les travaux multiserveur ;</span><span class="sxs-lookup"><span data-stu-id="cf607-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="cf607-117">des procédures stockées de travail qui ne modifient pas les planifications ou les étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="cf607-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="cf607-118">**Pour forcer l'interrogation d'un serveur maître par un serveur cible**</span><span class="sxs-lookup"><span data-stu-id="cf607-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="cf607-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf607-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="cf607-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf607-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="cf607-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf607-121">See Also</span></span>  
 [<span data-ttu-id="cf607-122">Gérer les événements</span><span class="sxs-lookup"><span data-stu-id="cf607-122">Manage Events</span></span>](manage-events.md)  
  
  
