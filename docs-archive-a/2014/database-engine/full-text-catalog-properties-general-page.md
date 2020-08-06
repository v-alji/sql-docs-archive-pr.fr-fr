---
title: Propriétés du catalogue de texte intégral (page général) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707776"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="64aca-102">Propriétés du catalogue de texte intégral (page Général)</span><span class="sxs-lookup"><span data-stu-id="64aca-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="64aca-103">Cette section présente les options et fonctions disponibles dans la page **Général** de la boîte de dialogue **Propriétés du catalogue de texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="64aca-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64aca-104">Pour les bases de données [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] , un catalogue de texte intégral est un concept logique qui fait référence à un groupe d'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64aca-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="64aca-105">Le catalogue de texte intégral est un objet virtuel qui n'appartient à aucun groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="64aca-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="64aca-106">Options</span><span class="sxs-lookup"><span data-stu-id="64aca-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="64aca-107">Propriétés</span><span class="sxs-lookup"><span data-stu-id="64aca-107">Properties</span></span>  
 <span data-ttu-id="64aca-108">**Catalogue par défaut**</span><span class="sxs-lookup"><span data-stu-id="64aca-108">**Default Catalog**</span></span>  
 <span data-ttu-id="64aca-109">Indique si le catalogue est le catalogue par défaut de la base de données.</span><span class="sxs-lookup"><span data-stu-id="64aca-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="64aca-110">**État du remplissage**</span><span class="sxs-lookup"><span data-stu-id="64aca-110">**Population Status**</span></span>  
 <span data-ttu-id="64aca-111">Indique l'état du catalogue.</span><span class="sxs-lookup"><span data-stu-id="64aca-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="64aca-112">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="64aca-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="64aca-113">**Idle**</span><span class="sxs-lookup"><span data-stu-id="64aca-113">**Idle**</span></span>  
  
-   <span data-ttu-id="64aca-114">**Analyse en cours**</span><span class="sxs-lookup"><span data-stu-id="64aca-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="64aca-115">**En pause**</span><span class="sxs-lookup"><span data-stu-id="64aca-115">**Paused**</span></span>  
  
-   <span data-ttu-id="64aca-116">**Throttled**</span><span class="sxs-lookup"><span data-stu-id="64aca-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="64aca-117">**Récupération**</span><span class="sxs-lookup"><span data-stu-id="64aca-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="64aca-118">**Arrêter**</span><span class="sxs-lookup"><span data-stu-id="64aca-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="64aca-119">**Remplissage incrémentiel en cours**</span><span class="sxs-lookup"><span data-stu-id="64aca-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="64aca-120">**Construction des index**</span><span class="sxs-lookup"><span data-stu-id="64aca-120">**Building index**</span></span>  
  
-   <span data-ttu-id="64aca-121">**Le disque est en pause plein**</span><span class="sxs-lookup"><span data-stu-id="64aca-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="64aca-122">**Suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="64aca-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="64aca-123">**Nombre d’éléments**</span><span class="sxs-lookup"><span data-stu-id="64aca-123">**Item Count**</span></span>  
 <span data-ttu-id="64aca-124">Affiche le nombre d'éléments de texte intégral contenus dans le catalogue.</span><span class="sxs-lookup"><span data-stu-id="64aca-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="64aca-125">**Taille du catalogue**</span><span class="sxs-lookup"><span data-stu-id="64aca-125">**Catalog Size**</span></span>  
 <span data-ttu-id="64aca-126">Affiche la taille en mégaoctets du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64aca-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="64aca-127">**Nom**</span><span class="sxs-lookup"><span data-stu-id="64aca-127">**Name**</span></span>  
 <span data-ttu-id="64aca-128">Nom du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64aca-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="64aca-129">**Respecter les accents**</span><span class="sxs-lookup"><span data-stu-id="64aca-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="64aca-130">Affichez ou modifiez si le catalogue est sensible aux marques diacritiques, telles qu’un tilde ( **~** ), un accent aigu (**́**) ou un tréma (**̈**).</span><span class="sxs-lookup"><span data-stu-id="64aca-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="64aca-131">Les valeurs autorisées sont :</span><span class="sxs-lookup"><span data-stu-id="64aca-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="64aca-132">**Non**</span><span class="sxs-lookup"><span data-stu-id="64aca-132">**No**</span></span>  
  
