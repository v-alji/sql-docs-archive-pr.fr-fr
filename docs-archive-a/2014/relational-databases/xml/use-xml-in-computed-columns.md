---
title: Utiliser des données XML dans les colonnes calculées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695447"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="a1625-102">Utiliser des données XML dans les colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="a1625-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="a1625-103">Une instance XML peut faire office de source ou de type de colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="a1625-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="a1625-104">Les exemples dans cette rubrique indiquent comment utiliser des données XML avec des colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="a1625-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="a1625-105">Création de colonnes calculées à partir de colonnes XML</span><span class="sxs-lookup"><span data-stu-id="a1625-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="a1625-106">Dans l'instruction `CREATE TABLE` suivante, une colonne de type `xml` (`col2`) est calculée à partir de `col1`:</span><span class="sxs-lookup"><span data-stu-id="a1625-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="a1625-107">Le type de données `xml` peut également faire office de source pour la création d'une colonne calculée, comme le montre l'instruction `CREATE TABLE` suivante :</span><span class="sxs-lookup"><span data-stu-id="a1625-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="a1625-108">Vous pouvez créer une colonne calculée en extrayant une valeur d'une colonne de type `xml` , comme le montre l'exemple ci-après.</span><span class="sxs-lookup"><span data-stu-id="a1625-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="a1625-109">Étant donné que les méthodes de type de données `xml` ne peuvent pas être directement utilisées pour créer des colonnes calculées, l'exemple définit d'abord une fonction (`my_udf`) qui renvoie une valeur d'une instance XML.</span><span class="sxs-lookup"><span data-stu-id="a1625-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="a1625-110">La fonction inclut la méthode `value()` du type `xml` .</span><span class="sxs-lookup"><span data-stu-id="a1625-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="a1625-111">Le nom de la fonction est ensuite spécifié dans l'instruction `CREATE TABLE` de la colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="a1625-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="a1625-112">Comme l'exemple précédent, l'exemple suivant définit une fonction afin de renvoyer une instance de type `xml` pour une colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="a1625-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="a1625-113">Dans la fonction, la méthode `query()` du type de données `xml` extrait une valeur d'un paramètre de type `xml` .</span><span class="sxs-lookup"><span data-stu-id="a1625-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="a1625-114">Dans l'instruction `CREATE TABLE` suivante, `Col2` est une colonne calculée qui utilise les données XML (élément`<Features>` ) renvoyées par la fonction :</span><span class="sxs-lookup"><span data-stu-id="a1625-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="a1625-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a1625-115">In This Section</span></span>  
  
|<span data-ttu-id="a1625-116">Rubrique</span><span class="sxs-lookup"><span data-stu-id="a1625-116">Topic</span></span>|<span data-ttu-id="a1625-117">Description</span><span class="sxs-lookup"><span data-stu-id="a1625-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a1625-118">Promouvoir les valeurs XML les plus fréquentes à l’aide de colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="a1625-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="a1625-119">Décrit comment utiliser la promotion de propriété avec des colonnes calculées et des tables de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a1625-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
