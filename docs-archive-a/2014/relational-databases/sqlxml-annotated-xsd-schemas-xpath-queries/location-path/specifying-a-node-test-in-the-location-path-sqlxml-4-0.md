---
title: Spécification d’un test de nœud dans le chemin d’accès d’emplacement (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610541"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="12485-102">Spécification d'un test de nœud dans le chemin d'accès d'emplacement (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="12485-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="12485-103">Un test de nœud spécifie le type de nœud sélectionné par le niveau d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="12485-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="12485-104">Chaque axe (`child`, `parent`, `attribute` ou `self`) possède un type de nœud principal.</span><span class="sxs-lookup"><span data-stu-id="12485-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="12485-105">Pour l' `attribute` axe, le type de nœud principal est **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="12485-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="12485-106">Pour les `parent` `child` axes, et `self` , le type de nœud principal est **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="12485-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12485-107">Le test de nœud générique \* (par exemple, `child::*`) n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="12485-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="12485-108">Test de nœud : exemple 1</span><span class="sxs-lookup"><span data-stu-id="12485-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="12485-109">Le chemin d’accès de l’emplacement `child::Customer` sélectionne **\<Customer>** les éléments enfants du nœud de contexte.</span><span class="sxs-lookup"><span data-stu-id="12485-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="12485-110">Dans cet exemple, `child` est l'axe et `Customer` est le test de nœud.</span><span class="sxs-lookup"><span data-stu-id="12485-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="12485-111">Le type de nœud principal de l' `child` axe est **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="12485-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="12485-112">Par conséquent, le test de nœud a la valeur TRUE si le **\<Customer>** nœud est un **\<element>** nœud.</span><span class="sxs-lookup"><span data-stu-id="12485-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="12485-113">Si le nœud de contexte n’a pas **\<Customer>** d’enfants, un ensemble de nœuds vide est retourné.</span><span class="sxs-lookup"><span data-stu-id="12485-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="12485-114">Test de nœud : exemple 2</span><span class="sxs-lookup"><span data-stu-id="12485-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="12485-115">Le chemin d’accès de l’emplacement `attribute::CustomerID` sélectionne l’attribut **CustomerID** du nœud de contexte.</span><span class="sxs-lookup"><span data-stu-id="12485-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="12485-116">Dans l’exemple, `attribute` est l’axe et `CustomerID` est le test de nœud.</span><span class="sxs-lookup"><span data-stu-id="12485-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="12485-117">Le type de nœud principal de l' `attribute` axe est **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="12485-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="12485-118">Par conséquent, le test de nœud a la valeur TRUE si **CustomerID** est un **\<attribute>** nœud.</span><span class="sxs-lookup"><span data-stu-id="12485-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="12485-119">Si le nœud de contexte n’a pas de **CustomerID**, un ensemble de nœuds vide est retourné.</span><span class="sxs-lookup"><span data-stu-id="12485-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12485-120">Dans cette implémentation de XPath, si une étape de localisation fait référence à un **\<element>** ou à un **\<attribute>** type qui n’est pas déclaré dans le schéma, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="12485-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="12485-121">Dans une implémentation de XPath dans MSXML, un ensemble de nœud vide est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="12485-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="12485-122">Syntaxe abrégée des axes</span><span class="sxs-lookup"><span data-stu-id="12485-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="12485-123">La syntaxe abrégée suivante est prise en charge pour le chemin d'accès d'emplacement :</span><span class="sxs-lookup"><span data-stu-id="12485-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="12485-124">`attribute::` peut être abrégé en `@`.</span><span class="sxs-lookup"><span data-stu-id="12485-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="12485-125">Le chemin d'accès d'emplacement `Customer[@CustomerID="ALFKI"]` est identique à `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="12485-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="12485-126">`child::` peut être omis dans un niveau d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="12485-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="12485-127">Par conséquent, `child` est l'axe par défaut.</span><span class="sxs-lookup"><span data-stu-id="12485-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="12485-128">Le chemin d'accès d'emplacement `Customer/Order` est identique à `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="12485-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="12485-129">`self::node()` peut être abrégé en un point et `parent::node()` peut être abrégé en deux points (..).</span><span class="sxs-lookup"><span data-stu-id="12485-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
