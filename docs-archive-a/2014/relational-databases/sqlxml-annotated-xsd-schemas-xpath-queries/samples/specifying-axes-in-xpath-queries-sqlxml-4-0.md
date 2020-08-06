---
title: Spécification d’axes dans les requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600739"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="28864-102">Spécification d'axes dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="28864-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="28864-103">Les exemples suivants montrent comment spécifier des axes dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="28864-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="28864-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="28864-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="28864-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="28864-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="28864-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="28864-107">R.</span><span class="sxs-lookup"><span data-stu-id="28864-107">A.</span></span> <span data-ttu-id="28864-108">Récupérer les éléments enfants du nœud de contexte</span><span class="sxs-lookup"><span data-stu-id="28864-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="28864-109">La requête XPath suivante sélectionne tous les **\<Contact>** éléments enfants du nœud de contexte :</span><span class="sxs-lookup"><span data-stu-id="28864-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="28864-110">Dans la requête, `child` est l’axe et `Contact` est le test de nœud (true si `Contact` est un **\<element>** nœud, car \<element> est le type de nœud principal associé à l' `child` axe).</span><span class="sxs-lookup"><span data-stu-id="28864-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="28864-111">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="28864-111">The `child` axis is the default.</span></span> <span data-ttu-id="28864-112">Par conséquent, la requête peut être écrite sous la forme :</span><span class="sxs-lookup"><span data-stu-id="28864-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="28864-113">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="28864-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="28864-114">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="28864-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="28864-115">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="28864-116">Créez le modèle ci-dessous (XPathAxesSampleA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="28864-117">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="28864-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="28864-118">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="28864-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="28864-119">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="28864-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="28864-120">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28864-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="28864-121">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="28864-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="28864-122">B.</span><span class="sxs-lookup"><span data-stu-id="28864-122">B.</span></span> <span data-ttu-id="28864-123">Récupérer les petits-enfants du nœud de contexte</span><span class="sxs-lookup"><span data-stu-id="28864-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="28864-124">La requête XPath suivante sélectionne tous les **\<Order>** éléments enfants des **\<Customer>** éléments enfants du nœud de contexte :</span><span class="sxs-lookup"><span data-stu-id="28864-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="28864-125">Dans la requête, `child` est l’axe et `Customer` et `Order` sont les tests de nœud (ces tests de nœuds ont la valeur true si Customer et Order sont des **\<element>** nœuds, car le **\<element>** nœud est le nœud principal de l' `child` axe).</span><span class="sxs-lookup"><span data-stu-id="28864-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="28864-126">Pour chaque nœud correspondant **\<Customer>** à, les nœuds correspondants **\<Orders>** sont ajoutés au résultat.</span><span class="sxs-lookup"><span data-stu-id="28864-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="28864-127">Seul **\<Order>** est retourné dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="28864-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="28864-128">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="28864-128">The `child` axis is the default.</span></span> <span data-ttu-id="28864-129">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="28864-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="28864-130">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="28864-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="28864-131">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="28864-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="28864-132">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="28864-133">Créez le modèle suivant (XPathAxesSampleB.xml) et enregistrez-le dans le répertoire où :</span><span class="sxs-lookup"><span data-stu-id="28864-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="28864-134">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="28864-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="28864-135">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="28864-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="28864-136">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="28864-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="28864-137">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28864-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="28864-138">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="28864-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="28864-139">Si la requête XPath est spécifiée en tant que `Customer/Order/OrderDetail` , à partir de chaque nœud correspondant **\<Customer>** à la requête se déplace vers ses **\<Order>** éléments.</span><span class="sxs-lookup"><span data-stu-id="28864-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="28864-140">Et pour chaque nœud correspondant **\<Order>** à, la requête ajoute les nœuds **\<OrderDetail>** au résultat.</span><span class="sxs-lookup"><span data-stu-id="28864-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="28864-141">Seul **\<OrderDetail>** est retourné dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="28864-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="28864-142">C.</span><span class="sxs-lookup"><span data-stu-id="28864-142">C.</span></span> <span data-ttu-id="28864-143">Utiliser...</span><span class="sxs-lookup"><span data-stu-id="28864-143">Use ..</span></span> <span data-ttu-id="28864-144">pour spécifier l'axe parent</span><span class="sxs-lookup"><span data-stu-id="28864-144">to specify the parent axis</span></span>  
 <span data-ttu-id="28864-145">La requête suivante récupère tous les **\<Order>** éléments avec un élément parent **\<Customer>** dont l’attribut **CustomerID** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="28864-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="28864-146">La requête utilise l' `child` axe dans le prédicat pour rechercher le parent de l' **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="28864-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="28864-147">L'axe `child` est l'axe par défaut.</span><span class="sxs-lookup"><span data-stu-id="28864-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="28864-148">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="28864-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="28864-149">La requête XPath est équivalente à :</span><span class="sxs-lookup"><span data-stu-id="28864-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="28864-150">La requête XPath `/Order[../@CustomerID="1"]` retourne une erreur, car il n’existe aucun parent de **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="28864-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="28864-151">Bien qu’il puisse y avoir des éléments dans le schéma de mappage qui contiennent **\<Order>** , le XPath n’a pas commencé sur l’un d’eux ; par conséquent, **\<Order>** est considéré comme le type d’élément de niveau supérieur dans le document.</span><span class="sxs-lookup"><span data-stu-id="28864-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="28864-152">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="28864-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="28864-153">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="28864-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="28864-154">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="28864-155">Créez le modèle suivant (XPathAxesSampleC.xml) et enregistrez-le dans le répertoire où :</span><span class="sxs-lookup"><span data-stu-id="28864-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="28864-156">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="28864-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="28864-157">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="28864-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="28864-158">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="28864-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="28864-159">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28864-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="28864-160">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="28864-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="28864-161">D.</span><span class="sxs-lookup"><span data-stu-id="28864-161">D.</span></span> <span data-ttu-id="28864-162">Spécifier l'axe attribute</span><span class="sxs-lookup"><span data-stu-id="28864-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="28864-163">La requête XPath suivante sélectionne tous les **\<Customer>** éléments enfants du nœud de contexte avec une valeur d’attribut **CustomerID** de 1 :</span><span class="sxs-lookup"><span data-stu-id="28864-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="28864-164">Dans le prédicat `attribute::CustomerID` , `attribute` est l’axe et `CustomerID` est le test de nœud (si `CustomerID` est un attribut, le test de nœud a la valeur true, car le **\<attribute>** nœud est le nœud principal de l' `attribute` axe).</span><span class="sxs-lookup"><span data-stu-id="28864-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="28864-165">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et l'axe `child` étant l'axe par défaut, il peut être omis dans la requête :</span><span class="sxs-lookup"><span data-stu-id="28864-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="28864-166">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="28864-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="28864-167">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="28864-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="28864-168">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="28864-169">Créez le modèle ci-dessous (XPathAxesSampleD.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="28864-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="28864-170">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="28864-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="28864-171">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="28864-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="28864-172">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="28864-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="28864-173">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="28864-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="28864-174">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="28864-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
