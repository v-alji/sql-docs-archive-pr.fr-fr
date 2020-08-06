---
title: 'Leçon 1 : Conversion d’une table en structure hiérarchique | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708155"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="b90ae-102">Leçon 1 : Conversion d'une table en structure hiérarchique</span><span class="sxs-lookup"><span data-stu-id="b90ae-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="b90ae-103">Les clients qui ont des tables utilisant des jointures réflexives pour exprimer des relations hiérarchiques peuvent convertir leurs tables en structure hiérarchique en suivant les procédures fournies dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="b90ae-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="b90ae-104">Il est relativement facile d'effectuer une migration de cette représentation vers une autre à l'aide de `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="b90ae-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="b90ae-105">Après la migration, les utilisateurs disposeront d'une représentation hiérarchique compacte et facile à comprendre, qui peut être indexée de plusieurs façons pour que les requêtes soient efficaces.</span><span class="sxs-lookup"><span data-stu-id="b90ae-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="b90ae-106">Cette leçon examine une table existante, crée une table contenant une colonne `hierarchyid`, remplit la table avec les données de la table source, puis illustre trois stratégies d'indexation.</span><span class="sxs-lookup"><span data-stu-id="b90ae-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="b90ae-107">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b90ae-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="b90ae-108">Étude de la structure actuelle de la table Employee</span><span class="sxs-lookup"><span data-stu-id="b90ae-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="b90ae-109">Remplissage d'une table avec des données hiérarchiques existantes</span><span class="sxs-lookup"><span data-stu-id="b90ae-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="b90ae-110">Optimisation de la table NewOrg</span><span class="sxs-lookup"><span data-stu-id="b90ae-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="b90ae-111">Résumé : Conversion d’une table en une structure hiérarchique</span><span class="sxs-lookup"><span data-stu-id="b90ae-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="b90ae-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="b90ae-112">Prerequisites</span></span>  
 <span data-ttu-id="b90ae-113">Cette leçon requiert l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b90ae-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b90ae-114">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b90ae-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b90ae-115">Étude de la structure actuelle de la table Employee</span><span class="sxs-lookup"><span data-stu-id="b90ae-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="b90ae-116">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b90ae-116">Next Lesson</span></span>  
 [<span data-ttu-id="b90ae-117">Leçon 2 : Création et gestion de données dans une table hiérarchique</span><span class="sxs-lookup"><span data-stu-id="b90ae-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
