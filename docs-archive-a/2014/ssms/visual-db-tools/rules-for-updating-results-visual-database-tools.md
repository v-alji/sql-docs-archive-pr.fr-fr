---
title: Règles relatives à la mise à jour des résultats (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703700"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="6d6d2-102">Règles relatives à la mise à jour des résultats (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6d6d2-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="6d6d2-103">Dans de nombreux cas, vous pouvez mettre à jour le jeu de résultats affiché dans le [volet Résultats](visual-database-tools.md),</span><span class="sxs-lookup"><span data-stu-id="6d6d2-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="6d6d2-104">avec quelques exceptions.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="6d6d2-105">En général, pour mettre à jour des résultats, le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) doit disposer de suffisamment d’informations pour identifier de façon unique la ligne de la table.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="6d6d2-106">C'est le cas par exemple si la requête inclut une clé primaire dans la liste de sortie.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="6d6d2-107">En outre, vous devez être autorisé à mettre à jour la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="6d6d2-108">Si votre requête est basée sur une vue, vous devriez pouvoir la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="6d6d2-109">Les mêmes règles s'appliquent, sauf qu'il s'agit des tables sous-jacentes de la vue et non simplement de la vue elle-même.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d6d2-110">Le Concepteur de requêtes et de vues ne peut pas déterminer à l'avance si vous pouvez mettre à jour un ensemble de résultats basé sur une vue.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="6d6d2-111">En conséquence, il affiche toutes les vues, même celles que vous ne pouvez pas mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="6d6d2-112">Le tableau suivant récapitule les cas spécifiques dans lesquels vous pourriez mettre à jour ou non des résultats de requête dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="6d6d2-113">Dans de nombreux cas, c'est la base de données que vous utilisez qui décide si vous pouvez mettre à jour des résultats de requête.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="6d6d2-114">Requête</span><span class="sxs-lookup"><span data-stu-id="6d6d2-114">Query</span></span>|<span data-ttu-id="6d6d2-115">Les résultats peuvent-ils être mis à jour ?</span><span class="sxs-lookup"><span data-stu-id="6d6d2-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="6d6d2-116">Requête basée sur une table dont la clé primaire figure dans la liste de sortie</span><span class="sxs-lookup"><span data-stu-id="6d6d2-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="6d6d2-117">Oui (sauf dans les cas répertoriés ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="6d6d2-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="6d6d2-118">Requête basée sur une table n'ayant ni index unique ni clé primaire</span><span class="sxs-lookup"><span data-stu-id="6d6d2-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="6d6d2-119">Dépend de la requête et de la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-119">Depends on query and database.</span></span> <span data-ttu-id="6d6d2-120">Certaines bases de données autorisent la mise à jour s'il y a suffisamment d'informations pour identifier des enregistrements de façon unique.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="6d6d2-121">Requête basée sur plusieurs tables non jointes</span><span class="sxs-lookup"><span data-stu-id="6d6d2-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="6d6d2-122">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-122">No.</span></span>|  
|<span data-ttu-id="6d6d2-123">Requête basée sur des données marquées en lecture seule dans la base de données</span><span class="sxs-lookup"><span data-stu-id="6d6d2-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="6d6d2-124">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-124">No.</span></span>|  
|<span data-ttu-id="6d6d2-125">Requête basée sur une vue qui implique une table sans contrainte</span><span class="sxs-lookup"><span data-stu-id="6d6d2-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="6d6d2-126">Oui (sauf dans les cas répertoriés ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="6d6d2-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="6d6d2-127">Requête basée sur des tables jointes avec une relation de type un-à-un</span><span class="sxs-lookup"><span data-stu-id="6d6d2-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="6d6d2-128">Oui (sauf dans les cas répertoriés ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="6d6d2-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="6d6d2-129">Requête basée sur des tables jointes avec une relation de type un-à-plusieurs</span><span class="sxs-lookup"><span data-stu-id="6d6d2-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="6d6d2-130">Généralement, oui.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-130">Usually.</span></span>|  
|<span data-ttu-id="6d6d2-131">Requête basée sur trois tables ou plus entre lesquelles existe une relation plusieurs-à-plusieurs</span><span class="sxs-lookup"><span data-stu-id="6d6d2-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="6d6d2-132">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-132">No.</span></span>|  
|<span data-ttu-id="6d6d2-133">Requête basée sur une table dans laquelle la mise à jour n'est pas autorisée</span><span class="sxs-lookup"><span data-stu-id="6d6d2-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="6d6d2-134">Suppression autorisée, mais mise à jour interdite.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="6d6d2-135">Requête basée sur une table dans laquelle la suppression n'est pas autorisée</span><span class="sxs-lookup"><span data-stu-id="6d6d2-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="6d6d2-136">Mise à jour autorisée, mais suppression interdite.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="6d6d2-137">Requête d'agrégation</span><span class="sxs-lookup"><span data-stu-id="6d6d2-137">Aggregate query</span></span>|<span data-ttu-id="6d6d2-138">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-138">No.</span></span>|  
|<span data-ttu-id="6d6d2-139">Requête basée sur une sous-requête contenant des totaux ou des fonctions d'agrégation</span><span class="sxs-lookup"><span data-stu-id="6d6d2-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="6d6d2-140">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-140">No.</span></span>|  
|<span data-ttu-id="6d6d2-141">Requête utilisant le mot clé DISTINCT pour exclure des lignes en double</span><span class="sxs-lookup"><span data-stu-id="6d6d2-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="6d6d2-142">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-142">No.</span></span>|  
|<span data-ttu-id="6d6d2-143">Requête dont la clause FROM inclut une fonction définie par l'utilisateur qui renvoie un tableau et qui contient plusieurs instructions de sélection</span><span class="sxs-lookup"><span data-stu-id="6d6d2-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="6d6d2-144">Non.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-144">No.</span></span>|  
|<span data-ttu-id="6d6d2-145">Requête dont la clause FROM inclut une fonction définie par l'utilisateur en ligne</span><span class="sxs-lookup"><span data-stu-id="6d6d2-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="6d6d2-146">Oui.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-146">Yes.</span></span>|  
  
 <span data-ttu-id="6d6d2-147">En outre, il est quelquefois impossible de mettre à jour certaines colonnes spécifiques des résultats.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="6d6d2-148">La liste suivante indique des types de colonnes spécifiques impossibles à mettre à jour dans le volet Résultats.</span><span class="sxs-lookup"><span data-stu-id="6d6d2-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="6d6d2-149">Colonnes basées sur des expressions</span><span class="sxs-lookup"><span data-stu-id="6d6d2-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="6d6d2-150">Colonnes basées sur des fonctions scalaires définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d6d2-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="6d6d2-151">Lignes ou colonnes supprimées par un autre utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d6d2-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="6d6d2-152">Lignes ou colonnes verrouillées par un autre utilisateur (en général, les lignes verrouillées peuvent être mises à jour dès qu'elles sont déverrouillées)</span><span class="sxs-lookup"><span data-stu-id="6d6d2-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="6d6d2-153">Colonnes de type Timestamp ou BLOB</span><span class="sxs-lookup"><span data-stu-id="6d6d2-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6d2-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d6d2-154">See Also</span></span>  
 [<span data-ttu-id="6d6d2-155">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6d6d2-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
