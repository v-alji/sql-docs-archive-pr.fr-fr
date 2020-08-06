---
title: Propriétés de l’index de recherche en texte intégral (page général) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614795"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="2f34b-102">Propriétés d'index de recherche en texte intégral (page Général)</span><span class="sxs-lookup"><span data-stu-id="2f34b-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="2f34b-103">**Pour afficher ou changer les propriétés modifiables d'un index de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="2f34b-104">Gérer les index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="2f34b-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="2f34b-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="2f34b-105">UI element list</span></span>  
 <span data-ttu-id="2f34b-106">**Catalogue de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="2f34b-107">Affiche le nom du catalogue de texte intégral auquel l'index de recherche en texte intégral est associé.</span><span class="sxs-lookup"><span data-stu-id="2f34b-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="2f34b-108">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="2f34b-108">**Database**</span></span>  
 <span data-ttu-id="2f34b-109">Affiche le nom de la base de données dans laquelle réside l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="2f34b-110">**Table**</span><span class="sxs-lookup"><span data-stu-id="2f34b-110">**Table**</span></span>  
 <span data-ttu-id="2f34b-111">Affiche le nom de la table dans laquelle est défini l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="2f34b-112">**Clé d'index de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="2f34b-113">Affiche le nom de la clé d'index de recherche en texte intégral, qui est un index unique dans une colonne unique de la table.</span><span class="sxs-lookup"><span data-stu-id="2f34b-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="2f34b-114">**État de remplissage de la table de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="2f34b-115">Affiche l'état de remplissage de la table indexée de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="2f34b-116">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f34b-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="2f34b-117">0 = Inactif.</span><span class="sxs-lookup"><span data-stu-id="2f34b-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="2f34b-118">1 = Remplissage complet en cours.</span><span class="sxs-lookup"><span data-stu-id="2f34b-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="2f34b-119">2 = Remplissage incrémentiel en cours.</span><span class="sxs-lookup"><span data-stu-id="2f34b-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="2f34b-120">3 = Propagation des changements suivis en cours.</span><span class="sxs-lookup"><span data-stu-id="2f34b-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="2f34b-121">4 = Index de mise à jour en arrière-plan en cours (suivi des modifications automatique, par exemple).</span><span class="sxs-lookup"><span data-stu-id="2f34b-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="2f34b-122">5 = Indexation de texte intégral accélérée ou suspendue.</span><span class="sxs-lookup"><span data-stu-id="2f34b-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="2f34b-123">**Index de recherche en texte intégral actif**</span><span class="sxs-lookup"><span data-stu-id="2f34b-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="2f34b-124">Indique si la table possède un index de recherche en texte intégral actif.</span><span class="sxs-lookup"><span data-stu-id="2f34b-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="2f34b-125">1 = Vrai</span><span class="sxs-lookup"><span data-stu-id="2f34b-125">1 = True</span></span>  
  
 <span data-ttu-id="2f34b-126">0 = Faux</span><span class="sxs-lookup"><span data-stu-id="2f34b-126">0 = False</span></span>  
  
 <span data-ttu-id="2f34b-127">**Groupe de fichiers d'un index de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="2f34b-128">Le groupe de fichiers auquel l'index de recherche en texte intégral appartient.</span><span class="sxs-lookup"><span data-stu-id="2f34b-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="2f34b-129">**Liste de mots vides de l’index de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="2f34b-130">La liste de mots vides actuellement associée à l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="2f34b-131">Une liste de mots vides est une liste de [mots vides](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="2f34b-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="2f34b-132">La liste de mots vides associée à un index de recherche en texte intégral, s'applique aux requêtes de texte intégral sur cet index.</span><span class="sxs-lookup"><span data-stu-id="2f34b-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="2f34b-133">Vous pouvez supprimer la liste de mots vides de l’index en la sélectionnant **\<OFF>** dans la liste, ou vous pouvez sélectionner une autre liste de mots vides ; **\<SYSTEM>** indique la liste de mots vides système.</span><span class="sxs-lookup"><span data-stu-id="2f34b-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="2f34b-134">**Pour créer une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="2f34b-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="2f34b-135">Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="2f34b-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="2f34b-136">**Liste de propriétés de recherche**</span><span class="sxs-lookup"><span data-stu-id="2f34b-136">**Search Property List**</span></span>  
 <span data-ttu-id="2f34b-137">Liste de propriétés de recherche actuellement associée à l'index de recherche en texte intégral, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="2f34b-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="2f34b-138">Une liste de propriétés de recherche spécifie un ensemble de propriétés du document incluses dans l'index de recherche en texte intégral associé, s'il est rempli.</span><span class="sxs-lookup"><span data-stu-id="2f34b-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="2f34b-139">Pour plus d’informations, consultez [Rechercher les propriétés du document à l’aide des listes de propriétés de recherche](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="2f34b-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="2f34b-140">**\<Off>** indique qu’il n’existe actuellement aucune liste de propriétés de recherche associée à l’index.</span><span class="sxs-lookup"><span data-stu-id="2f34b-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="2f34b-141">Vous pouvez supprimer la liste de propriétés de recherche actuelle de l’index en la sélectionnant **\<Off>** dans la liste, ou vous pouvez sélectionner une autre liste de propriétés de recherche dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2f34b-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="2f34b-142">Seules les listes des propriétés de recherche de la base de données actuelle sont répertoriées ici.</span><span class="sxs-lookup"><span data-stu-id="2f34b-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f34b-143">Vous pouvez associer une liste de propriétés de recherche donnée à plusieurs index de recherche en texte intégral dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="2f34b-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="2f34b-144">**Pour créer une liste de propriétés de recherche**</span><span class="sxs-lookup"><span data-stu-id="2f34b-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="2f34b-145">Rechercher les propriétés du document à l’aide des listes des propriétés de recherche</span><span class="sxs-lookup"><span data-stu-id="2f34b-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="2f34b-146">**Nombre d'éléments de la table de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="2f34b-147">Indique le nombre de lignes qui ont été correctement indexées en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="2f34b-148">Cette propriété correspond à la propriété `TableFulltextItemCount` retournée par la fonction OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f34b-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="2f34b-149">**Documents traités de la table de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="2f34b-150">Affiche le nombre de lignes qui ont été traitées depuis le démarrage de l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="2f34b-151">Dans une table en cours d'indexation pour une recherche en texte intégral, toutes les colonnes d'une ligne sont considérées comme faisant partie d'un même document à indexer.</span><span class="sxs-lookup"><span data-stu-id="2f34b-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="2f34b-152">Les lignes supprimées ne sont pas comptées.</span><span class="sxs-lookup"><span data-stu-id="2f34b-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f34b-153">0</span><span class="sxs-lookup"><span data-stu-id="2f34b-153">0</span></span>|<span data-ttu-id="2f34b-154">Indique que l'indexation de texte intégral est terminée et qu'aucun remplissage n'est actif.</span><span class="sxs-lookup"><span data-stu-id="2f34b-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="2f34b-155">> 0</span><span class="sxs-lookup"><span data-stu-id="2f34b-155">> 0</span></span>|<span data-ttu-id="2f34b-156">Dans le cas d'un remplissage actif, indique le nombre de documents traités par des opérations d'insertion ou de mise à jour depuis une opération de remplissage, d'activation d'un suivi de modification avec remplissage de l'index de mise à jour en arrière-plan (par exemple, suivi des modifications automatique), de modification du schéma d'index de recherche en texte intégral, de reconstruction du catalogue de texte intégral, de redémarrage de l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], etc.</span><span class="sxs-lookup"><span data-stu-id="2f34b-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="2f34b-157">**Modifications en attente de la table de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="2f34b-158">Nombre d'entrées de suivi des modifications en attente de traitement.</span><span class="sxs-lookup"><span data-stu-id="2f34b-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="2f34b-159">0 = Le suivi des modifications n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="2f34b-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="2f34b-160">NULL = La table n'a pas d'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="2f34b-161">**Nombre d'erreurs de la table de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="2f34b-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="2f34b-162">Nombre de lignes que la recherche en texte intégral n'a pas indexées.</span><span class="sxs-lookup"><span data-stu-id="2f34b-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="2f34b-163">0 = Le remplissage est terminé.</span><span class="sxs-lookup"><span data-stu-id="2f34b-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="2f34b-164">\>0 = l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2f34b-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="2f34b-165">Nombre de documents qui n'ont pas été indexés depuis le début d'un remplissage de suivi des modifications intégral, incrémentiel ou manuel.</span><span class="sxs-lookup"><span data-stu-id="2f34b-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="2f34b-166">Dans le cas d'un suivi des modifications avec index de mise à jour en arrière-plan, nombre de lignes qui n'ont pas été indexées depuis le début du remplissage, ou depuis le redémarrage du remplissage.</span><span class="sxs-lookup"><span data-stu-id="2f34b-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="2f34b-167">Ceci peut être provoqué par une modification du schéma, une reconstruction du catalogue, un redémarrage du serveur, etc.</span><span class="sxs-lookup"><span data-stu-id="2f34b-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="2f34b-168">**Indexation de texte intégral activée**</span><span class="sxs-lookup"><span data-stu-id="2f34b-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="2f34b-169">Spécifie si l'indexation de texte intégral est activée.</span><span class="sxs-lookup"><span data-stu-id="2f34b-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f34b-170">**True**</span><span class="sxs-lookup"><span data-stu-id="2f34b-170">**True**</span></span>|<span data-ttu-id="2f34b-171">activé</span><span class="sxs-lookup"><span data-stu-id="2f34b-171">Enabled</span></span>|  
