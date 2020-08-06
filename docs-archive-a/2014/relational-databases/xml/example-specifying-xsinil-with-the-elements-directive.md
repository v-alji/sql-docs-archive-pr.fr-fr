---
title: 'Exemple : spécification de XSINIL avec la directive ELEMENTS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, specifying XSINIL example
ms.assetid: 07c873ff-1f9d-480e-8536-862c39eb8249
author: rothja
ms.author: jroth
ms.openlocfilehash: 7817d2c72909ca66fb9fac10f8fcb32a759faf56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695460"
---
# <a name="example-specifying-xsinil-with-the-elements-directive"></a><span data-ttu-id="ec5d0-102">Exemple : spécification de XSINIL avec la directive ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="ec5d0-102">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>
  <span data-ttu-id="ec5d0-103">La requête suivante spécifie la directive `ELEMENTS` pour générer des données XML centrées sur les éléments à partir du résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="ec5d0-103">The following query specifies the `ELEMENTS` directive to generate element-centric XML from the query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec5d0-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="ec5d0-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="ec5d0-105">Le résultat partiel est le suivant.</span><span class="sxs-lookup"><span data-stu-id="ec5d0-105">This is the partial result.</span></span>  
  
```  
<row>  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
 <span data-ttu-id="ec5d0-106">Comme la colonne `Color` possède des valeurs NULL pour certains produits, les données XML résultantes ne génèrent pas l'élément <`Color`> correspondant.</span><span class="sxs-lookup"><span data-stu-id="ec5d0-106">Because the `Color` column has null values for some products, the resulting XML will not generate the corresponding <`Color`> element.</span></span> <span data-ttu-id="ec5d0-107">En ajoutant la directive `XSINIL` à `ELEMENTS`, vous pouvez générer l'élément <`Color`> même pour les valeurs de couleurs NULL dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="ec5d0-107">By adding the `XSINIL` directive with `ELEMENTS`, you can generate the <`Color`> element even for NULL color values in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS XSINIL ;  
```  
  
 <span data-ttu-id="ec5d0-108">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="ec5d0-108">This is the partial result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
  <Color xsi:nil="true" />  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec5d0-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec5d0-109">See Also</span></span>  
 [<span data-ttu-id="ec5d0-110">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="ec5d0-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
