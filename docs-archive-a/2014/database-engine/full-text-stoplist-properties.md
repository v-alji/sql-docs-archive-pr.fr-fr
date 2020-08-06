---
title: Propriétés de la STOPLIST de texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614787"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="e7336-102">Propriétés de la liste de mots vides de texte intégral</span><span class="sxs-lookup"><span data-stu-id="e7336-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="e7336-103">Utilisez cette boîte de dialogue pour ajouter ou supprimer des mots vides, supprimer tous les mots vides pour une langue spécifique ou effacer la liste de mots vides actuelle.</span><span class="sxs-lookup"><span data-stu-id="e7336-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="e7336-104">Un mot vide est un mot utilisé couramment et inclus dans une liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e7336-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="e7336-105">Les mots vides répertoriés dans une liste de mots vides sont omis de l'indexation de texte intégral pour les tables qui utilisent la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e7336-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="e7336-106">Pour plus d’informations, consultez [Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="e7336-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="e7336-107">**Pour utiliser SQL Server Management Studio pour modifier des propriétés de liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e7336-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="e7336-108">Configurer et gérer les mots vides et listes de mots vides pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="e7336-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="e7336-109">Options</span><span class="sxs-lookup"><span data-stu-id="e7336-109">Options</span></span>  
 <span data-ttu-id="e7336-110">**Action**</span><span class="sxs-lookup"><span data-stu-id="e7336-110">**Action**</span></span>  
 <span data-ttu-id="e7336-111">Spécifie l'action que vous souhaitez effectuer.</span><span class="sxs-lookup"><span data-stu-id="e7336-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="e7336-112">**Ajouter un mot vide**</span><span class="sxs-lookup"><span data-stu-id="e7336-112">**Add stopword**</span></span>  
 <span data-ttu-id="e7336-113">Ajouter un mot utilisé couramment à la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e7336-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="e7336-114">**Supprimer le mot vide**</span><span class="sxs-lookup"><span data-stu-id="e7336-114">**Delete stopword**</span></span>  
 <span data-ttu-id="e7336-115">Supprimer un mot vide de la liste de mots vides.</span><span class="sxs-lookup"><span data-stu-id="e7336-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="e7336-116">**Supprimer tous les mots vides**</span><span class="sxs-lookup"><span data-stu-id="e7336-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="e7336-117">Supprimer tous les mots vides pour une langue spécifique.</span><span class="sxs-lookup"><span data-stu-id="e7336-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="e7336-118">**Effacer la liste de mots vides**</span><span class="sxs-lookup"><span data-stu-id="e7336-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="e7336-119">Effacer la liste de mots vides en supprimant tous les mots vides pour toutes les langues.</span><span class="sxs-lookup"><span data-stu-id="e7336-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="e7336-120">**Mot vide**</span><span class="sxs-lookup"><span data-stu-id="e7336-120">**Stopword**</span></span>  
 <span data-ttu-id="e7336-121">Si vous avez sélectionné **Ajouter un mot vide** ou **Supprimer le mot vide**, entrez le mot vide dans le champ **Mot vide** .</span><span class="sxs-lookup"><span data-stu-id="e7336-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="e7336-122">Tout nouveau mot vide doit être unique ; autrement dit, il ne doit pas déjà figurer dans la liste de mots vides correspondant à la langue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e7336-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="e7336-123">**Langue de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="e7336-123">**Full-text language**</span></span>  
 <span data-ttu-id="e7336-124">Si vous avez sélectionné **Ajouter un mot vide**, **Supprimer le mot vide**ou **Supprimer tous les mots vides**, sélectionnez la langue des mots vides dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="e7336-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="e7336-125">Celle-ci répertorie toutes les langues de texte intégral prises en charge par l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="e7336-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7336-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7336-126">See Also</span></span>  
 <span data-ttu-id="e7336-127">[sys. fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7336-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="e7336-128">[sys. fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7336-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="e7336-129">[Configurer et gérer mots vides et mots vides pour la recherche en texte intégral](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="e7336-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="e7336-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7336-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="e7336-131">[CRÉER une STOPLIST de texte intégral &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7336-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="e7336-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7336-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
