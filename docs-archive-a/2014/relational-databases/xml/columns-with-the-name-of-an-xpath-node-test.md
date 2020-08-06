---
title: Colonnes avec le nom d’un test de nœud XPath | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697620"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="7b7aa-102">Colonnes avec le nom d'un test de nœud XPath</span><span class="sxs-lookup"><span data-stu-id="7b7aa-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="7b7aa-103">Si le nom de colonne est l'un des tests de nœud XPath, le contenu est mappé comme le montre le tableau ci-après.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="7b7aa-104">Lorsque le nom de colonne est un test de nœud XPath, le contenu est mappé au nœud correspondant.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="7b7aa-105">Si le type SQL de la colonne est `xml`, une erreur est renvoyée.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="7b7aa-106">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="7b7aa-106">Column Name</span></span>|<span data-ttu-id="7b7aa-107">Comportement</span><span class="sxs-lookup"><span data-stu-id="7b7aa-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="7b7aa-108">text()</span><span class="sxs-lookup"><span data-stu-id="7b7aa-108">text()</span></span>|<span data-ttu-id="7b7aa-109">Dans le cas d'une colonne nommée text(), la valeur de chaîne contenue dans cette colonne est ajoutée en tant que nœud de texte.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="7b7aa-110">comment()</span><span class="sxs-lookup"><span data-stu-id="7b7aa-110">comment()</span></span>|<span data-ttu-id="7b7aa-111">Dans le cas d'une colonne nommée comment(), la valeur de chaîne contenue dans cette colonne est ajoutée en tant que commentaire XML.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="7b7aa-112">node()</span><span class="sxs-lookup"><span data-stu-id="7b7aa-112">node()</span></span>|<span data-ttu-id="7b7aa-113">Dans le cas d'une colonne nommée node(), le résultat est le même que lorsque le nom de colonne est un caractère générique (\*).</span><span class="sxs-lookup"><span data-stu-id="7b7aa-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="7b7aa-114">processing-instruction(name)</span><span class="sxs-lookup"><span data-stu-id="7b7aa-114">processing-instruction(name)</span></span>|<span data-ttu-id="7b7aa-115">Dans le cas d'une colonne dont le nom est une instruction de traitement, la valeur de chaîne contenue dans cette colonne est ajoutée en tant que valeur PI du nom cible de l'instruction de traitement.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="7b7aa-116">La requête suivante affiche l'utilisation des tests de nœud comme noms de colonne.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="7b7aa-117">Elle ajoute des nœuds de texte et des commentaires dans le document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="7b7aa-118">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="7b7aa-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="7b7aa-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b7aa-119">See Also</span></span>  
 [<span data-ttu-id="7b7aa-120">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="7b7aa-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
