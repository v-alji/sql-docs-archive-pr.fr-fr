---
title: Générer des frères à l’aide d’une requête imbriquée en mode AUTO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710420"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="1dbbc-102">Générer des frères à l'aide d'une requête imbriquée en mode AUTO</span><span class="sxs-lookup"><span data-stu-id="1dbbc-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="1dbbc-103">L'exemple suivant indique comment générer des frères à l'aide d'une requête imbriquée en mode AUTO.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="1dbbc-104">La seule autre façon de générer ce type de document XML consiste à utiliser le mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="1dbbc-105">Toutefois, cette méthode peut s'avérer lourde.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dbbc-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="1dbbc-106">Example</span></span>  
 <span data-ttu-id="1dbbc-107">Cette requête construit le document XML qui fournit les informations sur les commandes.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="1dbbc-108">Notamment :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="1dbbc-109">Les informations sur les en-têtes des commandes, `SalesOrderID`, `SalesPersonID`et `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="1dbbc-110">stocke ces informations dans la table `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="1dbbc-111">Les informations sur les détails des commandes.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-111">Sales order detail information.</span></span> <span data-ttu-id="1dbbc-112">Elles indiquent un ou plusieurs produits commandés, le prix unitaire et la quantité commandée.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="1dbbc-113">Ces informations sont stockées dans la table `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="1dbbc-114">Les informations sur le vendeur.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-114">Sales person information.</span></span> <span data-ttu-id="1dbbc-115">Il s'agit du vendeur qui a traité la commande.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="1dbbc-116">La table `SalesPerson` fournit le `SalesPersonID`.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="1dbbc-117">Pour cette requête, vous devez joindre cette table à la table `Employee` afin de rechercher le nom du vendeur.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="1dbbc-118">Les deux requêtes `SELECT` distinctes ci-après génèrent un document XML dont la forme varie peu.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="1dbbc-119">La première requête génère un document XML dans lequel <`SalesPerson`> et <`SalesOrderHeader`> apparaissent en tant qu'enfants frères de <`SalesOrder`> :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="1dbbc-120">Dans la requête précédente, l'instruction `SELECT` la plus externe effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="1dbbc-121">Elle interroge l'ensemble de lignes `SalesOrder`, spécifié dans la clause `FROM`.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="1dbbc-122">Le résultat est un document XML possédant un ou plusieurs éléments <`SalesOrder`>.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="1dbbc-123">Spécifie le mode `AUTO` et la directive `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="1dbbc-124">`AUTO`le mode transforme le résultat de la requête en XML, tandis `TYPE` que la directive retourne le résultat sous forme de `xml` type.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="1dbbc-125">Elle inclut deux instructions `SELECT` imbriquées séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="1dbbc-126">La première instruction `SELECT` imbriquée extrait les informations sur la commande, l'en-tête et les détails, tandis que la seconde instruction `SELECT` imbriquée extrait les informations sur le vendeur.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="1dbbc-127">L'instruction `SELECT` qui extrait `SalesOrderID`, `SalesPersonID`et `CustomerID` inclut elle-même une autre instruction imbriquée `SELECT ... FOR XML` (avec le mode `AUTO` et la directive `TYPE` ) qui retourne des informations sur les détails des commandes.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="1dbbc-128">L'instruction `SELECT` qui extrait les informations sur le vendeur interroge un ensemble de lignes, `SalesPerson`, créé dans la clause `FROM` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="1dbbc-129">Pour que les requêtes `FOR XML` fonctionnent, vous devez fournir un nom pour l'ensemble de lignes anonyme généré dans la clause `FROM` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="1dbbc-130">Dans ce cas, le nom fourni est `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="1dbbc-131">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="1dbbc-132">La requête suivante génère les mêmes informations sur la commande, sauf que, dans le document XML obtenu, <`SalesPerson`> apparaît en tant que frère de <`SalesOrderDetail`> :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="1dbbc-133">Voici la requête :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="1dbbc-134">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="1dbbc-135">Étant donné que la directive `TYPE` renvoie un résultat de requête de type `xml`, vous pouvez recourir à différentes méthodes de type de données `xml` pour interroger le document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="1dbbc-136">Pour plus d’informations, consultez [Méthodes de données de type xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="1dbbc-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="1dbbc-137">Dans la requête suivante, notez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1dbbc-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="1dbbc-138">La requête précédente est ajoutée à la clause `FROM` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="1dbbc-139">Les résultats de la requête sont renvoyés sous la forme d'une table.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-139">The query result is returned as a table.</span></span> <span data-ttu-id="1dbbc-140">Notez l'ajout de l'alias `XmlCol` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="1dbbc-141">La clause `SELECT` définit une requête XQuery par rapport à l'alias `XmlCol` renvoyé dans la clause `FROM` .</span><span class="sxs-lookup"><span data-stu-id="1dbbc-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="1dbbc-142">La méthode `query()` du type de données `xml` est utilisée dans la spécification de la requête XQuery.</span><span class="sxs-lookup"><span data-stu-id="1dbbc-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="1dbbc-143">Pour plus d’informations, consultez [Méthode query&#40;&#41; &#40;type de données xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="1dbbc-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1dbbc-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dbbc-144">See Also</span></span>  
 [<span data-ttu-id="1dbbc-145">Utiliser des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="1dbbc-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
