---
title: 'Forçages de type de données et annotation sql : DataType (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605353"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="5c740-102">Forçages de type de données et annotation sql:datatype (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5c740-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="5c740-103">Dans un schéma XSD, l'attribut `xsd:type` spécifie le type de données XSD d'un élément ou d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="5c740-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="5c740-104">Lorsqu'un schéma XSD est utilisé pour extraire des données de la base de données, le type de données spécifié est utilisé pour formater les données.</span><span class="sxs-lookup"><span data-stu-id="5c740-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="5c740-105">Outre la spécification d'un type XSD dans un schéma, vous pouvez également spécifier un type de données Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l'annotation `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="5c740-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="5c740-106">Les attributs `xsd:type` et `sql:datatype` contrôlent le mappage entre les types de données XSD et les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c740-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="5c740-107">Attribut xsd:type</span><span class="sxs-lookup"><span data-stu-id="5c740-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="5c740-108">Vous pouvez utiliser l'attribut `xsd:type` pour spécifier le type de données XML d'un attribut ou d'un élément qui est mappé à une colonne.</span><span class="sxs-lookup"><span data-stu-id="5c740-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="5c740-109">L'attribut `xsd:type` affecte le document qui est retourné à partir du serveur, de même que la requête XPath qui est exécutée.</span><span class="sxs-lookup"><span data-stu-id="5c740-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="5c740-110">Lorsqu'une requête XPath est exécutée sur un schéma de mappage qui contient `xsd:type`, XPath utilise le type de données spécifié lors du traitement de la requête.</span><span class="sxs-lookup"><span data-stu-id="5c740-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="5c740-111">Pour plus d’informations sur la façon dont XPath utilise `xsd:type` , consultez [mappage de types de données XSD à des types de données XPath &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c740-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5c740-112">Dans un document retourné, tous les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont convertis en représentations sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="5c740-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="5c740-113">Certains types de données requièrent des conversions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="5c740-113">Some data types require additional conversions.</span></span> <span data-ttu-id="5c740-114">Le tableau suivant répertorie les conversions qui sont utilisées pour différentes valeurs de `xsd:type`.</span><span class="sxs-lookup"><span data-stu-id="5c740-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="5c740-115">Type de données XSD</span><span class="sxs-lookup"><span data-stu-id="5c740-115">XSD data type</span></span>|<span data-ttu-id="5c740-116">Conversion SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c740-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="5c740-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="5c740-117">Boolean</span></span>|<span data-ttu-id="5c740-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="5c740-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="5c740-119">Date</span><span class="sxs-lookup"><span data-stu-id="5c740-119">Date</span></span>|<span data-ttu-id="5c740-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="5c740-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="5c740-121">Décimal</span><span class="sxs-lookup"><span data-stu-id="5c740-121">decimal</span></span>|<span data-ttu-id="5c740-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="5c740-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="5c740-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="5c740-123">id/idref/idrefs</span></span>|<span data-ttu-id="5c740-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="5c740-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="5c740-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="5c740-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="5c740-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="5c740-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="5c740-127">Temps</span><span class="sxs-lookup"><span data-stu-id="5c740-127">Time</span></span>|<span data-ttu-id="5c740-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="5c740-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="5c740-129">Tous les autres</span><span class="sxs-lookup"><span data-stu-id="5c740-129">All others</span></span>|<span data-ttu-id="5c740-130">Aucune conversion supplémentaire</span><span class="sxs-lookup"><span data-stu-id="5c740-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5c740-131">Certaines des valeurs retournées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent ne pas être compatibles avec les types de données XML spécifiés en utilisant `xsd:type`, soit parce que la conversion n'est pas possible (par exemple, la conversion de "XYZ" en type de données `decimal`), soit parce que la valeur dépasse la plage de ce type de données (par exemple, -100000 converti en type XSD `UnsignedShort`).</span><span class="sxs-lookup"><span data-stu-id="5c740-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="5c740-132">Les conversions de type incompatibles peuvent générer des documents XML non valides ou des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c740-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="5c740-133">Mappage des types de données SQL Server en types de données XSD</span><span class="sxs-lookup"><span data-stu-id="5c740-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="5c740-134">Le tableau ci-dessous montre un mappage évident de types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en types de données XSD.</span><span class="sxs-lookup"><span data-stu-id="5c740-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="5c740-135">Si vous connaissez le type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ce tableau fournit le type XSD correspondant que vous pouvez spécifier dans le schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="5c740-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="5c740-136">Type de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c740-136">SQL Server data type</span></span>|<span data-ttu-id="5c740-137">Type de données XSD</span><span class="sxs-lookup"><span data-stu-id="5c740-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="5c740-138">Annotation sql:datatype</span><span class="sxs-lookup"><span data-stu-id="5c740-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="5c740-139">L'annotation `sql:datatype` permet de spécifier le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; cette annotation doit être spécifiée dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="5c740-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="5c740-140">Vous effectuez un chargement en masse dans une `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colonne à partir d’un `dateTime` type xsd, `date` ou `time` .</span><span class="sxs-lookup"><span data-stu-id="5c740-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="5c740-141">Dans ce cas, vous devez identifier le type de données de colonne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="5c740-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="5c740-142">Cette règle s'applique également aux codes de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5c740-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="5c740-143">Vous effectuez un chargement en masse dans une colonne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type et la valeur xsd est un GUID qui comprend des accolades ({et}).</span><span class="sxs-lookup"><span data-stu-id="5c740-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="5c740-144">Lorsque vous spécifiez `sql:datatype="uniqueidentifier"`, les accolades sont supprimées de la valeur avant son insertion dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="5c740-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="5c740-145">Si `sql:datatype` n'est pas spécifié, la valeur est envoyée avec les accolades et l'insertion ou la mise à jour échoue.</span><span class="sxs-lookup"><span data-stu-id="5c740-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="5c740-146">Le type de données XML `base64Binary` est mappé à différents types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (`binary`, `image` ou `varbinary`).</span><span class="sxs-lookup"><span data-stu-id="5c740-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="5c740-147">Pour mapper le type de données XML `base64Binary` à un type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifique, utilisez l'annotation `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="5c740-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="5c740-148">Cette annotation spécifie le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explicite de la colonne à laquelle l'attribut est mappé.</span><span class="sxs-lookup"><span data-stu-id="5c740-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="5c740-149">Ceci est utile lorsque les données sont stockées dans les bases de données.</span><span class="sxs-lookup"><span data-stu-id="5c740-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="5c740-150">En spécifiant l'annotation `sql:datatype`, vous pouvez identifier le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explicite.</span><span class="sxs-lookup"><span data-stu-id="5c740-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="5c740-151">Il est recommandé en général de spécifier `sql:datatype` dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="5c740-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5c740-152">Exemples</span><span class="sxs-lookup"><span data-stu-id="5c740-152">Examples</span></span>  
 <span data-ttu-id="5c740-153">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="5c740-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="5c740-154">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5c740-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="5c740-155">R.</span><span class="sxs-lookup"><span data-stu-id="5c740-155">A.</span></span> <span data-ttu-id="5c740-156">Spécification de xsd:type</span><span class="sxs-lookup"><span data-stu-id="5c740-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="5c740-157">Cet exemple montre comment un type XSD `date` qui est spécifié en utilisant l'attribut `xsd:type` dans le schéma affecte le document XML résultant.</span><span class="sxs-lookup"><span data-stu-id="5c740-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="5c740-158">Le schéma fournit une vue XML de la table Sales.SalesOrderHeader dans la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5c740-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5c740-159">Dans ce schéma XSD, trois attributs retournent une valeur de date à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c740-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5c740-160">Lorsque le schéma :</span><span class="sxs-lookup"><span data-stu-id="5c740-160">When the schema:</span></span>  
  
