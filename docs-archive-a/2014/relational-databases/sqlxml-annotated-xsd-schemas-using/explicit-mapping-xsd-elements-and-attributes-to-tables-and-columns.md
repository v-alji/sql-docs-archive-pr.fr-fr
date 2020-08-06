---
title: Mappage explicite d’éléments et d’attributs XSD à des tables et des colonnes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602002"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="4effb-102">Mappage explicite d'éléments et d'attributs XSD avec les tables et les colonnes (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4effb-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="4effb-103">Lors de l'utilisation d'un schéma XSD pour fournir une vue XML de la base de données relationnelle, les éléments et les attributs du schéma doivent être mappés avec les tables et les colonnes de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4effb-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="4effb-104">Les lignes de la table/vue de la base de données seront mappées avec les éléments du document XML.</span><span class="sxs-lookup"><span data-stu-id="4effb-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="4effb-105">Les valeurs des colonnes de la base de données sont mappées avec les attributs ou les éléments.</span><span class="sxs-lookup"><span data-stu-id="4effb-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="4effb-106">Lorsque les requêtes XPath sont spécifiées par rapport au schéma XSD annoté, les données des éléments et des attributs du schéma sont extraites des tables et des colonnes avec lesquelles elles sont mappées.</span><span class="sxs-lookup"><span data-stu-id="4effb-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="4effb-107">Pour obtenir une valeur unique de la base de données, le mappage spécifié dans le schéma XSD doit posséder les spécifications de relation et de champ.</span><span class="sxs-lookup"><span data-stu-id="4effb-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="4effb-108">Si le nom d'un élément/attribut n'est pas identique à celui de la table/vue ou de la colonne à laquelle il est mappé, les annotations `sql:relation` et `sql:field` sont utilisées pour spécifier le mappage entre un élément ou un attribut d'un document XML et la table (vue) ou colonne d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="4effb-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="4effb-109">sql-relation</span><span class="sxs-lookup"><span data-stu-id="4effb-109">sql-relation</span></span>  
 <span data-ttu-id="4effb-110">L'annotation `sql:relation` est ajoutée pour mapper un nœud XML du schéma XSD avec une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="4effb-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="4effb-111">Le nom d'une table (vue) est spécifiée comme valeur de l'annotation `sql:relation`.</span><span class="sxs-lookup"><span data-stu-id="4effb-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="4effb-112">Lorsque l'annotation `sql:relation` est spécifiée sur un élément, sa portée s'applique à tous les attributs et éléments enfants décrits dans la définition de type complexe de cet élément, fournissant ainsi un raccourci pour l'écriture d'annotations.</span><span class="sxs-lookup"><span data-stu-id="4effb-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="4effb-113">L' `sql:relation` annotation est également utile lorsque les identificateurs qui sont valides dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne sont pas valides dans XML.</span><span class="sxs-lookup"><span data-stu-id="4effb-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="4effb-114">Par exemple, « Détails des commandes » est un nom de table valide dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais non en XML.</span><span class="sxs-lookup"><span data-stu-id="4effb-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="4effb-115">Dans de tels cas, l'annotation `sql:relation` peut être utilisée pour spécifier le mappage, par exemple :</span><span class="sxs-lookup"><span data-stu-id="4effb-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="4effb-116">sql-field</span><span class="sxs-lookup"><span data-stu-id="4effb-116">sql-field</span></span>  
 <span data-ttu-id="4effb-117">L'annotation `sql-field` mappe un élément ou un attribut avec une colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="4effb-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="4effb-118">L'annotation `sql:field` est ajoutée pour mapper un nœud XML du schéma avec une colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="4effb-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="4effb-119">Vous ne pouvez pas spécifier `sql:field` sur un élément de contenu vide.</span><span class="sxs-lookup"><span data-stu-id="4effb-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4effb-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="4effb-120">Examples</span></span>  
 <span data-ttu-id="4effb-121">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="4effb-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="4effb-122">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4effb-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="4effb-123">R.</span><span class="sxs-lookup"><span data-stu-id="4effb-123">A.</span></span> <span data-ttu-id="4effb-124">Spécification des annotations sql:relation et sql:field</span><span class="sxs-lookup"><span data-stu-id="4effb-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="4effb-125">Dans cet exemple, le schéma XSD se compose d’un **\<Contact>** élément de type complexe avec les **\<FName>** **\<LName>** éléments enfants et et l’attribut **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="4effb-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="4effb-126">L' `sql:relation` annotation mappe l' **\<Contact>** élément à la table Person. contact de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4effb-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="4effb-127">L' `sql:field` annotation mappe l' **\<FName>** élément à la colonne FirstName et **\<LName>** à l’élément à la colonne LastName.</span><span class="sxs-lookup"><span data-stu-id="4effb-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="4effb-128">Aucune annotation n’est spécifiée pour l’attribut **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="4effb-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="4effb-129">Il s'ensuit un mappage par défaut de l'attribut avec la colonne du même nom.</span><span class="sxs-lookup"><span data-stu-id="4effb-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4effb-130">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="4effb-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4effb-131">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="4effb-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="4effb-132">Enregistrez le fichier sous le nom MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="4effb-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="4effb-133">Copiez le modèle suivant ci-dessous et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="4effb-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="4effb-134">Enregistrez le fichier sous le nom MySchema-annotatedT.xml dans le même répertoire que celui où vous avez enregistré MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="4effb-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4effb-135">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (MySchema-annotated.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="4effb-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4effb-136">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="4effb-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="4effb-137">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="4effb-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4effb-138">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4effb-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4effb-139">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="4effb-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