|<span data-ttu-id="2f34b-172">**False**</span><span class="sxs-lookup"><span data-stu-id="2f34b-172">**False**</span></span>|<span data-ttu-id="2f34b-173">Désactivé</span><span class="sxs-lookup"><span data-stu-id="2f34b-173">Disabled</span></span>|  
  
 <span data-ttu-id="2f34b-174">**Suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="2f34b-174">**Change Tracking**</span></span>  
 <span data-ttu-id="2f34b-175">Spécifie si le suivi des modifications de texte intégral est activé dans la table, et le cas échant, son type.</span><span class="sxs-lookup"><span data-stu-id="2f34b-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="2f34b-176">Le suivi des modifications de texte intégral conserve un enregistrement des lignes qui ont été modifiées dans une table ou dans une vue indexée configurée pour l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="2f34b-177">Ces modifications peuvent être propagées à l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="2f34b-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="2f34b-178">Les valeurs pour **Suivi des modifications** sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f34b-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f34b-179">**Désactivé**</span><span class="sxs-lookup"><span data-stu-id="2f34b-179">**Off**</span></span>|<span data-ttu-id="2f34b-180">L'index de recherche en texte intégral n'est pas mis à jour avec les modifications des données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="2f34b-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="2f34b-181">**Manuel**</span><span class="sxs-lookup"><span data-stu-id="2f34b-181">**Manual**</span></span>|<span data-ttu-id="2f34b-182">L'index de recherche en texte intégral n'est pas mis à jour automatiquement au fur et à mesure des modifications des données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="2f34b-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="2f34b-183">Toutefois, les modifications apportées aux données sous-jacentes sont conservées et vous pouvez les propager à</span><span class="sxs-lookup"><span data-stu-id="2f34b-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="2f34b-184">l'index de recherche en texte intégral soit de manière planifiée à l'aide de l'Agent SQL Server, soit de façon manuelle.</span><span class="sxs-lookup"><span data-stu-id="2f34b-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="2f34b-185">**Automatique**</span><span class="sxs-lookup"><span data-stu-id="2f34b-185">**Automatic**</span></span>|<span data-ttu-id="2f34b-186">L'index de recherche en texte intégral est mis à jour automatiquement au fur et à mesure des modifications des données sous-jacentes dans la table de base.</span><span class="sxs-lookup"><span data-stu-id="2f34b-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="2f34b-187">**Remplir à nouveau l'index**</span><span class="sxs-lookup"><span data-stu-id="2f34b-187">**Repopulate index**</span></span>  
 <span data-ttu-id="2f34b-188">Cliquez pour démarrer le remplissage de l'index de recherche en texte intégral lors de la sortie de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2f34b-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="2f34b-189">Sélectionnez l'un des types de remplissage suivants :</span><span class="sxs-lookup"><span data-stu-id="2f34b-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f34b-190">**Complète**</span><span class="sxs-lookup"><span data-stu-id="2f34b-190">**Full**</span></span>|<span data-ttu-id="2f34b-191">Au cours d'un remplissage complet d'une table, les entrées d'index sont créées pour toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="2f34b-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="2f34b-192">**Incrémentielle**</span><span class="sxs-lookup"><span data-stu-id="2f34b-192">**Incremental**</span></span>|<span data-ttu-id="2f34b-193">Le remplissage incrémentiel permet de mettre à jour l'index de recherche en texte intégral pour les lignes ajoutées, supprimées ou modifiées après le dernier remplissage ou pendant l'exécution de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="2f34b-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="2f34b-194">Pour effectuer un remplissage incrémentiel, il est nécessaire que la table de base contienne une colonne du type de données `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="2f34b-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="2f34b-195">**Mettre à jour**</span><span class="sxs-lookup"><span data-stu-id="2f34b-195">**Update**</span></span>|<span data-ttu-id="2f34b-196">L'index de recherche en texte intégral est mis à jour chaque fois que les données de la table de base sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="2f34b-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f34b-197">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f34b-197">See Also</span></span>  
 [<span data-ttu-id="2f34b-198">Commencer à utiliser la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="2f34b-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
