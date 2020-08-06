---
title: Colonnes avec nom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696528"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="ce535-102">Colonnes avec nom</span><span class="sxs-lookup"><span data-stu-id="ce535-102">Columns with a Name</span></span>
  <span data-ttu-id="ce535-103">Les conditions suivantes sont celles dans lesquelles les colonnes de l'ensemble de lignes avec nom sont mappées, avec respect de la casse, au document XML obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="ce535-104">Le nom de colonne commence par un arobase (\@).</span><span class="sxs-lookup"><span data-stu-id="ce535-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="ce535-105">Le nom de colonne ne commence pas par un signe (\@).</span><span class="sxs-lookup"><span data-stu-id="ce535-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="ce535-106">Le nom de colonne ne commence pas par un arobase (\@) et contient une barre oblique (/).</span><span class="sxs-lookup"><span data-stu-id="ce535-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="ce535-107">Plusieurs colonnes partagent le même préfixe.</span><span class="sxs-lookup"><span data-stu-id="ce535-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="ce535-108">Une colonne porte un nom différent.</span><span class="sxs-lookup"><span data-stu-id="ce535-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="ce535-109">Le nom de colonne commence par un arobase (\@)</span><span class="sxs-lookup"><span data-stu-id="ce535-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="ce535-110">Si le nom de colonne commence par un arobase ( \@ ) et ne contient pas de barre oblique (/), un attribut de l' `row` élément <> avec la valeur de colonne correspondante est créé.</span><span class="sxs-lookup"><span data-stu-id="ce535-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="ce535-111">Par exemple, la requête suivante renvoie un ensemble de lignes à deux colonnes (\@PmId, Name).</span><span class="sxs-lookup"><span data-stu-id="ce535-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="ce535-112">Dans le document XML obtenu, un attribut **PmId** est ajouté à l’élément <`row`> correspondant et une valeur de ProductModelID lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="ce535-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="ce535-113">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="ce535-114">À un niveau donné, les attributs doivent précéder tous les autres types de nœuds, tels que les nœuds d'élément et les nœuds de texte.</span><span class="sxs-lookup"><span data-stu-id="ce535-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="ce535-115">La requête suivante renvoie une erreur :</span><span class="sxs-lookup"><span data-stu-id="ce535-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="ce535-116">Le nom de colonne ne commence pas par un arobase (\@)</span><span class="sxs-lookup"><span data-stu-id="ce535-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="ce535-117">Si le nom de colonne ne commence pas par un arobase ( \@ ), qu’il ne s’agit pas de l’un des tests de nœud XPath et qu’il ne contient pas de barre oblique (/), un élément XML qui est un sous-élément de l’élément Row, <`row`> par défaut, est créé.</span><span class="sxs-lookup"><span data-stu-id="ce535-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="ce535-118">La requête suivante spécifie le nom de colonne, qui est le résultat.</span><span class="sxs-lookup"><span data-stu-id="ce535-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="ce535-119">Par conséquent, un élément enfant <`result`> est ajouté à l'élément <`row`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="ce535-120">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="ce535-121">La requête suivante spécifie le nom de colonne ManuWorkCenterInformation pour le document XML retourné par la requête XQuery portant sur la colonne Instruction de type **xml**.</span><span class="sxs-lookup"><span data-stu-id="ce535-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="ce535-122">Par conséquent, un élément <`ManuWorkCenterInformation`> est ajouté en tant qu'enfant de l'élément <`row`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="ce535-123">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="ce535-124">Le nom de colonne ne commence pas par un arobase (\@) et contient une barre oblique (/)</span><span class="sxs-lookup"><span data-stu-id="ce535-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="ce535-125">Si le nom de colonne ne commence pas par un arobase (\@) mais contient une barre oblique (/), il indique une hiérarchie XML.</span><span class="sxs-lookup"><span data-stu-id="ce535-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="ce535-126">Par exemple, si le nom de colonne est « Name1/Name2/Name3.../Name***n*** », chaque partie Name***i*** représente un nom d’élément imbriqué dans l’élément de ligne actuel (avec i égal à 1) ou situé sous l’élément nommé Name***i-1***.</span><span class="sxs-lookup"><span data-stu-id="ce535-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="ce535-127">Si la partie Name***n*** commence par « \@ », elle est mappée à un attribut de l’élément Name***n-1***.</span><span class="sxs-lookup"><span data-stu-id="ce535-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="ce535-128">Par exemple, la requête suivante renvoie un ID et un nom d'employé représentés sous la forme d'un élément complexe EmpName qui contient un prénom (First), un deuxième prénom (Middle) et un nom de famille (Last).</span><span class="sxs-lookup"><span data-stu-id="ce535-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="ce535-129">Les noms de colonnes sont utilisés comme chemin d'accès dans la construction du document XML en mode PATH.</span><span class="sxs-lookup"><span data-stu-id="ce535-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="ce535-130">Le nom de colonne qui contient les valeurs d’ID d’employé commence par « \@ ». Par conséquent, un attribut, **EmpID**, est ajouté à l' `row` élément <>.</span><span class="sxs-lookup"><span data-stu-id="ce535-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="ce535-131">Le nom de toutes les autres colonnes contient une barre oblique (/) qui indique la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ce535-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="ce535-132">Le document XML obtenu possède l'enfant <`EmpName`> sous l'élément <`row`>, et l'enfant <`EmpName`> possède les éléments enfants <`First`>, <`Middle`> et <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="ce535-133">Le deuxième prénom de l'employé est NULL et, par défaut, la valeur NULL correspond à l'absence de l'élément ou de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="ce535-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="ce535-134">Si vous souhaitez que des éléments soient générés pour les valeurs NULL, vous pouvez spécifier la directive ELEMENTS avec XSINIL, comme le montre la requête ci-après.</span><span class="sxs-lookup"><span data-stu-id="ce535-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="ce535-135">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="ce535-136">Par défaut, le mode PATH génère des données XML centrées sur l'attribut.</span><span class="sxs-lookup"><span data-stu-id="ce535-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="ce535-137">Par conséquent, la spécification de la directive ELEMENTS dans une requête en mode PATH est sans effet.</span><span class="sxs-lookup"><span data-stu-id="ce535-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="ce535-138">Toutefois, comme le montre l'exemple précédent, la directive ELEMENTS, associée à XSINIL, permet de générer des éléments pour les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="ce535-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="ce535-139">Outre l'ID et le nom, la requête suivante extrait l'adresse d'un employé.</span><span class="sxs-lookup"><span data-stu-id="ce535-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="ce535-140">Conformément au chemin d'accès indiqué dans les noms des colonnes d'adresses, un élément enfant <`Address`> est ajouté à l'élément <`row`> et les détails de l'adresse sont ajoutés en tant qu'éléments enfants de l'élément <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="ce535-141">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="ce535-142">Plusieurs colonnes partagent le même préfixe de chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="ce535-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="ce535-143">Si plusieurs colonnes partagent le même préfixe de chemin d'accès, elles sont regroupées sous le même nom.</span><span class="sxs-lookup"><span data-stu-id="ce535-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="ce535-144">Si différents préfixes d'espace de noms sont utilisés alors qu'ils sont liés au même espace de noms, un chemin d'accès est considéré comme différent.</span><span class="sxs-lookup"><span data-stu-id="ce535-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="ce535-145">Dans la requête précédente, les colonnes FirstName, MiddleName et LastName partagent le même préfixe EmpName. Par conséquent, elles sont ajoutées en tant qu'enfants de l'élément <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="ce535-146">Cela était également le cas lors de la création de l'élément <`Address`> dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="ce535-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="ce535-147">Une colonne porte un nom différent</span><span class="sxs-lookup"><span data-stu-id="ce535-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="ce535-148">Si une colonne intermédiaire et portant un nom différent apparaît, elle rompt le regroupement, comme le montre la requête modifiée suivante.</span><span class="sxs-lookup"><span data-stu-id="ce535-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="ce535-149">La requête rompt le regroupement de FirstName, MiddleName et LastName, tel que spécifié dans la requête précédente, en ajoutant des colonnes d'adresse entre les colonnes FirstName et MiddleName.</span><span class="sxs-lookup"><span data-stu-id="ce535-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="ce535-150">Par conséquent, la requête crée deux éléments <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="ce535-151">Le premier élément <`EmpName`> possède l'élément enfant <`FirstName`> et le second élément <`EmpName`> possède les éléments enfants <`MiddleName`> et <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="ce535-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="ce535-152">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ce535-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce535-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce535-153">See Also</span></span>  
 [<span data-ttu-id="ce535-154">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="ce535-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
