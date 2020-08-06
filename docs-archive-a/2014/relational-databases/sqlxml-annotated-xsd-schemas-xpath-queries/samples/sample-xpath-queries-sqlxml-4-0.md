---
title: Exemples de requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600742"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="f1f75-102">Exemples de requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f1f75-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="f1f75-103">Cette section fournit des exemples de requêtes XPath pour SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="f1f75-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="f1f75-104">Pour des raisons d'illustration, ces exemples de requêtes XPath sont spécifiés dans un modèle exécuté à l'aide d'ADO.</span><span class="sxs-lookup"><span data-stu-id="f1f75-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="f1f75-105">Par conséquent, vous devez utiliser un fichier de schéma de mappage, SampleSchema1.xml, également fourni dans cette section.</span><span class="sxs-lookup"><span data-stu-id="f1f75-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="f1f75-106">Enregistrez ce fichier dans le répertoire où vos modèles sont stockés.</span><span class="sxs-lookup"><span data-stu-id="f1f75-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1f75-107">Les exemples de requêtes dans cette section sont groupés par type d'opération XPath effectuée par la requête.</span><span class="sxs-lookup"><span data-stu-id="f1f75-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1f75-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f1f75-108">In This Section</span></span>  
 [<span data-ttu-id="f1f75-109">Exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-110">Utilisez ce fichier avec les exemples de requêtes XPath fournis dans cette section.</span><span class="sxs-lookup"><span data-stu-id="f1f75-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="f1f75-111">Spécification d’axes dans les requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-112">Illustre la façon dont les axes sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-113">Spécification de prédicats de valeurs booléennes dans des requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-114">Illustre la façon dont les prédicats à valeurs booléennes sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-115">La spécification d’opérateurs relationnels dans des requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-116">Illustre la façon dont les opérateurs de relation sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-117">La spécification d’opérateurs arithmétiques dans des requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-118">Illustre la façon dont les opérateurs arithmétiques sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-119">Spécification de fonctions de conversion explicite dans les requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-120">Illustre la façon dont les fonctions de conversion explicite sont spécifiées dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-121">La spécification d’opérateurs booléens dans les requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-122">Illustre la façon dont les opérateurs booléens sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-123">Spécification de fonctions booléennes dans des requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-124">Illustre la façon dont les fonctions booléennes sont spécifiées dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="f1f75-125">Spécification de variables XPath dans les requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1f75-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="f1f75-126">Illustre comment les variables XPath sont spécifiées dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="f1f75-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
