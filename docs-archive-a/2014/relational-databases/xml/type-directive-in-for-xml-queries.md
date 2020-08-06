---
title: Directive TYPE dans les requêtes FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614405"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="bb498-102">Directive TYPE dans les requêtes FOR XML</span><span class="sxs-lookup"><span data-stu-id="bb498-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bb498-103">la prise en charge du [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) vous permet éventuellement de demander que le résultat d’une requête for XML soit retourné en tant que `xml` type de données en spécifiant la directive type.</span><span class="sxs-lookup"><span data-stu-id="bb498-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="bb498-104">Cela vous permet de traiter le résultat d'une requête FOR XML sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="bb498-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="bb498-105">Par exemple, vous pouvez spécifier une requête XQuery par rapport à celle-ci, assigner le résultat à une `xml` variable de type ou écrire [des requêtes for XML imbriquées](use-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="bb498-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb498-106">renvoie des données d'instance de type de données XML au client comme résultat de différentes constructions de serveur telles que des requêtes FOR XML qui utilisent la directive TYPE ou dans lesquelles le type de données `xml` permet de renvoyer des valeurs de données d'instance XML à partir de paramètres de sortie et de colonnes de table SQL.</span><span class="sxs-lookup"><span data-stu-id="bb498-106">returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="bb498-107">Dans le code de l'application cliente, le fournisseur ADO.NET demande à ce que ces informations de type de données XML soient envoyées dans un encodage binaire à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="bb498-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="bb498-108">Toutefois, si vous utilisez FOR XML sans la directive TYPE, les données XML reviennent en tant que type chaîne.</span><span class="sxs-lookup"><span data-stu-id="bb498-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="bb498-109">Dans tous les cas, le fournisseur client est toujours en mesure de gérer toute forme XML.</span><span class="sxs-lookup"><span data-stu-id="bb498-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="bb498-110">Notez qu'une clause FOR XML de premier niveau sans directive TYPE ne peut pas être utilisée avec les curseurs.</span><span class="sxs-lookup"><span data-stu-id="bb498-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bb498-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="bb498-111">Examples</span></span>  
 <span data-ttu-id="bb498-112">Les exemples suivants illustrent l'utilisation de la directive TYPE avec des requêtes FOR XML.</span><span class="sxs-lookup"><span data-stu-id="bb498-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="bb498-113">Extraction des résultats de la requête FOR XML en tant que type xml</span><span class="sxs-lookup"><span data-stu-id="bb498-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="bb498-114">La requête suivante extrait des informations de contact client de la table `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="bb498-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="bb498-115">Étant donné que la directive `TYPE` est spécifiée sous la forme `FOR XML`, le résultat est renvoyé en tant que type `xml`.</span><span class="sxs-lookup"><span data-stu-id="bb498-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="bb498-116">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="bb498-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="bb498-117">Affectation des résultats de la requête FOR XML à une variable de type xml</span><span class="sxs-lookup"><span data-stu-id="bb498-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="bb498-118">Dans l'exemple suivant, un résultat FOR XML est affecté à une variable de type `xml`, `@x`.</span><span class="sxs-lookup"><span data-stu-id="bb498-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="bb498-119">La requête récupère les informations de contact, telles que `BusinessEntityID` , `FirstName` , `LastName` et des numéros de téléphone supplémentaires, à partir de la `AdditionalContactInfo` colonne de `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="bb498-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="bb498-120">Étant donné que la clause `FOR XML` spécifie la directive `TYPE`, le document XML est renvoyé en tant que type `xml` et affecté à une variable.</span><span class="sxs-lookup"><span data-stu-id="bb498-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="bb498-121">Interrogation des résultats d'une requête FOR XML</span><span class="sxs-lookup"><span data-stu-id="bb498-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="bb498-122">Les requêtes FOR XML renvoient des données XML.</span><span class="sxs-lookup"><span data-stu-id="bb498-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="bb498-123">Par conséquent, vous pouvez appliquer des méthodes de type `xml`, telles que `query()` et `value()`, au résultat XML renvoyé par des requêtes FOR XML.</span><span class="sxs-lookup"><span data-stu-id="bb498-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="bb498-124">Dans la requête suivante, la méthode `query()` du type de données `xml` permet d'interroger le résultat de la requête `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="bb498-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="bb498-125">Pour plus d’informations, consultez [Méthode query&#40;&#41; &#40;type de données xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="bb498-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="bb498-126">La requête `SELECT ... FOR XML` interne retourne un résultat de type `xml` auquel la clause `SELECT` externe applique la méthode `query()` au type `xml`.</span><span class="sxs-lookup"><span data-stu-id="bb498-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="bb498-127">Notez la directive `TYPE` spécifiée.</span><span class="sxs-lookup"><span data-stu-id="bb498-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="bb498-128">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="bb498-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="bb498-129">Dans la requête suivante, la méthode `value()` du type de données `xml` permet d'extraire une valeur du résultat XML renvoyé par la requête `SELECT...FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="bb498-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="bb498-130">Pour plus d’informations, consultez [Méthode value&#40;&#41; &#40;type de données xml&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="bb498-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="bb498-131">L'expression de chemin d'accès XQuery dans la méthode `value()` extrait le premier numéro de téléphone d'un contact client dont `BusinessEntityID` a pour valeur `1`.</span><span class="sxs-lookup"><span data-stu-id="bb498-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb498-132">Si la directive TYPE n'est pas spécifiée, le résultat de la requête FOR XML est renvoyé en tant que type `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="bb498-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="bb498-133">Utilisation des résultats de la requête FOR XML dans INSERT, UPDATE et DELETE (Transact-SQL DML)</span><span class="sxs-lookup"><span data-stu-id="bb498-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="bb498-134">L'exemple suivant montre comment des requêtes FOR XML peuvent être utilisées dans des instructions DML (Data Manipulation Language, langage de manipulation de données).</span><span class="sxs-lookup"><span data-stu-id="bb498-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="bb498-135">Dans l'exemple, la requête `FOR XML` renvoie une instance de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="bb498-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="bb498-136">L'instruction `INSERT` insère ce document XML dans une table.</span><span class="sxs-lookup"><span data-stu-id="bb498-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb498-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb498-137">See Also</span></span>  
 [<span data-ttu-id="bb498-138">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bb498-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
