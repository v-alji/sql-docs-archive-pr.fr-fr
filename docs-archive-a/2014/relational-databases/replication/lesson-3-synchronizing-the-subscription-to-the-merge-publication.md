---
title: 'Leçon 3 : Synchronisation de l’abonnement et de la publication de fusion | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707375"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="bdc4e-102">Leçon 3 : Synchronisation de l'abonnement et de la publication de fusion</span><span class="sxs-lookup"><span data-stu-id="bdc4e-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="bdc4e-103">Dans cette leçon, vous allez démarrer l'Agent de fusion pour initialiser l'abonnement à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdc4e-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bdc4e-104">Vous allez également utiliser cette procédure pour effectuer la synchronisation avec le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="bdc4e-105">Pour effectuer cette leçon, vous devez avoir terminé la leçon précédente, [Leçon 2 : Création d’un abonnement à la publication de fusion](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="bdc4e-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="bdc4e-106">Pour démarrer la synchronisation et initialiser l'abonnement</span><span class="sxs-lookup"><span data-stu-id="bdc4e-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="bdc4e-107">Connectez-vous à l’Abonné dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur et le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="bdc4e-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="bdc4e-108">Dans le dossier **Abonnements locaux** , cliquez avec le bouton droit sur l’abonnement de la base de données **SalesOrdersReplica** , puis cliquez sur **Afficher l’état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="bdc4e-109">Cliquez sur **Démarrer** pour initialiser l’abonnement.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bdc4e-110">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="bdc4e-110">Next Steps</span></span>  
 <span data-ttu-id="bdc4e-111">Vous avez exécuté avec succès l'Agent de fusion dans le but de démarrer la synchronisation et d'initialiser l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="bdc4e-112">Vous pouvez aussi insérer, mettre à jour ou supprimer les données des tables **SalesOrderHeader** ou **SalesOrderDetail** sur le serveur de publication ou l’Abonné, répéter cette procédure quand la connexion réseau est disponible pour synchroniser les données entre le serveur de publication et l’Abonné, puis interroger les tables **SalesOrderHeader** ou **SalesOrderDetail** de l’autre serveur pour visualiser les modifications répliquées.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="bdc4e-113">Ainsi s'achève le didacticiel sur la réplication des données avec les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="bdc4e-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="bdc4e-114">Pour obtenir un didacticiel similaire utilisant la réplication transactionnelle, consultez [Didacticiel : Réplication de données entre serveurs connectés en permanence](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bdc4e-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc4e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdc4e-115">See Also</span></span>  
 <span data-ttu-id="bdc4e-116">[Initialiser un abonnement avec un instantané](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="bdc4e-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="bdc4e-117">[Synchroniser les données](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="bdc4e-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="bdc4e-118">Synchroniser un abonnement par extraction (pull)</span><span class="sxs-lookup"><span data-stu-id="bdc4e-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
