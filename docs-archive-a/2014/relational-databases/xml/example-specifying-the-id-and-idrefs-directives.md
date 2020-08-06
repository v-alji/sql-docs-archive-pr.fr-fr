---
title: 'Exemple : Spécification des directives ID et IDREFS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613346"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="c4254-102">Exemple : Spécification des directives ID et IDREF</span><span class="sxs-lookup"><span data-stu-id="c4254-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="c4254-103">Un attribut d'élément peut être spécifié comme attribut de type `ID` et l'attribut `IDREFS` peut ensuite être utilisé pour y faire référence.</span><span class="sxs-lookup"><span data-stu-id="c4254-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="c4254-104">Cela permet de créer des liens à l'intérieur du document et est assimilable aux relations entre clés primaires et clés étrangères dans les bases de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="c4254-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="c4254-105">Cet exemple illustre l'utilisation des directives `ID` et `IDREFS` pour créer des attributs de types `ID` et `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="c4254-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="c4254-106">Étant donné que les ID ne peuvent pas être des valeurs entières, dans cet exemple, leurs valeurs sont converties.</span><span class="sxs-lookup"><span data-stu-id="c4254-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="c4254-107">En d'autres termes, ils subissent une conversion de type.</span><span class="sxs-lookup"><span data-stu-id="c4254-107">In other words, they are type casted.</span></span> <span data-ttu-id="c4254-108">Des préfixes sont utilisés pour les valeurs d'ID.</span><span class="sxs-lookup"><span data-stu-id="c4254-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="c4254-109">Supposons que vous souhaitez construire un document XML comme suit :</span><span class="sxs-lookup"><span data-stu-id="c4254-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="c4254-110">L'attribut `SalesOrderIDList` de l'élément < `Customer` > est un attribut à valeurs multiples qui fait référence à l'attribut `SalesOrderID` de l'élément < `SalesOrder` >.</span><span class="sxs-lookup"><span data-stu-id="c4254-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="c4254-111">Pour établir ce lien, vous devez déclarer l’attribut `SalesOrderID` comme étant de type `ID` et l’attribut `SalesOrderIDList` de l’élément <`Customer`> comme étant de type `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="c4254-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="c4254-112">Comme un client peut passer plusieurs commandes, le type `IDREFS` est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c4254-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="c4254-113">Les éléments de type `IDREFS` ont également plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="c4254-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="c4254-114">Par conséquent, vous devez recourir à une clause de sélection distincte qui réutilisera les mêmes informations de colonne de balise, de parent et de clé.</span><span class="sxs-lookup"><span data-stu-id="c4254-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="c4254-115">La clause `ORDER BY` doit faire en sorte que la séquence des lignes qui composent les valeurs `IDREFS` apparaisse regroupée sous leur élément parent.</span><span class="sxs-lookup"><span data-stu-id="c4254-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="c4254-116">La requête ci-après génère le document XML souhaité.</span><span class="sxs-lookup"><span data-stu-id="c4254-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="c4254-117">La requête utilise les directives `ID` et `IDREFS` pour remplacer les types dans les noms de colonne (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span><span class="sxs-lookup"><span data-stu-id="c4254-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4254-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4254-118">See Also</span></span>  
 [<span data-ttu-id="c4254-119">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="c4254-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
