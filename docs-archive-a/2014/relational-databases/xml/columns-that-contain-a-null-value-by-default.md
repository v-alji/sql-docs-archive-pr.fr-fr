---
title: Colonnes contenant une valeur NULL par défaut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- columns [XML in SQL Server], null default value
ms.assetid: 9381c07f-6887-4a62-9730-32661f9aa87c
author: rothja
ms.author: jroth
ms.openlocfilehash: 92ea51101f73695be2075a1b41deb62ca021f496
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600684"
---
# <a name="columns-that-contain-a-null-value-by-default"></a><span data-ttu-id="7d78d-102">Colonnes contenant une valeur NULL par défaut</span><span class="sxs-lookup"><span data-stu-id="7d78d-102">Columns that Contain a Null Value By Default</span></span>
  <span data-ttu-id="7d78d-103">Par défaut, une valeur NULL dans une colonne correspond à l'absence de l'attribut, du nœud ou de l'élément.</span><span class="sxs-lookup"><span data-stu-id="7d78d-103">By default, a null value in a column maps to the absence of the attribute, node, or element.</span></span> <span data-ttu-id="7d78d-104">Vous pouvez remplacer ce comportement par défaut en demandant un document XML centré sur l'élément à l'aide de la directive ELEMENTS et en spécifiant XSINIL afin de demander l'ajout d'éléments pour les valeurs NULL, comme le montre la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="7d78d-104">This default behavior can be overwritten by requesting element-centric XML using the ELEMENTS directive and specifying XSINIL to request adding elements for NULL values, as shown in the following query:</span></span>  
  
```  
SELECT EmployeeID as "@EmpID",   
       FirstName  as "EmpName/First",   
       MiddleName as "EmpName/Middle",   
       LastName   as "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="7d78d-105">Le résultat est le suivant.</span><span class="sxs-lookup"><span data-stu-id="7d78d-105">The following shows the result.</span></span> <span data-ttu-id="7d78d-106">Si XSINIL n'est pas spécifié, l'élément <`Middle`> est absent.</span><span class="sxs-lookup"><span data-stu-id="7d78d-106">Note that if XSINIL is not specified, the <`Middle`> element will be absent.</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d78d-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d78d-107">See Also</span></span>  
 [<span data-ttu-id="7d78d-108">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="7d78d-108">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
