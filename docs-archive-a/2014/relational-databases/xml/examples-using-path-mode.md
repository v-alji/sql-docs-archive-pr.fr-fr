---
title: 'Exemples : Utilisation du mode PATH | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710463"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="cb8f7-102">Exemples : Utilisation du mode PATH</span><span class="sxs-lookup"><span data-stu-id="cb8f7-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="cb8f7-103">Les exemples suivants montrent comment utiliser le mode PATH pour générer un document XML à partir d'une requête SELECT.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="cb8f7-104">Nombre de ces requêtes sont spécifiées par rapport aux documents XML des instructions de fabrication de bicyclettes stockés dans la colonne Instructions de la table ProductModel.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="cb8f7-105">Spécification d'une requête simple en mode PATH</span><span class="sxs-lookup"><span data-stu-id="cb8f7-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="cb8f7-106">Cette requête spécifie un mode FOR XML PATH.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="cb8f7-107">Le résultat suivant est un document XML centré sur l'élément dans lequel chaque valeur de colonne de l'ensemble de lignes obtenu est incluse dans un élément.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="cb8f7-108">Étant donné que la clause `SELECT` ne spécifie aucun alias pour les noms de colonnes, les noms d'éléments enfants générés sont les mêmes que les noms de colonnes correspondants dans la clause `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="cb8f7-109">Pour chaque ligne de l'ensemble de lignes, une balise <`row`> est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="cb8f7-110">Le résultat suivant est le même que la requête en mode `RAW` avec l'option `ELEMENTS` spécifiée.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="cb8f7-111">Il renvoie un document XML centré sur l'élément avec un élément <`row`> par défaut pour chaque ligne du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="cb8f7-112">Vous pouvez éventuellement spécifier le nom d'élément de ligne pour remplacer l'élément <`row`> par défaut.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="cb8f7-113">Par exemple, la requête suivante renvoie l'élément <`ProductModel`> de chaque ligne de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="cb8f7-114">Le document XML obtenu possède un nom d'élément de ligne spécifié.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="cb8f7-115">Si vous spécifiez une chaîne nulle, l'élément d'habillage n'est pas généré.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="cb8f7-116">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="cb8f7-117">Spécification de noms de colonnes de type XPath</span><span class="sxs-lookup"><span data-stu-id="cb8f7-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="cb8f7-118">Dans la requête suivante, le nom de colonne `ProductModelID` spécifié commence par « \@ » et ne contient pas de barre oblique (« / »).</span><span class="sxs-lookup"><span data-stu-id="cb8f7-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="cb8f7-119">Par conséquent, un attribut de l'élément <`row`> ayant la valeur de colonne correspondante est créé dans le document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="cb8f7-120">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="cb8f7-121">Vous pouvez ajouter un élément de niveau supérieur unique en spécifiant l'option `root` dans `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="cb8f7-122">Pour générer une hiérarchie, vous pouvez inclure une syntaxe de type PATH.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="cb8f7-123">Par exemple, remplacez le nom de la colonne `Name` par « SomeChild/ModelName » afin d'obtenir un document XML avec hiérarchie, comme le montre le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="cb8f7-124">Outre l'ID et le nom du modèle de produit, la requête suivante extrait les emplacements des instructions de fabrication du modèle.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="cb8f7-125">Étant donné que la colonne Instructions est de type `xml`, la méthode `query()` de type de données `xml` est spécifiée pour extraire l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="cb8f7-126">Le résultat partiel est le suivant.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-126">This is the partial result.</span></span> <span data-ttu-id="cb8f7-127">Étant donné que la requête spécifie ManuInstr comme nom de colonne, le code XML retourné par la `query()` méthode est encapsulé dans une `ManuInstr` balise <> comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="cb8f7-128">Dans la requête FOR XML précédente, vous pouvez inclure des espaces de noms pour les éléments <`Root`> et <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="cb8f7-129">Pour ce faire, vous pouvez définir la liaison préfixe/espace de noms à l'aide de WITH XMLNAMESPACES puis utiliser des préfixes dans la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="cb8f7-130">Pour plus d’informations, consultez [Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="cb8f7-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="cb8f7-131">Notez que le préfixe `MI` est également défini dans `WITH XMLNAMESPACES`.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="cb8f7-132">Par conséquent, la méthode `query()` du type `xml` spécifié ne définit pas le préfixe dans le prologue de la requête.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="cb8f7-133">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="cb8f7-134">Génération d'une liste de valeurs à l'aide du mode PATH</span><span class="sxs-lookup"><span data-stu-id="cb8f7-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="cb8f7-135">Pour chaque modèle de produit, cette requête construit une liste de valeurs d'ID de produit.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="cb8f7-136">Pour chaque ID de produit, la requête construit également des éléments imbriqués <`ProductName`>, comme le montre le fragment XML suivant :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="cb8f7-137">La requête ci-après génère le document XML souhaité :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="cb8f7-138">Notez les points suivants dans la requête précédente :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="cb8f7-139">La première clause `SELECT` imbriquée renvoie une liste d'identificateurs ProductID en utilisant `data()` comme nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="cb8f7-140">Étant donné que la requête spécifie une chaîne vide comme nom d'élément de ligne dans `FOR XML PATH`, aucun élément n'est généré.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="cb8f7-141">À la place, la liste de valeurs est affectée à l'attribut `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="cb8f7-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="cb8f7-142">La seconde clause `SELECT` imbriquée extrait les noms des produits du modèle concerné.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="cb8f7-143">Elle génère des éléments <`ProductName`> qui sont renvoyés inclus dans l'élément <`ProductNames`>, car la requête spécifie `ProductNames` comme nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="cb8f7-144">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="cb8f7-145">La sous-requête qui construit les noms de produits renvoie le résultat sous la forme d'une chaîne décomposée en entités puis ajoutée au document XML.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="cb8f7-146">Si vous ajoutez la directive type, `FOR XML PATH (''), type`, la sous-requête renvoie le résultat en tant que type `xml` et aucune décomposition en entités ne se produit.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="cb8f7-147">Ajout d'espaces de noms au document XML obtenu</span><span class="sxs-lookup"><span data-stu-id="cb8f7-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="cb8f7-148">Comme l’explique la rubrique [Ajout d’espaces de noms à l’aide de WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), vous pouvez utiliser WITH XMLNAMESPACES pour inclure des espaces de noms dans les requêtes en mode PATH.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="cb8f7-149">Par exemple, les noms spécifiés dans la clause SELECT comprennent des préfixes d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="cb8f7-150">La requête en mode `PATH` suivante construit un document XML avec des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="cb8f7-151">L'attribut `@xml:lang` ajouté à l'élément <`English`> est défini dans l'espace de noms xml prédéfini.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="cb8f7-152">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="cb8f7-153">La requête suivante est similaire à l'exemple C, sauf qu'elle utilise `WITH XMLNAMESPACES` pour inclure des espaces de noms dans le résultat XML.</span><span class="sxs-lookup"><span data-stu-id="cb8f7-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="cb8f7-154">Pour plus d’informations, consultez [Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="cb8f7-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="cb8f7-155">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="cb8f7-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="cb8f7-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb8f7-156">See Also</span></span>  
 [<span data-ttu-id="cb8f7-157">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="cb8f7-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
