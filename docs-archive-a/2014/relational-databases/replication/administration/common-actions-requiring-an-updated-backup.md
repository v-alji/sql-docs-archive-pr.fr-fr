---
title: Actions courantes nécessitant une sauvegarde mise à jour | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696715"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="4803b-102">Actions courantes nécessitant une sauvegarde mise à jour</span><span class="sxs-lookup"><span data-stu-id="4803b-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="4803b-103">Si vous effectuez des sauvegardes régulières des journaux, toutes les modifications liées à la réplication doivent être capturées dans les sauvegardes des journaux.</span><span class="sxs-lookup"><span data-stu-id="4803b-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="4803b-104">Si vous ne sauvegardez pas les journaux, effectuez une sauvegarde des bases de données de publication, de distribution, d'abonnement ainsi que des bases de données **msdb**et **master** après avoir apporté des modifications à votre schéma ou topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="4803b-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="4803b-105">Base de données de publication</span><span class="sxs-lookup"><span data-stu-id="4803b-105">Publication Database</span></span>  
 <span data-ttu-id="4803b-106">Sauvegardez la base de données de publication après avoir :</span><span class="sxs-lookup"><span data-stu-id="4803b-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="4803b-107">créé de nouvelles de publications ;</span><span class="sxs-lookup"><span data-stu-id="4803b-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="4803b-108">modifié toute propriété de publication, notamment le filtrage ;</span><span class="sxs-lookup"><span data-stu-id="4803b-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="4803b-109">ajouté des articles à une publication existante ;</span><span class="sxs-lookup"><span data-stu-id="4803b-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="4803b-110">réalisé une réinitialisation des abonnements au niveau de la publication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="4803b-111">effectué une modification de schéma sur une table publiée ;</span><span class="sxs-lookup"><span data-stu-id="4803b-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="4803b-112">Exécution de script à la demande avec [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4803b-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="4803b-113">modifié toute propriété d'article ;</span><span class="sxs-lookup"><span data-stu-id="4803b-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="4803b-114">supprimé une publication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="4803b-115">supprimé un article ;</span><span class="sxs-lookup"><span data-stu-id="4803b-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="4803b-116">désactivé la réplication.</span><span class="sxs-lookup"><span data-stu-id="4803b-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="4803b-117">Base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="4803b-117">Distribution Database</span></span>  
 <span data-ttu-id="4803b-118">Sauvegardez la base de données de distribution après avoir :</span><span class="sxs-lookup"><span data-stu-id="4803b-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="4803b-119">créé ou modifié des profils d'Agent de réplication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="4803b-120">modifié les paramètres de profils d'Agent de réplication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="4803b-121">modifié les propriétés d'Agent de réplication (notamment les planifications) d'abonnements envoyés.</span><span class="sxs-lookup"><span data-stu-id="4803b-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="4803b-122">Une nouvelle plage d'identité est assignée par la fonctionnalité de gestion des plages d'identité.</span><span class="sxs-lookup"><span data-stu-id="4803b-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="4803b-123">Base de données d'abonnement</span><span class="sxs-lookup"><span data-stu-id="4803b-123">Subscription Database</span></span>  
 <span data-ttu-id="4803b-124">Sauvegardez la base de données d'abonnement après avoir :</span><span class="sxs-lookup"><span data-stu-id="4803b-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="4803b-125">modifié toute propriété d'abonnement ;</span><span class="sxs-lookup"><span data-stu-id="4803b-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="4803b-126">modifié la priorité d'un abonnement de fusion sur le serveur de publication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="4803b-127">supprimé un abonnement ;</span><span class="sxs-lookup"><span data-stu-id="4803b-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="4803b-128">désactivé la réplication.</span><span class="sxs-lookup"><span data-stu-id="4803b-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="4803b-129">Base de données msdb</span><span class="sxs-lookup"><span data-stu-id="4803b-129">msdb Database</span></span>  
 <span data-ttu-id="4803b-130">Sauvegardez la base de données système **msdb** sur le nœud approprié après avoir :</span><span class="sxs-lookup"><span data-stu-id="4803b-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="4803b-131">activé ou désactivé la réplication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="4803b-132">ajouté ou supprimé une base de données de distribution (sur le serveur de distribution) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="4803b-133">activé ou désactivé une base de données destinée à être publiée (sur le serveur de publication) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="4803b-134">créé ou modifié des profils d'Agent de réplication (sur le serveur de distribution) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="4803b-135">modifié des paramètres de profils d'Agent de réplication (sur le serveur de distribution) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="4803b-136">modifié les propriétés d'Agent de réplication (notamment les planifications) d'un abonnement envoyé (sur le serveur de distribution) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="4803b-137">modifié les propriétés d'Agent de réplication (notamment les planifications) d'un abonnement extrait (sur l'Abonné) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="4803b-138">créé un package DTS associé à une publication transactionnelle qui utilise des abonnements transformables (sur le serveur de distribution et sur le serveur de publication) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="4803b-139">ajouté ou supprimé un abonnement transformable (sur le serveur de distribution et sur le serveur de publication) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="4803b-140">Base de données master</span><span class="sxs-lookup"><span data-stu-id="4803b-140">master Database</span></span>  
 <span data-ttu-id="4803b-141">Sauvegardez la base de données système **master** sur le nœud approprié après avoir :</span><span class="sxs-lookup"><span data-stu-id="4803b-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="4803b-142">activé ou désactivé la réplication ;</span><span class="sxs-lookup"><span data-stu-id="4803b-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="4803b-143">ajouté ou supprimé une base de données de distribution (sur le serveur de distribution) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="4803b-144">activé ou désactivé une base de données destinée à être publiée (sur le serveur de publication) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="4803b-145">ajouté la première publication, ou supprimé la dernière, dans une base de données (sur le serveur de publication) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="4803b-146">ajouté le premier abonnement, ou supprimé le dernier, dans une base de données (sur l'Abonné) ;</span><span class="sxs-lookup"><span data-stu-id="4803b-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="4803b-147">activé ou désactivé un serveur de publication sur un serveur de publication de distribution (sur le serveur de publication et le serveur de distribution).</span><span class="sxs-lookup"><span data-stu-id="4803b-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4803b-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4803b-148">See Also</span></span>  
 <span data-ttu-id="4803b-149">[Sauvegarde et restauration des bases de données SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4803b-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="4803b-150">Sauvegarder et restaurer des bases de données répliquées</span><span class="sxs-lookup"><span data-stu-id="4803b-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
