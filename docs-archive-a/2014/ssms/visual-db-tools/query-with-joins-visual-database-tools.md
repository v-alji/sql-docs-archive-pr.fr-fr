---
title: Interroger avec des jointures (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [Visual Database Tools]
- View Designer, joins
- table joins [SQL Server]
- multiple table joins
- Visual Database Tools [SQL Server], queries
- Query Designer [SQL Server], joins
- joins [SQL Server], queries
ms.assetid: 8f068207-d777-4e64-8c4c-d821f0ddb450
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9d0053e6786d96508be8a87347cdc0b19975a3fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697352"
---
# <a name="query-with-joins-visual-database-tools"></a><span data-ttu-id="95bf3-102">Interroger avec des jointures (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="95bf3-102">Query with Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="95bf3-103">Le résultat d'une requête peut inclure des données issues de plusieurs tables ou objets table.</span><span class="sxs-lookup"><span data-stu-id="95bf3-103">A query result can include data from multiple tables or table-valued objects.</span></span> <span data-ttu-id="95bf3-104">Pour combiner des données issues de plusieurs tables ou objets table, utilisez l'opération JOIN de SQL.</span><span class="sxs-lookup"><span data-stu-id="95bf3-104">To combine data from multiple table-valued objects, you use the JOIN operation from SQL.</span></span>  
  
 <span data-ttu-id="95bf3-105">Pour plus d'informations sur la création de requêtes associant plusieurs tables, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="95bf3-105">For information about creating queries using multiple tables, see the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95bf3-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="95bf3-106">In This Section</span></span>  
 [<span data-ttu-id="95bf3-107">Modifier des opérateurs de jointure &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-107">Modify Join Operators &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
 <span data-ttu-id="95bf3-108">Spécifier que les tables doivent être jointes à l'aide d'un opérateur autre qu'égal (=).</span><span class="sxs-lookup"><span data-stu-id="95bf3-108">Specify that tables should be joined using an operator other than equal (=).</span></span>  
  
 [<span data-ttu-id="95bf3-109">Représentation des jointures dans le Concepteur de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-109">How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;</span></span>](how-the-query-and-view-designer-represents-joins-visual-database-tools.md)  
 <span data-ttu-id="95bf3-110">Explique la représentation graphique de la jointure telle qu'elle s'affiche dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="95bf3-110">Explains the graphic representation of the join as you see it in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="95bf3-111">Joindre automatiquement des tables &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-111">Join Tables Automatically &#40;Visual Database Tools&#41;</span></span>](join-tables-automatically-visual-database-tools.md)  
 <span data-ttu-id="95bf3-112">Procédure permettant de laisser le Concepteur de requêtes et de vues décider si des tables doivent être jointes.</span><span class="sxs-lookup"><span data-stu-id="95bf3-112">Steps for allowing the Query and View Designer determine if tables should be joined.</span></span>  
  
 [<span data-ttu-id="95bf3-113">Joindre manuellement des tables &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-113">Join Tables Manually &#40;Visual Database Tools&#41;</span></span>](join-tables-manually-visual-database-tools.md)  
 <span data-ttu-id="95bf3-114">Procédure de création d'une jointure manuelle dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="95bf3-114">Steps for creating a join manually in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="95bf3-115">Joindre des tables sur plusieurs colonnes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-115">Join Tables on Multiple Columns &#40;Visual Database Tools&#41;</span></span>](join-tables-on-multiple-columns-visual-database-tools.md)  
 <span data-ttu-id="95bf3-116">Procédure de jointure de tables avec plusieurs critères pour chaque table.</span><span class="sxs-lookup"><span data-stu-id="95bf3-116">Steps for joining tables with multiple criteria for each table.</span></span>  
  
 [<span data-ttu-id="95bf3-117">Créer des jointures externes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-117">Create Outer Joins &#40;Visual Database Tools&#41;</span></span>](create-outer-joins-visual-database-tools.md)  
 <span data-ttu-id="95bf3-118">Spécifier que des tables jointes doivent inclure des lignes même en l'absence de lignes correspondantes entre les tables.</span><span class="sxs-lookup"><span data-stu-id="95bf3-118">Specify that joined tables should include rows even when they do not match rows in the corresponding table.</span></span>  
  
 [<span data-ttu-id="95bf3-119">Supprimer des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-119">Remove Joins &#40;Visual Database Tools&#41;</span></span>](remove-joins-visual-database-tools.md)  
 <span data-ttu-id="95bf3-120">Procédure de suppression d'une jointure entre des tables.</span><span class="sxs-lookup"><span data-stu-id="95bf3-120">Steps for removing a join between tables.</span></span>  
  
 [<span data-ttu-id="95bf3-121">Créer automatiquement des jointures réflexives &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-121">Create Self-Joins Automatically &#40;Visual Database Tools&#41;</span></span>](create-self-joins-automatically-visual-database-tools.md)  
 <span data-ttu-id="95bf3-122">Procédure permettant de laisser le Concepteur de requêtes et de vues créer une jointure réflexive.</span><span class="sxs-lookup"><span data-stu-id="95bf3-122">Steps for allowing the Query and View Designer to create a self-join.</span></span>  
  
 [<span data-ttu-id="95bf3-123">Créer manuellement des jointures réflexives &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-123">Create Self-Joins Manually &#40;Visual Database Tools&#41;</span></span>](create-self-joins-manually-visual-database-tools.md)  
 <span data-ttu-id="95bf3-124">Procédure d'utilisation d'une jointure pour trouver des sous-ensembles de données dans une même table.</span><span class="sxs-lookup"><span data-stu-id="95bf3-124">Steps for using a join to find subsets of data within a single table.</span></span>  
  
 [<span data-ttu-id="95bf3-125">Afficher les propriétés d’une jointure &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-125">View Join Properties &#40;Visual Database Tools&#41;</span></span>](view-join-properties-visual-database-tools.md)  
 <span data-ttu-id="95bf3-126">Procédure d'affichage des propriétés d'une jointure.</span><span class="sxs-lookup"><span data-stu-id="95bf3-126">Steps for viewing the properties of a join.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="95bf3-127">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="95bf3-127">Related Sections</span></span>  
 [<span data-ttu-id="95bf3-128">Types de requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-128">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
 <span data-ttu-id="95bf3-129">Fournit des liens vers des rubriques décrivant les types de requêtes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="95bf3-129">Provides links to topics describing the supported query types.</span></span>  
  
 [<span data-ttu-id="95bf3-130">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
 <span data-ttu-id="95bf3-131">Fournit des liens vers des rubriques qui décrivent les tâches de requêtes les plus courantes.</span><span class="sxs-lookup"><span data-stu-id="95bf3-131">Provides links to topics covering the most common query tasks.</span></span>  
  
 [<span data-ttu-id="95bf3-132">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="95bf3-132">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
 <span data-ttu-id="95bf3-133">Fournit des liens vers des rubriques décrivant les différents types de critères de recherche et leur mode d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="95bf3-133">Provides links to topics covering the various kinds of search criteria and how to use them.</span></span>  
  
  
