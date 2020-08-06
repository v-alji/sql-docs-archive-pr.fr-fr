---
title: Synchroniser les données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], about synchronization
- merge replication synchronization [SQL Server replication]
- scripts [SQL Server replication], synchronization and
- synchronization [SQL Server replication]
- snapshot replication [SQL Server], synchronization
- transactional replication, synchronization
- subscriptions [SQL Server replication], synchronizing
- on demand script execution
- replication [SQL Server], synchronization
- scripts [SQL Server replication]
ms.assetid: 724802f7-7d69-46d3-a330-bd8aa7f53114
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c92cc4d1ae8e836f169a731ecf3c37c81f3dbf10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701015"
---
# <a name="synchronize-data"></a><span data-ttu-id="df0a7-102">Synchroniser les données</span><span class="sxs-lookup"><span data-stu-id="df0a7-102">Synchronize Data</span></span>
  <span data-ttu-id="df0a7-103">La synchronisation des données est le processus de propagation des modifications de données et de schéma entre le serveur de publication et les abonnés après l'application de l'instantané initial sur les abonnés.</span><span class="sxs-lookup"><span data-stu-id="df0a7-103">Synchronizing data refers to the process of data and schema changes being propagated between the Publisher and Subscribers after the initial snapshot has been applied at the Subscriber.</span></span> <span data-ttu-id="df0a7-104">La synchronisation peut se produire :</span><span class="sxs-lookup"><span data-stu-id="df0a7-104">Synchronization can occur:</span></span>  
  
-   <span data-ttu-id="df0a7-105">En continu, ce qui est le mode normal pour la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="df0a7-105">Continuously, which is typical for transactional replication.</span></span>  
  
-   <span data-ttu-id="df0a7-106">À la demande, ce qui est le mode normal pour la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="df0a7-106">On demand, which is typical for merge replication.</span></span>  
  
-   <span data-ttu-id="df0a7-107">Suivant une planification, ce qui est le mode normal pour la réplication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="df0a7-107">On a schedule, which is typical for snapshot replication.</span></span>  
  
 <span data-ttu-id="df0a7-108">Lorsqu'un abonnement est synchronisé, différents processus se produisent en fonction de votre type de réplication :</span><span class="sxs-lookup"><span data-stu-id="df0a7-108">When a subscription is synchronized, different processes occur based on the type of replication you are using:</span></span>  
  
-   <span data-ttu-id="df0a7-109">Réplication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="df0a7-109">Snapshot replication.</span></span> <span data-ttu-id="df0a7-110">La synchronisation signifie que l'Agent de distribution applique de nouveau l'instantané sur l'Abonné pour que le schéma et les données de la base de données d'abonnement soient cohérents avec ceux de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="df0a7-110">Synchronization means that the Distribution Agent reapplies the snapshot at the Subscriber so that schema and data at the subscription database is consistent with the publication database.</span></span>  
  
     <span data-ttu-id="df0a7-111">Si des modifications de données ou de schéma ont été effectuées sur le serveur de publication, un nouvel  instantané doit être généré afin de propager les modifications sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="df0a7-111">If modifications to data or schema have been made at the Publisher, a new snapshot must be generated in order to propagate modifications to the Subscriber.</span></span>  
  
-   <span data-ttu-id="df0a7-112">Réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="df0a7-112">Transactional replication.</span></span> <span data-ttu-id="df0a7-113">La synchronisation signifie que l'Agent de distribution transfère les mises à jour, les insertions, les suppressions et toute autre modification de la base de données de distribution sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="df0a7-113">Synchronization means that the Distribution Agent transfers updates, inserts, deletes, and any other changes from the distribution database to the Subscriber.</span></span>  
  
