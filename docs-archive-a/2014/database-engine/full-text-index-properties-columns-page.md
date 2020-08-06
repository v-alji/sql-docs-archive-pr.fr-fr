---
title: Propriétés de l’index de recherche en texte intégral (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614798"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="42fc3-102">Propriétés d'index de texte intégral (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="42fc3-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="42fc3-103">**Pour afficher ou modifier les propriétés d'un index de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="42fc3-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="42fc3-104">Gérer les index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="42fc3-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="42fc3-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="42fc3-105">UI element list</span></span>  
 <span data-ttu-id="42fc3-106">**Index unique**</span><span class="sxs-lookup"><span data-stu-id="42fc3-106">**Unique index**</span></span>  
 <span data-ttu-id="42fc3-107">Sélectionnez un index dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="42fc3-107">Select an index from the drop down list.</span></span> <span data-ttu-id="42fc3-108">Cet index doit être un index unique, n'acceptant pas les valeurs Null, avec une colonne à clé unique.</span><span class="sxs-lookup"><span data-stu-id="42fc3-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="42fc3-109">**Sélectionnez les colonnes admissibles à indexer en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="42fc3-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="42fc3-110">La grille affiche les colonnes de table qui sont disponibles pour cet index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="42fc3-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="42fc3-111">Les colonnes qui sont actuellement indexées en texte intégral sont cochées.</span><span class="sxs-lookup"><span data-stu-id="42fc3-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="42fc3-112">Vous pouvez si vous le souhaitez cocher des colonnes supplémentaires à indexer en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="42fc3-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="42fc3-113">Assurez-vous qu'au moins une colonne est cochée avant de cliquer sur OK.</span><span class="sxs-lookup"><span data-stu-id="42fc3-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42fc3-114">**Colonnes disponibles**</span><span class="sxs-lookup"><span data-stu-id="42fc3-114">**Available Columns**</span></span>|<span data-ttu-id="42fc3-115">Nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="42fc3-115">The column name.</span></span>|  
|<span data-ttu-id="42fc3-116">**Langue pour l'analyseur lexical**</span><span class="sxs-lookup"><span data-stu-id="42fc3-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="42fc3-117">Langue dans laquelle les analyseurs lexicaux et les générateurs de formes dérivées effectuent une analyse linguistique sur l'ensemble des données indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="42fc3-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="42fc3-118">Pour plus d’informations, consultez [configurer et gérer des](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) analyseurs lexicaux et des générateurs de formes dérivées pour la recherche et [choisir une langue lors de la création d’un index de recherche en texte intégral](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="42fc3-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="42fc3-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="42fc3-119">**Type**</span></span>|<span data-ttu-id="42fc3-120">Nom de la colonne de table qui contient le type de document de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="42fc3-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="42fc3-121">Il s’agit d’une propriété en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="42fc3-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="42fc3-122">**Sémantique statistique**</span><span class="sxs-lookup"><span data-stu-id="42fc3-122">**Statistical Semantics**</span></span>|<span data-ttu-id="42fc3-123">Sélectionnez s'il faut activer l'indexation sémantique pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="42fc3-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="42fc3-124">Pour plus d’informations, consultez [Recherche sémantique &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42fc3-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="42fc3-125">Si vous sélectionnez une **langue** avant de sélectionner **Sémantique statistique**, et que la langue sélectionnée n'est pas associée à un modèle linguistique sémantique, la case à cocher **Sémantique statistique** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="42fc3-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="42fc3-126">Si vous sélectionnez **Sémantique statistique** avant de sélectionner une **langue**, les langues disponibles dans la zone de liste déroulante sont limitées à celles pour lesquelles il existe une prise en charge de modèle linguistique sémantique.</span><span class="sxs-lookup"><span data-stu-id="42fc3-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42fc3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42fc3-127">See Also</span></span>  
 [<span data-ttu-id="42fc3-128">Alimenter des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="42fc3-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
