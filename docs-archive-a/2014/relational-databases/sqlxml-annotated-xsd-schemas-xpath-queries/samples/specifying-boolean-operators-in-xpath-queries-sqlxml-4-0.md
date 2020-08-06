---
title: Spécification d’opérateurs booléens dans les requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600736"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="80510-102">Spécification d'opérateurs booléens dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="80510-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="80510-103">L'exemple suivant montre comment les opérateurs booléens sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="80510-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="80510-104">La requête XPath de cet exemple est spécifiée par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="80510-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="80510-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="80510-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="80510-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="80510-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="80510-107">R.</span><span class="sxs-lookup"><span data-stu-id="80510-107">A.</span></span> <span data-ttu-id="80510-108">Spécifier l'opérateur booléen OR</span><span class="sxs-lookup"><span data-stu-id="80510-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="80510-109">Cette requête XPath retourne les **\<Customer>** enfants de l’élément du nœud de contexte avec la valeur de l’attribut **CustomerID** 13 ou 31 :</span><span class="sxs-lookup"><span data-stu-id="80510-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="80510-110">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et l'axe `child` étant l'axe par défaut, il peut être omis :</span><span class="sxs-lookup"><span data-stu-id="80510-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="80510-111">Dans le prédicat, `attribute` est l’axe et `CustomerID` est le test de nœud (true si **CustomerID** est un **\<attribute>** nœud, car le **\<attribute>** nœud est le nœud principal de l' `attribute` axe).</span><span class="sxs-lookup"><span data-stu-id="80510-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="80510-112">Le prédicat filtre les **\<Customer>** éléments et retourne uniquement ceux qui répondent à la condition spécifiée dans le prédicat.</span><span class="sxs-lookup"><span data-stu-id="80510-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="80510-113">Pour tester les requêtes XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="80510-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="80510-114">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="80510-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="80510-115">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="80510-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="80510-116">Créez le modèle ci-après (BooleanOperatorsA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="80510-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="80510-117">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="80510-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="80510-118">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="80510-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="80510-119">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="80510-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="80510-120">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="80510-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="80510-121">Voici le jeu de résultats de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="80510-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
