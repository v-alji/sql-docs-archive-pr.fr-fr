---
title: Configurer et gérer les fichiers de dictionnaire des synonymes pour la recherche en texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710543"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="98629-102">Configurer et gérer les fichiers de dictionnaire des synonymes pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="98629-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="98629-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les requêtes de texte intégral peuvent rechercher les synonymes des termes spécifiés par l'utilisateur grâce à un dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="98629-104">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \*\* définit un jeu de synonymes pour une langue spécifique.</span><span class="sxs-lookup"><span data-stu-id="98629-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="98629-105">Les administrateurs système peuvent définir deux formes de synonymes : les jeux d'expansion et les jeux de remplacement.</span><span class="sxs-lookup"><span data-stu-id="98629-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="98629-106">En développant un dictionnaire des synonymes adapté à vos données de texte intégral, vous pouvez élargir efficacement l'étendue des requêtes de texte intégral sur ces données.</span><span class="sxs-lookup"><span data-stu-id="98629-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="98629-107">La mise en correspondance avec le dictionnaire des synonymes intervient pour toutes les requêtes [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) et [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) et pour les requêtes [CONTAINS](/sql/t-sql/queries/contains-transact-sql) et [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) qui spécifient la clause FORMSOF THESAURUS.</span><span class="sxs-lookup"><span data-stu-id="98629-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="98629-108">Tâches de base pour la configuration d’un fichier de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="98629-109">Pour que vos requêtes de recherche en texte intégral sur votre instance de serveur puissent rechercher les synonymes dans une langue donnée, vous devez au préalable définir des mappages de dictionnaire des synonymes pour cette langue.</span><span class="sxs-lookup"><span data-stu-id="98629-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="98629-110">Chaque dictionnaire des synonymes doit être configuré manuellement de façon à définir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="98629-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="98629-111">Paramètre de signes diacritiques</span><span class="sxs-lookup"><span data-stu-id="98629-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="98629-112">Pour un dictionnaire des synonymes donné, tous les modèles de recherche sont sensibles ou insensibles aux signes diacritiques tels qu’un tilde ( **~** ), un accent aigu (**??**) ou un tréma (**??**) (autrement dit, *respect* des accents ou non- *respect des accents*).</span><span class="sxs-lookup"><span data-stu-id="98629-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="98629-113">Par exemple, supposons que vous spécifiiez le modèle « CAF ?? »</span><span class="sxs-lookup"><span data-stu-id="98629-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="98629-114">à remplacer par d’autres modèles dans une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98629-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="98629-115">Si le dictionnaire des synonymes ne tient pas compte des accents, la recherche en texte intégral remplace les modèles « CAF ?? »</span><span class="sxs-lookup"><span data-stu-id="98629-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="98629-116">et « cafe ».</span><span class="sxs-lookup"><span data-stu-id="98629-116">and "cafe".</span></span> <span data-ttu-id="98629-117">Si le dictionnaire des synonymes respecte les accents, la recherche en texte intégral remplace uniquement le modèle « CAF ?? ».</span><span class="sxs-lookup"><span data-stu-id="98629-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="98629-118">Par défaut, un dictionnaire des synonymes ne tient pas compte des accents.</span><span class="sxs-lookup"><span data-stu-id="98629-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="98629-119">Jeu d'expansion</span><span class="sxs-lookup"><span data-stu-id="98629-119">Expansion set</span></span>  
  
     <span data-ttu-id="98629-120">Un jeu d'expansion contient un groupe de synonymes, tels que « writer », « author » et « journalist », qui sont substitués les uns aux autres par une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98629-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="98629-121">Les requêtes qui contiennent une correspondance pour un synonyme dans un jeu d'expansion sont développées de manière à inclure tous les autres synonymes du jeu d'expansion.</span><span class="sxs-lookup"><span data-stu-id="98629-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="98629-122">Pour plus d'informations, consultez « Structure XML d'un jeu d'expansion », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="98629-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="98629-123">Jeu de remplacement</span><span class="sxs-lookup"><span data-stu-id="98629-123">Replacement set</span></span>  
  
     <span data-ttu-id="98629-124">Un jeu de remplacement contient un modèle de texte à remplacer par un jeu de substitution.</span><span class="sxs-lookup"><span data-stu-id="98629-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="98629-125">Reportez-vous à l'exemple de la section « Structure XML d'un jeu de remplacement », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="98629-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="98629-126">Contenu initial des fichiers de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="98629-127">fournit un fichier de dictionnaire des synonymes XML par langue prise en charge.</span><span class="sxs-lookup"><span data-stu-id="98629-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="98629-128">Ces fichiers sont essentiellement vides.</span><span class="sxs-lookup"><span data-stu-id="98629-128">These files are essentially empty.</span></span> <span data-ttu-id="98629-129">Ils contiennent uniquement la structure XML de niveau supérieur commune à tous les dictionnaires des synonymes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et un exemple commenté de dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="98629-130">Les fichiers de dictionnaires des synonymes fournis avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiennent tous le code XML suivant :</span><span class="sxs-lookup"><span data-stu-id="98629-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="98629-131">Emplacement des fichiers de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="98629-132">L'emplacement par défaut des fichiers de dictionnaires des synonymes est :</span><span class="sxs-lookup"><span data-stu-id="98629-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="98629-133">*<SQL_Server_data_files_path>* \MSSQL12. MSSQLSERVER\MSSQL\FTDATA</span><span class="sxs-lookup"><span data-stu-id="98629-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="98629-134">Cet emplacement par défaut contient les fichiers suivants :</span><span class="sxs-lookup"><span data-stu-id="98629-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="98629-135">Fichiers de dictionnaires des synonymes spécifiques à chaque langue</span><span class="sxs-lookup"><span data-stu-id="98629-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="98629-136">Pendant l'installation, les fichiers des dictionnaires des synonymes vides sont installés à l'emplacement précité.</span><span class="sxs-lookup"><span data-stu-id="98629-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="98629-137">Un fichier distinct est fourni pour chaque langue prise en charge.</span><span class="sxs-lookup"><span data-stu-id="98629-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="98629-138">Ces fichiers peuvent être personnalisés par un administrateur système.</span><span class="sxs-lookup"><span data-stu-id="98629-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="98629-139">Les noms de fichier par défaut des fichiers des dictionnaires des synonymes utilisent le format suivant :</span><span class="sxs-lookup"><span data-stu-id="98629-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="98629-140">« TS » + \<three-letter language-abbreviation> + « . Xml »</span><span class="sxs-lookup"><span data-stu-id="98629-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="98629-141">Le nom du fichier du dictionnaire des synonymes d’une langue donnée est spécifié dans le Registre, dans la valeur HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<nom-instance>\MSSearch\\<abréviation-langue>.</span><span class="sxs-lookup"><span data-stu-id="98629-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="98629-142">Fichier du dictionnaire des synonymes global</span><span class="sxs-lookup"><span data-stu-id="98629-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="98629-143">Un fichier de dictionnaire des synonymes global vide, tsGlobal.xml.</span><span class="sxs-lookup"><span data-stu-id="98629-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="98629-144">Vous pouvez modifier l'emplacement et le nom d'un fichier de dictionnaire des synonymes en modifiant sa clé de Registre.</span><span class="sxs-lookup"><span data-stu-id="98629-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="98629-145">Pour chaque langue, l'emplacement du fichier de dictionnaire des synonymes est spécifié dans la valeur de Registre suivante :</span><span class="sxs-lookup"><span data-stu-id="98629-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="98629-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/ \<instance name> /MSSearch/Language/ \<language-abbreviation> /TsaurusFile</span><span class="sxs-lookup"><span data-stu-id="98629-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="98629-147">Le fichier du dictionnaire des synonymes global correspond à la langue « neutre », avec le LCID 0.</span><span class="sxs-lookup"><span data-stu-id="98629-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="98629-148">Cette valeur ne peut être modifiée que par des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="98629-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="98629-149">Utilisation des fichiers de dictionnaire des synonymes dans les requêtes</span><span class="sxs-lookup"><span data-stu-id="98629-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="98629-150">Une requête de dictionnaire des synonymes utilise à la fois le dictionnaire des synonymes spécifique à la langue et le dictionnaire des synonymes global.</span><span class="sxs-lookup"><span data-stu-id="98629-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="98629-151">En premier lieu, la requête recherche le fichier spécifique à la langue et le charge en vue du traitement (à moins qu'il ne soit déjà chargé).</span><span class="sxs-lookup"><span data-stu-id="98629-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="98629-152">La requête est développée pour inclure les synonymes spécifiques à la langue spécifiés par les règles de jeu d'expansion et de jeu de remplacement définies dans le fichier du dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="98629-153">Ces étapes sont ensuite répétées pour le dictionnaire des synonymes global.</span><span class="sxs-lookup"><span data-stu-id="98629-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="98629-154">Toutefois, si un terme fait déjà partie d'une correspondance dans le fichier du dictionnaire des synonymes spécifique à la langue, ce terme est inéligible pour la mise en correspondance dans le dictionnaire des synonymes global.</span><span class="sxs-lookup"><span data-stu-id="98629-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="98629-155">Fonctionnement de la structure d’un fichier de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="98629-156">Chaque fichier de dictionnaire des synonymes définit un conteneur XML dont l’ID est `Microsoft Search Thesaurus` et un commentaire, `<!--` ... `-->`, qui contient un exemple de dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="98629-157">Le dictionnaire des synonymes est défini dans un \<thesaurus> élément qui contient des exemples des éléments enfants qui définissent le paramètre de signes diacritiques, les jeux d’expansion et les jeux de remplacement, comme suit :</span><span class="sxs-lookup"><span data-stu-id="98629-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="98629-158">Structure XML du paramètre de signes diacritiques</span><span class="sxs-lookup"><span data-stu-id="98629-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="98629-159">Le paramètre de signes diacritiques d'un dictionnaire des synonymes est spécifié dans un élément <diacritics_sensitive> unique.</span><span class="sxs-lookup"><span data-stu-id="98629-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="98629-160">Cet élément contient une valeur entière qui contrôle le respect des accents, comme suit :</span><span class="sxs-lookup"><span data-stu-id="98629-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="98629-161">Paramètre de signes diacritiques</span><span class="sxs-lookup"><span data-stu-id="98629-161">Diacritics Setting</span></span>|<span data-ttu-id="98629-162">Valeur</span><span class="sxs-lookup"><span data-stu-id="98629-162">Value</span></span>|<span data-ttu-id="98629-163">XML</span><span class="sxs-lookup"><span data-stu-id="98629-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="98629-164">ne respectent pas les accents</span><span class="sxs-lookup"><span data-stu-id="98629-164">Accent insensitive</span></span>|<span data-ttu-id="98629-165">0</span><span class="sxs-lookup"><span data-stu-id="98629-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="98629-166">respectent les accents</span><span class="sxs-lookup"><span data-stu-id="98629-166">Accent sensitive</span></span>|<span data-ttu-id="98629-167">1</span><span class="sxs-lookup"><span data-stu-id="98629-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="98629-168">Ce paramètre ne peut être appliqué qu'une seule fois dans le fichier et s'applique à tous les modèles de recherche au sein du fichier.</span><span class="sxs-lookup"><span data-stu-id="98629-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="98629-169">Vous ne pouvez pas définir ce paramètre pour des modèles individuels.</span><span class="sxs-lookup"><span data-stu-id="98629-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="98629-170">Structure XML d'un ensemble d'expansion</span><span class="sxs-lookup"><span data-stu-id="98629-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="98629-171">Chaque jeu d’expansion est compris dans un élément \<expansion>.</span><span class="sxs-lookup"><span data-stu-id="98629-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="98629-172">Dans cet élément, vous spécifiez une ou plusieurs substitutions dans un élément \<sub>.</span><span class="sxs-lookup"><span data-stu-id="98629-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="98629-173">Dans le jeu d'expansion, vous pouvez spécifier un groupe de substitutions synonymes les unes des autres.</span><span class="sxs-lookup"><span data-stu-id="98629-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="98629-174">Par exemple, vous pouvez modifier la section expansion pour traiter les substitutions « writer », « author » et « journalist » en tant que synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="98629-175">Les requêtes de recherche en texte intégral contenant des correspondances dans une substitution sont étendues pour inclure toutes les autres substitutions spécifiées dans le jeu d'expansion.</span><span class="sxs-lookup"><span data-stu-id="98629-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="98629-176">Par conséquent, dans l'exemple précédent, lorsque vous émettez une requête FORMS OF THESAURUS ou FREETEXT pour le mot « author », la recherche en texte intégral renvoie également les résultats contenant les mots « writer » et « journalist ».</span><span class="sxs-lookup"><span data-stu-id="98629-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="98629-177">Voici à quoi ressemble la section du jeu d'expansion pour l'exemple ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="98629-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="98629-178">Structure XML d'un jeu de remplacement</span><span class="sxs-lookup"><span data-stu-id="98629-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="98629-179">Chaque jeu de remplacement est compris dans un élément \<replacement>.</span><span class="sxs-lookup"><span data-stu-id="98629-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="98629-180">Dans cet élément, vous pouvez spécifier un ou plusieurs modèles dans un élément \<pat> et zéro, une ou plusieurs substitutions dans des éléments \<sub>, à raison d’un par synonyme.</span><span class="sxs-lookup"><span data-stu-id="98629-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="98629-181">Vous pouvez spécifier un modèle de texte à remplacer par un jeu de substitution.</span><span class="sxs-lookup"><span data-stu-id="98629-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="98629-182">Les modèles et les substitutions peuvent contenir un mot ou une suite de mots.</span><span class="sxs-lookup"><span data-stu-id="98629-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="98629-183">L'absence de spécification d'une substitution pour un modèle a pour effet de supprimer le modèle de la requête de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="98629-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="98629-184">Par exemple, supposons que vous souhaitez remplacer les requêtes pour le motif « Win8 » par les substitutions « Windows Server 2012 » ou « Windows 8.0 ».</span><span class="sxs-lookup"><span data-stu-id="98629-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="98629-185">Si vous exécutez une requête de texte intégral pour « Win8 », la recherche en texte intégral renvoie seulement les résultats contenant « Windows Server 2012 » ou « Windows 8.0 ».</span><span class="sxs-lookup"><span data-stu-id="98629-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="98629-186">Elle ne renvoie pas les résultats contenant « Win8 ».</span><span class="sxs-lookup"><span data-stu-id="98629-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="98629-187">Cela est dû au fait que le motif « Win8 » a été « remplacé » par les motifs « Windows Server 2012 » et « Windows 8.0 ».</span><span class="sxs-lookup"><span data-stu-id="98629-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="98629-188">Voici à quoi ressemble la section du jeu de remplacement pour l'exemple ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="98629-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="98629-189">Si deux jeux de remplacement contiennent des motifs similaires en correspondance, le plus long des deux a priorité.</span><span class="sxs-lookup"><span data-stu-id="98629-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="98629-190">Par exemple, si vous exécutez une requête FORMS OF THESAURUS pour « Internet Explorer online community » avec les jeux de remplacement suivants, le jeu de remplacement « Internet Explorer » est prioritaire par rapport au jeu de remplacement « Internet ».</span><span class="sxs-lookup"><span data-stu-id="98629-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="98629-191">La requête sera donc traitée comme « IE online community » ou « IE 9 online community ».</span><span class="sxs-lookup"><span data-stu-id="98629-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="98629-192">and</span><span class="sxs-lookup"><span data-stu-id="98629-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="98629-193">Utilisation des fichiers de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="98629-194">**Pour modifier un fichier de dictionnaire des synonymes**</span><span class="sxs-lookup"><span data-stu-id="98629-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="98629-195">Modification d'un fichier de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="98629-196">**Pour charger un fichier de dictionnaire des synonymes mis à jour**</span><span class="sxs-lookup"><span data-stu-id="98629-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="98629-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98629-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="98629-198">**Pour consulter le résultat de la segmentation du texte en unités lexicales d'une combinaison d'analyseur lexical, de dictionnaire des synonymes et de liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="98629-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="98629-199">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98629-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="98629-200">Modification d’un fichier de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="98629-201">Le dictionnaire des synonymes d'une langue donnée peut être configuré en modifiant son fichier XML.</span><span class="sxs-lookup"><span data-stu-id="98629-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="98629-202">Au cours de l’installation, les fichiers de dictionnaire des synonymes vides qui contiennent uniquement le \<xml> conteneur et un élément d’exemple en commentaire \<thesaurus> sont installés.</span><span class="sxs-lookup"><span data-stu-id="98629-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="98629-203">Pour que les requêtes de recherche en texte intégral qui recherchent des synonymes fonctionnent correctement, vous devez créer un \<thesaurus> élément réel qui définit un jeu de synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="98629-204">Vous pouvez définir deux formes de synonymes : les jeux d'expansion et les jeux de remplacement.</span><span class="sxs-lookup"><span data-stu-id="98629-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="98629-205">**Restrictions applicables aux fichiers de dictionnaires des synonymes**</span><span class="sxs-lookup"><span data-stu-id="98629-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="98629-206">Les restrictions suivantes s'appliquent à la modification d'un fichier de dictionnaire des synonymes :</span><span class="sxs-lookup"><span data-stu-id="98629-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="98629-207">Seuls des administrateurs système peuvent mettre à jour, modifier ou supprimer des fichiers de dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="98629-208">Lorsque vous modifiez des fichiers de dictionnaire des synonymes à l'aide des outils d'édition de texte, les fichiers doivent être enregistrés au format Unicode et des marques d'ordre d'octets doivent être spécifiées.</span><span class="sxs-lookup"><span data-stu-id="98629-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="98629-209">Les entrées du dictionnaire des synonymes ne doivent pas être vides et la césure des mots ne doit pas résulter en une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="98629-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="98629-210">Les expressions du fichier de dictionnaire des synonymes ne doivent pas dépasser 512 caractères.</span><span class="sxs-lookup"><span data-stu-id="98629-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="98629-211">Un dictionnaire des synonymes ne doit pas contenir d’entrées en double parmi les entrées \<sub> des jeux d’expansion et les éléments \<pat> des jeux de remplacement.</span><span class="sxs-lookup"><span data-stu-id="98629-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="98629-212">**Recommandations pour les fichiers des dictionnaires des synonymes**</span><span class="sxs-lookup"><span data-stu-id="98629-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="98629-213">Nous vous recommandons de ne pas utiliser de caractères spéciaux dans les entrées d'un fichier de dictionnaire des synonymes.</span><span class="sxs-lookup"><span data-stu-id="98629-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="98629-214">En effet, le comportement des analyseurs lexicaux en ce qui concerne les caractères spéciaux est particulier.</span><span class="sxs-lookup"><span data-stu-id="98629-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="98629-215">Si une entrée de dictionnaire des synonymes contient des caractères spéciaux, les analyseurs lexicaux utilisés en association avec cette entrée peuvent avoir des conséquences comportementales subtiles pour une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98629-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="98629-216">Nous vous recommandons de ne pas utiliser de mots vides dans les entrées \<sub>, car les mots vides sont omis de l’index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98629-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="98629-217">Les requêtes sont élargies de façon à inclure les entrées \<sub> d’un fichier de dictionnaire des synonymes et, si une entrée \<sub> contient des mots vides, la taille de la requête augmente inutilement.</span><span class="sxs-lookup"><span data-stu-id="98629-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="98629-218">Pour modifier un fichier de dictionnaire des synonymes</span><span class="sxs-lookup"><span data-stu-id="98629-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="98629-219">Ouvrez le fichier de dictionnaire des synonymes dans le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="98629-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="98629-220">Si vous modifiez le fichier de dictionnaire des synonymes pour la première fois, supprimez les lignes de commentaires suivantes au début et à la fin du fichier :</span><span class="sxs-lookup"><span data-stu-id="98629-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="98629-221">Ajoutez, modifiez ou supprimez un jeu de remplacement ou un jeu d'expansion.</span><span class="sxs-lookup"><span data-stu-id="98629-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="98629-222">Enregistrez le fichier et fermez le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="98629-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="98629-223">Utilisez [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) pour charger le contenu du fichier du dictionnaire des synonymes dans tempdb, en spécifiant l’identificateur de paramètres régionaux (LCID) qui correspond à la langue du fichier.</span><span class="sxs-lookup"><span data-stu-id="98629-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="98629-224">Par exemple, pour le fichier du dictionnaire des synonymes anglais, tsenu.xml, le LCID correspondant est 1033.</span><span class="sxs-lookup"><span data-stu-id="98629-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="98629-225">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98629-225">See Also</span></span>  
 <span data-ttu-id="98629-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98629-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="98629-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98629-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="98629-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98629-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="98629-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98629-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="98629-230">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="98629-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
