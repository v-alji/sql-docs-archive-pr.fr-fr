---
title: Instructions et limitations du chargement en masse XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611707"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="771c2-102">Règles et limitations du chargement en masse XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="771c2-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="771c2-103">Lorsque vous utilisez le chargement en masse XML, vous devez connaître les indications et les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="771c2-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="771c2-104">Les schémas insérés ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="771c2-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="771c2-105">Si vous possédez un schéma inséré dans le document XML source, le chargement en masse XML ignore ce schéma.</span><span class="sxs-lookup"><span data-stu-id="771c2-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="771c2-106">Vous spécifiez le schéma de mappage pour le chargement en masse XML externe aux données XML.</span><span class="sxs-lookup"><span data-stu-id="771c2-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="771c2-107">Vous ne pouvez pas spécifier le schéma de mappage au niveau d’un nœud à l’aide de l’attribut **xmlns = "x :Schema"** .</span><span class="sxs-lookup"><span data-stu-id="771c2-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="771c2-108">Le système vérifie qu'un document XML est correct, mais ne le valide pas.</span><span class="sxs-lookup"><span data-stu-id="771c2-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="771c2-109">Le chargement en masse XML vérifie le document XML pour déterminer s’il est bien formé, c’est-à-dire s’il est conforme aux exigences de syntaxe de la recommandation XML 1,0 de World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="771c2-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="771c2-110">Si le document n'est pas correct, le chargement en masse XML annule le traitement et retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="771c2-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="771c2-111">La seule exception à ceci est lorsque le document est un fragment (par exemple, le document n'a aucun élément racine unique), auquel cas le chargement en masse XML chargera le document.</span><span class="sxs-lookup"><span data-stu-id="771c2-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="771c2-112">Le chargement en masse XML ne valide pas le document par rapport à tout schéma de données XML ou DTD qui est défini ou référencé dans le fichier de données XML.</span><span class="sxs-lookup"><span data-stu-id="771c2-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="771c2-113">De plus, le chargement en masse XML ne valide pas le fichier de données XML par rapport au schéma de mappage fourni.</span><span class="sxs-lookup"><span data-stu-id="771c2-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="771c2-114">Toutes informations de prologue XML sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="771c2-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="771c2-115">Le chargement en masse XML ignore toutes les informations avant et après l' \<root> élément dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="771c2-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="771c2-116">Par exemple, le chargement en masse XML ignore toutes les déclarations XML, les définitions DTD internes, les références DTD externes, les commentaires, etc.</span><span class="sxs-lookup"><span data-stu-id="771c2-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="771c2-117">Si vous possédez un schéma de mappage qui définit une relation clé primaire/clé étrangère entre deux tables (par exemple, entre Customer et CustOrder), la table avec la clé primaire doit être décrite en premier dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="771c2-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="771c2-118">La table avec la colonne de clé étrangère doit apparaître ultérieurement dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="771c2-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="771c2-119">Cela est dû au fait que l’ordre dans lequel les tables sont identifiées dans le schéma est l’ordre utilisé pour les charger dans la base de données. Par exemple, le schéma XDR suivant génère une erreur lorsqu’il est utilisé dans le chargement en masse XML, car l' **\<Order>** élément est décrit avant l' **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="771c2-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="771c2-120">La colonne CustomerID dans CustOrder est une colonne de clé étrangère qui fait référence à la colonne de clé primaire CustomerID dans la table Cust.</span><span class="sxs-lookup"><span data-stu-id="771c2-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
        <ElementType name="Order" sql:relation="CustOrder" >  
          <AttributeType name="OrderID" />  
          <AttributeType name="CustomerID" />  
          <attribute type="OrderID" />  
          <attribute type="CustomerID" />  
        </ElementType>  
  
       <ElementType name="CustomerID" dt:type="int" />  
       <ElementType name="CompanyName" dt:type="string" />  
       <ElementType name="City" dt:type="string" />  
  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
       <ElementType name="Customers" sql:relation="Cust"   
                         sql:overflow-field="OverflowColumn"  >  
          <element type="CustomerID" sql:field="CustomerID" />  
          <element type="CompanyName" sql:field="CompanyName" />  
          <element type="City" sql:field="City" />  
          <element type="Order" >   
               <sql:relationship  
                   key-relation="Cust"  
                    key="CustomerID"  
                    foreign-key="CustomerID"  
                    foreign-relation="CustOrder" />  
          </element>  
       </ElementType>  
    </Schema>  
    ```  
  
-   <span data-ttu-id="771c2-121">Si le schéma ne spécifie pas de colonnes de dépassement à l'aide de l'annotation `sql:overflow-field`, le chargement en masse XML ignore toutes les données qui sont présentes dans le document XML, mais qui ne sont pas décrites dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="771c2-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="771c2-122">Le chargement en masse XML applique le schéma de mappage que vous avez spécifié toutes les fois qu'il rencontre des balises connues dans le flux de données XML.</span><span class="sxs-lookup"><span data-stu-id="771c2-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="771c2-123">Il ignore les données qui sont présentes dans le document XML mais qui ne sont pas décrites dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="771c2-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="771c2-124">Par exemple, supposons que vous ayez un schéma de mappage qui décrit un **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="771c2-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="771c2-125">Le fichier de données XML a une **\<AllCustomers>** balise racine (qui n’est pas décrite dans le schéma) qui englobe tous les **\<Customer>** éléments :</span><span class="sxs-lookup"><span data-stu-id="771c2-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="771c2-126">Dans ce cas, le chargement en masse XML ignore l' **\<AllCustomers>** élément et commence le mappage au niveau de l' **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="771c2-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="771c2-127">Le chargement en masse XML ignore les éléments qui ne sont pas décrits dans le schéma mais qui sont présents dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="771c2-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="771c2-128">Prenons l’exemple d’un autre fichier de données source XML qui contient des **\<Order>** éléments.</span><span class="sxs-lookup"><span data-stu-id="771c2-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="771c2-129">Ces éléments ne sont pas décrits dans le schéma de mappage :</span><span class="sxs-lookup"><span data-stu-id="771c2-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="771c2-130">Le chargement en masse XML ignore ces **\<Order>** éléments.</span><span class="sxs-lookup"><span data-stu-id="771c2-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="771c2-131">Toutefois, si vous utilisez l' `sql:overflow-field` annotation dans le schéma pour identifier une colonne en tant que colonne de dépassement, le chargement en masse XML stocke toutes les données non consommées dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="771c2-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="771c2-132">Les sections CDATA et les références d'entité sont traduites en chaînes équivalentes avant d'être stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="771c2-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="771c2-133">Dans cet exemple, une section CDATA encapsule la valeur de l' **\<City>** élément.</span><span class="sxs-lookup"><span data-stu-id="771c2-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="771c2-134">Le chargement en masse XML extrait la valeur de chaîne (« NY ») avant d’insérer l' **\<City>** élément dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="771c2-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="771c2-135">Le chargement en masse XML ne conserve pas les références d'entité.</span><span class="sxs-lookup"><span data-stu-id="771c2-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="771c2-136">Si le schéma de mappage spécifie la valeur par défaut pour un attribut et que les données de source XML ne contiennent pas cet attribut, le chargement en masse XML utilise la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="771c2-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="771c2-137">L’exemple de schéma XDR suivant affecte une valeur par défaut à l’attribut **HireDate** :</span><span class="sxs-lookup"><span data-stu-id="771c2-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="771c2-138">Dans ces données XML, l’attribut **HireDate** est manquant dans le deuxième **\<Customers>** élément.</span><span class="sxs-lookup"><span data-stu-id="771c2-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="771c2-139">Lorsque le chargement en masse XML insère le deuxième **\<Customers>** élément dans la base de données, il utilise la valeur par défaut spécifiée dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="771c2-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="771c2-140">L'annotation `sql:url-encode` n'est pas prise en charge :</span><span class="sxs-lookup"><span data-stu-id="771c2-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="771c2-141">Vous ne pouvez pas spécifier une URL dans l'entrée de données XML et vous attendre à ce que le chargement en masse lise les données à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="771c2-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="771c2-142">Les tables qui sont identifiées dans le schéma de mappage sont créées (la base de données doit exister).</span><span class="sxs-lookup"><span data-stu-id="771c2-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="771c2-143">Si une ou plusieurs tables existent déjà dans la base de données, la propriété SGDropTables détermine si ces tables préexistantes doivent être supprimées et recréées.</span><span class="sxs-lookup"><span data-stu-id="771c2-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="771c2-144">Si vous spécifiez la propriété SchemaGen (par exemple, SchemaGen = true), les tables identifiées dans le schéma de mappage sont créées.</span><span class="sxs-lookup"><span data-stu-id="771c2-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="771c2-145">Toutefois, SchemaGen ne crée pas de contraintes (telles que les contraintes de clé primaire/clé étrangère) sur ces tables, à une exception près : si les nœuds XML qui constituent la clé primaire dans une relation sont définis comme ayant un type XML d’ID (autrement dit, `type="xsd:ID"` pour xsd) et que la propriété SGUseID a la valeur true pour SchemaGen, non seulement les clés primaires créées à partir des nœuds de type ID, mais les relations clé primaire/clé étrangère sont créées à partir de relations de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="771c2-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="771c2-146">SchemaGen n’utilise pas les facettes et les extensions de schéma XSD pour générer le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="771c2-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="771c2-147">Si vous spécifiez la propriété SchemaGen (par exemple, SchemaGen = true) sur le chargement en masse, seules les tables (et non les vues de nom partagé) spécifiées sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="771c2-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="771c2-148">SchemaGen fournit uniquement des fonctionnalités de base pour générer le schéma relationnel à partir de XSD annoté.</span><span class="sxs-lookup"><span data-stu-id="771c2-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="771c2-149">L'utilisateur doit modifier manuellement les tables générées, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="771c2-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="771c2-150">Dans les cas où il existe plus de relations entre les tables, SchemaGen tente de créer une relation unique qui comprend toutes les clés impliquées entre les deux tables.</span><span class="sxs-lookup"><span data-stu-id="771c2-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="771c2-151">Cette limitation peut être à l'origine d'une erreur [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="771c2-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="771c2-152">Lorsque vous chargez en masse des données XML dans une base de données, il doit y avoir au moins un attribut ou élément enfant dans le schéma de mappage qui est mappé à une colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="771c2-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="771c2-153">Si vous insérez des valeurs de date à l'aide du chargement en masse XML, les valeurs doivent être spécifiées au format (-)SSAA-MM-JJ((+-)TZ).</span><span class="sxs-lookup"><span data-stu-id="771c2-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="771c2-154">Ceci est le format XSD standard pour la date.</span><span class="sxs-lookup"><span data-stu-id="771c2-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="771c2-155">Certains indicateurs de propriété ne sont pas compatibles avec d'autres indicateurs de propriété.</span><span class="sxs-lookup"><span data-stu-id="771c2-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="771c2-156">Par exemple, le chargement en masse ne prend pas en charge `Ignoreduplicatekeys=true` avec `Keepidentity=false`.</span><span class="sxs-lookup"><span data-stu-id="771c2-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="771c2-157">Lorsque `Keepidentity=false`, le chargement en masse attend que le serveur génère les valeurs de clés.</span><span class="sxs-lookup"><span data-stu-id="771c2-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="771c2-158">Les tables doivent avoir une contrainte `IDENTITY` sur la clé.</span><span class="sxs-lookup"><span data-stu-id="771c2-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="771c2-159">Le serveur ne générera pas de clés dupliquées, ce qui signifie qu'il est inutile d'affecter la valeur `Ignoreduplicatekeys` à `true`.</span><span class="sxs-lookup"><span data-stu-id="771c2-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="771c2-160">`Ignoreduplicatekeys` ne doit avoir la valeur `true` que lors du téléchargement des valeurs de clés primaires à partir du flux de données entrant dans une table qui comporte des lignes et qu'il existe un risque potentiel de conflit des valeurs de clés primaires.</span><span class="sxs-lookup"><span data-stu-id="771c2-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
