---
title: Utilisation des classes managées SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701676"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="bd860-102">Utilisation des classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="bd860-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="bd860-103">Cette section fournit des exemples d'applications qui montrent comment utiliser les classes managées [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML.</span><span class="sxs-lookup"><span data-stu-id="bd860-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="bd860-104">Pour plus d’informations sur l’accès et la modification des données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, et sur l’utilisation de DiffGrams pour mettre à jour des données dans des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, consultez [accès à la fonctionnalité SQLXML dans l’environnement .net](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bd860-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd860-105">Vous pouvez également écrire des applications [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio pour charger en masse des documents XML à l'aide du chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="bd860-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="bd860-106">Pour plus d’informations, consultez [exécution du chargement en masse de données XML &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="bd860-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="bd860-107">Vous devez ajouter une référence à la DLL de chargement en masse XML (Xblkld4.dll) dans votre application.</span><span class="sxs-lookup"><span data-stu-id="bd860-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="bd860-108">Il s'agit d'une DLL COM pour laquelle Visual Studio .NET crée automatiquement la bibliothèque de wrappers.</span><span class="sxs-lookup"><span data-stu-id="bd860-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd860-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bd860-109">In This Section</span></span>  
 [<span data-ttu-id="bd860-110">Exécution de requêtes SQL &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="bd860-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="bd860-111">Exécution de requêtes SQL à l'aide de la méthode ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="bd860-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="bd860-112">Traitement du XML côté client &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="bd860-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="bd860-113">L’exécution de requêtes XPath &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="bd860-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="bd860-114">Exécution de requêtes XPath avec des espaces de noms &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="bd860-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="bd860-115">Exécution de fichiers modèles à l'aide de la propriété CommandText</span><span class="sxs-lookup"><span data-stu-id="bd860-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="bd860-116">Exécution de fichiers modèles à l'aide de la propriété CommandStream</span><span class="sxs-lookup"><span data-stu-id="bd860-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="bd860-117">L’application d’une transformation XSL &#40;les classes managées SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="bd860-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
