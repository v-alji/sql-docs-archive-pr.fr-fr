---
title: Spécification d’opérateurs relationnels dans des requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600728"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="c8bcc-102">Spécification d'opérateurs de relation dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c8bcc-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="c8bcc-103">Les exemples suivants montrent comment les opérateurs de relation sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="c8bcc-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="c8bcc-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="c8bcc-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c8bcc-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="c8bcc-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="c8bcc-107">R.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-107">A.</span></span> <span data-ttu-id="c8bcc-108">Spécifier un opérateur relationnel</span><span class="sxs-lookup"><span data-stu-id="c8bcc-108">Specify relational operator</span></span>  
 <span data-ttu-id="c8bcc-109">Cette requête XPath retourne les éléments enfants de l' **\<Customer>** élément où la valeur de l’attribut **CustomerID** est « 1 » et où tous les **\<Order>** éléments enfants contiennent un **\<OrderDetail>** enfant avec un attribut **OrderQty** avec une valeur supérieure à 3 :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="c8bcc-110">Le prédicat spécifié dans les crochets filtre les **\<Customer>** éléments.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="c8bcc-111">Seuls les **\<Customer>** éléments ayant au moins un **\<OrderDetail>** petit-enfant avec une valeur d’attribut OrderQty supérieure à 3 sont retournés.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="c8bcc-112">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-112">The `child` axis is the default.</span></span> <span data-ttu-id="c8bcc-113">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="c8bcc-114">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="c8bcc-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="c8bcc-115">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="c8bcc-116">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="c8bcc-117">Créez le modèle suivant (SpecifyRelationalA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c8bcc-118">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c8bcc-119">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="c8bcc-120">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c8bcc-121">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c8bcc-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c8bcc-122">Voici le jeu de résultats de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="c8bcc-123">B.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-123">B.</span></span> <span data-ttu-id="c8bcc-124">Spécifier l'opérateur relationnel dans la requête XPath et utiliser une fonction booléenne pour comparer le résultat</span><span class="sxs-lookup"><span data-stu-id="c8bcc-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="c8bcc-125">Cette requête retourne tous les **\<Order>** éléments enfants du nœud de contexte qui ont une valeur d’attribut **SalesPersonID** inférieure à 270 :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="c8bcc-126">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et comme l'axe `child` est la valeur par défaut, il peut être absent de la requête :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c8bcc-127">Lorsque cette requête est spécifiée dans un modèle, le caractère de < doit être encodé par entité, car le caractère < a une signification particulière dans un document XML.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="c8bcc-128">Dans un modèle, utilisez `<` pour spécifier le caractère <.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="c8bcc-129">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="c8bcc-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="c8bcc-130">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="c8bcc-131">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="c8bcc-132">Créez le modèle suivant (SpecifyRelationalB.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c8bcc-133">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c8bcc-134">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="c8bcc-135">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="c8bcc-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c8bcc-136">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c8bcc-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c8bcc-137">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="c8bcc-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  
