---
title: Supprimer des index XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600682"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="ef7af-102">Supprimer des index XML</span><span class="sxs-lookup"><span data-stu-id="ef7af-102">Drop XML Indexes</span></span>
  <span data-ttu-id="ef7af-103">L’instruction [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] permet de supprimer des index XML et non XML, qu’ils soient primaires ou secondaires.</span><span class="sxs-lookup"><span data-stu-id="ef7af-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="ef7af-104">Les options DROP INDEX ne s'appliquent cependant pas aux index XML.</span><span class="sxs-lookup"><span data-stu-id="ef7af-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="ef7af-105">Si vous supprimez l'index XML primaire, tous les index secondaires présents sont alors également supprimés.</span><span class="sxs-lookup"><span data-stu-id="ef7af-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="ef7af-106">La syntaxe DROP avec *TableName.IndexName* est cependant en cours de retrait des fonctionnalités et n’est pas prise en charge pour les index XML.</span><span class="sxs-lookup"><span data-stu-id="ef7af-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="ef7af-107">Exemple : Création puis suppression d’un index XML primaire</span><span class="sxs-lookup"><span data-stu-id="ef7af-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="ef7af-108">L'exemple suivant propose la création d'un index XML portant sur une colonne de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="ef7af-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="ef7af-109">Lorsqu'une table est supprimée, tous les index XML qui lui sont associés sont également automatiquement supprimés.</span><span class="sxs-lookup"><span data-stu-id="ef7af-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="ef7af-110">Ceci dit, une colonne XML ne peut pas être supprimée d'une table si un index XML existe sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="ef7af-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="ef7af-111">L'exemple suivant propose la création d'un index XML portant sur une colonne de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="ef7af-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="ef7af-112">Pour plus d’informations, consultez [Comparer du XML typé et du XML non typé](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ef7af-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="ef7af-113">Vous pouvez à présent créer un index XML primaire relatif à `Co12`.</span><span class="sxs-lookup"><span data-stu-id="ef7af-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="ef7af-114">Exemple : Création d’un index XML à l’aide de l’option d’index DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="ef7af-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="ef7af-115">Dans cet exemple, un index XML est créé sur une colonne nommée`XmlColx`.</span><span class="sxs-lookup"><span data-stu-id="ef7af-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="ef7af-116">Ensuite, un autre index XML portant le même nom est créé sur une autre colonne nommée`XmlColy`.</span><span class="sxs-lookup"><span data-stu-id="ef7af-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="ef7af-117">L'option `DROP_EXISTING` étant spécifiée, l'index XML existant sur (`XmlColx)` est supprimé et un nouvel index sur (`XmlColy`) est créé.</span><span class="sxs-lookup"><span data-stu-id="ef7af-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="ef7af-118">La requête renvoie le nom de la colonne sur laquelle l'index XML spécifié est créé.</span><span class="sxs-lookup"><span data-stu-id="ef7af-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7af-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef7af-119">See Also</span></span>  
 [<span data-ttu-id="ef7af-120">Index XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ef7af-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
