---
title: MSSQLSERVER_8710 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615162"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="cf583-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="cf583-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="cf583-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cf583-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf583-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cf583-104">Product Name</span></span>|<span data-ttu-id="cf583-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cf583-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cf583-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cf583-106">Event ID</span></span>|<span data-ttu-id="cf583-107">8710</span><span class="sxs-lookup"><span data-stu-id="cf583-107">8710</span></span>|  
|<span data-ttu-id="cf583-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cf583-108">Event Source</span></span>|<span data-ttu-id="cf583-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cf583-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cf583-110">Composant</span><span class="sxs-lookup"><span data-stu-id="cf583-110">Component</span></span>|<span data-ttu-id="cf583-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cf583-111">SQLEngine</span></span>|  
|<span data-ttu-id="cf583-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cf583-112">Symbolic Name</span></span>|<span data-ttu-id="cf583-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="cf583-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="cf583-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cf583-114">Message Text</span></span>|<span data-ttu-id="cf583-115">Les fonctions d'agrégation utilisées avec les requêtes CUBE, ROLLUP ou GROUPING SET doivent permettre la fusion des sous-agrégats.</span><span class="sxs-lookup"><span data-stu-id="cf583-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="cf583-116">Pour résoudre ce problème, supprimez la fonction d'agrégation ou écrivez la requête en utilisant UNION ALL sur les clauses GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="cf583-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cf583-117">Explication</span><span class="sxs-lookup"><span data-stu-id="cf583-117">Explanation</span></span>  
 <span data-ttu-id="cf583-118">Une fonction d'agrégation a été utilisée avec des requêtes CUBE, ROLLUP ou GROUPING SET qui ne fournit pas de méthode pour fusionner les sous-agrégats.</span><span class="sxs-lookup"><span data-stu-id="cf583-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf583-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cf583-119">User Action</span></span>  
 <span data-ttu-id="cf583-120">Pour résoudre ce problème, supprimez la fonction d'agrégation ou écrivez la requête en utilisant UNION ALL sur les clauses GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="cf583-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
