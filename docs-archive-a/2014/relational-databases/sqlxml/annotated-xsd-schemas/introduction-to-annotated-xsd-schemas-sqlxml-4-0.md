---
title: Présentation des schémas XSD annotés (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611675"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="4a5a3-102">Introduction aux schémas XSD annotés (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="4a5a3-103">Vous pouvez créer des vues XML de données relationnelles à l'aide du langage XSD (XML Schema Definition).</span><span class="sxs-lookup"><span data-stu-id="4a5a3-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="4a5a3-104">Ces vues peuvent ensuite être interrogées à l'aide de requêtes XML Path (XPath).</span><span class="sxs-lookup"><span data-stu-id="4a5a3-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="4a5a3-105">Cette opération équivaut à créer des vues à l'aide d'instructions CREATE VIEW et à spécifier ensuite des requêtes SQL contre les vues.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="4a5a3-106">Un schéma XML décrit la structure d'un document XML, ainsi que diverses contraintes agissant sur les données du document.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="4a5a3-107">Lorsque vous spécifiez des requêtes XPath à exécuter dans le schéma, la structure du document XML retournée est déterminée par le schéma dans lequel la requête XPath est exécutée.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="4a5a3-108">Dans un schéma XSD, l' **\<xsd:schema>** élément englobe le schéma entier ; toutes les déclarations d’éléments doivent être contenues dans l' **\<xsd:schema>** élément.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="4a5a3-109">Vous pouvez décrire des attributs qui définissent l’espace de noms dans lequel le schéma réside et les espaces de noms utilisés dans le schéma en tant que propriétés de l' **\<xsd:schema>** élément.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="4a5a3-110">Un schéma XSD valide doit contenir l' **\<xsd:schema>** élément défini comme suit :</span><span class="sxs-lookup"><span data-stu-id="4a5a3-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="4a5a3-111">L' **\<xsd:schema>** élément est dérivé de la spécification de l’espace de noms du schéma XML à http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="4a5a3-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="4a5a3-112">Annotations dans le schéma XSD</span><span class="sxs-lookup"><span data-stu-id="4a5a3-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="4a5a3-113">Vous pouvez utiliser un schéma XSD avec des annotations qui décrivent le mappage à une base de données, interroger la base de données, puis retourner les résultats sous la forme d'un document XML.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="4a5a3-114">Les annotations sont fournies pour mapper un schéma XSD à des tables et des colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="4a5a3-115">Vous pouvez définir et exécuter des requêtes XPath dans la vue XML créée par le schéma XSD pour interroger la base de données et obtenir des résultats sous forme de données XML.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a5a3-116">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, le langage de schéma XSD prend en charge les annotations introduites avec le langage de schéma XDR (XML-Data Reduced) dans [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a5a3-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="4a5a3-117">Le langage XDR annoté est déconseillé dans SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="4a5a3-118">Dans le contexte de la base de données relationnelle, il est utile de mapper le schéma XSD arbitraire à un magasin relationnel.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="4a5a3-119">Une manière d'y parvenir consiste à annoter le schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="4a5a3-120">Un schéma XSD avec les annotations est appelé schéma de *mappage*, qui fournit des informations relatives à la façon dont les données XML doivent être mappées à la Banque de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="4a5a3-121">Un schéma de mappage constitue en réalité une vue XML des données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="4a5a3-122">Ces mappages peuvent servir à extraire des données relationnelles sous la forme d'un document XML.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="4a5a3-123">Espace de noms des annotations</span><span class="sxs-lookup"><span data-stu-id="4a5a3-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="4a5a3-124">Dans un schéma XSD, les annotations sont spécifiées à l’aide de l’espace de noms **urn : schemas-microsoft-com : mapping-schema**.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="4a5a3-125">Comme indiqué dans l’exemple suivant, le moyen le plus simple de spécifier l’espace de noms consiste à le spécifier dans la **\<xsd:schema>** balise.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="4a5a3-126">Le préfixe d’espace de noms utilisé est arbitraire.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="4a5a3-127">Dans cette documentation, le préfixe **SQL** est utilisé pour désigner l’espace de noms d’annotation et pour distinguer les annotations de cet espace de noms de celles d’autres espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="4a5a3-128">Exemple de schéma XSD annoté</span><span class="sxs-lookup"><span data-stu-id="4a5a3-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="4a5a3-129">Dans l’exemple suivant, le schéma XSD se compose d’un **\<Person.Contact>** élément.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="4a5a3-130">L' **\<Employee>** élément a un attribut **ContactID** et **\<FirstName>** des **\<LastName>** éléments enfants :</span><span class="sxs-lookup"><span data-stu-id="4a5a3-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4a5a3-131">Des annotations sont ajoutées à ce schéma XSD pour mapper ses éléments et attributs aux tables et colonnes de base de données :</span><span class="sxs-lookup"><span data-stu-id="4a5a3-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
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
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4a5a3-132">Dans le schéma de mappage, l' **\<Contact>** élément est mappé à la table Person. contact dans l’exemple de base de données AdventureWorks à l’aide de l' `sql:relation` annotation.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="4a5a3-133">Les attributs ConID, FName et LName sont mappés aux colonnes ContactID, FirstName et LastName dans la table Person.Contact à l'aide des annotations `sql:field`.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="4a5a3-134">Ce schéma XSD annoté crée la vue XML des données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="4a5a3-135">Vous pouvez interroger cette vue XML au moyen du langage XPath.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="4a5a3-136">En guise de résultat, une requête XPath retourne un document XML au lieu de l'ensemble de lignes retourné par les requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a5a3-137">Dans le schéma de mappage, le respect de la casse pour les valeurs relationnelles spécifiées (telles que le nom de table et le nom de colonne) varie selon que SQL Server utilise des paramètres de classement sensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="4a5a3-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="4a5a3-138">Pour plus d’informations, consultez [Prise en charge d’Unicode et du classement](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="4a5a3-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="4a5a3-139">Autres ressources</span><span class="sxs-lookup"><span data-stu-id="4a5a3-139">Other Resources</span></span>  
 <span data-ttu-id="4a5a3-140">Vous trouverez des informations supplémentaires sur le langage XSD (XML Schema Definition), le langage XPath ( XML Path) et le langage XSLT (Extensible Stylesheet Language Transformations) sur les sites Web aux adresses suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a5a3-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="4a5a3-141">Schéma XML, partie 0 : introduction, recommandation du W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="4a5a3-142">Schéma XML, partie 1 : structures, recommandation du W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="4a5a3-143">Schéma XML, partie 2 : types de données, recommandation du W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="4a5a3-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="4a5a3-145">XSLT (XSL Transformations) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="4a5a3-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5a3-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a5a3-146">See Also</span></span>  
 <span data-ttu-id="4a5a3-147">[Considérations sur la sécurité des schémas annotés &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="4a5a3-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="4a5a3-148">Les schémas XDR annotés &#40;dépréciés dans SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4a5a3-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