-   <span data-ttu-id="df0a7-114">Réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="df0a7-114">Merge replication.</span></span> <span data-ttu-id="df0a7-115">La synchronisation signifie que l'Agent de distribution charge les modifications de l'Abonné sur le serveur de publication, puis télécharge les modifications du serveur de publication sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="df0a7-115">Synchronization means that the Merge Agent uploads changes from the Subscriber to the Publisher and then downloads changes from the Publisher to the Subscriber.</span></span> <span data-ttu-id="df0a7-116">S'il existe des conflits, ils sont détectés et résolus.</span><span class="sxs-lookup"><span data-stu-id="df0a7-116">Conflicts, if any, are detected and resolved.</span></span> <span data-ttu-id="df0a7-117">Dès que la convergence des données est assurée, le serveur de publication et tous les abonnés disposent des mêmes valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="df0a7-117">Data is converged, and the Publisher and all Subscribers eventually end up with the same data values.</span></span> <span data-ttu-id="df0a7-118">Si des conflits ont été détectés et corrigés, le travail validé par certains utilisateurs est modifié pour résoudre le conflit en fonction de vos stratégies définies.</span><span class="sxs-lookup"><span data-stu-id="df0a7-118">If conflicts were detected and resolved, work that was committed by some of the users is changed to resolve the conflict according to policies you define.</span></span>  
  
 <span data-ttu-id="df0a7-119">Chaque fois que la synchronisation se produit, les publications d'instantanés actualisent complètement le schéma de l'Abonné, les modifications de schéma sont donc toutes appliquées sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="df0a7-119">Snapshot publications completely refresh the schema at the Subscriber every time synchronization occurs, so all schema changes are applied to the Subscriber.</span></span> <span data-ttu-id="df0a7-120">La réplication transactionnelle et la réplication de fusion prennent également en charge les modifications de schéma les plus courantes.</span><span class="sxs-lookup"><span data-stu-id="df0a7-120">Transactional replication and merge replication also support the most common schema changes.</span></span> <span data-ttu-id="df0a7-121">Pour plus d’informations, consultez [Modifier le schéma dans les bases de données de publication](publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-121">For more information, see [Make Schema Changes on Publication Databases](publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
 <span data-ttu-id="df0a7-122">Pour synchroniser un abonnement par émission de données (push), consultez [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-122">To synchronize a push subscription, see [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="df0a7-123">Pour synchroniser un abonnement par extraction de données (pull), consultez [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-123">To synchronize a pull subscription, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="df0a7-124">Pour définir des plannings de synchronisation, consultez [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-124">To set synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="df0a7-125">**Pour afficher et résoudre les conflits de synchronisation**</span><span class="sxs-lookup"><span data-stu-id="df0a7-125">**To view and resolve synchronization conflicts**</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="df0a7-126">: [Afficher et résoudre les conflits de données pour les publications de fusion &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="df0a7-126">: [View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md)</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="df0a7-127">: [Afficher les conflits de données pour les publications transactionnelles &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="df0a7-127">: [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)</span></span>  
  
## <a name="executing-code-during-synchronization"></a><span data-ttu-id="df0a7-128">Exécution de code pendant la synchronisation</span><span class="sxs-lookup"><span data-stu-id="df0a7-128">Executing Code During Synchronization</span></span>  
 <span data-ttu-id="df0a7-129">La réplication prend en charge deux méthodes d'exécution de code pendant la synchronisation :</span><span class="sxs-lookup"><span data-stu-id="df0a7-129">Replication supports two methods of executing code during synchronization</span></span>  
  
-   <span data-ttu-id="df0a7-130">L'exécution de script à la demande est prise en charge pour la réplication transactionnelle et la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="df0a7-130">On demand script execution is supported for transactional replication and merge replication.</span></span> <span data-ttu-id="df0a7-131">Vous pouvez, lors de l'utilisation de script à la demande, spécifier un script SQL à exécuter pendant la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="df0a7-131">Using on demand script execution you can specify a SQL script to run during synchronization.</span></span> <span data-ttu-id="df0a7-132">Le script est copié sur l'Abonné et exécuté par la commande **sqlcmd** au début du processus de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="df0a7-132">The script is copied to the Subscriber and executed using **sqlcmd** at the beginning of the synchronization process.</span></span> <span data-ttu-id="df0a7-133">Le script n'a pas accès aux modifications répliquées car elles sont appliquées à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="df0a7-133">The script does not have access to the replicated changes as they are applied to the Subscriber.</span></span> <span data-ttu-id="df0a7-134">Pour plus d’informations, consultez [Exécuter des scripts pendant la synchronisation &#40;programmation Transact-SQL de la réplication&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-134">For more information, see [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](execute-scripts-during-synchronization-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="df0a7-135">Les gestionnaires de logique métier sont pris en charge par la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="df0a7-135">Business logic handlers are supported for merge replication.</span></span> <span data-ttu-id="df0a7-136">Vous pouvez, à l'aide de l'infrastructure du gestionnaire de logique métier, écrire un assembly de code managé qui est appelé pendant le processus de synchronisation de fusion.</span><span class="sxs-lookup"><span data-stu-id="df0a7-136">Using the business logic handler framework you can write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="df0a7-137">L'assembly comprend une logique métier qui peut répondre à un certain nombre de conditions au cours de la synchronisation : les modifications de données, les conflits et les erreurs.</span><span class="sxs-lookup"><span data-stu-id="df0a7-137">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="df0a7-138">Pour plus d’informations, consultez [Exécuter la logique métier lors de la synchronisation de fusion](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="df0a7-138">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0a7-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df0a7-139">See Also</span></span>  
 [<span data-ttu-id="df0a7-140">Détecter et résoudre les conflits de réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="df0a7-140">Detect and Resolve Merge Replication Conflicts</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
