---
title: 'Spécification de relations à l’aide de SQL : Relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605348"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="757b4-102">Spécification de relations à l'aide de sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="757b4-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="757b4-103">Les éléments d'un document XML peuvent être liés.</span><span class="sxs-lookup"><span data-stu-id="757b4-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="757b4-104">Les éléments peuvent être imbriqués hiérarchiquement ; en outre, des relations ID, IDREF ou IDREFS peuvent être spécifiées entre les éléments.</span><span class="sxs-lookup"><span data-stu-id="757b4-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="757b4-105">Par exemple, dans un schéma XSD, un **\<Customer>** élément contient des **\<Order>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="757b4-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="757b4-106">Lorsque le schéma est mappé à la base de données AdventureWorks, l’élément est mappé **\<Customer>** à la table Sales. Customer et l’élément est mappé **\<Order>** à la table Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="757b4-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="757b4-107">Ces tables sous-jacentes, Sales.Customer et Sales.SalesOrderHeader, sont liées, car les clients passent des commandes.</span><span class="sxs-lookup"><span data-stu-id="757b4-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="757b4-108">CustomerID dans la table Sales.SalesOrderHeader est une clé étrangère qui fait référence à la clé primaire CustomerID dans la table Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="757b4-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="757b4-109">Vous pouvez établir ces relations entre les éléments de schéma de mappage à l’aide de l' `sql:relationship` annotation.</span><span class="sxs-lookup"><span data-stu-id="757b4-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="757b4-110">Dans le schéma XSD annoté, l'annotation `sql:relationship` est utilisée pour imbriquer hiérarchiquement les éléments du schéma, en fonction des relations de clé primaire et de clé étrangère qui existent entre les tables sous-jacentes auxquelles les éléments sont mappés.</span><span class="sxs-lookup"><span data-stu-id="757b4-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="757b4-111">En spécifiant l'annotation `sql:relationship`, vous devez identifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="757b4-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="757b4-112">La table parente (Sales.Customer) et la table enfant (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="757b4-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="757b4-113">La ou les colonnes qui composent la relation entre la table parente et la table enfant.</span><span class="sxs-lookup"><span data-stu-id="757b4-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="757b4-114">Par exemple, la colonne CustomerID, qui apparaît à la fois dans la table parente et la table enfant.</span><span class="sxs-lookup"><span data-stu-id="757b4-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="757b4-115">Ces informations sont utilisées pour générer la hiérarchie appropriée.</span><span class="sxs-lookup"><span data-stu-id="757b4-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="757b4-116">Pour fournir les noms de tables et les informations de jointure nécessaires, les attributs suivants sont spécifiés dans l'annotation `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="757b4-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="757b4-117">Ces attributs sont valides uniquement avec l' **\<sql:relationship>** élément :</span><span class="sxs-lookup"><span data-stu-id="757b4-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="757b4-118">**Nom**</span><span class="sxs-lookup"><span data-stu-id="757b4-118">**Name**</span></span>  
 <span data-ttu-id="757b4-119">Spécifie le nom unique de la relation.</span><span class="sxs-lookup"><span data-stu-id="757b4-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="757b4-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="757b4-120">**Parent**</span></span>  
 <span data-ttu-id="757b4-121">Spécifie la relation parente (table).</span><span class="sxs-lookup"><span data-stu-id="757b4-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="757b4-122">Il s'agit d'un attribut facultatif ; si l'attribut n'est pas spécifié, le nom de la table parente est obtenu à partir des informations contenues dans la hiérarchie enfant du document.</span><span class="sxs-lookup"><span data-stu-id="757b4-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="757b4-123">Si le schéma spécifie deux hiérarchies parent-enfant qui utilisent le même **\<sql:relationship>** , mais des éléments parents différents, vous ne spécifiez pas l’attribut parent dans **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="757b4-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="757b4-124">Ces informations sont obtenues à partir de la hiérarchie du schéma.</span><span class="sxs-lookup"><span data-stu-id="757b4-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="757b4-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="757b4-125">**parent-key**</span></span>  
 <span data-ttu-id="757b4-126">Spécifie la clé parente du parent.</span><span class="sxs-lookup"><span data-stu-id="757b4-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="757b4-127">Si la clé parente est composée de plusieurs colonnes, les valeurs sont spécifiées en étant séparées par un espace.</span><span class="sxs-lookup"><span data-stu-id="757b4-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="757b4-128">Il existe un mappage de position entre les valeurs spécifiées pour la clé multicolonne et pour la clé enfant correspondante.</span><span class="sxs-lookup"><span data-stu-id="757b4-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="757b4-129">**Division**</span><span class="sxs-lookup"><span data-stu-id="757b4-129">**Child**</span></span>  
 <span data-ttu-id="757b4-130">Spécifie la relation enfant (table).</span><span class="sxs-lookup"><span data-stu-id="757b4-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="757b4-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="757b4-131">**child-key**</span></span>  
 <span data-ttu-id="757b4-132">Spécifie la clé enfant de l'enfant faisant référence à la clé parente du parent.</span><span class="sxs-lookup"><span data-stu-id="757b4-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="757b4-133">Si la clé enfant est composée de plusieurs attributs (colonnes), les valeurs de child-key sont spécifiées en étant séparées par un espace.</span><span class="sxs-lookup"><span data-stu-id="757b4-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="757b4-134">Il existe un mappage de position entre les valeurs spécifiées pour la clé multicolonne et pour la clé parente correspondante.</span><span class="sxs-lookup"><span data-stu-id="757b4-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="757b4-135">**Inverse**</span><span class="sxs-lookup"><span data-stu-id="757b4-135">**Inverse**</span></span>  
 <span data-ttu-id="757b4-136">Cet attribut spécifié sur **\<sql:relationship>** est utilisé par codes.</span><span class="sxs-lookup"><span data-stu-id="757b4-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="757b4-137">Pour plus d’informations, consultez [spécification de l’attribut SQL : inverse sur SQL : Relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="757b4-138">L' `sql:key-fields` annotation doit être spécifiée dans un élément qui contient un élément enfant, qui a un **\<sql:relationship>** défini entre l’élément et l’enfant, et qui ne fournit pas la clé primaire de la table spécifiée dans l’élément parent.</span><span class="sxs-lookup"><span data-stu-id="757b4-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="757b4-139">Même si le schéma ne spécifie pas **\<sql:relationship>** , vous devez spécifier `sql:key-fields` pour produire la hiérarchie appropriée.</span><span class="sxs-lookup"><span data-stu-id="757b4-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="757b4-140">Pour plus d’informations, consultez [identification des colonnes clés à l’aide de SQL : key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="757b4-141">Pour produire une imbrication correcte dans le résultat, il est recommandé `sql:key-fields` de spécifier dans tous les schémas.</span><span class="sxs-lookup"><span data-stu-id="757b4-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="757b4-142">Exemples</span><span class="sxs-lookup"><span data-stu-id="757b4-142">Examples</span></span>  
 <span data-ttu-id="757b4-143">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="757b4-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="757b4-144">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="757b4-145">R.</span><span class="sxs-lookup"><span data-stu-id="757b4-145">A.</span></span> <span data-ttu-id="757b4-146">Spécification de l'annotation sql:relationship sur un élément</span><span class="sxs-lookup"><span data-stu-id="757b4-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="757b4-147">Le schéma XSD annoté suivant comprend les **\<Customer>** **\<Order>** éléments et.</span><span class="sxs-lookup"><span data-stu-id="757b4-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="757b4-148">L' **\<Order>** élément est un élément enfant de l' **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="757b4-149">Dans le schéma, l' `sql:relationship` annotation est spécifiée sur l' **\<Order>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="757b4-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="757b4-150">La relation elle-même est définie dans l' **\<xsd:appinfo>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="757b4-151">L' **\<relationship>** élément identifie CustomerID dans la table Sales. SalesOrderHeader comme une clé étrangère qui fait référence à la clé primaire CustomerID dans la table Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="757b4-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="757b4-152">Par conséquent, les commandes appartenant à un client apparaissent en tant qu’élément enfant de cet **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="757b4-153">Le schéma précédent utilise une relation nommée.</span><span class="sxs-lookup"><span data-stu-id="757b4-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="757b4-154">Vous pouvez également spécifier une relation sans nom.</span><span class="sxs-lookup"><span data-stu-id="757b4-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="757b4-155">Les résultats sont identiques.</span><span class="sxs-lookup"><span data-stu-id="757b4-155">The results are same.</span></span>  
  
 <span data-ttu-id="757b4-156">Voici le schéma modifié dans lequel une relation sans nom est spécifiée :</span><span class="sxs-lookup"><span data-stu-id="757b4-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="757b4-157">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="757b4-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="757b4-158">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="757b4-159">Enregistrez le fichier sous le nom sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="757b4-160">Copiez le modèle suivant ci-dessous et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="757b4-161">Enregistrez le fichier sous le nom sql-relationshipT.xml dans le répertoire où vous avez enregistré le fichier sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="757b4-162">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (sql-relationship.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="757b4-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="757b4-163">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="757b4-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="757b4-164">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="757b4-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="757b4-165">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="757b4-166">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="757b4-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="757b4-167">B.</span><span class="sxs-lookup"><span data-stu-id="757b4-167">B.</span></span> <span data-ttu-id="757b4-168">Spécification d'une chaîne de relation</span><span class="sxs-lookup"><span data-stu-id="757b4-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="757b4-169">Pour cet exemple, vous souhaitez obtenir le document XML suivant à l'aide des données provenant de la base de données AdventureWorks :</span><span class="sxs-lookup"><span data-stu-id="757b4-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="757b4-170">Pour chaque commande de la table Sales. SalesOrderHeader, le document XML comporte un **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="757b4-171">Chaque **\<Order>** élément a une liste d' **\<Product>** éléments enfants, un pour chaque produit demandé dans la commande.</span><span class="sxs-lookup"><span data-stu-id="757b4-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="757b4-172">Pour spécifier un schéma XSD qui produit cette hiérarchie, vous devez indiquer deux relations : OrderOD et ODProduct.</span><span class="sxs-lookup"><span data-stu-id="757b4-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="757b4-173">La relation OrderOD spécifie la relation parent-enfant entre les tables Sales.SalesOrderHeader et Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="757b4-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="757b4-174">La relation ODProduct spécifie la relation entre les tables Sales.SalesOrderDetail et Production.Product.</span><span class="sxs-lookup"><span data-stu-id="757b4-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="757b4-175">Dans le schéma suivant, l' `msdata:relationship` annotation sur l' **\<Product>** élément spécifie deux valeurs : OrderOD et ODProduct.</span><span class="sxs-lookup"><span data-stu-id="757b4-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="757b4-176">L'ordre dans lequel ces valeurs sont spécifiées est important.</span><span class="sxs-lookup"><span data-stu-id="757b4-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="757b4-177">Au lieu de spécifier une relation nommée, vous pouvez spécifier une relation anonyme.</span><span class="sxs-lookup"><span data-stu-id="757b4-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="757b4-178">Dans ce cas, le contenu entier de **\<annotation>** ... **\</annotation>** , qui décrit les deux relations, apparaît comme un élément enfant de **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="757b4-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="757b4-179">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="757b4-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="757b4-180">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="757b4-181">Enregistrez le fichier sous le nom relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="757b4-182">Copiez le modèle suivant ci-dessous et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="757b4-183">Enregistrez le fichier sous le nom relationshipChainT.xml dans le répertoire où vous avez enregistré le fichier relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="757b4-184">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (relationshipChain.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="757b4-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="757b4-185">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="757b4-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="757b4-186">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="757b4-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="757b4-187">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="757b4-188">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="757b4-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="757b4-189">C.</span><span class="sxs-lookup"><span data-stu-id="757b4-189">C.</span></span> <span data-ttu-id="757b4-190">Spécification de l'annotation de relation sur un attribut</span><span class="sxs-lookup"><span data-stu-id="757b4-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="757b4-191">Dans cet exemple, le schéma comprend un \<Customer> élément avec un \<CustomerID> élément enfant et un attribut attribut OrderIDList de type IDREFS.</span><span class="sxs-lookup"><span data-stu-id="757b4-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="757b4-192">L' \<Customer> élément est mappé à la table Sales. Customer dans la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="757b4-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="757b4-193">Par défaut, l’étendue de ce mappage s’applique à tous les éléments ou attributs enfants `sql:relation` , sauf si est spécifié sur l’élément ou l’attribut enfant, auquel cas la relation de clé primaire/clé étrangère appropriée doit être définie à l’aide de l' \<relationship> élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="757b4-194">En outre, l'élément ou l'attribut enfant, qui spécifie la table distincte à l'aide de l'annotation `relation`, doit également spécifier l'annotation `relationship`.</span><span class="sxs-lookup"><span data-stu-id="757b4-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="757b4-195">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="757b4-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="757b4-196">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="757b4-197">Enregistrez le fichier sous le nom relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="757b4-198">Copiez le modèle suivant et collez-le dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="757b4-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="757b4-199">Enregistrez le fichier sous le nom relationship-on-attributeT.xml dans le répertoire où vous avez enregistré le fichier relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="757b4-200">La requête dans le modèle sélectionne un client dont le CustomerID est 1.</span><span class="sxs-lookup"><span data-stu-id="757b4-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="757b4-201">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (relationship-on-attribute.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="757b4-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="757b4-202">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="757b4-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="757b4-203">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="757b4-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="757b4-204">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="757b4-205">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="757b4-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="757b4-206">D.</span><span class="sxs-lookup"><span data-stu-id="757b4-206">D.</span></span> <span data-ttu-id="757b4-207">Spécification de sql:relationship sur plusieurs éléments</span><span class="sxs-lookup"><span data-stu-id="757b4-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="757b4-208">Dans cet exemple, le schéma XSD annoté contient les **\<Customer>** éléments, **\<Order>** et **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="757b4-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="757b4-209">L' **\<Order>** élément est un élément enfant de l' **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="757b4-210">**\<sql:relationship>** est spécifié sur l' **\<Order>** élément enfant ; par conséquent, les commandes appartenant à un client apparaissent en tant qu’éléments enfants de **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="757b4-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="757b4-211">L' **\<Order>** élément comprend l' **\<OrderDetail>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="757b4-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="757b4-212">**\<sql:relationship>** est spécifié sur **\<OrderDetail>** l’élément enfant, donc les détails de la commande qui se rapportent à une commande apparaissent en tant qu’éléments enfants de cet **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="757b4-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
        parent="Sales.Customer"  
        parent-key="CustomerID"  
        child="Sales.SalesOrderHeader"  
        child-key="CustomerID" />  
  
    <sql:relationship name="OrderOrderDetail"  
        parent="Sales.SalesOrderHeader"  
        parent-key="SalesOrderID"  
        child="Sales.SalesOrderDetail"  
        child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
              sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                             sql:relationship="OrderOrderDetail"   
                             maxOccurs="unbounded" >  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                    <xsd:attribute name="ProductID" type="xsd:string" />  
                    <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="757b4-213">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="757b4-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="757b4-214">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="757b4-215">Enregistrez le fichier sous le nom relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="757b4-216">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="757b4-217">Enregistrez le fichier sous le nom relationship-multiple-elementsT.xml dans le répertoire où vous avez enregistré le fichier relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="757b4-218">La requête du modèle retourne des informations de commande pour un client dont CustomerID a la valeur 1 et SalesOrderID la valeur 43860.</span><span class="sxs-lookup"><span data-stu-id="757b4-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="757b4-219">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (relationship-multiple-elements.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="757b4-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="757b4-220">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="757b4-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="757b4-221">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="757b4-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="757b4-222">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="757b4-223">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="757b4-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="757b4-224">E.</span><span class="sxs-lookup"><span data-stu-id="757b4-224">E.</span></span> <span data-ttu-id="757b4-225">Spécification de \<sql:relationship> sans l’attribut parent</span><span class="sxs-lookup"><span data-stu-id="757b4-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="757b4-226">Cet exemple illustre la spécification de l' **\<sql:relationship>** attribut sans l’attribut **parent** .</span><span class="sxs-lookup"><span data-stu-id="757b4-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="757b4-227">Prenons par exemple les tables d'employés suivantes :</span><span class="sxs-lookup"><span data-stu-id="757b4-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="757b4-228">La vue XML suivante a les **\<Emp1>** **\<Emp2>** éléments et qui sont mappés aux tables Sales. Emp1 et Sales. EMP2 :</span><span class="sxs-lookup"><span data-stu-id="757b4-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="757b4-229">Dans le schéma, l' **\<Emp1>** élément et l' **\<Emp2>** élément sont de type `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="757b4-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="757b4-230">Le type `EmpType` décrit un **\<Order>** élément enfant et le correspondant **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="757b4-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="757b4-231">Dans ce cas, il n’existe aucun parent unique pouvant être identifié dans à **\<sql:relationship>** l’aide de l’attribut **parent** .</span><span class="sxs-lookup"><span data-stu-id="757b4-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="757b4-232">Dans ce cas, vous ne spécifiez pas l’attribut **parent** dans **\<sql:relationship>** ; les informations d’attribut **parent** sont obtenues à partir de la hiérarchie dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="757b4-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="757b4-233">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="757b4-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="757b4-234">Créez ces tables dans la base de données AdventureWorks :</span><span class="sxs-lookup"><span data-stu-id="757b4-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="757b4-235">Ajoutez ces exemples de données dans les tables :</span><span class="sxs-lookup"><span data-stu-id="757b4-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="757b4-236">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="757b4-237">Enregistrez le fichier sous le nom relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="757b4-238">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="757b4-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="757b4-239">Enregistrez le fichier sous le nom relationship-noparentT.xml dans le répertoire où vous avez enregistré le fichier relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="757b4-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="757b4-240">La requête dans le modèle sélectionne tous les \<Emp1> éléments (par conséquent, le parent est Emp1).</span><span class="sxs-lookup"><span data-stu-id="757b4-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="757b4-241">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (relationship-noparent.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="757b4-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="757b4-242">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="757b4-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="757b4-243">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="757b4-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="757b4-244">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="757b4-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="757b4-245">Voici un jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="757b4-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
