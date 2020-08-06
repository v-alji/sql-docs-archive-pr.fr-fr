---
title: Sauvegarde et restauration des serveurs de publication Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600804"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="172a8-102">Sauvegarde et restauration des serveurs de publication Oracle</span><span class="sxs-lookup"><span data-stu-id="172a8-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="172a8-103">Suivez ces instructions lors de la sauvegarde et de la restauration :</span><span class="sxs-lookup"><span data-stu-id="172a8-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="172a8-104">Vérifiez que l'Agent de lecture du journal n'est pas en cours d'exécution et que d'autres activités de la base de données sur les tables publiées n'ont pas lieu alors que le serveur de publication est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="172a8-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="172a8-105">Sauvegardez le serveur de publication et le serveur de distribution au même moment.</span><span class="sxs-lookup"><span data-stu-id="172a8-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="172a8-106">Si le serveur de publication ou le serveur de distribution doit être restauré, réinitialisez tous les abonnements.</span><span class="sxs-lookup"><span data-stu-id="172a8-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="172a8-107">Pour restaurer un Abonné à partir d'une sauvegarde (sans avoir à réinitialiser les abonnements), les transactions remises à la base de données de distribution après la fin de la dernière sauvegarde de la base de données doivent être encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="172a8-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="172a8-108">La période de temps pendant laquelle les transactions sont disponibles dépend des paramètres de rétention de la distribution.</span><span class="sxs-lookup"><span data-stu-id="172a8-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="172a8-109">Pour plus d’informations, consultez [Expiration et désactivation des abonnements](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="172a8-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="172a8-110">Si le serveur de publication ou le serveur de distribution devient désynchronisé à la suite d'une restauration de la base de données, les agents de réplication consignent des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="172a8-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="172a8-111">À ce stade, vous devez supprimer et recréer toutes les publications et tous les abonnements concernés :</span><span class="sxs-lookup"><span data-stu-id="172a8-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="172a8-112">Placez la définition des publications et des abonnements dans des scripts.</span><span class="sxs-lookup"><span data-stu-id="172a8-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="172a8-113">Pour plus d'informations, voir [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="172a8-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="172a8-114">Si la définition des publications a changé entre les versions des états du serveur de publication et du serveur de distribution, vous devez modifier les scripts.</span><span class="sxs-lookup"><span data-stu-id="172a8-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="172a8-115">Supprimez les publications et les abonnements.</span><span class="sxs-lookup"><span data-stu-id="172a8-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="172a8-116">Exécutez les scripts créés à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="172a8-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="172a8-117">Si le serveur de publication doit être supprimé et reconfiguré, supprimez le synonyme public **MSSQLSERVERDISTRIBUTOR** et l'utilisateur de réplication Oracle configuré avec l'option **CASCADE** pour supprimer tous les objets de réplication du serveur de publication Oracle.</span><span class="sxs-lookup"><span data-stu-id="172a8-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172a8-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="172a8-118">See Also</span></span>  
 <span data-ttu-id="172a8-119">[Sauvegarder et restaurer des bases de données répliquées](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="172a8-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="172a8-120">[Configurer un serveur de publication Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="172a8-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="172a8-121">Vue d’ensemble de la publication Oracle</span><span class="sxs-lookup"><span data-stu-id="172a8-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
