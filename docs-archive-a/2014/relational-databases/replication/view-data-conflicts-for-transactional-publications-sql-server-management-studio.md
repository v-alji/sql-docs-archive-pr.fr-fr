---
title: Afficher les conflits de données pour les publications transactionnelles (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612765"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="0c949-102">afficher les conflits de données pour les publications de fusion (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0c949-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0c949-103">Vous pouvez afficher les conflits pour la réplication transactionnelle d'égal à égal et la réplication transactionnelle avec des abonnements mis à jour en attente dans la Visionneuse des conflits de réplication de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c949-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="0c949-104">Pour plus d’informations sur la détection et la résolution des conflits, consultez [Détection de conflit dans la réplication d’égal à égal](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) et [Définir des options de résolution des conflits de mise à jour en attente &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="0c949-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="0c949-105">La disponibilité des données de conflit dépend du type de réplication et de la période de rétention des conflits :</span><span class="sxs-lookup"><span data-stu-id="0c949-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="0c949-106">Pour la réplication d'égal à égal, par défaut, l'Agent de distribution échoue lorsqu'il détecte un conflit.</span><span class="sxs-lookup"><span data-stu-id="0c949-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="0c949-107">Une erreur de conflit est enregistrée dans le journal des erreurs, mais aucune donnée de conflit n'est enregistrée dans la table de conflits ; par conséquent, la consultation de cette erreur n'est pas possible.</span><span class="sxs-lookup"><span data-stu-id="0c949-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="0c949-108">Si l'Agent de distribution est autorisé à continuer, un conflit est enregistré localement sur chaque nœud où il a été détecté.</span><span class="sxs-lookup"><span data-stu-id="0c949-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="0c949-109">Pour plus d'informations, consultez « Gestion des conflits » dans [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0c949-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="0c949-110">Pour des abonnements mis à jour en attente, les données sont disponibles pour chaque conflit.</span><span class="sxs-lookup"><span data-stu-id="0c949-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="0c949-111">Les données de conflit sont disponibles dans la Visionneuse des conflits de réplication pendant la durée définie comme période de rétention des conflits (par défaut, 14 jours).</span><span class="sxs-lookup"><span data-stu-id="0c949-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="0c949-112">Pour définir la période de rétention des conflits, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c949-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="0c949-113">Spécifiez une valeur de rétention pour le paramètre @conflict_retention de [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0c949-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="0c949-114">Spécifiez une valeur `'conflict_retention'` pour le @property paramètre et une valeur de rétention pour le @value paramètre de [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0c949-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="0c949-115">Pour afficher les conflits</span><span class="sxs-lookup"><span data-stu-id="0c949-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="0c949-116">Connectez-vous au serveur approprié dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur :</span><span class="sxs-lookup"><span data-stu-id="0c949-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="0c949-117">Pour la réplication d'égal à égal, il s'agit du nœud où le conflit s'est produit.</span><span class="sxs-lookup"><span data-stu-id="0c949-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="0c949-118">Pour les abonnements mis à jour en attente, il s'agit du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="0c949-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="0c949-119">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="0c949-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="0c949-120">Cliquez avec le bouton droit sur la publication dont vous souhaitez afficher les conflits puis cliquez sur **Afficher les conflits**.</span><span class="sxs-lookup"><span data-stu-id="0c949-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="0c949-121">Dans la boîte de dialogue **Sélectionner la table de conflits** , sélectionnez une base de données et une table dont il faut afficher les conflits.</span><span class="sxs-lookup"><span data-stu-id="0c949-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="0c949-122">Dans la Visionneuse des conflits de réplication, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c949-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="0c949-123">Filtrer des lignes avec les boutons situés à droite de la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="0c949-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="0c949-124">Sélectionner une ligne dans la grille supérieure pour afficher des informations sur cette ligne dans la grille inférieure.</span><span class="sxs-lookup"><span data-stu-id="0c949-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="0c949-125">Sélectionner une ou plusieurs lignes dans la grille supérieure puis cliquer sur **Supprimer**, pour supprimer la ligne de la table des métadonnées des conflits.</span><span class="sxs-lookup"><span data-stu-id="0c949-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="0c949-126">Cliquer sur le bouton des propriétés (**...**) pour afficher des informations plus détaillées sur une colonne concernée par un conflit.</span><span class="sxs-lookup"><span data-stu-id="0c949-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="0c949-127">Sélectionner l'option **Consigner les détails de ce conflit** pour enregistrer les données de conflit dans un journal.</span><span class="sxs-lookup"><span data-stu-id="0c949-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="0c949-128">Pour spécifier l'emplacement du fichier, pointez sur le menu **Affichage** puis cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="0c949-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="0c949-129">Entrez une valeur ou cliquez sur le bouton Parcourir (**...**) pour accéder au fichier approprié.</span><span class="sxs-lookup"><span data-stu-id="0c949-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="0c949-130">Cliquez sur **OK** pour fermer la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="0c949-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="0c949-131">Fermer la Visionneuse des conflits de réplication.</span><span class="sxs-lookup"><span data-stu-id="0c949-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c949-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c949-132">See Also</span></span>  
 <span data-ttu-id="0c949-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="0c949-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="0c949-134">Queued Updating Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="0c949-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
