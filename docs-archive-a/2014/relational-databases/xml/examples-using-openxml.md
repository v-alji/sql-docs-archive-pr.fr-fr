---
title: 'Exemples : Utilisation d’OPENXML | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710472"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="aeba7-102">Exemples : Utilisation de OPENXML</span><span class="sxs-lookup"><span data-stu-id="aeba7-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="aeba7-103">Les exemples de cette rubrique montrent comment utiliser OPENXML pour créer une vue d'un ensemble de lignes d'un document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="aeba7-104">Pour plus d’informations sur la syntaxe d’OPENXML, consultez [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aeba7-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="aeba7-105">Les exemples montrent tous les aspects de OPENXML, sauf la spécification des métapropriétés.</span><span class="sxs-lookup"><span data-stu-id="aeba7-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="aeba7-106">Pour plus d’informations sur la spécification de métapropriétés dans OPENXML, consultez [Spécifier des métapropriétés dans OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="aeba7-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aeba7-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="aeba7-107">Examples</span></span>  
 <span data-ttu-id="aeba7-108">Lors de l’extraction de données, *rowpattern* sert à identifier les nœuds du document XML qui déterminent les lignes.</span><span class="sxs-lookup"><span data-stu-id="aeba7-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="aeba7-109">De plus, *rowpattern* est exprimé dans le langage du modèle XPath utilisé dans la mise en œuvre XPath de MSXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="aeba7-110">Par exemple, si le modèle s’achève au niveau d’un élément ou d’un attribut, une ligne est créée pour chaque nœud d’élément ou d’attribut sélectionné par *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="aeba7-111">La valeur *flags* fournit le mappage par défaut.</span><span class="sxs-lookup"><span data-stu-id="aeba7-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="aeba7-112">Si aucun *ColPattern* n’est spécifié dans *SchemaDeclaration*, le mappage défini par la valeur *flags* est appliqué.</span><span class="sxs-lookup"><span data-stu-id="aeba7-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="aeba7-113">La valeur *flags* est ignorée si *ColPattern* est spécifié dans *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="aeba7-114">Le paramètre *ColPattern* spécifié détermine le mappage (centré sur l’attribut ou sur l’élément), ainsi que la façon dont les données en excès ou non consommées sont traitées.</span><span class="sxs-lookup"><span data-stu-id="aeba7-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="aeba7-115">R.</span><span class="sxs-lookup"><span data-stu-id="aeba7-115">A.</span></span> <span data-ttu-id="aeba7-116">Exécution d'une instruction SELECT simple avec OPENXML</span><span class="sxs-lookup"><span data-stu-id="aeba7-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="aeba7-117">Dans cet exemple, le document XML est constitué des éléments <`Customer`>, <`Order`> et <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="aeba7-118">L’instruction OPENXML extrait des informations sur les clients dans un ensemble de lignes à deux colonnes ( **CustomerID** et **ContactName**) à partir du document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="aeba7-119">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-120">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-121">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-122">*rowpattern* (/ROOT/Customer) identifie les nœuds <`Customer`> à traiter.</span><span class="sxs-lookup"><span data-stu-id="aeba7-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="aeba7-123">Le paramètre *flags* prend la valeur **1** pour indiquer qu’il s’agit d’un mappage centré sur l’attribut.</span><span class="sxs-lookup"><span data-stu-id="aeba7-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="aeba7-124">Ainsi, les attributs XML sont mappés sur les colonnes de l’ensemble de lignes défini dans *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="aeba7-125">Dans *SchemaDeclaration*(dans la clause WITH), les valeurs *ColName* spécifiées correspondent aux noms d’attributs XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="aeba7-126">Par conséquent, le paramètre *ColPattern* n’est pas spécifié dans *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="aeba7-127">Ensuite, l'instruction SELECT extrait toutes les colonnes dans l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="aeba7-128">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="aeba7-129">Dans la mesure où les éléments <`Customer`> n’ont pas de sous-éléments, si la même instruction SELECT s’exécute avec une valeur *flags* de **2**, pour indiquer qu’il s’agit d’un mappage centré sur l’élément, les valeurs de **CustomerID** et de **ContactName** pour les deux clients sont renvoyées comme NULL.</span><span class="sxs-lookup"><span data-stu-id="aeba7-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="aeba7-130">@xmlDocument peut également être de type **xml** ou de type **(n)varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="aeba7-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="aeba7-131">Si, dans le document XML, les éléments <`CustomerID`> et <`ContactName`> sont des sous-éléments, le mappage centré sur l'élément extrait les valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="aeba7-132">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="aeba7-133">Remarquez que le descripteur de document renvoyé par **sp_xml_preparedocument** n’est valide que pendant la durée du traitement et non pendant l’ensemble de la session.</span><span class="sxs-lookup"><span data-stu-id="aeba7-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="aeba7-134">B.</span><span class="sxs-lookup"><span data-stu-id="aeba7-134">B.</span></span> <span data-ttu-id="aeba7-135">Spécification de ColPattern pour effectuer un mappage entre les colonnes d'un ensemble de lignes et les attributs/éléments XML</span><span class="sxs-lookup"><span data-stu-id="aeba7-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="aeba7-136">Cet exemple montre comment le modèle XPath est défini dans le paramètre facultatif *ColPattern* pour fournir un mappage entre les colonnes d’un ensemble de lignes et les attributs/éléments XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="aeba7-137">Dans cet exemple, le document XML est constitué des éléments <`Customer`>, <`Order`> et <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="aeba7-138">L’instruction OPENXML extrait des informations sur les clients et les commandes sous la forme d’un ensemble de lignes (**CustomerID**, **OrderDate**, **ProdID**et **Qty**) à partir du document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="aeba7-139">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-140">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-141">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifie les nœuds <`OrderDetail`> à traiter.</span><span class="sxs-lookup"><span data-stu-id="aeba7-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="aeba7-143">À titre d’illustration, le paramètre *flags* prend la valeur **2** pour indiquer qu’il s’agit d’un mappage centré sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="aeba7-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="aeba7-144">Toutefois, le mappage spécifié dans *ColPattern* remplace ce dernier.</span><span class="sxs-lookup"><span data-stu-id="aeba7-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="aeba7-145">Autrement dit, le modèle XPath spécifié dans *ColPattern* mappe les colonnes de l’ensemble de lignes sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="aeba7-146">Il en résulte un mappage centré sur l'attribut.</span><span class="sxs-lookup"><span data-stu-id="aeba7-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="aeba7-147">Dans *SchemaDeclaration*(dans la clause WITH), le paramètre *ColPattern* est également spécifié avec les paramètres *ColName* et *ColType* .</span><span class="sxs-lookup"><span data-stu-id="aeba7-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="aeba7-148">Le paramètre facultatif *ColPattern* correspond au modèle XPath spécifié et définit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-149">Les colonnes **OrderID**, **CustomerID** et **OrderDate** de l’ensemble de lignes sont mappées sur les attributs du parent des nœuds identifiés par *rowpattern* et *rowpattern* identifie les nœuds <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="aeba7-150">Par conséquent, les colonnes **CustomerID** et **OrderDate** sont mappées sur les attributs **CustomerID** et **OrderDate** de l’élément <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="aeba7-151">Les colonnes **ProdID** et **Qty** de l’ensemble de lignes sont mappées sur les attributs **ProductID** et **Quantity** des nœuds identifiés par *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="aeba7-152">Ensuite, l'instruction SELECT extrait toutes les colonnes dans l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="aeba7-153">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="aeba7-154">Le modèle XPath défini comme *ColPattern* peut également être spécifié pour mapper les éléments XML sur les colonnes de l’ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="aeba7-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="aeba7-155">(aboutissant ainsi à un mappage centré sur l'élément).</span><span class="sxs-lookup"><span data-stu-id="aeba7-155">This results in element-centric mapping.</span></span> <span data-ttu-id="aeba7-156">Dans l'exemple suivant, <`CustomerID`> et <`OrderDate`> du document XML sont des sous-éléments de l'élément <`Orders`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="aeba7-157">Dans la mesure où *ColPattern* se substitue au mappage spécifié dans le paramètre *flags* , il n’y a pas lieu de spécifier le paramètre *flags* dans OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="aeba7-158">C.</span><span class="sxs-lookup"><span data-stu-id="aeba7-158">C.</span></span> <span data-ttu-id="aeba7-159">Combinaison du mappage centré sur les attributs et du mappage centré sur les éléments</span><span class="sxs-lookup"><span data-stu-id="aeba7-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="aeba7-160">Dans cet exemple, le paramètre *flags* a la valeur **3** pour indiquer qu’il s’agit d’un mappage centré à la fois sur l’attribut et sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="aeba7-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="aeba7-161">Dans ce cas, le mappage centré sur l'attribut est appliqué en premier, puis le mappage centré sur l'élément est appliqué ensuite pour toutes les colonnes non encore traitées.</span><span class="sxs-lookup"><span data-stu-id="aeba7-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="aeba7-162">Voici le résultat :</span><span class="sxs-lookup"><span data-stu-id="aeba7-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="aeba7-163">Le mappage centré sur l’attribut est appliqué à **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="aeba7-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="aeba7-164">Il n’y a pas d’attribut **ContactName** dans l’élément <`Customer`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="aeba7-165">Par conséquent, le mappage centré sur l'élément est appliqué.</span><span class="sxs-lookup"><span data-stu-id="aeba7-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="aeba7-166">D.</span><span class="sxs-lookup"><span data-stu-id="aeba7-166">D.</span></span> <span data-ttu-id="aeba7-167">Spécification de la fonction XPath text() en tant que ColPattern</span><span class="sxs-lookup"><span data-stu-id="aeba7-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="aeba7-168">Dans cet exemple, le document XML est constitué des éléments <`Customer`> et <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="aeba7-169">L’instruction OPENXML extrait un ensemble de lignes constitué de l’attribut **oid** de l’élément <`Order`>, de l’ID du parent du nœud identifié par *rowpattern* et de la chaîne de valeur de feuille du contenu de l’élément.</span><span class="sxs-lookup"><span data-stu-id="aeba7-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="aeba7-170">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-171">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-172">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-173">*rowpattern* (/root/Customer/Order) identifie les nœuds <`Order`> à traiter.</span><span class="sxs-lookup"><span data-stu-id="aeba7-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="aeba7-174">Le paramètre *flags* prend la valeur **1** pour indiquer qu’il s’agit d’un mappage centré sur l’attribut.</span><span class="sxs-lookup"><span data-stu-id="aeba7-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="aeba7-175">Ainsi, les attributs XML sont mappés sur les colonnes de l’ensemble de lignes définies dans *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="aeba7-176">Dans *SchemaDeclaration* (dans la clause WITH), les noms de colonne de l’ensemble de lignes **oid** et **amount** correspondent aux noms des attributs XML équivalents.</span><span class="sxs-lookup"><span data-stu-id="aeba7-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="aeba7-177">Par conséquent, le paramètre *ColPattern* n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="aeba7-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="aeba7-178">Pour la colonne **comment** de l’ensemble de lignes, la fonction XPath **text()** est spécifiée en tant que *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="aeba7-179">Ceci remplace le mappage centré sur l’attribut défini dans le paramètre *flags*; la colonne contient la chaîne de valeur de feuille du contenu de l’élément.</span><span class="sxs-lookup"><span data-stu-id="aeba7-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="aeba7-180">Ensuite, l'instruction SELECT extrait toutes les colonnes dans l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="aeba7-181">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="aeba7-182">E.</span><span class="sxs-lookup"><span data-stu-id="aeba7-182">E.</span></span> <span data-ttu-id="aeba7-183">Spécification de TableName dans la clause WITH</span><span class="sxs-lookup"><span data-stu-id="aeba7-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="aeba7-184">Dans cet exemple, *TableName* est spécifié dans la clause WITH au lieu de *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="aeba7-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="aeba7-185">Cela est utile si vous disposez d’une table dont la structure vous convient et qu’aucun modèle de colonne (paramètre *ColPattern* ) n’est requis.</span><span class="sxs-lookup"><span data-stu-id="aeba7-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="aeba7-186">Dans cet exemple, le document XML est constitué des éléments <`Customer`> et <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="aeba7-187">L’instruction OPENXML extrait les informations sur les commandes dans un ensemble de lignes à trois colonnes (**oid**, **date**et **amount**) à partir du document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="aeba7-188">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-189">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-190">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-191">*rowpattern* (/root/Customer/Order) identifie les nœuds <`Order`> à traiter.</span><span class="sxs-lookup"><span data-stu-id="aeba7-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="aeba7-192">Il n’y a pas de paramètre *SchemaDeclaration* dans la clause WITH.</span><span class="sxs-lookup"><span data-stu-id="aeba7-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="aeba7-193">Un nom de table est spécifié à la place.</span><span class="sxs-lookup"><span data-stu-id="aeba7-193">Instead, a table name is specified.</span></span> <span data-ttu-id="aeba7-194">Par conséquent, le schéma de la table est utilisé en guise de schéma de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="aeba7-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="aeba7-195">Le paramètre *flags* prend la valeur **1** pour indiquer qu’il s’agit d’un mappage centré sur l’attribut.</span><span class="sxs-lookup"><span data-stu-id="aeba7-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="aeba7-196">Par conséquent, les attributs des éléments (identifiés par *rowpattern*) sont mappés sur les colonnes de l’ensemble de lignes portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="aeba7-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="aeba7-197">Ensuite, l'instruction SELECT extrait toutes les colonnes dans l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="aeba7-198">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="aeba7-199">F.</span><span class="sxs-lookup"><span data-stu-id="aeba7-199">F.</span></span> <span data-ttu-id="aeba7-200">Obtention du résultat dans un format de table edge</span><span class="sxs-lookup"><span data-stu-id="aeba7-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="aeba7-201">Dans cet exemple, la clause WITH n'est pas spécifiée dans l'instruction OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="aeba7-202">Par conséquent, l'ensemble de lignes généré par OPENXML possède un format de table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="aeba7-203">L'instruction SELECT renvoie toutes les colonnes dans la table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="aeba7-204">Dans cet exemple, le document XML est constitué des éléments <`Customer`>, <`Order`> et <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="aeba7-205">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-206">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-207">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-208">*rowpattern* (/ROOT/Customer) identifie les nœuds <`Customer`> à traiter.</span><span class="sxs-lookup"><span data-stu-id="aeba7-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="aeba7-209">La clause WITH n'est pas fournie.</span><span class="sxs-lookup"><span data-stu-id="aeba7-209">The WITH clause is not provided.</span></span> <span data-ttu-id="aeba7-210">Par conséquent, OPENXML renvoie l'ensemble de lignes dans un format de table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="aeba7-211">Ensuite, l'instruction SELECT extrait toutes les colonnes dans la table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="aeba7-212">Le résultat est renvoyé sous la forme de table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-212">The result is returned as an edge table.</span></span> <span data-ttu-id="aeba7-213">Vous pouvez écrire des requêtes sur la table edge afin d'obtenir des informations.</span><span class="sxs-lookup"><span data-stu-id="aeba7-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="aeba7-214">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="aeba7-214">For example:</span></span>  
  