-   <span data-ttu-id="5c740-161">Spécifie `xsd:type=date` sur l’attribut **OrderDate** , la partie Date de la valeur retournée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour l’attribut **OrderDate** est affichée.</span><span class="sxs-lookup"><span data-stu-id="5c740-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="5c740-162">Spécifie `xsd:type=time` sur l’attribut **ShipDate** , la partie heure de la valeur retournée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour l’attribut **ShipDate** est affichée.</span><span class="sxs-lookup"><span data-stu-id="5c740-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="5c740-163">Ne spécifie pas `xsd:type` sur l’attribut **DueDate** , la même valeur que celle retournée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est affichée.</span><span class="sxs-lookup"><span data-stu-id="5c740-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="5c740-164">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="5c740-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="5c740-165">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5c740-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="5c740-166">Enregistrez le fichier sous le nom xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="5c740-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="5c740-167">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5c740-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="5c740-168">Enregistrez le fichier sous le nom xsdTypeT.xml dans le répertoire où vous avez enregistré xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="5c740-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="5c740-169">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (xsdType.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="5c740-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="5c740-170">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="5c740-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="5c740-171">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="5c740-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="5c740-172">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5c740-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="5c740-173">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="5c740-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="5c740-174">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="5c740-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="5c740-175">B.</span><span class="sxs-lookup"><span data-stu-id="5c740-175">B.</span></span> <span data-ttu-id="5c740-176">Spécification du type de données SQL à l'aide de sql:datatype</span><span class="sxs-lookup"><span data-stu-id="5c740-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="5c740-177">Pour obtenir un exemple fonctionnel, consultez l’exemple G dans les [exemples de chargement en masse XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5c740-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="5c740-178">Dans cet exemple, une valeur GUID qui inclut "{" et "}" fait l'objet d'un chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="5c740-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="5c740-179">Le schéma dans cet exemple spécifie `sql:datatype` pour identifier le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme `uniqueidentifier`.</span><span class="sxs-lookup"><span data-stu-id="5c740-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="5c740-180">Cet exemple montre quand `sql:datatype` doit être spécifié dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="5c740-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
