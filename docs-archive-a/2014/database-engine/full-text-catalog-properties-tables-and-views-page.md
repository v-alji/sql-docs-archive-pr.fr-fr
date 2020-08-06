---
title: Propriétés du catalogue de texte intégral (page tables et vues) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707771"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="35d87-102">Propriétés du catalogue de texte intégral (page Tables et vues)</span><span class="sxs-lookup"><span data-stu-id="35d87-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="35d87-103">Utilisez cette page de dialogue pour consulter ou modifier les tables et les vues qui sont attribuées au catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="35d87-104">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="35d87-104">UI element list</span></span>  
 <span data-ttu-id="35d87-105">**Tous les objets admissibles de table ou de vue dans cette base de données**</span><span class="sxs-lookup"><span data-stu-id="35d87-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="35d87-106">Répertorie les tables et les vues sur lesquelles un index unique est défini, mais qui ne font pas déjà partie du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="35d87-107">Pour sélectionner une table ou une vue et l’affecter au catalogue, sélectionnez les éléments dans la zone de liste et appuyez sur le bouton « -> ».</span><span class="sxs-lookup"><span data-stu-id="35d87-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="35d87-108">**Objets de table ou de vue attribués au catalogue**</span><span class="sxs-lookup"><span data-stu-id="35d87-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="35d87-109">Répertorie les tables et les vues qui sont actuellement attribuées au catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="35d87-110">Propriétés de l'objet sélectionné</span><span class="sxs-lookup"><span data-stu-id="35d87-110">Selected Object Properties</span></span>  
 <span data-ttu-id="35d87-111">**Propriétés de l'objet sélectionné**</span><span class="sxs-lookup"><span data-stu-id="35d87-111">**Selected object properties**</span></span>  
 <span data-ttu-id="35d87-112">Affiche les propriétés de l'objet sélectionné dans la liste des objets attribués au catalogue.</span><span class="sxs-lookup"><span data-stu-id="35d87-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="35d87-113">**Index unique**</span><span class="sxs-lookup"><span data-stu-id="35d87-113">**Unique Index**</span></span>  
 <span data-ttu-id="35d87-114">Répertorie les index uniques de la table ou de la vue qui sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="35d87-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="35d87-115">**Table activée pour la recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="35d87-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="35d87-116">Activez cette case à cocher pour activer l'indexation de texte intégral sur la table.</span><span class="sxs-lookup"><span data-stu-id="35d87-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="35d87-117">Désactivez cette case à cocher pour désactiver l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="35d87-118">Grille des colonnes admissibles</span><span class="sxs-lookup"><span data-stu-id="35d87-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35d87-119">**Colonnes disponibles**</span><span class="sxs-lookup"><span data-stu-id="35d87-119">**Available Columns**</span></span>|<span data-ttu-id="35d87-120">Affiche toutes les colonnes qui sont indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="35d87-121">Activez une case à cocher pour ajouter une colonne à l'index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="35d87-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="35d87-122">**Langue pour l'analyseur lexical**</span><span class="sxs-lookup"><span data-stu-id="35d87-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="35d87-123">Affiche le langage de l'analyseur lexical.</span><span class="sxs-lookup"><span data-stu-id="35d87-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="35d87-124">**Colonne de type de données**</span><span class="sxs-lookup"><span data-stu-id="35d87-124">**Data Type Column**</span></span>|<span data-ttu-id="35d87-125">Répertorie le nom de la colonne dans la table qui contient le type de document de la colonne répertoriée dans **colonnes disponibles** si la colonne est une `varbinary(max)` `image` colonne ou.</span><span class="sxs-lookup"><span data-stu-id="35d87-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="35d87-126">**Sémantique statistique**</span><span class="sxs-lookup"><span data-stu-id="35d87-126">**Statistical Semantics**</span></span>|<span data-ttu-id="35d87-127">Sélectionnez s'il faut activer l'indexation sémantique pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="35d87-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="35d87-128">Pour plus d’informations, consultez [Recherche sémantique &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="35d87-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="35d87-129">Si vous sélectionnez une **langue** avant de sélectionner **Sémantique statistique**, et que la langue sélectionnée n'est pas associée à un modèle linguistique sémantique, la case à cocher **Sémantique statistique** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="35d87-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="35d87-130">Si vous sélectionnez **Sémantique statistique** avant de sélectionner une **langue**, les langues disponibles dans la zone de liste déroulante sont limitées à celles pour lesquelles il existe une prise en charge de modèle linguistique sémantique.</span><span class="sxs-lookup"><span data-stu-id="35d87-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="35d87-131">Suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="35d87-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35d87-132">**Automatique**</span><span class="sxs-lookup"><span data-stu-id="35d87-132">**Automatic**</span></span>|<span data-ttu-id="35d87-133">L'index de recherche en texte intégral est automatiquement mis à jour lorsque des données sont modifiées, ajoutées ou supprimées dans la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="35d87-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="35d87-134">**Manuel**</span><span class="sxs-lookup"><span data-stu-id="35d87-134">**Manual**</span></span>|<span data-ttu-id="35d87-135">Lorsque des données sont modifiées, ajoutées ou supprimées dans les données indexées, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] effectue le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="35d87-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="35d87-136">Lorsque le suivi **Manuel** des modifications est activé, l'index n'est pas automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="35d87-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="35d87-137">Par contre, un administrateur peut appliquer les modifications manuellement à l’aide d’une instruction [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="35d87-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="35d87-138">**Aucun suivi**</span><span class="sxs-lookup"><span data-stu-id="35d87-138">**Do not track change**</span></span>|<span data-ttu-id="35d87-139">Lorsque cette option est activée, les modifications apportées aux données indexées du catalogue ne sont pas enregistrées.</span><span class="sxs-lookup"><span data-stu-id="35d87-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="35d87-140">Un administrateur doit générer l'index en utilisant ALTER FULLTEXT INDEX avec FULL POPULATION ou INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="35d87-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35d87-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35d87-141">See Also</span></span>  
 <span data-ttu-id="35d87-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35d87-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="35d87-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35d87-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="35d87-144">Alimenter des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="35d87-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
