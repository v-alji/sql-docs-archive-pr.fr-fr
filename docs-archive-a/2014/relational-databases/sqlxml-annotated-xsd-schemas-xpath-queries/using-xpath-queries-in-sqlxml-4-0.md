---
title: Utilisation de requêtes XPath dans SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611689"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="b329d-102">Utilisation des requêtes XPath dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="b329d-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="b329d-103">La prise en charge par Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des schémas XSD annotés vous permet de créer des vues XML des données relationnelles stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b329d-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="b329d-104">Vous pouvez utiliser un sous-ensemble du langage XPath pour interroger les vues XML créées par un schéma XSD annoté.</span><span class="sxs-lookup"><span data-stu-id="b329d-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b329d-105">Pour comprendre les requêtes XPath dans SQLXML 4.0, vous devez avoir une bonne connaissance des vues XML et des concepts connexes tels que les modèles et les schémas de mappage.</span><span class="sxs-lookup"><span data-stu-id="b329d-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="b329d-106">Pour plus d’informations, consultez [Introduction aux schémas XSD Annotés &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b329d-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="b329d-107">Pour plus d’informations sur XPath, consultez la norme XPath définie par le World Wide Web Consortium (W3C) à l’adresse http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="b329d-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b329d-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b329d-108">In This Section</span></span>  
 [<span data-ttu-id="b329d-109">Introduction à l’utilisation de requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b329d-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="b329d-110">Fournit des informations d'introduction sur les requêtes XPath dans SQLXML 4.0, y compris les fonctionnalités prises en charge et non prises en charge de la spécification XPath du W3C.</span><span class="sxs-lookup"><span data-stu-id="b329d-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="b329d-111">Spécification d’un chemin d’accès d’emplacement &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b329d-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="b329d-112">Décrit comment spécifier les chemins d'accès d'emplacement dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="b329d-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="b329d-113">Exemples de requêtes XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b329d-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="b329d-114">Fournit des exemples de requêtes XPath pour SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="b329d-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="b329d-115">Types de données XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b329d-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="b329d-116">Décrit les types de données Xpath, qui sont considérablement différents de ceux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et XSD.</span><span class="sxs-lookup"><span data-stu-id="b329d-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b329d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b329d-117">See Also</span></span>  
 [<span data-ttu-id="b329d-118">Mise en forme XML côté client &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b329d-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
