---
title: Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709108"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="e450b-102">Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="e450b-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="e450b-103">Pour éviter que l'index de recherche en texte intégral ne devienne encombré, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise un mécanisme qui ignore les chaînes courantes qui ne sont d'aucune utilité pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="e450b-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="e450b-104">Ces chaînes ignorées sont appelées des *mots vides*.</span><span class="sxs-lookup"><span data-stu-id="e450b-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="e450b-105">Pendant la création d'un index, le moteur de texte intégral omet les mots vides de l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e450b-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="e450b-106">Cela signifie que les requêtes de texte intégral ne rechercheront pas les mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="e450b-107">Comprendre mots vides et mots vides</span><span class="sxs-lookup"><span data-stu-id="e450b-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="e450b-108">Un mot vide peut être un mot ayant une signification dans une langue spécifique ou être un *jeton* qui n’a pas de signification linguistique.</span><span class="sxs-lookup"><span data-stu-id="e450b-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="e450b-109">Par exemple, en français, les mots tels que « un », « et », « est » ou « le » sont écartés de l'index de recherche en texte intégral, car ils sont inutiles dans le cadre d'une recherche.</span><span class="sxs-lookup"><span data-stu-id="e450b-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="e450b-110">Bien qu'il ignore l'inclusion des mots vides, l'index de recherche en texte intégral prend en considération leur position.</span><span class="sxs-lookup"><span data-stu-id="e450b-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="e450b-111">Prenons l'exemple de l'expression suivante : « Instructions are applicable to these Adventure Works Cycles models ».</span><span class="sxs-lookup"><span data-stu-id="e450b-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="e450b-112">Le tableau suivant décrit la position des mots dans l'expression :</span><span class="sxs-lookup"><span data-stu-id="e450b-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="e450b-113">Word</span><span class="sxs-lookup"><span data-stu-id="e450b-113">Word</span></span>|<span data-ttu-id="e450b-114">Position</span><span class="sxs-lookup"><span data-stu-id="e450b-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="e450b-115">Instructions</span><span class="sxs-lookup"><span data-stu-id="e450b-115">Instructions</span></span>|<span data-ttu-id="e450b-116">1</span><span class="sxs-lookup"><span data-stu-id="e450b-116">1</span></span>|  
|<span data-ttu-id="e450b-117">are</span><span class="sxs-lookup"><span data-stu-id="e450b-117">are</span></span>|<span data-ttu-id="e450b-118">2</span><span class="sxs-lookup"><span data-stu-id="e450b-118">2</span></span>|  
|<span data-ttu-id="e450b-119">applicable</span><span class="sxs-lookup"><span data-stu-id="e450b-119">applicable</span></span>|<span data-ttu-id="e450b-120">3</span><span class="sxs-lookup"><span data-stu-id="e450b-120">3</span></span>|  
|<span data-ttu-id="e450b-121">to</span><span class="sxs-lookup"><span data-stu-id="e450b-121">to</span></span>|<span data-ttu-id="e450b-122">4</span><span class="sxs-lookup"><span data-stu-id="e450b-122">4</span></span>|  
|<span data-ttu-id="e450b-123">these</span><span class="sxs-lookup"><span data-stu-id="e450b-123">these</span></span>|<span data-ttu-id="e450b-124">5</span><span class="sxs-lookup"><span data-stu-id="e450b-124">5</span></span>|  
|<span data-ttu-id="e450b-125">Adventure</span><span class="sxs-lookup"><span data-stu-id="e450b-125">Adventure</span></span>|<span data-ttu-id="e450b-126">6</span><span class="sxs-lookup"><span data-stu-id="e450b-126">6</span></span>|  
|<span data-ttu-id="e450b-127">Works</span><span class="sxs-lookup"><span data-stu-id="e450b-127">Works</span></span>|<span data-ttu-id="e450b-128">7</span><span class="sxs-lookup"><span data-stu-id="e450b-128">7</span></span>|  
|<span data-ttu-id="e450b-129">Cycles</span><span class="sxs-lookup"><span data-stu-id="e450b-129">Cycles</span></span>|<span data-ttu-id="e450b-130">8</span><span class="sxs-lookup"><span data-stu-id="e450b-130">8</span></span>|  
|<span data-ttu-id="e450b-131">modèles</span><span class="sxs-lookup"><span data-stu-id="e450b-131">models</span></span>|<span data-ttu-id="e450b-132">9</span><span class="sxs-lookup"><span data-stu-id="e450b-132">9</span></span>|  
  
 <span data-ttu-id="e450b-133">Les mots vides « are », « to » et « these » situés aux positions 2, 4 et 5 sont écartés de l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e450b-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="e450b-134">Cependant, les informations relatives à leur position sont conservées, sans affecter la position des autres mots de l'expression.</span><span class="sxs-lookup"><span data-stu-id="e450b-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="e450b-135">Les mots vides sont gérés dans des bases de données à l'aide d'objets appelés des listes de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="e450b-136">Une *liste de mots vides* est une liste qui, associée à un index de recherche en texte intégral, s’applique aux requêtes de texte intégral sur cet index.</span><span class="sxs-lookup"><span data-stu-id="e450b-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="e450b-137">Création d’une STOPLIST</span><span class="sxs-lookup"><span data-stu-id="e450b-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="e450b-138">Vous pouvez créer une liste de mots vides de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="e450b-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="e450b-139">Utilisation de la liste de mots vides fournie par le système dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e450b-139">Using the system-supplied stoplist in the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e450b-140">est fourni avec une liste de mots vides système qui contient les mots vides les plus couramment utilisés pour chaque langue prise en charge, c'est-à-dire pour chaque langue associée aux analyseurs lexicaux fournis par défaut.</span><span class="sxs-lookup"><span data-stu-id="e450b-140">ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="e450b-141">La liste de mots vides système contient les mots vides courants pour toutes les langues prises en charge.</span><span class="sxs-lookup"><span data-stu-id="e450b-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="e450b-142">Vous pouvez copier la liste de mots vides système, et personnaliser cette liste en ajoutant et en supprimant des mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="e450b-143">La liste de mots vides système est installée dans la base de données [Resource](../databases/resource-database.md) .</span><span class="sxs-lookup"><span data-stu-id="e450b-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="e450b-144">Créer votre propre liste de mots vides, puis en lui ajoutant des mots vides pour chaque langue que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="e450b-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="e450b-145">Vous pouvez également supprimer des mots vides de votre liste de mots vides si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e450b-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="e450b-146">Télécharger une liste de mots vides personnalisée depuis toute autre base de données dans l'instance de serveur actuelle, puis ajouter et supprimer des mots vides au besoin.</span><span class="sxs-lookup"><span data-stu-id="e450b-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="e450b-147">**Pour créer une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="e450b-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="e450b-149">Pour créer une liste de mots vides de texte intégral dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="e450b-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="e450b-150">Dans l'Explorateur d'objets, développez le serveur.</span><span class="sxs-lookup"><span data-stu-id="e450b-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="e450b-151">Développez **Bases de données**, puis développez la base de données dans laquelle vous souhaitez créer la liste de mots vides de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e450b-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="e450b-152">Développez **Stockage**, puis cliquez avec le bouton droit sur **Listes de mots vides de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="e450b-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="e450b-153">Sélectionnez **Nouvelle liste de mots vides de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="e450b-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="e450b-154">Spécifiez le nom de la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="e450b-155">Éventuellement, spécifiez une autre personne comme propriétaire de la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="e450b-156">Sélectionnez l'une des options de création de liste de mots vides suivantes :</span><span class="sxs-lookup"><span data-stu-id="e450b-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="e450b-157">**Créer une liste de mots vides vide**</span><span class="sxs-lookup"><span data-stu-id="e450b-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="e450b-158">**Créer à partir de la liste de mots vides système**</span><span class="sxs-lookup"><span data-stu-id="e450b-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="e450b-159">**Créer à partir d'une liste de mots vides de texte intégral existante**</span><span class="sxs-lookup"><span data-stu-id="e450b-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="e450b-160">Pour plus d’informations, consultez [Nouvelle liste de mots vides de texte intégral &#40;page Général&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="e450b-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="e450b-161">**Pour supprimer une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="e450b-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="e450b-163">Utilisation d’une STOPLIST dans les requêtes de texte intégral</span><span class="sxs-lookup"><span data-stu-id="e450b-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="e450b-164">Pour utiliser une liste de mots vides dans des requêtes, vous devez l'associer à un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e450b-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="e450b-165">Vous pouvez joindre une liste de mots vides à un index de recherche en texte intégral lorsque vous créez l'index, ou vous pouvez modifier ultérieurement l'index pour ajouter une liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="e450b-166">**Pour créer un index de recherche en texte intégral et lui associer une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="e450b-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="e450b-168">**Pour associer ou dissocier une liste de mots vides avec un index de recherche en texte intégral existant**</span><span class="sxs-lookup"><span data-stu-id="e450b-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="e450b-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="e450b-170">**Pour supprimer un message d'erreur si des mots vides provoquent l'échec d'une opération booléenne sur une requête de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="e450b-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="e450b-171">transform noise words (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="e450b-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="e450b-172">Affichage des métadonnées mots vides et STOPLIST</span><span class="sxs-lookup"><span data-stu-id="e450b-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="e450b-173">**Pour afficher tous les mots vides d'une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="e450b-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="e450b-175">**Pour obtenir des informations sur toutes les listes de mots vides dans la base de données actuelle**</span><span class="sxs-lookup"><span data-stu-id="e450b-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="e450b-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="e450b-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="e450b-178">**Pour consulter le résultat de la segmentation du texte en unités lexicales d'une combinaison d'analyseur lexical, de dictionnaire des synonymes et de liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="e450b-179">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="e450b-180">Modification du mots vides dans une STOPLIST</span><span class="sxs-lookup"><span data-stu-id="e450b-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="e450b-181">**Pour ajouter ou supprimer des mots vides dans une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e450b-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="e450b-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e450b-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="e450b-183">Pour modifier les mots vides dans une liste de mots vides dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="e450b-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="e450b-184">Dans l'Explorateur d'objets, développez le serveur.</span><span class="sxs-lookup"><span data-stu-id="e450b-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="e450b-185">Développez **Bases de données**, puis développez la base de données.</span><span class="sxs-lookup"><span data-stu-id="e450b-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="e450b-186">Développez **Stockage**, puis sélectionnez **Listes de mots vides de texte intégral**.</span><span class="sxs-lookup"><span data-stu-id="e450b-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="e450b-187">Cliquez avec le bouton droit sur la liste de mots vides dont vous souhaitez modifier les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e450b-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e450b-188">Dans la boîte de dialogue [Propriétés de la liste de mots vides de texte intégral](../../database-engine/full-text-stoplist-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="e450b-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="e450b-189">Dans la zone de liste **Action** , sélectionnez l’une des actions suivantes : **Ajouter un mot vide**, **Supprimer le mot vide**, **Supprimer tous les mots vides**ou **Effacer la liste de mots vides**.</span><span class="sxs-lookup"><span data-stu-id="e450b-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="e450b-190">Si la zone de texte **Mot vide** est activée pour l’action sélectionnée, entrez un mot vide unique.</span><span class="sxs-lookup"><span data-stu-id="e450b-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="e450b-191">Ce nouveau mot vide doit être unique ; autrement dit, il ne doit pas déjà figurer dans la liste de mots vides correspondant à la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e450b-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="e450b-192">Si la zone de liste **Langue de texte intégral** est activée pour l’action sélectionnée, sélectionnez une langue.</span><span class="sxs-lookup"><span data-stu-id="e450b-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="e450b-193">Mise à niveau des mots parasites à partir de SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="e450b-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="e450b-194">Les mots parasites ont été remplacés par les mots vides.</span><span class="sxs-lookup"><span data-stu-id="e450b-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="e450b-195">Lorsqu'une base de données est mise à niveau à partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], les fichiers de mots parasites ne sont plus utilisés.</span><span class="sxs-lookup"><span data-stu-id="e450b-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="e450b-196">Toutefois, les fichiers de mots parasites sont stockés dans le dossier FTDATA\ FTNoiseThesaurusBak, et vous pouvez les utiliser ultérieurement lors de la mise à jour ou de la génération des listes de mots vides correspondantes.</span><span class="sxs-lookup"><span data-stu-id="e450b-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="e450b-197">Pour plus d’informations sur la mise à niveau de fichiers de mots parasites en listes de mots vides, consultez [Mise à niveau de la fonction de recherche en texte intégral](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="e450b-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
