---
title: Spécification d’un espace de noms cible à l’aide de l’attribut targetNamespace (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613379"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="4e015-102">Spécification d'un espace de noms cible à l'aide de l'attribut targetNamespace (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4e015-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="4e015-103">Dans l’écriture de schémas XSD, vous pouvez utiliser l’attribut XSD **targetNamespace** pour spécifier un espace de noms cible.</span><span class="sxs-lookup"><span data-stu-id="4e015-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="4e015-104">Cette rubrique décrit le fonctionnement des attributs XSD **targetNamespace**, **elementFormDefault**et **attributeFormDefault** , comment ils affectent l’instance XML générée et comment les requêtes XPath sont spécifiées avec des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="4e015-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="4e015-105">Vous pouvez utiliser l’attribut **xsd : targetNamespace** pour placer des éléments et des attributs de l’espace de noms par défaut dans un espace de noms différent.</span><span class="sxs-lookup"><span data-stu-id="4e015-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="4e015-106">Vous pouvez également spécifier si les éléments et attributs du schéma déclarés localement doivent apparaître qualifiés par un espace de noms, soit explicitement en utilisant un préfixe, soit implicitement par défaut.</span><span class="sxs-lookup"><span data-stu-id="4e015-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="4e015-107">Vous pouvez utiliser les attributs **elementFormDefault** et **attributeFormDefault** sur l' **\<xsd:schema>** élément pour spécifier globalement la qualification des éléments et attributs locaux, ou vous pouvez utiliser l’attribut **Form** pour spécifier séparément des éléments et des attributs individuels.</span><span class="sxs-lookup"><span data-stu-id="4e015-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4e015-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="4e015-108">Examples</span></span>  
 <span data-ttu-id="4e015-109">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="4e015-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="4e015-110">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4e015-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="4e015-111">R.</span><span class="sxs-lookup"><span data-stu-id="4e015-111">A.</span></span> <span data-ttu-id="4e015-112">Spécification d'un espace de noms cible</span><span class="sxs-lookup"><span data-stu-id="4e015-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="4e015-113">Le schéma XSD suivant spécifie un espace de noms cible à l’aide de l’attribut **xsd : targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="4e015-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="4e015-114">Le schéma définit également les valeurs des attributs **elementFormDefault** et **attributeFormDefault** sur **« Unqualified »** (valeur par défaut pour ces attributs).</span><span class="sxs-lookup"><span data-stu-id="4e015-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="4e015-115">Il s’agit d’une déclaration globale qui affecte tous les éléments locaux ( **\<Order>** dans le schéma) et les attributs (**CustomerID**, **ContactName**et **OrderID** dans le schéma).</span><span class="sxs-lookup"><span data-stu-id="4e015-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4e015-116">Dans le schéma :</span><span class="sxs-lookup"><span data-stu-id="4e015-116">In the schema:</span></span>  
  
-   <span data-ttu-id="4e015-117">Les déclarations de type **CustomerType** et **OrderType** sont globales et, par conséquent, sont incluses dans l’espace de noms cible du schéma.</span><span class="sxs-lookup"><span data-stu-id="4e015-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="4e015-118">Par conséquent, lorsque ces types sont référencés dans la déclaration de l' **\<Customer>** élément et de son **\<Order>** élément enfant, un préfixe est spécifié et est associé à l’espace de noms cible.</span><span class="sxs-lookup"><span data-stu-id="4e015-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="4e015-119">L' **\<Customer>** élément est également inclus dans l’espace de noms cible du schéma, car il s’agit d’un élément global dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="4e015-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="4e015-120">Exécutez la requête XPath suivante sur le schéma :</span><span class="sxs-lookup"><span data-stu-id="4e015-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="4e015-121">La requête XPath génère ce document d'instance (seules quelques commandes sont affichées) :</span><span class="sxs-lookup"><span data-stu-id="4e015-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="4e015-122">Ce document d’instance définit l’espace de noms urn : MyNamespace et associe un préfixe (Y0) à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="4e015-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="4e015-123">Le préfixe est appliqué uniquement à l' **\<Customer>** élément global.</span><span class="sxs-lookup"><span data-stu-id="4e015-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="4e015-124">(L’élément est global parce qu’il est déclaré en tant qu’enfant de **\<xsd:schema>** l’élément dans le schéma.)</span><span class="sxs-lookup"><span data-stu-id="4e015-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="4e015-125">Le préfixe n’est pas appliqué aux éléments et attributs locaux, car la valeur des attributs **elementFormDefault** et **attributeFormDefault** est définie sur **« Unqualified »** dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="4e015-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="4e015-126">Notez que l' **\<Order>** élément est local, car sa déclaration apparaît en tant qu’enfant de l' **\<complexType>** élément qui définit l' **\<CustomerType>** élément.</span><span class="sxs-lookup"><span data-stu-id="4e015-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="4e015-127">De même, les attributs (**CustomerID**, **OrderID**et **ContactName**) sont locaux, et non globaux.</span><span class="sxs-lookup"><span data-stu-id="4e015-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="4e015-128">Pour créer un exemple fonctionnel de ce schéma</span><span class="sxs-lookup"><span data-stu-id="4e015-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="4e015-129">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="4e015-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="4e015-130">Enregistrez le fichier sous le nom targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="4e015-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="4e015-131">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="4e015-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="4e015-132">Enregistrez ce fichier sous le nom targetNameSpaceT.xml dans le répertoire où vous avez enregistré le fichier targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="4e015-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4e015-133">La requête XPath dans le modèle retourne l' **\<Customer>** élément pour le client dont le CustomerID est 1.</span><span class="sxs-lookup"><span data-stu-id="4e015-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="4e015-134">Notez que la requête XPath spécifie le préfixe d'espace de noms pour l'élément dans la requête et pas pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="4e015-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="4e015-135">(Les attributs locaux ne sont pas qualifiés, comme spécifié dans le schéma.)</span><span class="sxs-lookup"><span data-stu-id="4e015-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="4e015-136">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (targetNameSpace.xml) est relatif au répertoire dans lequel le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="4e015-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4e015-137">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="4e015-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="4e015-138">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="4e015-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4e015-139">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4e015-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4e015-140">Si le schéma spécifie des attributs **elementFormDefault** et **attributeFormDefault** avec la valeur **« Qualified »**, le document d’instance aura tous les éléments et attributs locaux qualifiés.</span><span class="sxs-lookup"><span data-stu-id="4e015-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="4e015-141">Vous pouvez modifier le schéma précédent pour inclure ces attributs dans l' **\<xsd:schema>** élément et réexécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="4e015-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="4e015-142">Dans la mesure où les attributs sont désormais également qualifiés dans l'instance, la requête XPath sera modifiée pour inclure le préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="4e015-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="4e015-143">La requête XPath modifiée est présentée ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4e015-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="4e015-144">Le document XML renvoyé est présenté ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4e015-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
