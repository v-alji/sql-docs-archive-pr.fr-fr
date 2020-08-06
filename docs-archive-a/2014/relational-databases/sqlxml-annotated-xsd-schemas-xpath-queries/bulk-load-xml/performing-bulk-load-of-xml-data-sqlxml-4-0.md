---
title: Exécution du chargement en masse de données XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695503"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="3b0e9-102">Exécution du chargement en masse de données XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3b0e9-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="3b0e9-103">Le chargement en masse XML est un objet COM autonome qui vous permet de charger des données XML semi-structurées dans des tables Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b0e9-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b0e9-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3b0e9-104">In This Section</span></span>  
 [<span data-ttu-id="3b0e9-105">Présentation du chargement en masse XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-106">Fournit des informations générales sur le chargement en masse de données XML avec l'utilitaire de chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="3b0e9-107">Les rubriques traitent de la diffusion en continu des données XML et des opérations de chargement en masse transactionnelles et non transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="3b0e9-108">Processus de génération d’enregistrements &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-109">Décrit le processus et les règles régissant la génération des enregistrements pour le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="3b0e9-110">Interprétation des annotations &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-111">Décrit la façon dont le chargement en masse XML interprète les annotations dans les schémas XSD et XDR.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="3b0e9-112">SQL Server modèle objet de chargement en masse XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-113">Décrit l’objet SQLXMLBulkLoad et ses méthodes et propriétés.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="3b0e9-114">Exemples de chargement en masse XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-115">Fournit un exemple de code utilisant le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="3b0e9-116">Les types de données et le comportement de chargement en masse XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-117">Décrit le comportement du chargement en masse XML avec différents types dans XSD et XDR.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="3b0e9-118">Instructions et limitations du chargement en masse XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3b0e9-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="3b0e9-119">Répertorie certains problèmes à connaître lors de l'utilisation du chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="3b0e9-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
