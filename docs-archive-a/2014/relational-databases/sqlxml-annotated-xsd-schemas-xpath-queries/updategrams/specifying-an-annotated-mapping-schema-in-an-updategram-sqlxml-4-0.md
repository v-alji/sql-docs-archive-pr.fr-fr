---
title: Spécification d’un schéma de mappage annoté dans un mise à jour (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611693"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="eb990-102">Spécification d'un schéma de mappage annoté dans un code de mise à jour (updategram) (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="eb990-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="eb990-103">Cette rubrique explique comment le schéma de mappage (XSD ou XDR) spécifié dans un code de mise à jour est utilisé pour traiter les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="eb990-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="eb990-104">Dans un mise à jour, vous pouvez fournir le nom d’un schéma de mappage annoté à utiliser pour mapper les éléments et les attributs du mise à jour aux tables et aux colonnes dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb990-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eb990-105">Lorsqu'un schéma de mappage est spécifié dans un code de mise à jour, les noms d'élément et d'attribut spécifiés dans le code de mise à jour doivent être mappés aux éléments et aux attributs dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="eb990-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="eb990-106">Pour spécifier un schéma de mappage, vous utilisez l' `mapping-schema` attribut de l' **\<sync>** élément.</span><span class="sxs-lookup"><span data-stu-id="eb990-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="eb990-107">Les exemples suivants présentent deux codes de mise à jour : l'un utilise un schéma de mappage simple et l'autre utilise un schéma plus complexe.</span><span class="sxs-lookup"><span data-stu-id="eb990-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb990-108">Cette documentation suppose une connaissance suffisante des modèles et de la prise en charge des schémas de mappage dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb990-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eb990-109">Pour plus d’informations, consultez [Introduction aux schémas XSD Annotés &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="eb990-110">Pour les applications héritées qui utilisent XDR, consultez [schémas XDR Annotés &#40;dépréciés dans SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="eb990-111">Traitement des types de données</span><span class="sxs-lookup"><span data-stu-id="eb990-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="eb990-112">Si le schéma spécifie `image` le `binary` type de données, ou `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (à l’aide de `sql:datatype` ) et ne spécifie pas de type de données XML, mise à jour suppose que le type de données XML est `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="eb990-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="eb990-113">Si vos données sont du type `bin.base`, vous devez spécifier explicitement le type (`dt:type=bin.base` ou `type="xsd:hexBinary"`).</span><span class="sxs-lookup"><span data-stu-id="eb990-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="eb990-114">Si le schéma spécifie le type de données XSD `dateTime`, `date` ou `time`, vous devez également spécifier le type de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] correspondant en utilisant `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="eb990-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="eb990-115">Lorsque vous gérez des paramètres de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, vous devez spécifier explicitement `sql:datatype="money"` sur le nœud approprié dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="eb990-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="eb990-116">Exemples</span><span class="sxs-lookup"><span data-stu-id="eb990-116">Examples</span></span>  
 <span data-ttu-id="eb990-117">Pour créer des exemples fonctionnels à l’aide des exemples suivants, vous devez respecter les exigences spécifiées dans la [Configuration requise pour l’exécution d’exemples SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="eb990-118">R.</span><span class="sxs-lookup"><span data-stu-id="eb990-118">A.</span></span> <span data-ttu-id="eb990-119">Création d'un code de mise à jour avec un schéma de mappage simple</span><span class="sxs-lookup"><span data-stu-id="eb990-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="eb990-120">Le schéma XSD suivant (SampleSchema.xml) est un schéma de mappage qui mappe l' **\<Customer>** élément à la table Sales. Customer :</span><span class="sxs-lookup"><span data-stu-id="eb990-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eb990-121">Le code de mise à jour suivant insère un enregistrement dans la table Sales.Customer et compte sur le schéma de mappage précédent pour mapper correctement ces données à la table.</span><span class="sxs-lookup"><span data-stu-id="eb990-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="eb990-122">Notez que le mise à jour utilise le même nom d’élément, **\<Customer>** , tel que défini dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="eb990-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="eb990-123">C'est absolument essentiel dans la mesure où le code de mise à jour spécifie un schéma particulier.</span><span class="sxs-lookup"><span data-stu-id="eb990-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="eb990-124">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="eb990-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="eb990-125">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="eb990-126">Enregistrez le fichier sous le nom SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="eb990-127">Copiez le modèle de code de mise à jour ci-dessous et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="eb990-128">Enregistrez le fichier sous le nom SampleUpdategram.xml dans le répertoire où vous avez enregistré le fichier SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="eb990-129">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleUpdateSchema.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="eb990-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="eb990-130">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="eb990-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="eb990-131">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="eb990-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="eb990-132">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="eb990-133">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="eb990-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="eb990-134">B.</span><span class="sxs-lookup"><span data-stu-id="eb990-134">B.</span></span> <span data-ttu-id="eb990-135">Insertion d'un enregistrement à l'aide de la relation parent-enfant spécifiée dans le schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="eb990-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="eb990-136">Les éléments du schéma peuvent être liés.</span><span class="sxs-lookup"><span data-stu-id="eb990-136">Schema elements can be related.</span></span> <span data-ttu-id="eb990-137">L' **\<sql:relationship>** élément spécifie la relation parent-enfant entre les éléments de schéma.</span><span class="sxs-lookup"><span data-stu-id="eb990-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="eb990-138">Ces informations sont utilisées pour mettre à jour les tables correspondantes qui ont une relation clé primaire/clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="eb990-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="eb990-139">Le schéma de mappage (SampleSchema.xml) suivant se compose de deux **\<Order>** éléments **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="eb990-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="eb990-140">Le mise à jour suivant utilise ce schéma XSD pour ajouter un nouvel enregistrement de détail de commande (un **\<OD>** élément dans le **\<after>** bloc) pour la commande 43860.</span><span class="sxs-lookup"><span data-stu-id="eb990-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="eb990-141">L'attribut `mapping-schema` est utilisé pour spécifier le schéma de mappage dans le code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="eb990-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="eb990-142">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="eb990-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="eb990-143">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="eb990-144">Enregistrez le fichier sous le nom SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="eb990-145">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="eb990-146">Enregistrez le fichier sous le nom SampleUpdategram.xml dans le répertoire où vous avez enregistré le fichier SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="eb990-147">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleUpdateSchema.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="eb990-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="eb990-148">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="eb990-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="eb990-149">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="eb990-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="eb990-150">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="eb990-151">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="eb990-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="eb990-152">C.</span><span class="sxs-lookup"><span data-stu-id="eb990-152">C.</span></span> <span data-ttu-id="eb990-153">Insertion d'un enregistrement à l'aide de la relation parent-enfant et de l'annotation inverse spécifiées dans le schéma XSD</span><span class="sxs-lookup"><span data-stu-id="eb990-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="eb990-154">Cet exemple montre comment la logique du code de mise à jour utilise la relation parent-enfant spécifiée dans le schéma XSD pour traiter des mises à jour, et comment l'annotation `inverse` est utilisée.</span><span class="sxs-lookup"><span data-stu-id="eb990-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="eb990-155">Pour plus d’informations sur l' `inverse` annotation, consultez [spécification de l’attribut SQL : inverse sur SQL : Relationship &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="eb990-156">Cet exemple suppose que les tables suivantes se trouvent dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eb990-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="eb990-157">`Cust (CustomerID, CompanyName)`, où `CustomerID` est la clé primaire</span><span class="sxs-lookup"><span data-stu-id="eb990-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="eb990-158">`Ord (OrderID, CustomerID)`, où `CustomerID` est une clé étrangère qui fait référence à la clé primaire `CustomerID` dans la table `Cust`.</span><span class="sxs-lookup"><span data-stu-id="eb990-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="eb990-159">Le code de mise à jour utilise le schéma XSD suivant pour insérer des enregistrements dans les tables Cust et Ord :</span><span class="sxs-lookup"><span data-stu-id="eb990-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="eb990-160">Le schéma XSD de cet exemple possède **\<Customer>** des **\<Order>** éléments et, et spécifie une relation parent-enfant entre les deux éléments.</span><span class="sxs-lookup"><span data-stu-id="eb990-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="eb990-161">Elle identifie **\<Order>** en tant qu’élément parent et **\<Customer>** en tant qu’élément enfant.</span><span class="sxs-lookup"><span data-stu-id="eb990-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="eb990-162">La logique de traitement du code de mise à jour utilise les informations relatives à la relation parent-enfant pour déterminer l'ordre dans lequel les enregistrements sont insérés dans les tables.</span><span class="sxs-lookup"><span data-stu-id="eb990-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="eb990-163">Dans cet exemple, la logique mise à jour tente d’abord d’insérer un enregistrement dans la table Ord (car **\<Order>** est le parent), puis tente d’insérer un enregistrement dans la table Cust (car **\<Customer>** est l’enfant).</span><span class="sxs-lookup"><span data-stu-id="eb990-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="eb990-164">Toutefois, en raison des informations de clé primaire/clé étrangère contenues dans le schéma de la table de base de données, cette opération d'insertion provoque une violation de clé étrangère dans la base de données et échoue.</span><span class="sxs-lookup"><span data-stu-id="eb990-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="eb990-165">Pour indiquer à la logique mise à jour d’inverser la relation parent-enfant au cours de l’opération de mise à jour, l' `inverse` annotation est spécifiée sur l' **\<relationship>** élément.</span><span class="sxs-lookup"><span data-stu-id="eb990-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="eb990-166">En conséquence, les enregistrements sont d'abord ajoutés dans la table Cust, puis dans la table Ord, et l'opération réussit.</span><span class="sxs-lookup"><span data-stu-id="eb990-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="eb990-167">Le code de mise à jour suivant insère une commande (OrderID=2) dans la table Ord et un client (CustomerID='AAAAA') dans la table Cust à l'aide du schéma XSD spécifié :</span><span class="sxs-lookup"><span data-stu-id="eb990-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="eb990-168">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="eb990-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="eb990-169">Créez ces tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="eb990-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="eb990-170">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="eb990-171">Enregistrez le fichier sous le nom SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="eb990-172">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="eb990-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="eb990-173">Enregistrez le fichier sous le nom SampleUpdategram.xml dans le répertoire où vous avez enregistré le fichier SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="eb990-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="eb990-174">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleUpdateSchema.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="eb990-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="eb990-175">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="eb990-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="eb990-176">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="eb990-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="eb990-177">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="eb990-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb990-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb990-178">See Also</span></span>  
 [<span data-ttu-id="eb990-179">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="eb990-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
