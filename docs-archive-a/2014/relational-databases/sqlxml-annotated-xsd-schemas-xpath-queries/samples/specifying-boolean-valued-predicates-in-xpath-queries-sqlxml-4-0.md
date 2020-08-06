---
title: Spécification de prédicats de valeurs booléennes dans des requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- nested predicates
- successive predicates
- predicates [SQLXML]
- top-level predicates
- Boolean-valued predicates
- multiple predicates
ms.assetid: 5f6e7219-6911-4bca-a54b-56b95e0b43dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 56f2f94ec895c5b76382d5103ca9d518b78cc899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600735"
---
# <a name="specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="7805a-102">Spécification de prédicats booléens dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7805a-102">Specifying Boolean-Valued Predicates in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="7805a-103">Les exemples suivants montrent comment les prédicats booléens sont spécifiés dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="7805a-103">The following examples show how Boolean-valued predicates are specified in XPath queries.</span></span> <span data-ttu-id="7805a-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="7805a-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="7805a-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7805a-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="7805a-106">Examples</span></span>  
  
### <a name="a-specify-multiple-predicates"></a><span data-ttu-id="7805a-107">R.</span><span class="sxs-lookup"><span data-stu-id="7805a-107">A.</span></span> <span data-ttu-id="7805a-108">Spécifier plusieurs prédicats</span><span class="sxs-lookup"><span data-stu-id="7805a-108">Specify multiple predicates</span></span>  
 <span data-ttu-id="7805a-109">La requête XPath suivante utilise plusieurs prédicats pour rechercher les informations de commande d'un ID de commande et d'un ID de client donnés :</span><span class="sxs-lookup"><span data-stu-id="7805a-109">The following XPath query uses multiple predicates to find order information for a given order ID and a customer ID:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]/child::Order[attribute::OrderID="Ord-43860"]  
```  
  
 <span data-ttu-id="7805a-110">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et comme l'axe `child` est la valeur par défaut, il peut être absent de la requête :</span><span class="sxs-lookup"><span data-stu-id="7805a-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="7805a-111">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="7805a-111">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="7805a-112">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="7805a-112">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="7805a-113">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-113">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="7805a-114">Créez le modèle suivant (BooleanValuedPredicatesA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-114">Create the following template (BooleanValuedPredicatesA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7805a-115">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="7805a-115">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7805a-116">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="7805a-116">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="7805a-117">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="7805a-117">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7805a-118">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7805a-118">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
     <span data-ttu-id="7805a-119">Voici le résultat :</span><span class="sxs-lookup"><span data-stu-id="7805a-119">Here is the result:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
        <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-761" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-762" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-765" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-768" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-770" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
      </Order>  
    </ROOT>  
    ```  
  
### <a name="b-specify-successive-and-nested-predicates"></a><span data-ttu-id="7805a-120">B.</span><span class="sxs-lookup"><span data-stu-id="7805a-120">B.</span></span> <span data-ttu-id="7805a-121">Spécifier les prédicats consécutifs et imbriqués</span><span class="sxs-lookup"><span data-stu-id="7805a-121">Specify successive and nested predicates</span></span>  
 <span data-ttu-id="7805a-122">La requête suivante affiche l'utilisation de prédicats consécutifs.</span><span class="sxs-lookup"><span data-stu-id="7805a-122">The following query shows using successive predicates.</span></span> <span data-ttu-id="7805a-123">La requête retourne tous les **\<Customer>** éléments enfants du nœud de contexte qui ont à la fois un attribut **SalesPersonID** avec une valeur de 277 et un attribut **TerritoryID** avec une valeur de 3 :</span><span class="sxs-lookup"><span data-stu-id="7805a-123">The query returns all the **\<Customer>** child elements of the context node that have both a **SalesPersonID** attribute with a value of 277 and a **TerritoryID** attribute with a value of 3:</span></span>  
  
```  
/child::Customer[attribute::SalesPersonID="277"][attribute::TerritoryID="3"]  
```  
  
 <span data-ttu-id="7805a-124">La requête retourne les **\<Customer>** éléments qui répondent aux conditions spécifiées dans les prédicats.</span><span class="sxs-lookup"><span data-stu-id="7805a-124">The query returns the **\<Customer>** elements that satisfy both the conditions specified in the predicates.</span></span>  
  
 <span data-ttu-id="7805a-125">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et comme l'axe `child` est la valeur par défaut, il peut être absent de la requête :</span><span class="sxs-lookup"><span data-stu-id="7805a-125">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@SalesPersonID="277"][@TerritoryID="3"]  
