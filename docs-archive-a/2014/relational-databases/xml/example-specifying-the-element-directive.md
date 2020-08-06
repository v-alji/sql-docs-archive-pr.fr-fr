---
title: 'Exemple : Spécification de la directive ELEMENT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
ms.assetid: 80dd5d1f-fa90-4f97-a186-8fa3f460a7f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a03d1049fa9df23eff759634bcd74f88f842a8e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695463"
---
# <a name="example-specifying-the-element-directive"></a><span data-ttu-id="fb355-102">Exemple : Spécification de la directive ELEMENT</span><span class="sxs-lookup"><span data-stu-id="fb355-102">Example: Specifying the ELEMENT Directive</span></span>
  <span data-ttu-id="fb355-103">Cette directive extrait des informations sur les employés et génère des données XML centrées sur l'élément, comme illustré par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="fb355-103">This retrieves employee information and generates element-centric XML as shown in the following:</span></span>  
  
```  
<Employee EmpID=...>  
  <Name>  
    <FName>...</FName>  
    <LName>...</LName>  
  </Name>  
</Employee>  
```  
  
 <span data-ttu-id="fb355-104">La requête demeure la même, à l'exception du fait que vous ajoutez la directive `ELEMENT` dans les noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="fb355-104">The query remains the same, except you add the `ELEMENT` directive in the column names.</span></span> <span data-ttu-id="fb355-105">Par conséquent, au lieu d'attributs, les éléments enfants <`FName`> et <`LName`> sont ajoutés à l'élément <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="fb355-105">Therefore, instead of attributes, the <`FName`> and <`LName`> element children are added to the <`Name`> element.</span></span> <span data-ttu-id="fb355-106">Étant donné que la colonne `Employee!1!EmpID` ne spécifie pas la directive `ELEMENT`, `EmpID` est ajouté en tant qu'attribut de l'élément <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="fb355-106">Because the `Employee!1!EmpID` column does not specify the `ELEMENT` directive, `EmpID` is added as the attribute of the <`Employee`> element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName!ELEMENT],  
       NULL       as [Name!2!LName!ELEMENT]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName!ELEMENT]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="fb355-107">Le résultat partiel est le suivant.</span><span class="sxs-lookup"><span data-stu-id="fb355-107">This is the partial result.</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name>`  
  
 `<FName>Ken</FName>`  
  
 `<LName>S??nchez</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name>`  
  
 `<FName>Terri</FName>`  
  
 `<LName>Duffy</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `...`  
  
## <a name="see-also"></a><span data-ttu-id="fb355-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb355-108">See Also</span></span>  
 [<span data-ttu-id="fb355-109">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="fb355-109">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
