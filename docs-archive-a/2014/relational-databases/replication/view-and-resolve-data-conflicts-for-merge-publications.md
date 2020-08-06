---
title: Afficher et résoudre les conflits de données pour les publications de fusion (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], viewing conflicts
- viewing conflict information
- conflict resolution [SQL Server replication], merge replication
ms.assetid: aeee9546-4480-49f9-8b1e-c71da1f056c7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77aa9ece0073149c017f6eca35a756b22751a74b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603923"
---
# <a name="view-and-resolve-data-conflicts-for-merge-publications-sql-server-management-studio"></a><span data-ttu-id="25344-102">afficher et résoudre les conflits de données pour les publications de fusion (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="25344-102">View and Resolve Data Conflicts for Merge Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="25344-103">Les conflits de réplication de fusion sont résolus en fonction de l'outil de résolution spécifié pour chaque article.</span><span class="sxs-lookup"><span data-stu-id="25344-103">Conflicts in merge replication are resolved based on the resolver specified for each article.</span></span> <span data-ttu-id="25344-104">Par défaut, les conflits sont résolus sans que l'utilisateur doive intervenir.</span><span class="sxs-lookup"><span data-stu-id="25344-104">By default, conflicts are resolved without the need for user intervention.</span></span> <span data-ttu-id="25344-105">Mais il est possible de les afficher et de modifier le résultat de la résolution dans la Visionneuse des conflits de réplication de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25344-105">But conflicts can be viewed, and the outcome of the resolution can be changed, in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span>  
  
 <span data-ttu-id="25344-106">Les données de conflit sont disponibles dans la Visionneuse des conflits de réplication pendant la durée définie comme période de rétention des conflits (par défaut 14 jours).</span><span class="sxs-lookup"><span data-stu-id="25344-106">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period (with a default of 14 days).</span></span> <span data-ttu-id="25344-107">Pour définir la période de rétention des conflits :</span><span class="sxs-lookup"><span data-stu-id="25344-107">To set the conflict retention period, either:</span></span>  
  
