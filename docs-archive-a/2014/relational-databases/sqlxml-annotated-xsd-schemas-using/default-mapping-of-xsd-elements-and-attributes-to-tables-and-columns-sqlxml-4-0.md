---
title: Mappage par défaut d’éléments et d’attributs XSD à des tables et des colonnes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605350"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="55fe2-102">Mappage par défaut d'éléments et d'attributs XSD à des tables et des colonnes (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="55fe2-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="55fe2-103">Par défaut, un élément de type complexe dans un schéma annoté XSD est mappé à la table (vue) du même nom dans la base de données spécifiée ; par ailleurs, un élément ou attribut de type simple est mappé à la colonne du même nom dans la table.</span><span class="sxs-lookup"><span data-stu-id="55fe2-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="55fe2-104">Exemples</span><span class="sxs-lookup"><span data-stu-id="55fe2-104">Examples</span></span>  
 <span data-ttu-id="55fe2-105">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="55fe2-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="55fe2-106">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="55fe2-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="55fe2-107">R.</span><span class="sxs-lookup"><span data-stu-id="55fe2-107">A.</span></span> <span data-ttu-id="55fe2-108">Spécification du mappage par défaut</span><span class="sxs-lookup"><span data-stu-id="55fe2-108">Specifying default mapping</span></span>  
 <span data-ttu-id="55fe2-109">Dans cet exemple, aucune annotation n'est spécifiée dans le schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="55fe2-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="55fe2-110">L' **\<Person.Contact>** élément est de type complexe et, par conséquent, est mappé par défaut à la table Person. contact de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="55fe2-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="55fe2-111">Tous les attributs (ContactID, FirstName, LastName) de l' **\<Person.Contact>** élément sont de type simple et sont mappés par défaut aux colonnes portant le même nom dans la table Person. contact.</span><span class="sxs-lookup"><span data-stu-id="55fe2-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="55fe2-112">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="55fe2-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="55fe2-113">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="55fe2-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="55fe2-114">Enregistrez le fichier sous le nom MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="55fe2-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="55fe2-115">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="55fe2-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="55fe2-116">Enregistrez le fichier sous le nom MySchemaT.xml dans le même répertoire que celui où vous avez enregistré MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="55fe2-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="55fe2-117">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (MySchema.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="55fe2-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="55fe2-118">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="55fe2-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="55fe2-119">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="55fe2-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="55fe2-120">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="55fe2-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="55fe2-121">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="55fe2-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="55fe2-122">B.</span><span class="sxs-lookup"><span data-stu-id="55fe2-122">B.</span></span> <span data-ttu-id="55fe2-123">Mappage d'un élément XML à une colonne de base de données</span><span class="sxs-lookup"><span data-stu-id="55fe2-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="55fe2-124">Dans cet exemple, le mappage par défaut a lieu également, car aucune annotation n'est utilisée.</span><span class="sxs-lookup"><span data-stu-id="55fe2-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="55fe2-125">L' **\<Person.Contact>** élément est de type complexe et est mappé à la table portant le même nom dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="55fe2-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="55fe2-126">Les éléments **\<FirstName>** et **\<LastName>** et l’attribut **EmployeeID** sont de type simple et, par conséquent, sont mappés aux colonnes portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="55fe2-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="55fe2-127">La seule différence entre ceci et l'exemple précédent réside dans le fait que les éléments sont utilisés pour le mappage des champs FirstName et LastName.</span><span class="sxs-lookup"><span data-stu-id="55fe2-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="55fe2-128">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="55fe2-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="55fe2-129">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="55fe2-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="55fe2-130">Enregistrez le fichier sous le nom MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="55fe2-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="55fe2-131">Créez le modèle suivant (MySchemaElementsT.xml) et enregistrez-le dans le même répertoire que celui utilisé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="55fe2-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="55fe2-132">Le chemin d'accès au répertoire spécifié pour le schéma de mappage est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="55fe2-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="55fe2-133">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="55fe2-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="55fe2-134">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="55fe2-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="55fe2-135">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="55fe2-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="55fe2-136">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="55fe2-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="55fe2-137">C.</span><span class="sxs-lookup"><span data-stu-id="55fe2-137">C.</span></span> <span data-ttu-id="55fe2-138">Mappage d'un élément XML à une colonne de type de données XML</span><span class="sxs-lookup"><span data-stu-id="55fe2-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="55fe2-139">Dans cet exemple, le mappage par défaut a lieu également, car aucune annotation n'est utilisée.</span><span class="sxs-lookup"><span data-stu-id="55fe2-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="55fe2-140">L' **\<Production.ProductModel>** élément est de type complexe et est mappé à la table portant le même nom dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="55fe2-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="55fe2-141">L’attribut **ProductModelID** est de type simple et, par conséquent, est mappé aux colonnes portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="55fe2-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="55fe2-142">La seule différence entre cet exemple et les exemples précédents est que l' **\<Instructions>** élément est mappé à une colonne qui utilise le `xml` type de données à l’aide du `xsd:anyType` type.</span><span class="sxs-lookup"><span data-stu-id="55fe2-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="55fe2-143">Le type de données `xml` a été introduit dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55fe2-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="55fe2-144">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="55fe2-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="55fe2-145">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="55fe2-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="55fe2-146">Enregistrez le fichier sous le nom MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="55fe2-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="55fe2-147">Créez le modèle suivant (MySchemaXmlAnyElementsT.xml) et enregistrez-le dans le même répertoire que celui utilisé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="55fe2-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="55fe2-148">Le chemin d'accès au répertoire spécifié pour le schéma de mappage est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="55fe2-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="55fe2-149">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="55fe2-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="55fe2-150">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="55fe2-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="55fe2-151">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="55fe2-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="55fe2-152">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="55fe2-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="55fe2-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55fe2-153">See Also</span></span>  
 <span data-ttu-id="55fe2-154">[Considérations sur la sécurité des schémas annotés &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="55fe2-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="55fe2-155">[Données XML &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="55fe2-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="55fe2-156">Prise en charge du type de données xml dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="55fe2-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
