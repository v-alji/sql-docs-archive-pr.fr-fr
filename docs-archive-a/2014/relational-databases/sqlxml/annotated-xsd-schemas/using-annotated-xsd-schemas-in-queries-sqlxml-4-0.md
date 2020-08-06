---
title: Utilisation de schémas XSD annotés dans les requêtes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611678"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="3f93b-102">Utilisation de schémas XSD annotés dans les requêtes (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3f93b-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="3f93b-103">Vous pouvez spécifier des requêtes sur un schéma annoté afin de récupérer des données de la base de données ; pour ce faire, spécifiez des requêtes XPath dans un modèle par rapport au schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="3f93b-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="3f93b-104">L' **\<sql:xpath-query>** élément vous permet de spécifier une requête XPath sur la vue XML définie par le schéma annoté.</span><span class="sxs-lookup"><span data-stu-id="3f93b-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="3f93b-105">Le schéma annoté sur lequel la requête XPath doit être exécutée est identifié à l’aide `mapping-schema` de l’attribut de l' **\<sql:xpath-query>** élément.</span><span class="sxs-lookup"><span data-stu-id="3f93b-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="3f93b-106">Les modèles sont des documents XML valides qui contiennent une ou plusieurs requêtes.</span><span class="sxs-lookup"><span data-stu-id="3f93b-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="3f93b-107">Les requêtes XPath et FOR XML retournent un fragment de document.</span><span class="sxs-lookup"><span data-stu-id="3f93b-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="3f93b-108">Les modèles servent de conteneurs pour les fragments de documents ; par conséquent, les modèles offrent un moyen de spécifier un élément unique, de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="3f93b-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="3f93b-109">Les exemples de cette rubrique utilisent des modèles pour spécifier une requête XPath portant sur un schéma annoté afin de récupérer des données dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3f93b-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="3f93b-110">Considérons par exemple ce schéma annoté :</span><span class="sxs-lookup"><span data-stu-id="3f93b-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="3f93b-111">Pour les besoins de l'exemple, ce schéma XSD est stocké dans le fichier nommé Schema2.xml.</span><span class="sxs-lookup"><span data-stu-id="3f93b-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="3f93b-112">Vous pouvez alors exécuter une requête XPath sur le schéma annoté spécifié dans le fichier modèle suivant (Schema2T.xml) :</span><span class="sxs-lookup"><span data-stu-id="3f93b-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="3f93b-113">Vous pouvez ensuite créer et utiliser le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter la requête dans le cadre d'un fichier modèle.</span><span class="sxs-lookup"><span data-stu-id="3f93b-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="3f93b-114">Pour plus d’informations, consultez [schémas XDR Annotés &#40;déconseillés dans SQLXML 4,0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3f93b-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="3f93b-115">Utilisation de schémas de mappage insérés</span><span class="sxs-lookup"><span data-stu-id="3f93b-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="3f93b-116">Un schéma annoté peut être inclus directement dans un modèle ; une requête XPath peut ensuite être spécifiée dans le modèle par rapport au schéma inséré.</span><span class="sxs-lookup"><span data-stu-id="3f93b-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="3f93b-117">Le modèle peut également être un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="3f93b-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="3f93b-118">Un modèle peut inclure plusieurs schémas insérés.</span><span class="sxs-lookup"><span data-stu-id="3f93b-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="3f93b-119">Pour utiliser un schéma inline inclus dans un modèle, spécifiez l’attribut **ID** avec une valeur unique sur l' **\<xsd:schema>** élément, puis utilisez **#idvalue** pour référencer le schéma Inline.</span><span class="sxs-lookup"><span data-stu-id="3f93b-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="3f93b-120">L’attribut **ID** est identique en ce qui concerne le comportement de **SQL : ID** ({urn : schemas-microsoft-com : XML-SQL} ID) utilisé dans les schémas XDR.</span><span class="sxs-lookup"><span data-stu-id="3f93b-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="3f93b-121">Par exemple, le modèle suivant spécifie deux schémas annotés insérés :</span><span class="sxs-lookup"><span data-stu-id="3f93b-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="3f93b-122">Le modèle spécifie également deux requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="3f93b-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="3f93b-123">Chacun des **\<xpath-query>** éléments identifie de façon unique le schéma de mappage en spécifiant l' `mapping-schema` attribut.</span><span class="sxs-lookup"><span data-stu-id="3f93b-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="3f93b-124">Lorsque vous spécifiez un schéma inline dans le modèle, l' `sql:is-mapping-schema` annotation doit également être spécifiée sur l' **\<xsd:schema>** élément.</span><span class="sxs-lookup"><span data-stu-id="3f93b-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="3f93b-125">`sql:is-mapping-schema` accepte une valeur booléenne (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="3f93b-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="3f93b-126">Un schéma Inline avec **SQL : is-mapping-schema = "1"** est traité comme un schéma annoté inline et n’est pas retourné dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="3f93b-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="3f93b-127">L'annotation `sql:is-mapping-schema` appartient à l'espace de noms du modèle `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="3f93b-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="3f93b-128">Pour tester cet exemple, enregistrez le modèle (InlineSchemaTemplate.xml) dans un répertoire local, puis créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) afin d'exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="3f93b-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="3f93b-129">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3f93b-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3f93b-130">En plus de spécifier l' `mapping-schema` attribut sur l' **\<sql:xpath-query>** élément dans un modèle (lorsqu’il existe une requête XPath) ou sur l' **\<updg:sync>** élément dans un mise à jour, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f93b-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="3f93b-131">Spécifiez l' `mapping-schema` attribut sur l' **\<ROOT>** élément (déclaration globale) dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="3f93b-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="3f93b-132">Ce schéma de mappage devient ensuite le schéma par défaut utilisé par l'ensemble des nœuds XPath et nœuds de code de mise à jour (updategram) qui n'ont pas d'annotation `mapping-schema` explicite.</span><span class="sxs-lookup"><span data-stu-id="3f93b-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="3f93b-133">Spécifiez l'attribut `mapping schema` en utilisant l'objet `Command` ADO.</span><span class="sxs-lookup"><span data-stu-id="3f93b-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="3f93b-134">L' `mapping-schema` attribut qui est spécifié sur l' **\<xpath-query>** **\<updg:sync>** élément ou a la priorité la plus élevée ; l' `Command` objet ADO a la priorité la plus faible.</span><span class="sxs-lookup"><span data-stu-id="3f93b-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="3f93b-135">Notez que si vous spécifiez une requête XPath dans un modèle et que vous ne spécifiez pas de schéma de mappage sur lequel la requête XPath est exécutée, la requête XPath est traitée comme une requête de type **dbobject** .</span><span class="sxs-lookup"><span data-stu-id="3f93b-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="3f93b-136">Considérons par exemple le modèle suivant :</span><span class="sxs-lookup"><span data-stu-id="3f93b-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="3f93b-137">Le modèle spécifie une requête XPath mais ne spécifie pas de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="3f93b-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="3f93b-138">Par conséquent, cette requête est traitée comme une requête de type **dbobject** dans laquelle production. ProductPhoto est le nom de la table et @ProductPhotoID = « 100 » est un prédicat qui recherche une photo du produit avec la valeur d’ID 100.</span><span class="sxs-lookup"><span data-stu-id="3f93b-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="3f93b-139">@LargePhotocolonne à partir de laquelle la valeur doit être récupérée.</span><span class="sxs-lookup"><span data-stu-id="3f93b-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
