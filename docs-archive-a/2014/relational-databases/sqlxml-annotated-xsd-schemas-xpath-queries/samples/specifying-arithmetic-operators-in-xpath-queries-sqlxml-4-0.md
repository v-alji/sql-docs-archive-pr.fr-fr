---
title: Spécification d’opérateurs arithmétiques dans des requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- arithmetic operators
- XPath operators [SQLXML]
- XPath queries [SQLXML], arithmetic operators
- operators [SQLXML]
ms.assetid: fdfbc87d-759f-4abc-acf5-a21de01f78d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 904f3b920029d45d1b72641a19e2ac07befd4def
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600740"
---
# <a name="specifying-arithmetic-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="0739b-102">Spécification d'opérateurs arithmétiques dans des requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="0739b-102">Specifying Arithmetic Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="0739b-103">L'exemple suivant montre comment les opérateurs arithmétiques sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="0739b-103">The following example shows how arithmetic operators are specified in XPath queries.</span></span> <span data-ttu-id="0739b-104">La requête XPath de cet exemple est spécifiée par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0739b-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="0739b-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="0739b-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0739b-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="0739b-106">Examples</span></span>  
  
### <a name="a-specify-the--arithmetic-operator"></a><span data-ttu-id="0739b-107">R.</span><span class="sxs-lookup"><span data-stu-id="0739b-107">A.</span></span> <span data-ttu-id="0739b-108">Spécifier l'opérateur arithmétique \*</span><span class="sxs-lookup"><span data-stu-id="0739b-108">Specify the \* arithmetic operator</span></span>  
 <span data-ttu-id="0739b-109">Cette requête XPath retourne **\<OrderDetail>** des éléments qui répondent au prédicat spécifié :</span><span class="sxs-lookup"><span data-stu-id="0739b-109">This XPath query returns **\<OrderDetail>** elements that satisfy the predicate specified:</span></span>  
  
```  
/child::OrderDetail[@UnitPrice * @Quantity = 12.350]  
```  
  
 <span data-ttu-id="0739b-110">Dans la requête, `child` est l’axe et `OrderDetail` est le test de nœud (true si **OrderDetail** est un **\<element node>** , car le **\<element>** nœud est le nœud principal de l' `child` axe).</span><span class="sxs-lookup"><span data-stu-id="0739b-110">In the query, `child` is the axis and `OrderDetail` is the node test (TRUE if **OrderDetail** is an **\<element node>**, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="0739b-111">Pour tous les **\<OrderDetail>** nœuds d’élément, le test dans le prédicat est appliqué, et seuls les nœuds qui satisfont à la condition sont retournés.</span><span class="sxs-lookup"><span data-stu-id="0739b-111">For all the **\<OrderDetail>** element nodes, the test in the predicate is applied, and only those nodes that satisfy the condition are returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0739b-112">Dans XPath, les nombres sont des nombres à virgule flottante double précision et la comparaison de nombres à virgule flottante comme dans l'exemple entraîne un arrondi.</span><span class="sxs-lookup"><span data-stu-id="0739b-112">The numbers in XPath are double-precision floating-point numbers, and comparing floating-point numbers as in the example causes rounding.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="0739b-113">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="0739b-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="0739b-114">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="0739b-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="0739b-115">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0739b-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="0739b-116">Créez le modèle suivant (ArithmeticOperatorA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0739b-116">Create the following template (ArithmeticOperatorA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /OrderDetail[@UnitPrice * @OrderQty = 12.350]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="0739b-117">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="0739b-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="0739b-118">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="0739b-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="0739b-119">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="0739b-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="0739b-120">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0739b-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
```  
Here is the partial result set of the template execution:    
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-710" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
   ...  
</ROOT>  
```  
  
  
