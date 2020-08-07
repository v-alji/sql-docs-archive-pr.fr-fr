---
title: MSSQLSERVER_8621 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611812"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="9156a-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="9156a-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="9156a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9156a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9156a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9156a-104">Product Name</span></span>|<span data-ttu-id="9156a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9156a-105">SQL Server</span></span>|  
|<span data-ttu-id="9156a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9156a-106">Event ID</span></span>|<span data-ttu-id="9156a-107">8621</span><span class="sxs-lookup"><span data-stu-id="9156a-107">8621</span></span>|  
|<span data-ttu-id="9156a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9156a-108">Event Source</span></span>|<span data-ttu-id="9156a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9156a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9156a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9156a-110">Component</span></span>|<span data-ttu-id="9156a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9156a-111">SQLEngine</span></span>|  
|<span data-ttu-id="9156a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9156a-112">Symbolic Name</span></span>|<span data-ttu-id="9156a-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="9156a-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="9156a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9156a-114">Message Text</span></span>|<span data-ttu-id="9156a-115">Espace de pile du processeur de requêtes insuffisant lors de l'optimisation de la requête.</span><span class="sxs-lookup"><span data-stu-id="9156a-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="9156a-116">Simplifiez la requête.</span><span class="sxs-lookup"><span data-stu-id="9156a-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9156a-117">Explication</span><span class="sxs-lookup"><span data-stu-id="9156a-117">Explanation</span></span>  
 <span data-ttu-id="9156a-118">La taille de la requête développée est la cause la plus probable de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="9156a-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="9156a-119">La requête développée substitue dans la requête d'origine les définitions de toutes les vues, colonnes calculées, fonctions [!INCLUDE[tsql](../../includes/tsql-md.md)] et expressions de table commune auxquelles elle fait référence, ainsi que les actions en cascade telles que la mise à jour des index secondaires, des vues et des déclencheurs.</span><span class="sxs-lookup"><span data-stu-id="9156a-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="9156a-120">La requête possède probablement une dimension importante ; par exemple, le nombre de tables référencées par les définitions de vues ou une expression scalaire très importante.</span><span class="sxs-lookup"><span data-stu-id="9156a-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9156a-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9156a-121">User Action</span></span>  
 <span data-ttu-id="9156a-122">Simplifiez la requête en la divisant en plusieurs requêtes le long de la dimension la plus importante.</span><span class="sxs-lookup"><span data-stu-id="9156a-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="9156a-123">Commencez par supprimer tous les éléments de la requête qui ne sont pas réellement nécessaires, puis essayez d'ajouter une table temporaire et de diviser la requête en deux.</span><span class="sxs-lookup"><span data-stu-id="9156a-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="9156a-124">Le simple déplacement d'une partie de la requête vers une sous-requête, une fonction ou une expression de table commune ne suffit pas, car ces éléments sont réassociés par le compilateur [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9156a-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
