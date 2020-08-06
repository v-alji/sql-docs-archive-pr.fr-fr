---
title: Visionneuse des conflits de réplication Microsoft (réplication transactionnelle) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599930"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="3fc2b-102">Visionneuse des conflits de réplication de Microsoft (réplication transactionnelle)</span><span class="sxs-lookup"><span data-stu-id="3fc2b-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="3fc2b-103">La Visionneuse des conflits de réplication vous permet d'examiner les conflits qui se sont produits lors de la synchronisation pour la réplication transactionnelle d'égal à égal et la réplication transactionnelle avec des abonnements de mise à jour en attente.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="3fc2b-104">Pour plus d’informations, consultez [Afficher les conflits de données pour les publications transactionnelles &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3fc2b-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fc2b-105">La Visionneuse des conflits de réplication affiche les conflits qui se produisent dans une réplication de fusion et dans une réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="3fc2b-106">Pour la réplication transactionnelle, vous pouvez utiliser la Visionneuse des conflits de réplication pour examiner les données de conflit, mais vous ne pouvez pas choisir une résolution différente du conflit.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3fc2b-107">Options</span><span class="sxs-lookup"><span data-stu-id="3fc2b-107">Options</span></span>  
 <span data-ttu-id="3fc2b-108">La Visionneuse des conflits de réplication comporte deux parties.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="3fc2b-109">La partie supérieure de la boîte de dialogue affiche la liste des conflits de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="3fc2b-110">Lorsque vous cliquez sur un élément de cette liste, les informations sur le conflit s'affichent dans la partie inférieure de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="3fc2b-111">Les données en conflit de la partie inférieure sont affichées dans les deux colonnes correspondantes (**Gagnant du conflit** et **Perdant du conflit**).</span><span class="sxs-lookup"><span data-stu-id="3fc2b-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="3fc2b-112">Si le conflit existe entre des données mises à jour et des données supprimées, il est possible qu'aucune donnée ne soit affichée pour le côté supprimé du conflit.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="3fc2b-113">Dans ce cas, la Visionneuse des conflits de réplication affiche un message dans l'une des colonnes qui indique que la ligne a été supprimée à un emplacement et mise à jour à un autre.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="3fc2b-114">Il indique également la résolution suggérée.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="3fc2b-115">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-115">**Database**</span></span>  
 <span data-ttu-id="3fc2b-116">Choisissez une base de données qui comporte des publications faisant l'objet de conflits.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="3fc2b-117">**Publication**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-117">**Publication**</span></span>  
 <span data-ttu-id="3fc2b-118">Choisissez une publication qui comporte des tables faisant l'objet de conflits.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="3fc2b-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-119">**Table**</span></span>  
 <span data-ttu-id="3fc2b-120">Choisissez une table qui comporte des conflits.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="3fc2b-121">**Définir le filtre**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-121">**Define Filter**</span></span>  
 <span data-ttu-id="3fc2b-122">Cliquez sur ce bouton pour ouvrir la boîte de dialogue **Définir les filtres** .</span><span class="sxs-lookup"><span data-stu-id="3fc2b-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="3fc2b-123">**Appliquer ou supprimer le filtre**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="3fc2b-124">Applique ou supprime un filtre défini dans la boîte de dialogue **Définir les filtres** .</span><span class="sxs-lookup"><span data-stu-id="3fc2b-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="3fc2b-125">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-125">**Select All**</span></span>  
 <span data-ttu-id="3fc2b-126">Sélectionne tous les conflits de la grille.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="3fc2b-127">**Sélectionner aucun**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-127">**Select None**</span></span>  
 <span data-ttu-id="3fc2b-128">Désélectionne tous les conflits de la grille.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="3fc2b-129">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-129">**Remove**</span></span>  
 <span data-ttu-id="3fc2b-130">Supprime les conflits sélectionnés et leurs métadonnées associées des tables système de réplication.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="3fc2b-131">**Afficher toutes les colonnes**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-131">**Show all columns**</span></span>  
 <span data-ttu-id="3fc2b-132">Sélectionnez cette option pour afficher toutes les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="3fc2b-133">**Afficher les cinq premières colonnes et les autres colonnes qui contiennent des données conflictuelles**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="3fc2b-134">Sélectionnez cette option pour afficher les cinq premières colonnes et toute colonne qui comporte des conflits.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="3fc2b-135">Cette option est utile lorsque la table comporte de nombreuses colonnes si vous voulez afficher uniquement les colonnes les plus pertinentes pour la résolution du conflit.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="3fc2b-136">Les cinq premières colonnes figurent toujours dans cette vue du fait que les champs qui identifient une ligne (par exemple la clé primaire ou les noms des champs) se trouvent souvent parmi les premières colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="3fc2b-137">**Informations sur la colonne** (**…**)</span><span class="sxs-lookup"><span data-stu-id="3fc2b-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="3fc2b-138">Affiche les informations sur la colonne : **Nom de la table**, **Nom de la colonne**, **Type de données**et **Valeur de la colonne**.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="3fc2b-139">**Consigner les détails de ce conflit**</span><span class="sxs-lookup"><span data-stu-id="3fc2b-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="3fc2b-140">Activez cette case pour enregistrer les détails du conflit dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="3fc2b-141">Pour spécifier l'emplacement du fichier, pointez sur le menu **Affichage** et cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="3fc2b-142">Entrez une valeur ou cliquez sur le bouton d'exploration (**...**) et allez au fichier voulu.</span><span class="sxs-lookup"><span data-stu-id="3fc2b-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="3fc2b-143">Cliquez sur **OK** pour fermer la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="3fc2b-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc2b-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fc2b-144">See Also</span></span>  
 <span data-ttu-id="3fc2b-145">[Détection de conflit dans la réplication d’égal à égal](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="3fc2b-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="3fc2b-146">Afficher les conflits de données pour les publications transactionnelles &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3fc2b-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  