-   <span data-ttu-id="25344-108">Spécifiez une valeur de rétention pour le **@conflict_retention** paramètre de [Sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25344-108">Specify a retention value for the **@conflict_retention** parameter of [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span>  
  
-   <span data-ttu-id="25344-109">Spécifiez une valeur de **conflict_retention** pour le **@property** paramètre et une valeur de rétention pour le **@value** paramètre de [SP_CHANGEMERGEPUBLICATION &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25344-109">Specify a value of **conflict_retention** for the **@property** parameter and a retention value for the **@value** parameter of [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="25344-110">Par défaut, les informations sur les conflits sont stockées dans les emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="25344-110">By default, conflict information is stored:</span></span>  
  
-   <span data-ttu-id="25344-111">Sur le serveur de publication et sur l'Abonné, si le niveau de compatibilité est égal ou supérieur à 90RTM.</span><span class="sxs-lookup"><span data-stu-id="25344-111">At the Publisher and Subscriber if the publication compatibility level is 90RTM or higher.</span></span>  
  
-   <span data-ttu-id="25344-112">Sur le serveur de publication, si le niveau de compatibilité est inférieur à 80RTM.</span><span class="sxs-lookup"><span data-stu-id="25344-112">At the Publisher if the publication compatibility level is lower than 80RTM.</span></span>  
  
-   <span data-ttu-id="25344-113">Sur le serveur de publication si les Abonnées exécutent [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25344-113">At the Publisher if Subscribers are running [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="25344-114">Les données conflictuelles ne peuvent pas être stockées sur les Abonnés [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25344-114">Conflict data cannot be stored on [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="25344-115">Le stockage des informations de conflits est contrôlé par la propriété de publication **conflict_logging**.</span><span class="sxs-lookup"><span data-stu-id="25344-115">Storage of conflict information is controlled by the **conflict_logging** publication property.</span></span> <span data-ttu-id="25344-116">Pour plus d’informations, consultez [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) et [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25344-116">For more information, see [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) and [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="25344-117">Il est également possible de résoudre les conflits de façon interactive au cours de la synchronisation à l'aide du programme de résolution interactif [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25344-117">Conflicts can also be resolved interactively during synchronization using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Interactive Resolver.</span></span> <span data-ttu-id="25344-118">Le résolveur interactif est disponible via le Gestionnaire de synchronisation [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="25344-118">The Interactive Resolver is available through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager.</span></span> <span data-ttu-id="25344-119">Pour plus d’informations, consultez [Synchroniser un abonnement à l’aide du Gestionnaire de synchronisation Windows &#40;Gestionnaire de synchronisation Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span><span class="sxs-lookup"><span data-stu-id="25344-119">For more information, see [Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span></span>  
  
### <a name="to-view-and-resolve-conflicts-for-merge-publications"></a><span data-ttu-id="25344-120">Pour afficher et résoudre les conflits des publications de fusion</span><span class="sxs-lookup"><span data-stu-id="25344-120">To view and resolve conflicts for merge publications</span></span>  
  
1.  <span data-ttu-id="25344-121">Connectez-vous au serveur de publication (ou à l’abonné, le cas échéant) dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="25344-121">Connect to the Publisher (or Subscriber if appropriate) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="25344-122">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="25344-122">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="25344-123">Cliquez avec le bouton droit sur la publication dont vous souhaitez afficher les conflits puis cliquez sur **Afficher les conflits**.</span><span class="sxs-lookup"><span data-stu-id="25344-123">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25344-124">Si vous spécifiez une valeur **'subscriber'** pour la propriété **conflict_logging** , l'option de menu **Afficher les conflits** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="25344-124">If you specified a value of **'subscriber'** for the **conflict_logging** property, the **View Conflicts** menu option is not available.</span></span> <span data-ttu-id="25344-125">Pour afficher les conflits, démarrez ConflictViewer.exe à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="25344-125">To view conflicts, start ConflictViewer.exe from the command prompt.</span></span> <span data-ttu-id="25344-126">Par défaut, ConflictViewer.exe se trouve dans le répertoire suivant : Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="25344-126">By default, ConflictViewer.exe is located in the following directory: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span></span> <span data-ttu-id="25344-127">Pour obtenir la liste des paramètres de démarrage valides, exécutez ConflictViewer.exe -?.</span><span class="sxs-lookup"><span data-stu-id="25344-127">For a list of valid startup parameters, run ConflictViewer.exe -?.</span></span>  
  
4.  <span data-ttu-id="25344-128">Dans la boîte de dialogue **Sélectionner la table de conflits** , sélectionnez une base de données et une table dont il faut afficher les conflits.</span><span class="sxs-lookup"><span data-stu-id="25344-128">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="25344-129">Dans la Visionneuse des conflits de réplication, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="25344-129">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="25344-130">Filtrer des lignes avec les boutons situés à droite de la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="25344-130">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="25344-131">Sélectionner une ligne dans la grille supérieure pour afficher des informations sur cette ligne dans la grille inférieure.</span><span class="sxs-lookup"><span data-stu-id="25344-131">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="25344-132">Sélectionner une ou plusieurs lignes dans la grille supérieure puis cliquer sur **Supprimer**, ce qui équivaut à cliquer sur le bouton **Soumettre le gagnant** (sans modifier les données).</span><span class="sxs-lookup"><span data-stu-id="25344-132">Select one or more rows in the upper grid, and then click **Remove**, which is equivalent to clicking the **Submit Winner** button (without making any changes to the data).</span></span>  
  
    -   <span data-ttu-id="25344-133">Cliquer sur le bouton des propriétés (**...**) pour afficher des informations plus détaillées sur une colonne concernée par un conflit.</span><span class="sxs-lookup"><span data-stu-id="25344-133">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="25344-134">Modifier des données dans la colonne **Gagnant du conflit** ou **Perdant du conflit** avant de soumettre les données (les données sont en lecture seule si la colonne est grisée).</span><span class="sxs-lookup"><span data-stu-id="25344-134">Edit data in the **Conflict winner** or **Conflict loser** column before submitting the data (data is read-only if the column is gray).</span></span>  
  
    -   <span data-ttu-id="25344-135">Cliquer sur **Soumettre le gagnant** pour accepter la ligne désignée comme gagnante du conflit.</span><span class="sxs-lookup"><span data-stu-id="25344-135">Click **Submit Winner** to accept the row designated as the winner of the conflict.</span></span>  
  
    -   <span data-ttu-id="25344-136">Cliquer sur **Soumettre le perdant** pour substituer la résolution et propager la valeur désignée comme perdante du conflit à tous les nœuds de la topologie.</span><span class="sxs-lookup"><span data-stu-id="25344-136">Click **Submit Loser** to override the resolution and to propagate the value designated as the loser of the conflict to all nodes in the topology.</span></span>  
  
    -   <span data-ttu-id="25344-137">Sélectionner l'option **Consigner les détails de ce conflit** pour enregistrer les données de conflit dans un journal.</span><span class="sxs-lookup"><span data-stu-id="25344-137">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="25344-138">Pour spécifier l'emplacement du fichier, pointez sur le menu **Affichage** puis cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="25344-138">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="25344-139">Entrez une valeur ou cliquez sur le bouton Parcourir (**...**) pour accéder au fichier approprié.</span><span class="sxs-lookup"><span data-stu-id="25344-139">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="25344-140">Cliquez sur **OK** pour fermer la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="25344-140">Click **OK** to exit the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="25344-141">Fermer la Visionneuse des conflits de réplication.</span><span class="sxs-lookup"><span data-stu-id="25344-141">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25344-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25344-142">See Also</span></span>  
 <span data-ttu-id="25344-143">[Détection et résolution des conflits de réplication de fusion avancée](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="25344-143">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="25344-144">Spécifier un programme de résolution d’articles de fusion</span><span class="sxs-lookup"><span data-stu-id="25344-144">Specify a Merge Article Resolver</span></span>](publish/specify-a-merge-article-resolver.md)  
  
  
