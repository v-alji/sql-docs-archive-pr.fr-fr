---
title: Nouvelle page de mots vides de texte intégral (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613622"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="4c1d6-102">Nouvelle liste de mots vides de texte intégral (page Général)</span><span class="sxs-lookup"><span data-stu-id="4c1d6-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="4c1d6-103">Utilisez cette boîte de dialogue pour créer une liste de mots vides de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="4c1d6-104">Une *liste de mots vides* est un ensemble de mots couramment utilisés, appelés *mots vides*, qui sont omis de l'indexation de texte intégral pour les tables qui utilisent cette liste.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="4c1d6-105">Pour plus d’informations, consultez [Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="4c1d6-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="4c1d6-106">**Pour utiliser SQL Server Management Studio afin de créer une liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="4c1d6-107">Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="4c1d6-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="4c1d6-108">Options</span><span class="sxs-lookup"><span data-stu-id="4c1d6-108">Options</span></span>  
 <span data-ttu-id="4c1d6-109">**Nom de la liste de mots vides de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="4c1d6-110">Entrez le nom de la liste de mots vides de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="4c1d6-111">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-111">**Owner**</span></span>  
 <span data-ttu-id="4c1d6-112">Spécifiez le propriétaire de la liste de mots vides de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="4c1d6-113">Si vous souhaitez que la propriété vous soit assignée à vous, à savoir, l'utilisateur actuel, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="4c1d6-114">Cliquez sur le bouton Parcourir pour spécifier un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="4c1d6-115">Options de création de liste de mots vides</span><span class="sxs-lookup"><span data-stu-id="4c1d6-115">Create stoplist options</span></span>  
 <span data-ttu-id="4c1d6-116">Cliquez sur l'une des options de création suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c1d6-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="4c1d6-117">**Créer une liste de mots vides vide**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="4c1d6-118">La nouvelle liste de mots vides ne contiendra pas de mots vides.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="4c1d6-119">**Créer à partir de la liste de mots vides système**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="4c1d6-120">La nouvelle liste de mots vides est créée à partir de la liste de mots vides qui existe par défaut dans la [base de données Resource](../relational-databases/databases/resource-database.md).</span><span class="sxs-lookup"><span data-stu-id="4c1d6-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="4c1d6-121">**Créer à partir d'une liste de mots vides de texte intégral existante**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="4c1d6-122">La nouvelle liste de mots vides est créée en copiant une liste de mots vides existante.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="4c1d6-123">**Base de données source**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-123">**Source database**</span></span>  
 <span data-ttu-id="4c1d6-124">Spécifie le nom de la base de données à laquelle appartient la liste de mots vides existante.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="4c1d6-125">La base de données actuelle est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-125">The current database is selected by default.</span></span> <span data-ttu-id="4c1d6-126">Vous pouvez si vous le souhaitez sélectionner une autre base de données dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="4c1d6-127">**Liste de mots vides source**</span><span class="sxs-lookup"><span data-stu-id="4c1d6-127">**Source stoplist**</span></span>  
 <span data-ttu-id="4c1d6-128">Spécifie le nom d'une liste de mots vides existante.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="4c1d6-129">Dans la liste des listes de mots vides disponibles, sélectionnez celle qui doit être utilisée comme source.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="4c1d6-130">Les listes de mots vides disponibles sont répertoriées dans l'ordre dans lequel elles apparaissent dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="4c1d6-131">Si des langues spécifiées dans les mots vides de la liste de mots vides source ne sont pas inscrits dans la base de données actuelle, l'exécution de CREATE FULLTEXT STOPLIST réussit, mais des avertissements sont retournés et les mots vides correspondants ne sont pas ajoutés.</span><span class="sxs-lookup"><span data-stu-id="4c1d6-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1d6-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c1d6-132">See Also</span></span>  
 <span data-ttu-id="4c1d6-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c1d6-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="4c1d6-134">[CRÉER une STOPLIST de texte intégral &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c1d6-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="4c1d6-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c1d6-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="4c1d6-136">[Configurer et gérer mots vides et mots vides pour la recherche en texte intégral](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="4c1d6-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="4c1d6-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c1d6-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
