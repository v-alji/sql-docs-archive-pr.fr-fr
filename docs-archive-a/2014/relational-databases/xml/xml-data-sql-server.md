---
title: Données XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML [SQL Server]
- XML [SQL Server], about XML
ms.assetid: 6a1793c9-9856-485c-aac5-88fda62f61a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 48ddec1de8492c86aecfd80ea960c4a01673c24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601999"
---
# <a name="xml-data-sql-server"></a><span data-ttu-id="26653-102">Données XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="26653-102">XML Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="26653-103">constitue une puissante plateforme de développement d’applications d’une grande richesse pour la gestion des données semi-structurées.</span><span class="sxs-lookup"><span data-stu-id="26653-103">provides a powerful platform for developing rich applications for semi-structured data management.</span></span> <span data-ttu-id="26653-104">La prise en charge de XML est intégrée à tous les composants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et sous-entend :</span><span class="sxs-lookup"><span data-stu-id="26653-104">Support for XML is integrated into all the components in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="26653-105">Type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="26653-105">The `xml` data type.</span></span> <span data-ttu-id="26653-106">Les valeurs XML peuvent être stockées de façon native dans une colonne de type de données `xml` qui peut être typée en fonction d'une collection de schémas XML ou rester non typée.</span><span class="sxs-lookup"><span data-stu-id="26653-106">XML values can be stored natively in an `xml` data type column that can be typed according to a collection of XML schemas, or left untyped.</span></span> <span data-ttu-id="26653-107">Vous pouvez indexer la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="26653-107">You can index the XML column.</span></span>  
  
-   <span data-ttu-id="26653-108">Possibilité de spécifier une requête XQuery sur des données XML stockées dans des colonnes et des variables de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="26653-108">The ability to specify an XQuery query against XML data stored in columns and variables of the `xml` type.</span></span>  
  
-   <span data-ttu-id="26653-109">Optimisation de OPENROWSET pour permettre le chargement en masse de données XML</span><span class="sxs-lookup"><span data-stu-id="26653-109">Enhancements to OPENROWSET to allow bulk loading of XML data.</span></span>  
  
-   <span data-ttu-id="26653-110">La clause FOR XML, pour extraire les données relationnelles au format XML.</span><span class="sxs-lookup"><span data-stu-id="26653-110">The FOR XML clause, to retrieve relational data in XML format.</span></span>  
  
-   <span data-ttu-id="26653-111">La fonction OPENXML, pour extraire les données XML au format relationnel.</span><span class="sxs-lookup"><span data-stu-id="26653-111">The OPENXML function, to retrieve XML data in relational format.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26653-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="26653-112">In This Section</span></span>  
 [<span data-ttu-id="26653-113">Type et colonnes de données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-113">XML Data Type and Columns &#40;SQL Server&#41;</span></span>](xml-data-type-and-columns-sql-server.md)  
 [<span data-ttu-id="26653-114">Index XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-114">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
 [<span data-ttu-id="26653-115">Collections de schémas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-115">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
 [<span data-ttu-id="26653-116">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-116">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
 [<span data-ttu-id="26653-117">OPENXML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-117">OPENXML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openxml-transact-sql)  
  
## <a name="related-content"></a><span data-ttu-id="26653-118">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="26653-118">Related Content</span></span>  
 [<span data-ttu-id="26653-119">Exemples d’importation et d’exportation en bloc de documents XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-119">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
 [<span data-ttu-id="26653-120">Références relatives au langage Xquery &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26653-120">XQuery Language Reference &#40;SQL Server&#41;</span></span>](/sql/xquery/xquery-language-reference-sql-server)  
  
