---
title: Index de texte intégral, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708864"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="db8e7-102">Boîte de dialogue Index de texte intégral (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="db8e7-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="db8e7-103">Cette boîte de dialogue permet de créer un index de texte intégral si vous souhaitez effectuer des recherches en texte intégral sur les colonnes de type texte de vos tables de base de données.</span><span class="sxs-lookup"><span data-stu-id="db8e7-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="db8e7-104">Un index de texte intégral se base sur un index normal ; vous devez donc d'abord le créer.</span><span class="sxs-lookup"><span data-stu-id="db8e7-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="db8e7-105">L'index normal doit être créé sur une colonne unique, non null ; il est conseillé de choisir une colonne contenant des petites valeurs plutôt que des grandes.</span><span class="sxs-lookup"><span data-stu-id="db8e7-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db8e7-106">Pour créer un index de texte intégral, vous devez d'abord créer un catalogue de texte intégral pour la base de données à l'aide d'un outil extérieur, tel que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="db8e7-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db8e7-107">La fonctionnalité d’index de texte intégral n’est pas disponible dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db8e7-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="db8e7-108">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="db8e7-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="db8e7-109">Options</span><span class="sxs-lookup"><span data-stu-id="db8e7-109">Options</span></span>  
 <span data-ttu-id="db8e7-110">**Index de texte intégral sélectionné**</span><span class="sxs-lookup"><span data-stu-id="db8e7-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="db8e7-111">Répertorie les index de texte intégral existants.</span><span class="sxs-lookup"><span data-stu-id="db8e7-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="db8e7-112">Sélectionnez un index pour afficher ses propriétés dans la partie droite de la grille.</span><span class="sxs-lookup"><span data-stu-id="db8e7-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="db8e7-113">Si la liste est vide, aucune relation de texte intégral n'est définie pour la table.</span><span class="sxs-lookup"><span data-stu-id="db8e7-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="db8e7-114">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="db8e7-114">**Add**</span></span>  
 <span data-ttu-id="db8e7-115">Crée un nouvel index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="db8e7-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="db8e7-116">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="db8e7-116">**Delete**</span></span>  
 <span data-ttu-id="db8e7-117">Supprime l’index de texte intégral sélectionné dans la liste **Index de texte intégral sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="db8e7-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="db8e7-118">**Catégorie Général**</span><span class="sxs-lookup"><span data-stu-id="db8e7-118">**General Category**</span></span>  
 <span data-ttu-id="db8e7-119">Développée, elle affiche les propriétés **Colonnes** et **Nom de catalogue de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="db8e7-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="db8e7-120">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="db8e7-120">**Columns**</span></span>  
 <span data-ttu-id="db8e7-121">Affiche une liste avec la virgule comme séparateur des noms de colonnes pouvant faire l'objet d'une recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="db8e7-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="db8e7-122">Pour afficher la liste complète, cliquez sur le bouton de sélection ( **...** ), à gauche du champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="db8e7-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="db8e7-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="db8e7-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="db8e7-124">Affiche le nom du catalogue de texte intégral dans lequel cet index de texte intégral est stocké.</span><span class="sxs-lookup"><span data-stu-id="db8e7-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="db8e7-125">Pour stocker l'index dans un autre catalogue, cliquez sur le nom du catalogue et choisissez-en un autre dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="db8e7-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db8e7-126">Le catalogue doit d'abord être créé dans un outil extérieur, tel que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="db8e7-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="db8e7-127">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="db8e7-127">**Identity Category**</span></span>  
 <span data-ttu-id="db8e7-128">Développée, elle affiche le champ Nom de cet index.</span><span class="sxs-lookup"><span data-stu-id="db8e7-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="db8e7-129">**Nom**</span><span class="sxs-lookup"><span data-stu-id="db8e7-129">**Name**</span></span>  
 <span data-ttu-id="db8e7-130">Affiche le nom spécifié par le système de cet index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="db8e7-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="db8e7-131">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="db8e7-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="db8e7-132">Développée, elle affiche les propriétés qui dictent le mode d'exécution de l'index.</span><span class="sxs-lookup"><span data-stu-id="db8e7-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="db8e7-133">**Actif**</span><span class="sxs-lookup"><span data-stu-id="db8e7-133">**Active**</span></span>  
 <span data-ttu-id="db8e7-134">Indique si vous pouvez actuellement exécuter une recherche en texte intégral à l'aide de cet index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="db8e7-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="db8e7-135">**Paramètre du suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="db8e7-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="db8e7-136">Décrit le statut du suivi des modifications pour cet index : Manuel, Auto ou Inactif.</span><span class="sxs-lookup"><span data-stu-id="db8e7-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="db8e7-137">**Analyse terminée**</span><span class="sxs-lookup"><span data-stu-id="db8e7-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="db8e7-138">Indique si l'analyse la plus récente est terminée.</span><span class="sxs-lookup"><span data-stu-id="db8e7-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="db8e7-139">Si cette propriété a la valeur Non, une analyse est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="db8e7-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="db8e7-140">**Date et heure de fin de l'analyse actuelle ou de la dernière analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="db8e7-141">Affiche la date et l'heure de l'achèvement de l'analyse la plus récente.</span><span class="sxs-lookup"><span data-stu-id="db8e7-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="db8e7-142">**Erreurs dans l'analyse actuelle ou dans la dernière analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="db8e7-143">Affiche le nombre d'erreurs dans analyse actuelle ou dans la dernière analyse.</span><span class="sxs-lookup"><span data-stu-id="db8e7-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="db8e7-144">**Version d'index**</span><span class="sxs-lookup"><span data-stu-id="db8e7-144">**Index Version**</span></span>  
 <span data-ttu-id="db8e7-145">Affiche la version du schéma de la table au moment du démarrage de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="db8e7-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="db8e7-146">**Ligne dans l'analyse actuelle ou dans la dernière analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="db8e7-147">Affiche le nombre de lignes mises à jour dans l'analyse actuelle ou dans la dernière analyse.</span><span class="sxs-lookup"><span data-stu-id="db8e7-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="db8e7-148">**Date et heure de début de l'analyse actuelle ou de la dernière analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="db8e7-149">Affiche la date et l'heure de démarrage de l'analyse actuelle ou de la dernière analyse.</span><span class="sxs-lookup"><span data-stu-id="db8e7-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="db8e7-150">**Horodatage de la prochaine analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="db8e7-151">Affiche la date et l'heure de démarrage de la prochaine analyse.</span><span class="sxs-lookup"><span data-stu-id="db8e7-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="db8e7-152">**Type de l'analyse actuelle ou de la dernière analyse**</span><span class="sxs-lookup"><span data-stu-id="db8e7-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="db8e7-153">Affiche le type de l'analyse actuelle ou de la dernière analyse : Complet, Incrémentiel, Mettre à jour ou Propagation automatique.</span><span class="sxs-lookup"><span data-stu-id="db8e7-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="db8e7-154">**Nom d'index unique**</span><span class="sxs-lookup"><span data-stu-id="db8e7-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="db8e7-155">Affiche la liste de tous les noms de colonnes de cette base de données qui possèdent des index uniques à une seule colonne.</span><span class="sxs-lookup"><span data-stu-id="db8e7-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="db8e7-156">Ces colonnes peuvent être utilisées pour créer un index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="db8e7-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8e7-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db8e7-157">See Also</span></span>  
 <span data-ttu-id="db8e7-158">[Utiliser l’Assistant indexation de texte intégral](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="db8e7-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="db8e7-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="db8e7-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
