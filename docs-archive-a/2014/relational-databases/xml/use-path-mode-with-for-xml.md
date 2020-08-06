---
title: Utiliser le mode PATH avec FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610513"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="f287a-102">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="f287a-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="f287a-103">Comme décrit dans la rubrique [Construction de code XML à l’aide de FOR XML](for-xml-sql-server.md), le mode PATH permet de combiner des éléments et des attributs de façon simplifiée.</span><span class="sxs-lookup"><span data-stu-id="f287a-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="f287a-104">En outre, il facilite l'extension de l'imbrication pour la représentation des propriétés complexes.</span><span class="sxs-lookup"><span data-stu-id="f287a-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="f287a-105">Vous pouvez utiliser des requêtes en mode FOR XML EXPLICIT pour construire un document XML de ce type à partir d'un ensemble de lignes, mais le mode PATH offre une solution plus simple que les requêtes en mode EXPLICIT potentiellement lourdes.</span><span class="sxs-lookup"><span data-stu-id="f287a-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="f287a-106">Le mode PATH, allié à la possibilité d’écrire des requêtes FOR XML imbriquées et de faire appel à la directive TYPE pour renvoyer les instances de type **xml** , vous permet d’écrire des requêtes de moindre complexité.</span><span class="sxs-lookup"><span data-stu-id="f287a-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="f287a-107">En mode PATH, les noms ou alias de colonnes sont traités en tant qu'expressions XPath.</span><span class="sxs-lookup"><span data-stu-id="f287a-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="f287a-108">Ces expressions indiquent comment les valeurs sont mappées au document XML.</span><span class="sxs-lookup"><span data-stu-id="f287a-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="f287a-109">Chaque expression XPath est un chemin d'accès XPath relatif qui fournit le type d'élément, tel que les valeurs d'attribut, d'élément et scalaire, ainsi que le nom et la hiérarchie du nœud à générer par rapport à l'élément de ligne.</span><span class="sxs-lookup"><span data-stu-id="f287a-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="f287a-110">Cette section décrit le mappage des colonnes dans un ensemble de lignes sous différentes conditions et fournit des exemples.</span><span class="sxs-lookup"><span data-stu-id="f287a-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f287a-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f287a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f287a-112">Colonnes sans nom</span><span class="sxs-lookup"><span data-stu-id="f287a-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="f287a-113">Colonnes avec nom</span><span class="sxs-lookup"><span data-stu-id="f287a-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="f287a-114">Colonnes avec un nom spécifié sous la forme d'un caractère générique</span><span class="sxs-lookup"><span data-stu-id="f287a-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="f287a-115">Colonnes avec le nom d’un test de nœud XPath</span><span class="sxs-lookup"><span data-stu-id="f287a-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="f287a-116">Noms de colonnes avec le chemin d’accès spécifié sous la forme data&#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="f287a-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="f287a-117">Colonnes contenant une valeur NULL par défaut</span><span class="sxs-lookup"><span data-stu-id="f287a-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="f287a-118">Prise en charge d'espace de noms en mode PATH</span><span class="sxs-lookup"><span data-stu-id="f287a-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="f287a-119">Exemples : Utilisation du mode PATH</span><span class="sxs-lookup"><span data-stu-id="f287a-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="f287a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f287a-120">See Also</span></span>  
 <span data-ttu-id="f287a-121">[Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="f287a-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="f287a-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f287a-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="f287a-123">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f287a-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