-   <span data-ttu-id="aeba7-215">La requête suivante renvoie le nombre de nœuds **Customer** dans le document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="aeba7-216">Comme la clause WITH n'est pas spécifiée, OPENXML renvoie une table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="aeba7-217">L'instruction SELECT interroge la table edge.</span><span class="sxs-lookup"><span data-stu-id="aeba7-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="aeba7-218">La requête suivante renvoie les noms locaux des nœuds XML de type element.</span><span class="sxs-lookup"><span data-stu-id="aeba7-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="aeba7-219">G.</span><span class="sxs-lookup"><span data-stu-id="aeba7-219">G.</span></span> <span data-ttu-id="aeba7-220">Spécification du paramètre rowpattern, terminé par un attribut</span><span class="sxs-lookup"><span data-stu-id="aeba7-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="aeba7-221">Dans cet exemple, le document XML est constitué des éléments <`Customer`>, <`Order`> et <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="aeba7-222">L’instruction OPENXML extrait les informations sur le détail des commandes dans un ensemble de lignes à trois colonnes (**ProductID**, **Quantity**et **OrderID**) à partir du document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="aeba7-223">Tout d’abord, la procédure stockée **sp_xml_preparedocument** est appelée pour obtenir un descripteur de document.</span><span class="sxs-lookup"><span data-stu-id="aeba7-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="aeba7-224">Ce descripteur est transmis à OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="aeba7-225">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="aeba7-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) se termine par un attribut XML, **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="aeba7-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="aeba7-227">Dans l'ensemble de lignes obtenu, une ligne est créée pour chaque nœud d'attribut sélectionné dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="aeba7-228">Dans cet exemple, le paramètre *flags* n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="aeba7-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="aeba7-229">En revanche, les mappages sont définis par le paramètre *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="aeba7-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="aeba7-230">Dans *SchemaDeclaration* (dans la clause WITH), le paramètre *ColPattern* est également spécifié avec les paramètres *ColName* et *ColType* .</span><span class="sxs-lookup"><span data-stu-id="aeba7-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="aeba7-231">Le paramètre facultatif *ColPattern* correspond au modèle XPath spécifié pour définir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="aeba7-232">Le modèle XPath ( **.** ) spécifié pour le paramètre *ColPattern* de la colonne **ProdID** de l’ensemble de lignes identifie le nœud de contexte (nœud actuel).</span><span class="sxs-lookup"><span data-stu-id="aeba7-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="aeba7-233">Comme pour le paramètre *rowpattern* spécifié, il s’agit de l’attribut **ProductID** de l’élément <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="aeba7-234">Le paramètre *ColPattern* **../\@Quantity**, spécifié pour la colonne **Qty** de l’ensemble de lignes, identifie l’attribut **Quantity** du parent <`OrderDetail`>, nœud du nœud de contexte\<ProductID>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="aeba7-235">De même, le paramètre *ColPattern* **../../\@OrderID**, spécifié pour la colonne **OID** de l’ensemble de lignes, identifie l’attribut **OrderID** du parent <`Order`> du nœud parent du nœud de contexte.</span><span class="sxs-lookup"><span data-stu-id="aeba7-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="aeba7-236">Le nœud parent est <`OrderDetail`> et le nœud de contexte est <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="aeba7-237">Ensuite, l'instruction SELECT extrait toutes les colonnes dans l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="aeba7-238">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="aeba7-239">H.</span><span class="sxs-lookup"><span data-stu-id="aeba7-239">H.</span></span> <span data-ttu-id="aeba7-240">Spécification d'un document XML comprenant plusieurs nœuds de texte</span><span class="sxs-lookup"><span data-stu-id="aeba7-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="aeba7-241">Si vous disposez d’un document XML comprenant plusieurs nœuds de texte, une instruction SELECT avec un paramètre *ColPattern\*\*\*text()*\* renvoie uniquement le premier nœud de texte, et non la totalité.</span><span class="sxs-lookup"><span data-stu-id="aeba7-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="aeba7-242">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="aeba7-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="aeba7-243">L’instruction SELECT renvoie **T** comme résultat (et non **TaU**).</span><span class="sxs-lookup"><span data-stu-id="aeba7-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="aeba7-244">I.</span><span class="sxs-lookup"><span data-stu-id="aeba7-244">I.</span></span> <span data-ttu-id="aeba7-245">Spécification du type de données xml dans la clause WITH</span><span class="sxs-lookup"><span data-stu-id="aeba7-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="aeba7-246">Dans la clause WITH, un modèle de colonne mappé sur la colonne de type **xml** (typé ou non typé) doit renvoyer une séquence vide ou une séquence d’éléments, des instructions de traitement, des nœuds de texte et des commentaires.</span><span class="sxs-lookup"><span data-stu-id="aeba7-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="aeba7-247">Les données sont converties en type de données **xml** .</span><span class="sxs-lookup"><span data-stu-id="aeba7-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="aeba7-248">Dans l’exemple suivant, la déclaration de schéma de la table de la clause WITH inclut des colonnes de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="aeba7-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="aeba7-249">Il s’agit plus précisément de transmettre une variable de type **xml** (\@x) à la fonction **sp_xml_preparedocument()** .</span><span class="sxs-lookup"><span data-stu-id="aeba7-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="aeba7-250">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="aeba7-251">Notez les points suivants par rapport au résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="aeba7-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="aeba7-252">Pour la colonne **lname** de type **varchar(30)** , la valeur est récupérée à partir de l’élément <`lname`> correspondant.</span><span class="sxs-lookup"><span data-stu-id="aeba7-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="aeba7-253">Pour la colonne **xmlname** de type **xml** , le même élément name est renvoyé en tant que valeur.</span><span class="sxs-lookup"><span data-stu-id="aeba7-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="aeba7-254">L'indicateur prend la valeur 10,</span><span class="sxs-lookup"><span data-stu-id="aeba7-254">The flag is set to 10.</span></span> <span data-ttu-id="aeba7-255">soit 2 + 8, où 2 indique qu'il s'agit d'un mappage centré sur l'élément et 8 indique que seules les données XML non consommées doivent être ajoutées à la colonne OverFlow définie dans la clause WITH.</span><span class="sxs-lookup"><span data-stu-id="aeba7-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="aeba7-256">Si vous définissez l'indicateur à 2, l'ensemble du document XML est copié dans la colonne OverFlow spécifiée dans la clause WITH.</span><span class="sxs-lookup"><span data-stu-id="aeba7-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="aeba7-257">Si la colonne de la clause WITH est une colonne en XML typé et que l'instance XML ne respecte pas le schéma, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="aeba7-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="aeba7-258">J.</span><span class="sxs-lookup"><span data-stu-id="aeba7-258">J.</span></span> <span data-ttu-id="aeba7-259">Extraction de valeurs individuelles à partir d'attributs à plusieurs valeurs</span><span class="sxs-lookup"><span data-stu-id="aeba7-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="aeba7-260">Un document XML peut avoir des attributs qui ont plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="aeba7-261">Par exemple, l’attribut **IDREFS** peut avoir plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="aeba7-262">Dans un document XML, les valeurs des attributs à plusieurs valeurs sont spécifiées sous la forme d'une chaîne qui contient les valeurs séparées par un espace.</span><span class="sxs-lookup"><span data-stu-id="aeba7-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="aeba7-263">Dans le document XML suivant, les attributs **attends** de l’élément \<Student> et **attendedBy** de l’élément \<Class> ont plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="aeba7-264">L'extraction de valeurs individuelles d'un attribut XML à plusieurs valeurs et le stockage de chacune d'entre elles dans une ligne distincte de la base de données demandent un travail supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="aeba7-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="aeba7-265">Cet exemple illustre le processus.</span><span class="sxs-lookup"><span data-stu-id="aeba7-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="aeba7-266">Cet exemple de document XML est constitué des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="aeba7-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="aeba7-267">Attributs **id** (ID étudiant), **name**et **attends** .</span><span class="sxs-lookup"><span data-stu-id="aeba7-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="aeba7-268">L’attribut **attends** est un attribut à plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="aeba7-269">Attributs **id** (ID cours), **name**et **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="aeba7-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="aeba7-270">L’attribut **attendedBy** est un attribut à plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="aeba7-271">L’attribut **attends** de \<Student> et l’attribut **attendedBy** de \<Class> représentent une relation **m:n** entre les tables Student et Class.</span><span class="sxs-lookup"><span data-stu-id="aeba7-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="aeba7-272">Un étudiant peut faire partie de plusieurs cours et un cours peut avoir plusieurs étudiants.</span><span class="sxs-lookup"><span data-stu-id="aeba7-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="aeba7-273">Supposons que vous vouliez fragmenter ce document et l'enregistrer dans la base de données comme suit :</span><span class="sxs-lookup"><span data-stu-id="aeba7-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="aeba7-274">Enregistrez les données \<Student> dans la table Students.</span><span class="sxs-lookup"><span data-stu-id="aeba7-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="aeba7-275">Enregistrez les données \<Class> dans la table Courses.</span><span class="sxs-lookup"><span data-stu-id="aeba7-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="aeba7-276">Enregistrez les données de la relation **m:n** (entre Student et Class) dans la table CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="aeba7-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="aeba7-277">L'extraction des valeurs demande davantage de travail.</span><span class="sxs-lookup"><span data-stu-id="aeba7-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="aeba7-278">Pour extraire ces informations et les stocker dans la table, utilisez ces procédures stockées :</span><span class="sxs-lookup"><span data-stu-id="aeba7-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="aeba7-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="aeba7-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="aeba7-280">Insère les valeurs de l'identificateur du cours et de l'identificateur de l'étudiant dans la table CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="aeba7-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="aeba7-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="aeba7-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="aeba7-282">Extrait les ID individuels des étudiants de chaque élément \<Course>.</span><span class="sxs-lookup"><span data-stu-id="aeba7-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="aeba7-283">Une table edge est utilisée pour extraire ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="aeba7-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="aeba7-284">Voici la procédure à suivre :</span><span class="sxs-lookup"><span data-stu-id="aeba7-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="aeba7-285">K.</span><span class="sxs-lookup"><span data-stu-id="aeba7-285">K.</span></span> <span data-ttu-id="aeba7-286">Extraction de données binaires à partir de données codées en mode Base64 dans XML</span><span class="sxs-lookup"><span data-stu-id="aeba7-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="aeba7-287">Des données binaires sont souvent incluses dans XML à l'aide de l'encodage base64.</span><span class="sxs-lookup"><span data-stu-id="aeba7-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="aeba7-288">Lorsque vous fragmentez ce code XML à l'aide d'une instruction OPENXML, vous recevez les données encodées en base64.</span><span class="sxs-lookup"><span data-stu-id="aeba7-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="aeba7-289">Cet exemple montre comment reconvertir en binaire les données encodées en base64.</span><span class="sxs-lookup"><span data-stu-id="aeba7-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="aeba7-290">Créez une table avec un exemple de données binaires.</span><span class="sxs-lookup"><span data-stu-id="aeba7-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="aeba7-291">Utilisez une requête FOR XML et l'option BINARY BASE64 pour construire du code XML où les données binaires sont encodées en base64.</span><span class="sxs-lookup"><span data-stu-id="aeba7-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="aeba7-292">Fragmentez le code XML à l'aide de OPENXML.</span><span class="sxs-lookup"><span data-stu-id="aeba7-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="aeba7-293">Les données renvoyées par OPENXML seront des données encodées en base64.</span><span class="sxs-lookup"><span data-stu-id="aeba7-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="aeba7-294">Ensuite, appelez la fonction .value pour reconvertir ces dernières en binaire.</span><span class="sxs-lookup"><span data-stu-id="aeba7-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Voici l'ensemble de résultats. <span data-ttu-id="aeba7-296">Les données binaires renvoyées sont les données binaires d'origine de la table T.</span><span class="sxs-lookup"><span data-stu-id="aeba7-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="aeba7-297">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aeba7-297">See Also</span></span>  
 <span data-ttu-id="aeba7-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeba7-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="aeba7-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeba7-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="aeba7-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aeba7-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="aeba7-301">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aeba7-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
