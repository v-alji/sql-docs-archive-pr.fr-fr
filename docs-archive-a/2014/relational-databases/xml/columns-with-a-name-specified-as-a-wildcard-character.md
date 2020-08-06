---
title: Colonnes avec un nom spécifié sous la forme d’un caractère générique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: d9551df1-5bb4-4c0b-880a-5bb049834884
author: rothja
ms.author: jroth
ms.openlocfilehash: 4b363baf8792628c2e17b1a695c19a6a338f4fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605286"
---
# <a name="columns-with-a-name-specified-as-a-wildcard-character"></a><span data-ttu-id="97230-102">Colonnes avec un nom spécifié sous la forme d'un caractère générique</span><span class="sxs-lookup"><span data-stu-id="97230-102">Columns with a Name Specified as a Wildcard Character</span></span>
  <span data-ttu-id="97230-103">Si le nom de colonne spécifié est un caractère générique (\*), le contenu de la colonne concernée est inséré comme si aucun nom de colonne n’était spécifié.</span><span class="sxs-lookup"><span data-stu-id="97230-103">If the column name specified is a wildcard character (\*), the content of that column is inserted as if there is no column name specified.</span></span> <span data-ttu-id="97230-104">Si cette colonne est une colonne de type non-`xml`, le contenu de la colonne est inséré en tant que nœud de texte, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="97230-104">If this column is a non-`xml` type column, the column content is inserted as a text node, as shown in the following example:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
       FirstName "*",   
       MiddleName "*",   
       LastName "*"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
    ON E.BusinessEntityID = P.BusinessEntityID  
WHERE E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="97230-105">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="97230-105">This is the result:</span></span>  
  
 `<row EmpID="1">KenJS??nchez</row>`  
  
 <span data-ttu-id="97230-106">Si la colonne est de type `xml`, l'arborescence XML correspondante est insérée.</span><span class="sxs-lookup"><span data-stu-id="97230-106">If the column is of `xml` type, the corresponding XML tree is inserted.</span></span> <span data-ttu-id="97230-107">Par exemple, la requête suivante spécifie « \* » pour le nom de la colonne qui contient le document XML renvoyé par la requête XQuery portant sur la colonne Instructions.</span><span class="sxs-lookup"><span data-stu-id="97230-107">For example, the following query specifies "\*" for the column name that contains the XML returned by the XQuery against the Instructions column.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
                /MI:root/MI:Location   
              ') as "*"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH;   
GO  
```  
  
 <span data-ttu-id="97230-108">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="97230-108">This is the result.</span></span> <span data-ttu-id="97230-109">le document XML renvoyé par la requête XQuery est inséré sans élément d'habillage.</span><span class="sxs-lookup"><span data-stu-id="97230-109">The XML returned by XQuery is inserted without a wrapping element.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location LocationID="10">...</MI:Location>`  
  
 `<MI:Location LocationID="20">...</MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="97230-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97230-110">See Also</span></span>  
 [<span data-ttu-id="97230-111">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="97230-111">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
