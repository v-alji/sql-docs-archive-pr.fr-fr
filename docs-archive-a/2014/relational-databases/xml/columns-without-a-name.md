---
title: Colonnes sans nom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697619"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="5581b-102">Colonnes sans nom</span><span class="sxs-lookup"><span data-stu-id="5581b-102">Columns without a Name</span></span>
  <span data-ttu-id="5581b-103">Toute colonne sans nom est insérée.</span><span class="sxs-lookup"><span data-stu-id="5581b-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="5581b-104">Par exemple, les colonnes calculées ou les requêtes scalaires imbriquées qui ne spécifient pas d'alias de colonne génèrent des colonnes sans nom.</span><span class="sxs-lookup"><span data-stu-id="5581b-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="5581b-105">Si la colonne est de type `xml`, le contenu de cette instance de type de données est inséré.</span><span class="sxs-lookup"><span data-stu-id="5581b-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="5581b-106">Sinon, le contenu de la colonne est inséré en tant que nœud de texte.</span><span class="sxs-lookup"><span data-stu-id="5581b-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="5581b-107">Génère ce document XML.</span><span class="sxs-lookup"><span data-stu-id="5581b-107">Produce this XML.</span></span> <span data-ttu-id="5581b-108">Par défaut, pour chaque ligne de l'ensemble de lignes, un élément <`row`> est généré dans le document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="5581b-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="5581b-109">Ce processus rappelle le mode RAW.</span><span class="sxs-lookup"><span data-stu-id="5581b-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="5581b-110">La requête suivante renvoie un ensemble de lignes de trois colonnes.</span><span class="sxs-lookup"><span data-stu-id="5581b-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="5581b-111">La troisième colonne sans nom possède des données XML.</span><span class="sxs-lookup"><span data-stu-id="5581b-111">The third column without a name has XML data.</span></span> <span data-ttu-id="5581b-112">Le mode PATH insère une instance du type xml.</span><span class="sxs-lookup"><span data-stu-id="5581b-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="5581b-113">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="5581b-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="5581b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5581b-114">See Also</span></span>  
 [<span data-ttu-id="5581b-115">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="5581b-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
