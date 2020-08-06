---
title: Comparaison de la requête FOR XML et de la requête FOR XML imbriquée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710460"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="e55e3-102">Comparaison de la requête FOR XML et de la requête FOR XML imbriquée</span><span class="sxs-lookup"><span data-stu-id="e55e3-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="e55e3-103">Cette rubrique compare une requête FOR XML d'un seul niveau à une requête FOR XML imbriquée.</span><span class="sxs-lookup"><span data-stu-id="e55e3-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="e55e3-104">L'un des avantages liés à l'utilisation des requêtes FOR XML imbriquées est que vous pouvez spécifier une combinaison de données XML centrées sur l'attribut et centrées sur l'élément pour les résultats de requête.</span><span class="sxs-lookup"><span data-stu-id="e55e3-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="e55e3-105">L'exemple suivant en offre une illustration.</span><span class="sxs-lookup"><span data-stu-id="e55e3-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e55e3-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="e55e3-106">Example</span></span>  
 <span data-ttu-id="e55e3-107">La requête `SELECT` suivante extrait de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] des informations sur les catégories et les sous-catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="e55e3-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e55e3-108">La requête ne contient aucune clause FOR XML imbriquée.</span><span class="sxs-lookup"><span data-stu-id="e55e3-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="e55e3-109">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="e55e3-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="e55e3-110">Si vous spécifiez la directive `ELEMENTS` dans la requête, vous recevez un résultat centré sur l'élément, comme le montre le fragment de résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="e55e3-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="e55e3-111">Ensuite, supposons que vous souhaitez générer une hiérarchie XML qui combine des données XML centrées sur l'attribut et centrées sur l'élément, comme le montre le fragment suivant :</span><span class="sxs-lookup"><span data-stu-id="e55e3-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="e55e3-112">Dans le fragment précédent, les informations relatives aux catégories de produits, telles que l'ID de catégorie et le nom de catégorie, sont des attributs.</span><span class="sxs-lookup"><span data-stu-id="e55e3-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="e55e3-113">Toutefois, les informations sur les sous-catégories sont centrées sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="e55e3-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="e55e3-114">Pour construire l'élément <`ProductCategory`>, vous pouvez écrire une requête `FOR XML`, comme l'illustre le code suivant :</span><span class="sxs-lookup"><span data-stu-id="e55e3-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="e55e3-115">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="e55e3-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="e55e3-116">Ensuite, pour construire les éléments <`ProductSubCategory`> imbriqués dans le document XML de votre choix, vous ajoutez une requête `FOR XML` imbriquée, comme le montre le code suivant :</span><span class="sxs-lookup"><span data-stu-id="e55e3-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="e55e3-117">Notez les points suivants par rapport à la requête ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="e55e3-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="e55e3-118">La requête `FOR XML` interne extrait des informations sur les sous-catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="e55e3-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="e55e3-119">La directive `ELEMENTS` est ajoutée à la requête `FOR XML` interne pour générer des données XML centrées sur l'élément, qui sont ajoutées aux données XML créées par la requête externe.</span><span class="sxs-lookup"><span data-stu-id="e55e3-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="e55e3-120">Par défaut, la requête externe génère des données XML centrées sur l'attribut.</span><span class="sxs-lookup"><span data-stu-id="e55e3-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="e55e3-121">Dans la requête interne, la directive `TYPE` est spécifiée de manière que le résultat soit de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="e55e3-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="e55e3-122">Si la directive `TYPE` n'est pas spécifiée, le résultat est de type `nvarchar(max)` et les données XML sont renvoyées sous la forme d'entités.</span><span class="sxs-lookup"><span data-stu-id="e55e3-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="e55e3-123">La requête externe spécifie également la directive `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="e55e3-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="e55e3-124">Ainsi, le résultat de cette requête retourné au client est de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="e55e3-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="e55e3-125">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="e55e3-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="e55e3-126">La requête suivante est simplement une extension de la requête précédente.</span><span class="sxs-lookup"><span data-stu-id="e55e3-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="e55e3-127">Elle montre la hiérarchie complète des produits stockés dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e55e3-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e55e3-128">Notamment :</span><span class="sxs-lookup"><span data-stu-id="e55e3-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="e55e3-129">Les catégories de produits</span><span class="sxs-lookup"><span data-stu-id="e55e3-129">Product categories</span></span>  
  
-   <span data-ttu-id="e55e3-130">Les sous-catégories de produits dans chaque catégorie</span><span class="sxs-lookup"><span data-stu-id="e55e3-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="e55e3-131">Les modèles de produits dans chaque sous-catégorie</span><span class="sxs-lookup"><span data-stu-id="e55e3-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="e55e3-132">Les produits dans chaque modèle</span><span class="sxs-lookup"><span data-stu-id="e55e3-132">Products in each model</span></span>  
  
 <span data-ttu-id="e55e3-133">La requête suivante peut s'avérer utile pour comprendre la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="e55e3-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="e55e3-134">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="e55e3-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="e55e3-135">Si vous supprimez la directive `ELEMENTS` de la requête `FOR XML` imbriquée qui génère les sous-catégories de produits, la totalité du résultat est centrée sur l'attribut.</span><span class="sxs-lookup"><span data-stu-id="e55e3-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="e55e3-136">Vous pouvez ensuite écrire cette requête sans imbrication.</span><span class="sxs-lookup"><span data-stu-id="e55e3-136">You can then write this query without nesting.</span></span> <span data-ttu-id="e55e3-137">L'ajout de la directive `ELEMENTS` aboutit à un document XML en partie centré sur l'attribut et en partie centré sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="e55e3-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="e55e3-138">Ce résultat ne peut pas être généré par une requête FOR XML d'un seul niveau.</span><span class="sxs-lookup"><span data-stu-id="e55e3-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55e3-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e55e3-139">See Also</span></span>  
 [<span data-ttu-id="e55e3-140">Utiliser des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="e55e3-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
