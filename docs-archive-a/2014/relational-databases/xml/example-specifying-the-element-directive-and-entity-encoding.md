---
title: 'Exemple : spécification de la directive ELEMENT et de l’encodage d’entité | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
- entity encoding [XML]
ms.assetid: 50cda5c1-7293-4080-93b3-872e3b8d484e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba4e419d31aa7c02cc2dc8f19a3350c233f042b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695472"
---
# <a name="example-specifying-the-element-directive-and-entity-encoding"></a><span data-ttu-id="43842-102">Exemple : Spécification de la directive ELEMENT et de l’encodage d’entité</span><span class="sxs-lookup"><span data-stu-id="43842-102">Example: Specifying the ELEMENT Directive and Entity Encoding</span></span>
  <span data-ttu-id="43842-103">Cet exemple illustre la différence entre les directives **ELEMENT** et **XML** .</span><span class="sxs-lookup"><span data-stu-id="43842-103">This example illustrates the difference between the **ELEMENT** and **XML** directives.</span></span> <span data-ttu-id="43842-104">La directive **ELEMENT** décompose les données en entités, contrairement à la directive **XML** .</span><span class="sxs-lookup"><span data-stu-id="43842-104">The **ELEMENT** directive entitizes the data, but the **XML** directive does not.</span></span> <span data-ttu-id="43842-105">L'élément \<Summary> reçoit des données XML, `<Summary>This is summary description</Summary>`, dans la requête.</span><span class="sxs-lookup"><span data-stu-id="43842-105">The \<Summary> element is assigned XML, `<Summary>This is summary description</Summary>`, in the query.</span></span>  
  
 <span data-ttu-id="43842-106">Prenons par exemple la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="43842-106">Consider this query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription!ELEMENT]  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        NULL,  
       '<Summary>This is summary description</Summary>'  
FROM   Production.ProductModel  
WHERE  ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="43842-107">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="43842-107">This is the result.</span></span> <span data-ttu-id="43842-108">la description résumée est décomposée en entités dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="43842-108">The summary description is entitized in the result.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription><Summary>This is summary description</Summary></SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="43842-109">Maintenant, si vous spécifiez la directive **XML** dans le nom de colonne ( `Summary!2!SummaryDescription!XML`) au lieu de la directive **ELEMENT** , vous obtenez la description résumée non décomposée en entités.</span><span class="sxs-lookup"><span data-stu-id="43842-109">Now, if you specify the **XML** directive in the column name, `Summary!2!SummaryDescription!XML`, instead of the **ELEMENT** directive, you will receive the summary description without entitization.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <Summary>This is summary description</Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="43842-110">Au lieu d’affecter une valeur XML statique, la requête suivante utilise la méthode **query()** du type **xml** pour extraire la description résumée des modèles de produit de la colonne CatalogDescription de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="43842-110">Instead of assigning a static XML value, the following query uses the **query()** method of the **xml** type to retrieve the product model summary description from the CatalogDescription column of **xml** type.</span></span> <span data-ttu-id="43842-111">Le résultat étant de type **xml** , aucune décomposition en entités n'est appliquée.</span><span class="sxs-lookup"><span data-stu-id="43842-111">Because the result is known to be of **xml** type, no entitization is applied.</span></span>  
  
```  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
       (SELECT CatalogDescription.query('  
            declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
          /pd:ProductDescription/pd:Summary'))  
FROM     Production.ProductModel  
WHERE    CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],Tag  
FOR XML EXPLICIT  
```  
  
## <a name="see-also"></a><span data-ttu-id="43842-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43842-112">See Also</span></span>  
 [<span data-ttu-id="43842-113">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="43842-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