-   <span data-ttu-id="64aca-133">**Oui**</span><span class="sxs-lookup"><span data-stu-id="64aca-133">**Yes**</span></span>  
  
-   <span data-ttu-id="64aca-134">Pour plus d’informations sur les signes diacritiques, consultez [diacritiques](https://www.merriam-webster.com/dictionary/diacritic) dans le dictionnaire Merriam-Webster.</span><span class="sxs-lookup"><span data-stu-id="64aca-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="64aca-135">**Date du dernier remplissage**</span><span class="sxs-lookup"><span data-stu-id="64aca-135">**Last Population Date**</span></span>  
 <span data-ttu-id="64aca-136">Affiche la date du dernier remplissage du catalogue.</span><span class="sxs-lookup"><span data-stu-id="64aca-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="64aca-137">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="64aca-137">**Owner**</span></span>  
 <span data-ttu-id="64aca-138">Propriétaire du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64aca-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="64aca-139">**Nombre de clés uniques**</span><span class="sxs-lookup"><span data-stu-id="64aca-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="64aca-140">Nombre de mots uniques qui constituent l'index de texte intégral du catalogue.</span><span class="sxs-lookup"><span data-stu-id="64aca-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="64aca-141">Action du catalogue</span><span class="sxs-lookup"><span data-stu-id="64aca-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64aca-142">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="64aca-142">**None**</span></span>|<span data-ttu-id="64aca-143">N'exécute aucune opération de type **Optimiser le catalogue**, **Reconstruire le catalogue**ou **Remplir à nouveau le catalogue** .</span><span class="sxs-lookup"><span data-stu-id="64aca-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="64aca-144">**Optimiser le catalogue**</span><span class="sxs-lookup"><span data-stu-id="64aca-144">**Optimize catalog**</span></span>|<span data-ttu-id="64aca-145">Optimise l'utilisation de l'espace du catalogue et améliore les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="64aca-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="64aca-146">Cette option améliore également la précision du classement de la pertinence des résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="64aca-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="64aca-147">Cette action exécute ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="64aca-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="64aca-148">**Reconstruire le catalogue**</span><span class="sxs-lookup"><span data-stu-id="64aca-148">**Rebuild catalog**</span></span>|<span data-ttu-id="64aca-149">Supprime et reconstruit le catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="64aca-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="64aca-150">Cette opération doit être exécutée si une propriété fondamentale du catalogue a été modifiée (par exemple, le respect des accents).</span><span class="sxs-lookup"><span data-stu-id="64aca-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="64aca-151">Pour que la reconstruction réussisse, le groupe de fichiers dans lequel réside le catalogue de texte intégral doit être en ligne ou accessible en lecture et en écriture.</span><span class="sxs-lookup"><span data-stu-id="64aca-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="64aca-152">Après la reconstruction, l'index de texte intégral sera rempli à nouveau.</span><span class="sxs-lookup"><span data-stu-id="64aca-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="64aca-153">Cette action exécute ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span><span class="sxs-lookup"><span data-stu-id="64aca-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="64aca-154">**Remplir à nouveau le catalogue**</span><span class="sxs-lookup"><span data-stu-id="64aca-154">**Repopulate catalog**</span></span>|<span data-ttu-id="64aca-155">Met à jour le catalogue avec les modifications récemment apportées aux données.</span><span class="sxs-lookup"><span data-stu-id="64aca-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="64aca-156">Cette option ne requiert aucun temps mort du catalogue.</span><span class="sxs-lookup"><span data-stu-id="64aca-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64aca-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64aca-157">See Also</span></span>  
 [<span data-ttu-id="64aca-158">Alimenter des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="64aca-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
