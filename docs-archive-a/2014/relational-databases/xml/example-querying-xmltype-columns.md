---
title: 'Exemple : interrogation de colonnes de type XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600678"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="53db1-102">Exemple : interrogation de colonnes de type XML</span><span class="sxs-lookup"><span data-stu-id="53db1-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="53db1-103">La requête ci-dessous inclut des colonnes de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="53db1-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="53db1-104">Elle extrait l'ID de modèle de produit, le nom et les étapes de fabrication dans le premier emplacement à partir de la colonne `Instructions` de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="53db1-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53db1-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="53db1-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="53db1-106">Le résultat est le suivant.</span><span class="sxs-lookup"><span data-stu-id="53db1-106">The following is the result.</span></span> <span data-ttu-id="53db1-107">Notez que la table stocke les instructions de fabrication de certains modèles de produits uniquement.</span><span class="sxs-lookup"><span data-stu-id="53db1-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="53db1-108">Les étapes de fabrication sont retournées comme sous-éléments de l'élément <`ProductModelData`> dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="53db1-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="53db1-109">Si la requête spécifie un nom de colonne pour les données XML retournées par la requête XQuery, comme spécifié dans l'instruction `SELECT` ci-dessous, les étapes de fabrication sont incluses dans l'élément qui possède le nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="53db1-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="53db1-110">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="53db1-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="53db1-111">La requête suivante spécifie la directive `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="53db1-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="53db1-112">Par conséquent, le résultat retourné est centré sur les éléments.</span><span class="sxs-lookup"><span data-stu-id="53db1-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="53db1-113">L'option `XSINIL` spécifiée avec la directive `ELEMENTS` retourne les éléments <`ManuSteps`>, même si la colonne correspondante dans l'ensemble de lignes est NULL.</span><span class="sxs-lookup"><span data-stu-id="53db1-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="53db1-114">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="53db1-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53db1-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53db1-115">See Also</span></span>  
 [<span data-ttu-id="53db1-116">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="53db1-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
