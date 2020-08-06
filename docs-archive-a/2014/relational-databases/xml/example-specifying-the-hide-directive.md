---
title: 'Exemple : spécification de la directive HIDE | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- HIDE directive
ms.assetid: 87504d87-1cbd-412a-9041-47884b6efcec
author: rothja
ms.author: jroth
ms.openlocfilehash: 423ee36f679467c07a604b9754172f6e261971b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613349"
---
# <a name="example-specifying-the-hide-directive"></a><span data-ttu-id="6563a-102">Exemple : spécification de la directive HIDE</span><span class="sxs-lookup"><span data-stu-id="6563a-102">Example: Specifying the HIDE Directive</span></span>
  <span data-ttu-id="6563a-103">Cet exemple illustre l'utilisation de la directive **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="6563a-103">This example illustrates the use of the **HIDE** directive.</span></span> <span data-ttu-id="6563a-104">Cette directive est utile quand vous souhaitez que la requête renvoie un attribut pour classer les lignes de la table universelle renvoyée par la requête, sans que cet attribut figure dans le document XML obtenu au final.</span><span class="sxs-lookup"><span data-stu-id="6563a-104">This directive is useful when you want the query to return an attribute for ordering the rows in the universal table that is returned by the query, but you do not want that attribute in the final resulting XML document.</span></span>  
  
 <span data-ttu-id="6563a-105">Cette requête construit le document XML suivant :</span><span class="sxs-lookup"><span data-stu-id="6563a-105">This query constructs this XML:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
           <Summary> element from XML stored in CatalogDescription column  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="6563a-106">Cette requête génère le document XML souhaité.</span><span class="sxs-lookup"><span data-stu-id="6563a-106">This query generates the XML you want.</span></span> <span data-ttu-id="6563a-107">Elle identifie deux groupes de colonnes possédant 1 et 2 comme valeurs Tag dans les noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="6563a-107">The query identifies two column groups having 1 and 2 as Tag values in the column names.</span></span>  
  
 <span data-ttu-id="6563a-108">Cette requête utilise la [méthode query() (type de données xml)](/sql/t-sql/xml/query-method-xml-data-type) du type de données **xml** pour interroger la colonne CatalogDescription de type **xml** afin d’extraire la description résumée.</span><span class="sxs-lookup"><span data-stu-id="6563a-108">This query uses the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) of the **xml** data type to query the CatalogDescription column of **xml** type in order to retrieve the summary description.</span></span> <span data-ttu-id="6563a-109">Elle utilise également la [méthode value() (type de données xml)](/sql/t-sql/xml/value-method-xml-data-type) du type de données **xml** pour extraire la valeur ProductModelID de la colonne CatalogDescription.</span><span class="sxs-lookup"><span data-stu-id="6563a-109">The query also uses the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) of the **xml** data type to retrieve the ProductModelID value from the CatalogDescription column.</span></span> <span data-ttu-id="6563a-110">Cette valeur n'est pas requise dans le document XML obtenu, mais elle est nécessaire pour trier l'ensemble de lignes obtenu.</span><span class="sxs-lookup"><span data-stu-id="6563a-110">This value is not required in the resulting XML, but is required to sort the resulting rowset.</span></span> <span data-ttu-id="6563a-111">Par conséquent, le nom de colonne, `[Summary!2!ProductModelID!HIDE]`, inclut la directive **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="6563a-111">Therefore, the column name, `[Summary!2!ProductModelID!HIDE]`, includes the **HIDE** directive.</span></span> <span data-ttu-id="6563a-112">Si cette colonne n'est pas incluse dans l'instruction SELECT, vous devez trier l'ensemble de lignes par `[ProductModel!1!ProdModelID]` et `[Summary!2!SummaryDescription]` , de type **xml** , et vous ne pouvez pas utiliser la colonne de type **xml** dans la clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="6563a-112">If this column is not included in the SELECT statement, you will have to sort the rowset by `[ProductModel!1!ProdModelID]` and `[Summary!2!SummaryDescription]` that is **xml** type and you cannot use the **xml** type column in ORDER BY.</span></span> <span data-ttu-id="6563a-113">Par conséquent, la colonne `[Summary!2!ProductModelID!HIDE]` est ajoutée puis spécifiée dans la clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="6563a-113">Therefore, the additional `[Summary!2!ProductModelID!HIDE]` column is added and is then specified in the ORDER BY clause.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID     as [ProductModel!1!ProdModelID],  
        Name               as [ProductModel!1!Name],  
        NULL               as [Summary!2!ProductModelID!hide],  
        NULL               as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
        CatalogDescription.value('  
         declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
       (/PD:ProductDescription/@ProductModelID)[1]', 'int'),  
        CatalogDescription.query('  
         declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /pd:ProductDescription/pd:Summary')  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],[Summary!2!ProductModelID!hide]  
FOR XML EXPLICIT  
go  
```  
  
 <span data-ttu-id="6563a-114">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="6563a-114">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <pd:Summary xmlns:pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription" xmlns="">  
        <p1:p xmlns:p1="http://www.w3.org/1999/xhtml">Our top-of-the-line competition mountain bike. Performance-enhancing options include the innovative HL Frame, super-smooth front suspension, and traction for all terrain. </p1:p>  
      </pd:Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6563a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6563a-115">See Also</span></span>  
 [<span data-ttu-id="6563a-116">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="6563a-116">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
