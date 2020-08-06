---
title: Spécification d’un axe (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610539"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="8cace-102">Spécification d'un axe (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8cace-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="8cace-103">L'axe spécifie la relation d'arborescence entre les nœuds sélectionnés par l'étape d'emplacement et le nœud de contexte.</span><span class="sxs-lookup"><span data-stu-id="8cace-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="8cace-104">Les axes suivants sont admis :`child`</span><span class="sxs-lookup"><span data-stu-id="8cace-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="8cace-105">Contient l'enfant du nœud du contexte.</span><span class="sxs-lookup"><span data-stu-id="8cace-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="8cace-106">L’expression XPath suivante (chemin d’accès d’emplacement) sélectionne à partir du nœud de contexte actuel tous les **\<Customer>** enfants :</span><span class="sxs-lookup"><span data-stu-id="8cace-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="8cace-107">Dans la requête XPath suivante, `child` est l'axe.</span><span class="sxs-lookup"><span data-stu-id="8cace-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="8cace-108">`Customer` est le test de nœud.</span><span class="sxs-lookup"><span data-stu-id="8cace-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="8cace-109">Contient le parent du nœud du contexte.</span><span class="sxs-lookup"><span data-stu-id="8cace-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="8cace-110">L’expression XPath suivante sélectionne tous les **\<Customer>** parents des **\<Order>** enfants :</span><span class="sxs-lookup"><span data-stu-id="8cace-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="8cace-111">Cette option est équivalente à la spécification de `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="8cace-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="8cace-112">Dans cette requête XPath, `child` et `parent` sont les axes.</span><span class="sxs-lookup"><span data-stu-id="8cace-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="8cace-113">`Customer` et `Order` sont les tests de nœud.</span><span class="sxs-lookup"><span data-stu-id="8cace-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="8cace-114">Contient l'attribut du nœud du contexte.</span><span class="sxs-lookup"><span data-stu-id="8cace-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="8cace-115">L’expression XPath suivante sélectionne l’attribut **CustomerID** du nœud de contexte :</span><span class="sxs-lookup"><span data-stu-id="8cace-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="8cace-116">Contient le nœud du contexte lui-même.</span><span class="sxs-lookup"><span data-stu-id="8cace-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="8cace-117">L’expression XPath suivante sélectionne le nœud actuel s’il s’agit du **\<Order>** nœud :</span><span class="sxs-lookup"><span data-stu-id="8cace-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="8cace-118">Dans cette requête XPath, `self` est l'axe et `Order` le test de nœud.</span><span class="sxs-lookup"><span data-stu-id="8cace-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
