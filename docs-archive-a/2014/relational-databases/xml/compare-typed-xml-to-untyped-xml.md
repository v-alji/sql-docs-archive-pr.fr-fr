---
title: Comparer du XML typé et du XML non typé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697616"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="eb11a-102">Comparer du XML typé et du XML non typé</span><span class="sxs-lookup"><span data-stu-id="eb11a-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="eb11a-103">Vous pouvez créer des variables, des paramètres et des colonnes du type `xml`.</span><span class="sxs-lookup"><span data-stu-id="eb11a-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="eb11a-104">Vous pouvez éventuellement associer une collection de schémas XML à une variable, un paramètre ou une colonne de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="eb11a-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="eb11a-105">Dans ce cas, l' `xml` instance de type de données est appelée *typée*.</span><span class="sxs-lookup"><span data-stu-id="eb11a-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="eb11a-106">Dans le cas contraire, l'instance XML est dite *non typée*.</span><span class="sxs-lookup"><span data-stu-id="eb11a-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="eb11a-107">Code XML bien formé et le type de données xml</span><span class="sxs-lookup"><span data-stu-id="eb11a-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="eb11a-108">Le type de données `xml` implémente le type de données `xml` de norme ISO.</span><span class="sxs-lookup"><span data-stu-id="eb11a-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="eb11a-109">Par conséquent, il peut stocker des documents bien formés en conformité avec XML version 1.0, ainsi que des fragments de contenu XML avec des nœuds de texte et un nombre arbitraire d'éléments de premier niveau dans une colonne XML non typée.</span><span class="sxs-lookup"><span data-stu-id="eb11a-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="eb11a-110">Le système vérifie que les données sont bien formées, n'exige pas l'association de schémas XML avec la colonne, puis rejette les données mal formées au sens large.</span><span class="sxs-lookup"><span data-stu-id="eb11a-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="eb11a-111">Il peut aussi s'agir de variables et de paramètres XML non typés.</span><span class="sxs-lookup"><span data-stu-id="eb11a-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="eb11a-112">Schémas XML</span><span class="sxs-lookup"><span data-stu-id="eb11a-112">XML Schemas</span></span>  
 <span data-ttu-id="eb11a-113">Un schéma XML donne les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb11a-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="eb11a-114">**Contraintes de validation.**</span><span class="sxs-lookup"><span data-stu-id="eb11a-114">**Validation constraints.**</span></span> <span data-ttu-id="eb11a-115">Chaque fois qu'une instance typée xml est affectée ou modifiée, SQL Server la valide.</span><span class="sxs-lookup"><span data-stu-id="eb11a-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="eb11a-116">**Informations sur le type de donnes.**</span><span class="sxs-lookup"><span data-stu-id="eb11a-116">**Data type information.**</span></span> <span data-ttu-id="eb11a-117">Les schémas fournissent des informations sur les types des attributs et des éléments de l'instance de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="eb11a-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="eb11a-118">Les informations de type fournissent une sémantique opérationnelle plus précise aux valeurs contenues dans l'instance qu'il n'est possible avec `xml` non typé.</span><span class="sxs-lookup"><span data-stu-id="eb11a-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="eb11a-119">Par exemple, des opérations arithmétiques décimales peuvent être effectuées sur une valeur décimale, mais pas sur une chaîne.</span><span class="sxs-lookup"><span data-stu-id="eb11a-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="eb11a-120">Grâce à cela, le stockage des données typées XML est considérablement plus compact qu'en cas de code XML non typé.</span><span class="sxs-lookup"><span data-stu-id="eb11a-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="eb11a-121">Choix de XML typé ou non typé</span><span class="sxs-lookup"><span data-stu-id="eb11a-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="eb11a-122">Utilisez le type de données `xml` non typé dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="eb11a-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="eb11a-123">Vous n'avez pas de schéma pour vos données XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="eb11a-124">Vous avez des schémas, mais vous ne voulez pas que le serveur valide les données.</span><span class="sxs-lookup"><span data-stu-id="eb11a-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="eb11a-125">C'est notamment le cas lorsqu'une application effectue la validation côté client avant de stocker les données sur le serveur, ou stocke temporairement les données XML déclarées non valides par rapport au schéma, ou utilise des composants de schéma non pris en charge par le serveur.</span><span class="sxs-lookup"><span data-stu-id="eb11a-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="eb11a-126">Utilisez `xml` le type de données typé dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="eb11a-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="eb11a-127">Il existe des schémas pour vos données XML et vous souhaitez que le serveur valide les données XML par rapport aux schémas XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="eb11a-128">Vous voulez profiter de l'optimisation du stockage et des requêtes que permettent les informations de type.</span><span class="sxs-lookup"><span data-stu-id="eb11a-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="eb11a-129">Vous voulez tirer parti des avantages que procurent les informations de type lors de la compilation de vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="eb11a-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="eb11a-130">Des colonnes, paramètres et variables en XML typé peuvent stocker des documents ou du contenu XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="eb11a-131">Toutefois, vous devez utiliser un indicateur pour spécifier qu'il s'agit d'un document ou d'un contenu au moment de la déclaration.</span><span class="sxs-lookup"><span data-stu-id="eb11a-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="eb11a-132">De plus, vous devez fournir la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="eb11a-133">Spécifiez DOCUMENT si chaque instance XML a un seul et unique élément de premier niveau.</span><span class="sxs-lookup"><span data-stu-id="eb11a-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="eb11a-134">Sinon, utilisez CONTENT.</span><span class="sxs-lookup"><span data-stu-id="eb11a-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="eb11a-135">Le compilateur de requête utilise l'indicateur DOCUMENT dans les vérifications de type lors de la compilation de la requête pour déduire les éléments singletons de premier niveau.</span><span class="sxs-lookup"><span data-stu-id="eb11a-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="eb11a-136">Création de XML typé</span><span class="sxs-lookup"><span data-stu-id="eb11a-136">Creating Typed XML</span></span>  
 <span data-ttu-id="eb11a-137">Avant de pouvoir créer des `xml` variables, des paramètres ou des colonnes typés, vous devez d’abord inscrire la collection de schémas XML à l’aide de l' [instruction CREATE XML schema collection &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb11a-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="eb11a-138">Vous pouvez ensuite associer la collection de schémas XML aux variables, paramètres ou colonnes typés `xml`.</span><span class="sxs-lookup"><span data-stu-id="eb11a-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="eb11a-139">Dans les exemples suivants, une convention d'affectation des noms en deux parties est utilisée pour spécifier le nom de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="eb11a-140">La première partie est le nom du schéma et la deuxième est le nom de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="eb11a-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="eb11a-141">Exemple : Association d’une collection de schémas à une variable de type xml</span><span class="sxs-lookup"><span data-stu-id="eb11a-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="eb11a-142">L’exemple suivant crée une `xml` variable de type et lui associe une collection de schémas.</span><span class="sxs-lookup"><span data-stu-id="eb11a-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="eb11a-143">La collection de schémas spécifiée dans l'exemple est déjà importée dans la base de données **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="eb11a-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="eb11a-144">Exemple : Spécification d’un schéma pour une colonne de type xml</span><span class="sxs-lookup"><span data-stu-id="eb11a-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="eb11a-145">L'exemple suivant crée une table avec une colonne de type `xml` et spécifie le schéma correspondant :</span><span class="sxs-lookup"><span data-stu-id="eb11a-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="eb11a-146">Exemple : Passage d’un paramètre de type xml à une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="eb11a-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="eb11a-147">L'exemple suivant passe un paramètre de type `xml` à une procédure stockée et spécifie un schéma pour la variable :</span><span class="sxs-lookup"><span data-stu-id="eb11a-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="eb11a-148">Notez les points suivants à propos de la collection de schémas XML :</span><span class="sxs-lookup"><span data-stu-id="eb11a-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="eb11a-149">Une collection de schémas XML est disponible seulement dans la base de données où elle a été inscrite à l'aide de [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb11a-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="eb11a-150">Si vous transformez une chaîne en données typées `xml`, l'analyse se charge de la validation et de l'attribution du type en fonction des espaces de noms du schéma XML de la collection spécifiée.</span><span class="sxs-lookup"><span data-stu-id="eb11a-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="eb11a-151">Vous pouvez convertir des données de `xml` typé en `xml` non typé, et inversement.</span><span class="sxs-lookup"><span data-stu-id="eb11a-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="eb11a-152">Pour plus d’informations sur d’autres façons de générer du code XML dans SQL Server, consultez [Créer des instances de données XML](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb11a-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="eb11a-153">Une fois le code XML généré, il peut être affecté à une variable de type `xml` ou stocké dans des colonnes de type `xml` en vue d'un traitement supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="eb11a-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="eb11a-154">Dans la hiérarchie des types de données, le type de données `xml` apparaît après `sql_variant` et les types définis par l'utilisateur, mais avant tout autre type intégré.</span><span class="sxs-lookup"><span data-stu-id="eb11a-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="eb11a-155">Exemple : Spécification de facettes pour imposer des contraintes sur une colonne typée xml</span><span class="sxs-lookup"><span data-stu-id="eb11a-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="eb11a-156">Vous pouvez définir des contraintes sur des colonnes typées `xml` de façon à n'autoriser que des éléments uniques de premier niveau pour chaque instance qui y est stockée.</span><span class="sxs-lookup"><span data-stu-id="eb11a-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="eb11a-157">Pour cela, vous devez spécifier la facette facultative `DOCUMENT` lors de la création de la table, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="eb11a-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="eb11a-158">Par défaut, les instances stockées dans la colonne typée `xml` sont considérées comme du contenu XML et non comme des documents XML</span><span class="sxs-lookup"><span data-stu-id="eb11a-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="eb11a-159">de façon à autoriser :</span><span class="sxs-lookup"><span data-stu-id="eb11a-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="eb11a-160">zéro ou plusieurs éléments de premier niveau ;</span><span class="sxs-lookup"><span data-stu-id="eb11a-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="eb11a-161">des nœuds de texte dans les éléments de premier niveau.</span><span class="sxs-lookup"><span data-stu-id="eb11a-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="eb11a-162">Vous pouvez aussi définir ce comportement de manière explicite en ajoutant la facette `CONTENT` , conformément à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="eb11a-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="eb11a-163">Remarquez que vous pouvez spécifier les facettes facultatives DOCUMENT/CONTENT chaque fois que vous définissez le type `xml` (xml typé).</span><span class="sxs-lookup"><span data-stu-id="eb11a-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="eb11a-164">Par exemple, lorsque vous créez une variable typée `xml`, vous pouvez ajouter la facette DOCUMENT/CONTENT, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="eb11a-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="eb11a-165">Définition de type de document (DTD)</span><span class="sxs-lookup"><span data-stu-id="eb11a-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="eb11a-166">Les colonnes, variables et paramètres de type de données `xml` peuvent être typés à l'aide d'un schéma XML, mais pas en utilisant DTD.</span><span class="sxs-lookup"><span data-stu-id="eb11a-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="eb11a-167">Toutefois, une DTD en ligne peut être utilisée à la fois avec du code XML typé et non typé pour fournir des valeurs par défaut et remplacer des références d'entité par leur forme étendue.</span><span class="sxs-lookup"><span data-stu-id="eb11a-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="eb11a-168">Vous pouvez convertir les DTD en documents de schéma XML à l'aide d'outils tiers, puis charger les schémas XML dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eb11a-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="eb11a-169">Mise à niveau de XML typé à partir de SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="eb11a-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="eb11a-170">offre plusieurs extensions de prise en charge du schéma XML, y compris la prise en charge de la validation de type lax, une gestion améliorée des données d'instance **xs:date**, **xs:time** et **xs:dateTime** et la nouvelle prise en charge des types de liste et d'union.</span><span class="sxs-lookup"><span data-stu-id="eb11a-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="eb11a-171">Dans la plupart des cas, les modifications n'affectent pas l'expérience de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="eb11a-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="eb11a-172">Toutefois, si vous avez utilisé une collection de schémas XML dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] qui autorisait les valeurs de type **xs:date**, **xs:time**ou **xs:dateTime** (ou n’importe quel sous-type), les étapes de mise à niveau suivantes ont lieu quand vous joignez votre base de données [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] à une version ultérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="eb11a-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="eb11a-173">Pour chaque colonne XML qui est typée avec une collection de schémas XML contenant des éléments ou des attributs typés comme **xs:anyType**, **xs:anySimpleType**, **xs:date** ou l'un de ses sous-types, **xs:time** ou tout sous-type, ou **xs:dateTime** ou l'un de ses sous-types, ou qui constituent des types d'union ou de liste contenant l'un de ces types, les événements suivants ont lieu :</span><span class="sxs-lookup"><span data-stu-id="eb11a-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="eb11a-174">Tous les index XML sur la colonne seront désactivés.</span><span class="sxs-lookup"><span data-stu-id="eb11a-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="eb11a-175">Toutes les valeurs [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] continueront d'être représentées dans la période Z, car elles ont été normalisées selon cette période.</span><span class="sxs-lookup"><span data-stu-id="eb11a-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="eb11a-176">Toute valeur **xs:date** ou **xs:dateTime** plus petite que le 1er janvier de l’année 1 provoque une erreur d’exécution quand l’index est reconstruit ou que des instructions XQuery ou XML-DML sont exécutées sur le type de données XML contenant cette valeur.</span><span class="sxs-lookup"><span data-stu-id="eb11a-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="eb11a-177">Toute année négative dans les facettes **xs:date** ou **xs:dateTime** ou les valeurs par défaut dans une collection de schémas XML sont mises à jour automatiquement en fonction de la plus petite valeur autorisée par le type **xs:date** ou **xs:dateTime** de base (par exemple, 0001-01-01T00:00:00.0000000Z pour **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="eb11a-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="eb11a-178">Notez que vous pouvez encore utiliser une simple instruction select SQL pour extraire le type de données XML entier, même s'il contient des années négatives.</span><span class="sxs-lookup"><span data-stu-id="eb11a-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="eb11a-179">Il est recommandé de remplacer les années négatives par une année comprise dans la plage nouvellement prise en charge, ou de modifier le type de l'élément ou attribut en **xs:string**.</span><span class="sxs-lookup"><span data-stu-id="eb11a-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb11a-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb11a-180">See Also</span></span>  
 <span data-ttu-id="eb11a-181">[Créer des instances de données XML](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="eb11a-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="eb11a-182">[méthodes de type de données xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="eb11a-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="eb11a-183">[Langage de modification de données XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="eb11a-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="eb11a-184">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb11a-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
