---
title: 'Exemple : Récupération des informations de modèle de produit au format XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610529"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="1904d-102">Exemple : Récupération des informations de modèle de produit au format XML</span><span class="sxs-lookup"><span data-stu-id="1904d-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="1904d-103">La requête suivante retourne des informations sur le modèle d'un produit.</span><span class="sxs-lookup"><span data-stu-id="1904d-103">The following query returns product model information.</span></span> <span data-ttu-id="1904d-104">`RAW` Le mode est spécifié dans la clause `FOR XML` .</span><span class="sxs-lookup"><span data-stu-id="1904d-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1904d-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="1904d-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="1904d-106">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="1904d-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="1904d-107">Vous pouvez récupérer des données XML centrées sur les éléments en spécifiant la directive `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="1904d-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="1904d-108">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="1904d-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="1904d-109">Vous pouvez éventuellement spécifier la directive `TYPE` pour récupérer les résultats en tant que type `xml`.</span><span class="sxs-lookup"><span data-stu-id="1904d-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="1904d-110">La directive `TYPE` ne modifie pas le contenu des résultats.</span><span class="sxs-lookup"><span data-stu-id="1904d-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="1904d-111">Seul le type de données des résultats est affecté.</span><span class="sxs-lookup"><span data-stu-id="1904d-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1904d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1904d-112">See Also</span></span>  
 [<span data-ttu-id="1904d-113">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="1904d-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