```  
  
 <span data-ttu-id="7805a-126">La requête XPath suivante illustre l'utilisation de prédicats imbriqués.</span><span class="sxs-lookup"><span data-stu-id="7805a-126">The following XPath query illustrates the use of nested predicates.</span></span> <span data-ttu-id="7805a-127">La requête retourne tous les **\<Customer>** éléments enfants du nœud de contexte qui incluent des **\<Order>** éléments enfants avec au moins un **\<Order>** élément ayant une valeur d’attribut **SalesPersonID** égale à 2.</span><span class="sxs-lookup"><span data-stu-id="7805a-127">The query returns all the **\<Customer>** child elements of the context node that include **\<Order>** child elements with at least one **\<Order>** element that has a **SalesPersonID** attribute value of 2.</span></span>  
  
```  
/Customer[Order[@SalesPersonID=2]]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="7805a-128">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="7805a-128">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="7805a-129">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="7805a-129">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="7805a-130">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-130">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="7805a-131">Créez le modèle suivant (nestedSuccessive.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-131">Create the following template (nestedSuccessive.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
             /Customer[@SalesPersonID="277"][@TerritoryID="3"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7805a-132">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="7805a-132">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7805a-133">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="7805a-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="7805a-134">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="7805a-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7805a-135">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7805a-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7805a-136">Les éléments suivants sont un résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="7805a-136">The following is a partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="22" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="22" CustomerType="S"   
            Orders="Ord-43874 Ord-44519 Ord-46989 Ord-48013 Ord-49130 Ord-50274 Ord-51807 Ord-57113 Ord-63162 Ord-69495">  
    <Order SalesOrderID="Ord-43874" SalesPersonID="277"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
                   OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    ...  
  </Customer>  
  <Customer CustomerID="39" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="39" CustomerType="S"   
            Orders="Ord-47428 Ord-48367 Ord-49529 Ord-50742 Ord-53591 Ord-59051 Ord-65301 Ord-71912">    <Order SalesOrderID="Ord-47428" SalesPersonID="277"   
           OrderDate="2002-09-01T00:00:00"   
           DueDate="2002-09-13T00:00:00"   
           ShipDate="2002-09-08T00:00:00">  
      <OrderDetail ProductID="Prod-759" UnitPrice="563.7528" OrderQty="2" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-769" UnitPrice="563.7528" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
### <a name="c-specify-a-top-level-predicate"></a><span data-ttu-id="7805a-137">C.</span><span class="sxs-lookup"><span data-stu-id="7805a-137">C.</span></span> <span data-ttu-id="7805a-138">Spécifier un prédicat de niveau supérieur</span><span class="sxs-lookup"><span data-stu-id="7805a-138">Specify a top-level predicate</span></span>  
 <span data-ttu-id="7805a-139">La requête suivante retourne les **\<Customer>** nœuds d’élément enfant du nœud de contexte qui ont des **\<Order>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="7805a-139">The following query returns the **\<Customer>** child element nodes of the context node that have **\<Order>** element children.</span></span> <span data-ttu-id="7805a-140">La requête teste le chemin d'accès de l'emplacement comme prédicat de niveau supérieur :</span><span class="sxs-lookup"><span data-stu-id="7805a-140">The query tests the location path as the top-level predicate:</span></span>  
  
```  
/child::Customer[child::Order]  
```  
  
 <span data-ttu-id="7805a-141">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="7805a-141">The `child` axis is the default.</span></span> <span data-ttu-id="7805a-142">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="7805a-142">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="7805a-143">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="7805a-143">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="7805a-144">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="7805a-144">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="7805a-145">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-145">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="7805a-146">Créez le modèle suivant (TopLevelPredicate.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="7805a-146">Create the following template (TopLevelPredicate.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7805a-147">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="7805a-147">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7805a-148">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="7805a-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="7805a-149">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="7805a-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7805a-150">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7805a-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7805a-151">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="7805a-151">Here is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280" TerritoryID="1" AccountNumber="1" CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    <Order SalesOrderID="Ord-44501" SalesPersonID="280" OrderDate="2001-11-01T00:00:00" DueDate="2001-11-13T00:00:00" ShipDate="2001-11-08T00:00:00">  
      <OrderDetail ProductID="Prod-725" UnitPrice="226.8571" OrderQty="3" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-726" UnitPrice="226.8571" OrderQty="2" UnitPriceDiscount="0" />   
      ...  
    </Order>    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
  
