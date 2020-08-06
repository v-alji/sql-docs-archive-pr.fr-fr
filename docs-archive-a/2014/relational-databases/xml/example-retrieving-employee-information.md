---
title: 'Exemple : Récupération d’informations sur les employés | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610521"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="63f3c-102">Exemple : Extraction d’informations sur les employés</span><span class="sxs-lookup"><span data-stu-id="63f3c-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="63f3c-103">Cet exemple extrait un ID et un nom pour chaque employé.</span><span class="sxs-lookup"><span data-stu-id="63f3c-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="63f3c-104">Dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , les ID des employés se trouvent dans la colonne BusinessEntityID de la table Employee.</span><span class="sxs-lookup"><span data-stu-id="63f3c-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="63f3c-105">Les noms des employés figurent dans la table Person.</span><span class="sxs-lookup"><span data-stu-id="63f3c-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="63f3c-106">La colonne BusinessEntityID peut être utilisée pour joindre les tables.</span><span class="sxs-lookup"><span data-stu-id="63f3c-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="63f3c-107">Supposons que vous souhaitez générer un document XML à l'aide de la transformation FOR XML EXPLICIT comme suit :</span><span class="sxs-lookup"><span data-stu-id="63f3c-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="63f3c-108">Étant donné que la hiérarchie comprend deux niveaux, vous écrivez deux requêtes `SELECT` et appliquez UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="63f3c-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="63f3c-109">Voici la première requête qui extrait les valeurs de l'élément <`Employee`> et de ses attributs.</span><span class="sxs-lookup"><span data-stu-id="63f3c-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="63f3c-110">La requête attribue `1` comme valeur `Tag` pour l'élément <`Employee`> et NULL comme valeur `Parent`, car il s'agit de l'élément de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="63f3c-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="63f3c-111">Voici la seconde requête.</span><span class="sxs-lookup"><span data-stu-id="63f3c-111">This is the second query.</span></span> <span data-ttu-id="63f3c-112">Elle extrait les valeurs de l'élément <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="63f3c-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="63f3c-113">Elle attribue `2` comme valeur `Tag` pour l'élément <`Name`> et `1` comme valeur de balise `Parent` identifiant <`Employee`> en tant que parent.</span><span class="sxs-lookup"><span data-stu-id="63f3c-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="63f3c-114">Vous combinez ces requêtes avec `UNION AL`L, appliquez `FOR XML EXPLICIT`et spécifiez la clause `ORDER BY` requise.</span><span class="sxs-lookup"><span data-stu-id="63f3c-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="63f3c-115">Vous devez trier l'ensemble de lignes par `BusinessEntityID` puis par nom afin que les valeurs NULL du nom apparaissent en premier.</span><span class="sxs-lookup"><span data-stu-id="63f3c-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="63f3c-116">En exécutant la requête suivante sans la clause FOR XML, vous pouvez visualiser la table universelle générée.</span><span class="sxs-lookup"><span data-stu-id="63f3c-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="63f3c-117">Voici la requête finale :</span><span class="sxs-lookup"><span data-stu-id="63f3c-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
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
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="63f3c-118">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="63f3c-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="63f3c-119">La première instruction `SELECT` spécifie les noms des colonnes dans l'ensemble de lignes obtenu.</span><span class="sxs-lookup"><span data-stu-id="63f3c-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="63f3c-120">Ces noms forment deux groupes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="63f3c-120">These names form two column groups.</span></span> <span data-ttu-id="63f3c-121">Le groupe qui possède la valeur `Tag``1` dans le nom de colonne identifie `Employee` en tant qu'élément et `EmpID` en tant qu'attribut.</span><span class="sxs-lookup"><span data-stu-id="63f3c-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="63f3c-122">L'autre groupe de colonnes possède la valeur `Tag` `2` dans la colonne et identifie <`Name`> en tant qu'élément et `FName` et `LName` en tant qu'attributs.</span><span class="sxs-lookup"><span data-stu-id="63f3c-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="63f3c-123">Le tableau suivant montre l'ensemble de lignes partiel généré par la requête :</span><span class="sxs-lookup"><span data-stu-id="63f3c-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="63f3c-124">Les lignes de la table universelle sont traitées comme suit pour générer l'arborescence XML obtenue :</span><span class="sxs-lookup"><span data-stu-id="63f3c-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="63f3c-125">La première ligne identifie la valeur `Tag``1`.</span><span class="sxs-lookup"><span data-stu-id="63f3c-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="63f3c-126">Par conséquent, le groupe de colonnes qui a la valeur `Tag``1` est identifié, `Employee!1!EmpID`.</span><span class="sxs-lookup"><span data-stu-id="63f3c-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="63f3c-127">Cette colonne identifie `Employee` en tant que nom d'élément.</span><span class="sxs-lookup"><span data-stu-id="63f3c-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="63f3c-128">Un élément <`Employee`> possédant les attributs `EmpID` est ensuite créé.</span><span class="sxs-lookup"><span data-stu-id="63f3c-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="63f3c-129">Les valeurs de colonnes correspondantes sont affectées à ces attributs.</span><span class="sxs-lookup"><span data-stu-id="63f3c-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="63f3c-130">La deuxième ligne a la valeur `Tag``2`.</span><span class="sxs-lookup"><span data-stu-id="63f3c-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="63f3c-131">Par conséquent, le groupe de colonnes qui a la valeur `Tag``2` dans le nom de colonne, `Name!2!FName`, `Name!2!LName`, est identifié.</span><span class="sxs-lookup"><span data-stu-id="63f3c-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="63f3c-132">Ces noms de colonnes identifient `Name` comme nom d'élément.</span><span class="sxs-lookup"><span data-stu-id="63f3c-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="63f3c-133">Un élément <`Name`> possédant les attributs `FName` et `LName` est créé.</span><span class="sxs-lookup"><span data-stu-id="63f3c-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="63f3c-134">Les valeurs de colonnes correspondantes sont ensuite affectées à ces attributs.</span><span class="sxs-lookup"><span data-stu-id="63f3c-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="63f3c-135">Cette ligne identifie `1` comme `Parent`.</span><span class="sxs-lookup"><span data-stu-id="63f3c-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="63f3c-136">Cet élément enfant est ajouté à l'élément <`Employee`> précédent.</span><span class="sxs-lookup"><span data-stu-id="63f3c-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="63f3c-137">Ce processus est répété pour le reste des lignes de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="63f3c-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="63f3c-138">Notez l'importance du tri des lignes dans la table universelle pour que FOR XML EXPLICIT puisse traiter l'ensemble de lignes dans l'ordre et générer le document XML souhaité.</span><span class="sxs-lookup"><span data-stu-id="63f3c-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f3c-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63f3c-139">See Also</span></span>  
 [<span data-ttu-id="63f3c-140">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="63f3c-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
