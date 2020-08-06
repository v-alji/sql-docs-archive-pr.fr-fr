---
title: Créer des instances de données XML | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710475"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="61ecd-102">Créer des instances de données XML</span><span class="sxs-lookup"><span data-stu-id="61ecd-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="61ecd-103">Cette rubrique décrit comment générer des instances XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="61ecd-104">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez générer des instances XML des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="61ecd-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="61ecd-105">Conversion du type des instances de chaîne.</span><span class="sxs-lookup"><span data-stu-id="61ecd-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="61ecd-106">Utilisation de l'instruction SELECT avec la clause FOR XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="61ecd-107">Utilisation des affectations de constante.</span><span class="sxs-lookup"><span data-stu-id="61ecd-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="61ecd-108">Utilisation du chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="61ecd-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="61ecd-109">Conversion du type des instances binaires et de chaîne</span><span class="sxs-lookup"><span data-stu-id="61ecd-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="61ecd-110">Vous pouvez analyser n’importe quel type de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] données de chaîne, comme **[n**] [**var**]**char**, **[n] Text**, **varbinary**et **image**, dans le `xml` type de données en castant (cast) ou en convertissant (Convert) la chaîne en `xml` type de données.</span><span class="sxs-lookup"><span data-stu-id="61ecd-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="61ecd-111">Le code XML non typé est vérifié de façon à voir s'il est bien formé.</span><span class="sxs-lookup"><span data-stu-id="61ecd-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="61ecd-112">Si un schéma est associé au `xml` type, la validation est également effectuée.</span><span class="sxs-lookup"><span data-stu-id="61ecd-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="61ecd-113">Pour plus d’informations, consultez [Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="61ecd-114">Les documents XML peuvent être encodés à l'aide de différents encodages (par exemple, UTF-8, UTF-16, Windows 1252).</span><span class="sxs-lookup"><span data-stu-id="61ecd-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="61ecd-115">Les règles définissant le comportement de l'analyseur et l'interaction entre les types de sources binaires et de chaîne avec l'encodage du document XML sont décrites ici.</span><span class="sxs-lookup"><span data-stu-id="61ecd-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="61ecd-116">Dans la mesure où le type **nvarchar** présuppose un encodage Unicode sur deux octets tel que UTF-16 ou UCS-2, l’analyseur XML traite la valeur de type chaîne comme un document ou un fragment XML encodé en Unicode sur 2 octets.</span><span class="sxs-lookup"><span data-stu-id="61ecd-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="61ecd-117">Ceci signifie que le document XML doit être encodé à l'aide d'un encodage Unicode sur deux octets et être compatible avec le type de données source.</span><span class="sxs-lookup"><span data-stu-id="61ecd-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="61ecd-118">Un document XML encodé en UTF-16 peut, mais ce n'est pas obligatoire, présenter un indicateur d'ordre des octets (ou BOM) UTF-16 puisque le contexte du type de source est suffisamment explicite sur le fait qu'il ne peut s'agir que d'un document encodé en Unicode sur deux octets.</span><span class="sxs-lookup"><span data-stu-id="61ecd-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="61ecd-119">Le contenu d’une chaîne de type **varchar** est traité, par l’analyseur XML, comme un fragment ou un document XML encodé sur un octet.</span><span class="sxs-lookup"><span data-stu-id="61ecd-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="61ecd-120">Étant donné que la chaîne source **varchar** est associée à une page de codes, l’analyseur utilise cette page pour l’encodage si aucun code explicite n’est spécifié dans le code XML lui-même. Si une instance XML dispose d’un BOM ou d’une déclaration d’encodage, ces éléments doivent être cohérents par rapport à la page de codes sinon l’analyseur renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="61ecd-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="61ecd-121">Le contenu du type **varbinary** est traité comme un flux CODEPOINT transmis directement à l’analyseur XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="61ecd-122">Le document ou le fragment XML doit donc fournir le BOM ou toute autre information d'encodage incluse.</span><span class="sxs-lookup"><span data-stu-id="61ecd-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="61ecd-123">L'analyseur se contente de consulter le flux pour déterminer l'encodage.</span><span class="sxs-lookup"><span data-stu-id="61ecd-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="61ecd-124">Ceci signifie que le document XML encodé en UTF-16 doit fournir le BOM UTF-16 et qu'une instance sans BOM ni déclaration d'encodage est interprétée en UTF-8.</span><span class="sxs-lookup"><span data-stu-id="61ecd-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="61ecd-125">Si l’encodage du document XML n’est pas connu à l’avance et que, avant la conversion en XML, les données sont transmises comme étant de type chaîne (string) ou binaire (binary) à la place de données XML, il est recommandé de traiter les données en tant que type **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="61ecd-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="61ecd-126">Ainsi, quand les données d’un fichier XML sont lues par le biais de OpenRowset(), ces données à lire doivent être spécifiées comme valeur **varbinary(max)** :</span><span class="sxs-lookup"><span data-stu-id="61ecd-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61ecd-127">Le code XML est représenté en interne dans un format binaire encodé en UTF-16.</span><span class="sxs-lookup"><span data-stu-id="61ecd-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="61ecd-128">L'encodage assuré par l'utilisateur n'est pas conservé, mais est pris en compte dans le processus d'analyse.</span><span class="sxs-lookup"><span data-stu-id="61ecd-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="61ecd-129">Conversion des types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="61ecd-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="61ecd-130">Si un type CLR défini par l'utilisateur présente une sérialisation XML, les instances de ce type peuvent être explicitement converties en un type de données XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="61ecd-131">Pour obtenir des détails sur la sérialisation XML d’un type CLR défini par l’utilisateur, consultez [Sérialisation XML à partir d’objets de base de données CLR](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="61ecd-132">Gestion des espaces blancs dans le code XML typé</span><span class="sxs-lookup"><span data-stu-id="61ecd-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="61ecd-133">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les espaces blancs figurant dans le contenu d'un élément ne sont pas significatifs s'ils se trouvent dans une séquence de données de type caractères composée uniquement d'espaces blancs délimités par des balises (balise de début ou de fin) et qu'ils ne font pas appel au codage d'entité.</span><span class="sxs-lookup"><span data-stu-id="61ecd-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="61ecd-134">(Les sections CDATA sont ignorées). Ce traitement des espaces blancs se différencie de la description des espaces blancs donnée dans la spécification XML 1.0 publiée par le W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="61ecd-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="61ecd-135">En effet, l'analyseur XML de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne reconnaît qu'un nombre limité des sous-ensembles DTD tels qu'ils existent dans XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="61ecd-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="61ecd-136">Pour plus d’informations sur les sous-ensembles DTD pris en charge dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [CAST et CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61ecd-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="61ecd-137">Par défaut, l'analyseur XML rejette les espaces blancs non significatifs lors de la conversion des données chaîne en XML si l'une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="61ecd-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="61ecd-138">`The xml:space` L’attribut n’est pas défini sur un élément ni sur ses éléments ancêtres.</span><span class="sxs-lookup"><span data-stu-id="61ecd-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="61ecd-139">L'attribut `xml:space` en vigueur sur un élément, ou sur l'un de ses éléments ancêtres, a la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="61ecd-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="61ecd-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61ecd-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="61ecd-141">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="61ecd-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="61ecd-142">Vous pouvez toutefois modifier ce comportement.</span><span class="sxs-lookup"><span data-stu-id="61ecd-142">However, you can change this behavior.</span></span> <span data-ttu-id="61ecd-143">Pour conserver les espaces blancs dans une instance du type de données xml, utilisez l’opérateur CONVERT et affectez à son paramètre facultatif *style* la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="61ecd-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="61ecd-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61ecd-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="61ecd-145">Si le paramètre *style* n’est pas utilisé ou s’il a la valeur 0, les espaces non significatifs ne sont pas conservés durant la conversion de l’instance du type de données xml.</span><span class="sxs-lookup"><span data-stu-id="61ecd-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="61ecd-146">Pour plus d’informations sur l’utilisation de l’opérateur CONVERT et de son paramètre *style* durant la conversion de données chaîne en instances du type de données xml, consultez [CAST et CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61ecd-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="61ecd-147">Exemple : conversion d’une valeur chaîne en xml typé et affectation de cette valeur à une colonne</span><span class="sxs-lookup"><span data-stu-id="61ecd-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="61ecd-148">L’exemple suivant convertit une variable chaîne qui contient un fragment XML en `xml` type de données, puis la stocke dans la `xml` colonne de type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="61ecd-149">L’opération d’insertion suivante convertit implicitement une chaîne en `xml` type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="61ecd-150">Vous pouvez convertir explicitement () la chaîne en `xml` type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="61ecd-151">Vous pouvez aussi utiliser la fonction convert(), comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="61ecd-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="61ecd-152">Exemple : conversion d’une valeur chaîne en xml typé et affectation de cette valeur à une variable</span><span class="sxs-lookup"><span data-stu-id="61ecd-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="61ecd-153">Dans l’exemple suivant, une chaîne est convertie en `xml` type et assignée à une variable du `xml` type de données :</span><span class="sxs-lookup"><span data-stu-id="61ecd-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="61ecd-154">Utilisation de l'instruction SELECT avec la clause FOR XML</span><span class="sxs-lookup"><span data-stu-id="61ecd-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="61ecd-155">Vous pouvez utiliser la clause FOR XML dans une instruction SELECT pour renvoyer les résultats sous forme de code XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="61ecd-156">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61ecd-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="61ecd-157">L’instruction SELECT retourne un fragment XML textuel qui est ensuite analysé au cours de l’assignation à la `xml` variable de type de données.</span><span class="sxs-lookup"><span data-stu-id="61ecd-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="61ecd-158">Vous pouvez également utiliser la [directive type](type-directive-in-for-xml-queries.md) dans la clause FOR XML qui retourne directement un résultat de requête for XML en tant que `xml` type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="61ecd-159">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="61ecd-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="61ecd-160">Dans l’exemple suivant, le `xml` résultat typé d’une requête for XML est inséré dans une `xml` colonne de type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="61ecd-161">Pour plus d’informations sur FOR XML, consultez [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61ecd-162">renvoie des instances du type de données `xml` au client comme résultat des différentes constructions serveur, telles que les requêtes FOR XML qui utilisent la directive TYPE, ou dans lesquelles le type de données `xml` est utilisé pour renvoyer du code XML d'après des colonnes, des variables et des paramètres de sortie SQL.</span><span class="sxs-lookup"><span data-stu-id="61ecd-162">returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="61ecd-163">Dans un code d'application cliente, le fournisseur ADO.NET demande que les informations de type de données `xml` soient transmises en code binaire depuis le serveur.</span><span class="sxs-lookup"><span data-stu-id="61ecd-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="61ecd-164">Toutefois, si vous utilisez FOR XML sans la directive TYPE, les données XML reviennent en tant que type chaîne.</span><span class="sxs-lookup"><span data-stu-id="61ecd-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="61ecd-165">Dans tous les cas, le fournisseur client est toujours en mesure de gérer toute forme XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="61ecd-166">Utilisation des affectations de constante</span><span class="sxs-lookup"><span data-stu-id="61ecd-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="61ecd-167">Une constante de chaîne peut être utilisée lorsqu’une instance du `xml` type de données est attendue.</span><span class="sxs-lookup"><span data-stu-id="61ecd-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="61ecd-168">Cela revient à convertir implicitement (via CAST) une chaîne en XML.</span><span class="sxs-lookup"><span data-stu-id="61ecd-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="61ecd-169">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="61ecd-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="61ecd-170">L’exemple précédent convertit implicitement la chaîne en `xml` type de données et l’assigne à une `xml` variable de type.</span><span class="sxs-lookup"><span data-stu-id="61ecd-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="61ecd-171">L’exemple suivant insère une chaîne constante dans une `xml` colonne de type :</span><span class="sxs-lookup"><span data-stu-id="61ecd-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="61ecd-172">En cas de XML typé, la conformité du code XML est validée par rapport au schéma spécifié.</span><span class="sxs-lookup"><span data-stu-id="61ecd-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="61ecd-173">Pour plus d’informations, consultez [Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="61ecd-174">Utilisation du chargement en masse</span><span class="sxs-lookup"><span data-stu-id="61ecd-174">Using Bulk Load</span></span>  
 <span data-ttu-id="61ecd-175">La fonctionnalité améliorée [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) vous permet de charger en masse des documents XML dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="61ecd-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="61ecd-176">Vous pouvez charger en masse des instances XML à partir de fichiers dans les `xml` colonnes de type de la base de données.</span><span class="sxs-lookup"><span data-stu-id="61ecd-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="61ecd-177">Pour obtenir des exemples fonctionnels, consultez [ Exemples d’importation et d’exportation en bloc de documents XML &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="61ecd-178">Pour plus d’informations sur le chargement de documents XML, consultez [Charger des données XML](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="61ecd-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61ecd-179">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="61ecd-179">In This Section</span></span>  
  
|<span data-ttu-id="61ecd-180">Rubrique</span><span class="sxs-lookup"><span data-stu-id="61ecd-180">Topic</span></span>|<span data-ttu-id="61ecd-181">Description</span><span class="sxs-lookup"><span data-stu-id="61ecd-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="61ecd-182">Récupérer et interroger des données XML</span><span class="sxs-lookup"><span data-stu-id="61ecd-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="61ecd-183">Décrit les parties des instances XML qui ne sont pas conservées lorsqu'elles sont stockées dans des bases de données.</span><span class="sxs-lookup"><span data-stu-id="61ecd-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61ecd-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61ecd-184">See Also</span></span>  
 <span data-ttu-id="61ecd-185">[Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="61ecd-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="61ecd-186">[méthodes de type de données xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="61ecd-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="61ecd-187">[Langage de modification de données XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="61ecd-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="61ecd-188">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="61ecd-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
