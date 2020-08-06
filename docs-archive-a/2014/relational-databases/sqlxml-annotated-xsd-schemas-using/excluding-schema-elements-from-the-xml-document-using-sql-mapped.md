---
title: 'Exclusion d’éléments de schéma du document XML obtenu à l’aide de SQL : mapped (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605351"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="2188b-102">Exclusion d'éléments du schéma du document XML obtenu à l'aide de sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2188b-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="2188b-103">Chaque élément et chaque attribut du schéma XSD sont mappés à une vue/table et à une colonne de base de données en raison du mappage par défaut.</span><span class="sxs-lookup"><span data-stu-id="2188b-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="2188b-104">Si vous souhaitez créer un élément dans le schéma XSD qui n'est mappé à aucune table (vue) ou colonne de base de données et qui n'apparaît pas dans le XML, vous pouvez spécifier l'annotation `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="2188b-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="2188b-105">L'annotation `sql:mapped` est particulièrement utile si le schéma ne peut pas être modifié ou si le schéma est utilisé pour valider le code XML d'autres sources et qu'il contient cependant des données qui ne sont pas stockées dans votre base de données.</span><span class="sxs-lookup"><span data-stu-id="2188b-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="2188b-106">L'annotation `sql:mapped` diffère de `sql:is-constant` en ce que les éléments et les attributs non mappés n'apparaissent pas dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="2188b-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="2188b-107">L'annotation `sql:mapped` prend une valeur booléenne (0 = faux, 1 = vrai).</span><span class="sxs-lookup"><span data-stu-id="2188b-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="2188b-108">Les valeurs acceptables sont 0, 1, true et false.</span><span class="sxs-lookup"><span data-stu-id="2188b-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2188b-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="2188b-109">Examples</span></span>  
 <span data-ttu-id="2188b-110">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="2188b-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="2188b-111">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2188b-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="2188b-112">R.</span><span class="sxs-lookup"><span data-stu-id="2188b-112">A.</span></span> <span data-ttu-id="2188b-113">Spécification de l'annotation sql:mapped</span><span class="sxs-lookup"><span data-stu-id="2188b-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="2188b-114">Supposons que vous ayez un schéma XSD provenant d'une autre source.</span><span class="sxs-lookup"><span data-stu-id="2188b-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="2188b-115">Ce schéma XSD se compose d’un **\<Person.Contact>** élément avec les attributs **ContactID**, **FirstName**, **LastName**et **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="2188b-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="2188b-116">Lors du mappage de ce schéma XSD à la table Person. contact de la base de données AdventureWorks, `sql:mapped` est spécifié sur l’attribut **HomeAddress** parce que la table Employees ne stocke pas les adresses personnelles des employés.</span><span class="sxs-lookup"><span data-stu-id="2188b-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="2188b-117">En conséquence, cet attribut n'est pas mappé avec la base de données et n'est pas retourné dans le document XML obtenu lorsqu'une requête XPath est spécifiée sur le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="2188b-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="2188b-118">Le mappage par défaut a lieu pour le reste du schéma.</span><span class="sxs-lookup"><span data-stu-id="2188b-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="2188b-119">L' **\<Person.Contact>** élément est mappé à la table Person. contact, et tous les attributs sont mappés aux colonnes portant le même nom dans la table Person. contact.</span><span class="sxs-lookup"><span data-stu-id="2188b-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="2188b-120">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="2188b-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="2188b-121">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="2188b-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="2188b-122">Enregistrez le fichier sous le nom sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="2188b-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="2188b-123">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="2188b-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="2188b-124">Enregistrez le fichier sous le nom sql-mappedT.xml dans le même répertoire que celui où vous avez enregistré sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="2188b-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2188b-125">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (MySchema.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="2188b-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2188b-126">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="2188b-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="2188b-127">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="2188b-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2188b-128">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2188b-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2188b-129">L'ensemble de résultats est le suivant :</span><span class="sxs-lookup"><span data-stu-id="2188b-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="2188b-130">Notez que ContactID, FirstName et LastName sont présents, mais que HomeAddress ne l'est pas parce que le schéma de mappage a spécifié 0 pour l'attribut `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="2188b-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2188b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2188b-131">See Also</span></span>  
 [<span data-ttu-id="2188b-132">Mappage par défaut d’éléments et d’attributs XSD à des tables et des colonnes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2188b-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
