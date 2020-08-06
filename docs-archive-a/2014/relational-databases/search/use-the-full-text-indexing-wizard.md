---
title: Utiliser l’Assistant Indexation de texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697818"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="175bd-102">Utiliser l'Assistant Indexation de texte intégral</span><span class="sxs-lookup"><span data-stu-id="175bd-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="175bd-103">L'Assistant Indexation de texte intégral vous guide tout au long d'une série d'étapes destinées à vous aider à créer un index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="175bd-104">Pour utiliser l'Assistant Indexation de texte intégral</span><span class="sxs-lookup"><span data-stu-id="175bd-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="175bd-105">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table sur laquelle vous souhaitez créer un index de recherche en texte intégral, pointez sur **Index de recherche en texte intégral**, puis cliquez sur **Define Full-Text Index**(Définir l’index de recherche en texte intégral).</span><span class="sxs-lookup"><span data-stu-id="175bd-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="175bd-106">**Index unique**</span><span class="sxs-lookup"><span data-stu-id="175bd-106">**Unique Index**</span></span>  
     <span data-ttu-id="175bd-107">Sélectionnez un index dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="175bd-107">Select an index from the drop down list.</span></span> <span data-ttu-id="175bd-108">Cet index doit être un index unique, n'acceptant pas les valeurs Null, avec une colonne à clé unique.</span><span class="sxs-lookup"><span data-stu-id="175bd-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="175bd-109">Sélectionnez le plus petit index de clé unique comme clé unique de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="175bd-110">Pour optimiser les performances, un index cluster est recommandé.</span><span class="sxs-lookup"><span data-stu-id="175bd-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="175bd-111">**Colonnes disponibles**</span><span class="sxs-lookup"><span data-stu-id="175bd-111">**Available Columns**</span></span>  
     <span data-ttu-id="175bd-112">Pour inclure une colonne dans l'index, activez la case à cocher en regard du nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="175bd-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="175bd-113">Les colonnes sur lesquelles ne doivent pas porter l'indexation de texte intégral sont grisées et leur case à cocher est désactivée.</span><span class="sxs-lookup"><span data-stu-id="175bd-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="175bd-114">**Langue pour l'analyseur lexical**</span><span class="sxs-lookup"><span data-stu-id="175bd-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="175bd-115">Sélectionnez une langue dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="175bd-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="175bd-116">Ce choix sera utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour identifier les analyseurs lexicaux appropriés pour l'index.</span><span class="sxs-lookup"><span data-stu-id="175bd-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="175bd-117">utilise des analyseurs lexicaux pour identifier les limites des mots dans les données indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="175bd-118">**Colonne de type**</span><span class="sxs-lookup"><span data-stu-id="175bd-118">**Type Column**</span></span>  
     <span data-ttu-id="175bd-119">Sélectionnez le nom de la colonne qui contient le type de document de la colonne indexée en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="175bd-120">La **colonne de type** est activée uniquement lorsque la colonne nommée dans la colonne **colonnes disponibles** est de `varbinary(max)` type `image` ou.</span><span class="sxs-lookup"><span data-stu-id="175bd-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="175bd-121">**Sémantique statistique**</span><span class="sxs-lookup"><span data-stu-id="175bd-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="175bd-122">Sélectionnez s'il faut activer l'indexation sémantique pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="175bd-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="175bd-123">Pour plus d’informations, consultez [Recherche sémantique &#40;SQL Server&#41;](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="175bd-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="175bd-124">Si vous sélectionnez une **langue** avant de sélectionner **Sémantique statistique**, et que la langue sélectionnée n'est pas associée à un modèle linguistique sémantique, la case à cocher **Sémantique statistique** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="175bd-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="175bd-125">Si vous sélectionnez **Sémantique statistique** avant de sélectionner une **langue**, les langues disponibles dans la zone de liste déroulante sont limitées à celles pour lesquelles il existe une prise en charge de modèle linguistique sémantique.</span><span class="sxs-lookup"><span data-stu-id="175bd-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="175bd-126">Sélectionnez les options de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="175bd-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="175bd-127">**Automatiquement**</span><span class="sxs-lookup"><span data-stu-id="175bd-127">**Automatically**</span></span>  
     <span data-ttu-id="175bd-128">Activez cette case d'option pour que l'index de texte intégral soit mis à jour automatiquement lorsque des modifications sont apportées aux données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="175bd-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="175bd-129">**Saisissiez**</span><span class="sxs-lookup"><span data-stu-id="175bd-129">**Manually**</span></span>  
     <span data-ttu-id="175bd-130">Activez cette case d'option si vous ne voulez pas que l'index de texte intégral soit mis à jour automatiquement lorsque des modifications sont apportées aux données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="175bd-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="175bd-131">Les modifications apportées aux données sous-jacentes sont conservées.</span><span class="sxs-lookup"><span data-stu-id="175bd-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="175bd-132">Toutefois, pour appliquer les modifications à l'index de texte intégral, vous devez démarrer ou planifier ce processus manuellement.</span><span class="sxs-lookup"><span data-stu-id="175bd-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="175bd-133">**Aucun suivi**</span><span class="sxs-lookup"><span data-stu-id="175bd-133">**Do not track changes**</span></span>  
     <span data-ttu-id="175bd-134">Activez cette case d'option si vous ne voulez pas que l'index de texte intégral soit mis à jour avec les modifications apportées aux données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="175bd-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="175bd-135">**Démarrer le remplissage complet une fois l'index créé**</span><span class="sxs-lookup"><span data-stu-id="175bd-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="175bd-136">Activez cette case d'option pour déclencher un remplissage complet lorsque cet Assistant se détermine avec succès.</span><span class="sxs-lookup"><span data-stu-id="175bd-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="175bd-137">Cela consiste à créer la structure d'index de texte intégral dans le catalogue et à la remplir avec les données indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="175bd-138">Sélectionnez le catalogue, le groupe de fichiers de l'index et la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="175bd-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="175bd-139">**Sélectionner un catalogue de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="175bd-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="175bd-140">Sélectionnez un catalogue de texte intégral dans la liste.</span><span class="sxs-lookup"><span data-stu-id="175bd-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="175bd-141">Le catalogue par défaut pour la base de données devient l'élément sélectionné par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="175bd-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="175bd-142">Si aucun catalogue n’est disponible, cette dernière est désactivée, et la case **Créer un nouveau catalogue** est cochée, mais désactivée.</span><span class="sxs-lookup"><span data-stu-id="175bd-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="175bd-143">**Créer un catalogue**</span><span class="sxs-lookup"><span data-stu-id="175bd-143">**Create a new catalog**</span></span>|<span data-ttu-id="175bd-144">Sélectionnez cette option pour créer un nouveau catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="175bd-145">**Nom**</span><span class="sxs-lookup"><span data-stu-id="175bd-145">**Name**</span></span>  
     <span data-ttu-id="175bd-146">Entrez le nom du nouveau catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="175bd-147">**Définir en tant que catalogue par défaut**</span><span class="sxs-lookup"><span data-stu-id="175bd-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="175bd-148">Sélectionnez cette option afin que le catalogue devienne la valeur par défaut pour cette base de données.</span><span class="sxs-lookup"><span data-stu-id="175bd-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="175bd-149">**Respect des accents**</span><span class="sxs-lookup"><span data-stu-id="175bd-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="175bd-150">Indiquez si le nouveau catalogue doit respecter les accents ou non.</span><span class="sxs-lookup"><span data-stu-id="175bd-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="175bd-151">Si la base de données respecte les accents, l’option **Respect** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="175bd-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="175bd-152">**Sélectionner le groupe de fichiers d'index**</span><span class="sxs-lookup"><span data-stu-id="175bd-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="175bd-153">Spécifiez le groupe de fichiers sur lequel créer l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="175bd-154">Sélectionnez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="175bd-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="175bd-155">Valeur</span><span class="sxs-lookup"><span data-stu-id="175bd-155">Value</span></span>|<span data-ttu-id="175bd-156">Description</span><span class="sxs-lookup"><span data-stu-id="175bd-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="175bd-157">Si la table ou la vue n'est pas partitionnée, sélectionnez cette option pour utiliser le même groupe de fichiers que la table ou la vue sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="175bd-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="175bd-158">Si la table ou la vue est partitionnée, le groupe de fichiers primaire est utilisé.</span><span class="sxs-lookup"><span data-stu-id="175bd-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="175bd-159">**PRIMARY**</span><span class="sxs-lookup"><span data-stu-id="175bd-159">**PRIMARY**</span></span>|<span data-ttu-id="175bd-160">Sélectionnez cette option pour utiliser le groupe de fichiers primaire pour le nouvel index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="175bd-161">*groupe de fichiers par défaut spécifié par l’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="175bd-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="175bd-162">S'il existe une liste de mots vides par défaut définie par l'utilisateur, sélectionnez son nom dans la liste pour utiliser ce groupe de fichiers pour le nouvel index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="175bd-163">**Sélectionner la liste de mots vides de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="175bd-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="175bd-164">Spécifiez une liste de mots vides à utiliser pour l'index de recherche en texte intégral ou désactivez l'utilisation de listes de mots vides.</span><span class="sxs-lookup"><span data-stu-id="175bd-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="175bd-165">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures, les mots vides sont gérés dans les bases de données à l'aide d'objets appelés listes de mots vides.</span><span class="sxs-lookup"><span data-stu-id="175bd-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="175bd-166">Une *liste de mots vides* est une liste qui, associée à un index de recherche en texte intégral, s’applique aux requêtes de texte intégral sur cet index.</span><span class="sxs-lookup"><span data-stu-id="175bd-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="175bd-167">Pour plus d’informations, consultez [Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="175bd-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="175bd-168">Sélectionnez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="175bd-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="175bd-169">Valeur</span><span class="sxs-lookup"><span data-stu-id="175bd-169">Value</span></span>|<span data-ttu-id="175bd-170">Description</span><span class="sxs-lookup"><span data-stu-id="175bd-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="175bd-171">Sélectionnez cette option pour utiliser la liste de mots vides système sur le nouvel index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="175bd-172">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="175bd-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="175bd-173">Sélectionnez cette option pour désactiver des listes de mots vides pour le nouvel index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="175bd-174">*user-defined-stoplist-name*</span><span class="sxs-lookup"><span data-stu-id="175bd-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="175bd-175">La liste affiche le nom de chaque liste de mots vides définie par l'utilisateur, le cas échéant, qui a été créée sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="175bd-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="175bd-176">Sélectionnez une liste de mots vides définie par l'utilisateur à utiliser pour le nouvel index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="175bd-177">Éventuellement, vous pouvez définir la planification de remplissage.</span><span class="sxs-lookup"><span data-stu-id="175bd-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="175bd-178">Les opérations d'indexation commencent alors immédiatement, sauf si elles ont été planifiées pour plus tard.</span><span class="sxs-lookup"><span data-stu-id="175bd-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="175bd-179">Les planifications sont créées immédiatement, même si elles ne seront pas exécutées avant l'heure planifiée.</span><span class="sxs-lookup"><span data-stu-id="175bd-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="175bd-180">**Nouvelle planification de table**</span><span class="sxs-lookup"><span data-stu-id="175bd-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="175bd-181">Définition d'un remplissage de planification de table.</span><span class="sxs-lookup"><span data-stu-id="175bd-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="175bd-182">**Nouvelle planification de catalogue**</span><span class="sxs-lookup"><span data-stu-id="175bd-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="175bd-183">Définition d'un remplissage de planification d'un catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="175bd-184">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="175bd-184">**Edit**</span></span>  
     <span data-ttu-id="175bd-185">Modification d'une planification.</span><span class="sxs-lookup"><span data-stu-id="175bd-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="175bd-186">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="175bd-186">**Delete**</span></span>  
     <span data-ttu-id="175bd-187">Suppression d'une planification.</span><span class="sxs-lookup"><span data-stu-id="175bd-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="175bd-188">Affichage ou contrôle de la progression de l'Assistant Indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="175bd-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="175bd-189">**Stop**</span><span class="sxs-lookup"><span data-stu-id="175bd-189">**Stop**</span></span>  
     <span data-ttu-id="175bd-190">Interrompt l'opération en cours et empêche l'Assistant d'exécuter les opérations de texte intégral suivantes au cours de cette session.</span><span class="sxs-lookup"><span data-stu-id="175bd-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="175bd-191">**Report**</span><span class="sxs-lookup"><span data-stu-id="175bd-191">**Report**</span></span>  
     <span data-ttu-id="175bd-192">Lorsque toutes les opérations ont fini de s'exécuter, cliquez sur ce bouton pour accéder à un rapport sur les opérations effectuées.</span><span class="sxs-lookup"><span data-stu-id="175bd-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="175bd-193">Vous pouvez afficher le rapport, l'imprimer dans un fichier, le copier dans le Presse-papiers ou l'envoyer par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="175bd-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
