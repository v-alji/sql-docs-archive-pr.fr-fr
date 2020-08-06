---
title: 'Exemple : Renommage de l’élément &lt;row&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
author: rothja
ms.author: jroth
ms.openlocfilehash: 39375fa125f451f21d936b3a6897b93928fa2f02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600677"
---
# <a name="example-renaming-the-ltrowgt-element"></a><span data-ttu-id="a1ae3-102">Exemple : Renommage de l’élément &lt;row&gt;</span><span class="sxs-lookup"><span data-stu-id="a1ae3-102">Example: Renaming the &lt;row&gt; Element</span></span>
  <span data-ttu-id="a1ae3-103">Pour chaque ligne du jeu de résultats, le mode RAW génère un élément `<row>`.</span><span class="sxs-lookup"><span data-stu-id="a1ae3-103">For each row in the result set, the RAW mode generates an element `<row>`.</span></span> <span data-ttu-id="a1ae3-104">Vous pouvez éventuellement spécifier un autre nom pour cet élément en spécifiant un argument facultatif pour le mode RAW, comme illustré dans cette requête.</span><span class="sxs-lookup"><span data-stu-id="a1ae3-104">You can optionally specify another name for this element by specifying an optional argument to the RAW mode, as shown in this query.</span></span> <span data-ttu-id="a1ae3-105">La requête retourne un élément <`ProductModel`> pour chaque ligne de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="a1ae3-105">The query returns a <`ProductModel`> element for each row in the rowset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ae3-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="a1ae3-106">Example</span></span>  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 <span data-ttu-id="a1ae3-107">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="a1ae3-107">This is the result.</span></span> <span data-ttu-id="a1ae3-108">La directive `ELEMENTS` étant ajoutée à la requête, le résultat est centré sur les éléments.</span><span class="sxs-lookup"><span data-stu-id="a1ae3-108">Because the `ELEMENTS` directive is added in the query, the result is element-centric.</span></span>  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a><span data-ttu-id="a1ae3-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1ae3-109">See Also</span></span>  
 [<span data-ttu-id="a1ae3-110">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="a1ae3-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
