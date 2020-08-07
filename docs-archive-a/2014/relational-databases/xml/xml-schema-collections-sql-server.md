---
title: Collections de schémas XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611629"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="6d609-102">Collections de schémas XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6d609-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="6d609-103">Comme décrit dans la rubrique, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server fournit un stockage natif des données XML par le biais du `xml` type de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="6d609-104">Vous pouvez éventuellement associer des schémas XSD à une variable ou une colonne de `xml` type par le biais d’une collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="6d609-105">La collection de schémas XML stocke les schémas XML importés et peut ensuite servir à :</span><span class="sxs-lookup"><span data-stu-id="6d609-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="6d609-106">valider des instances XML ;</span><span class="sxs-lookup"><span data-stu-id="6d609-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="6d609-107">typer les données XML lors de leur stockage dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="6d609-108">Remarquez que la collection de schémas XML est une entité de métadonnées de même qu'une table de la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="6d609-109">Vous pouvez les créer, les modifier et les supprimer.</span><span class="sxs-lookup"><span data-stu-id="6d609-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="6d609-110">Les schémas spécifiés dans une instruction [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) sont automatiquement importés dans l’objet de collection de schémas XML nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="6d609-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="6d609-111">Vous pouvez importer d’autres schémas ou composants de schéma dans un objet de collection existant dans la base de données à l’aide de l’instruction [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6d609-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="6d609-112">Comme l’explique la rubrique [XML typé et non typé](../xml/compare-typed-xml-to-untyped-xml.md), le code XML stocké dans une colonne ou une variable à laquelle un schéma est associé est dit XML **typé**, car le schéma fournit toutes les informations nécessaires sur le type des données de l’instance.</span><span class="sxs-lookup"><span data-stu-id="6d609-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="6d609-113">SQL Server utilise ces informations de type pour optimiser le stockage des données.</span><span class="sxs-lookup"><span data-stu-id="6d609-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="6d609-114">Le moteur de traitement des requêtes utilise aussi le schéma pour vérifier le type et optimiser les requêtes et la modification des données.</span><span class="sxs-lookup"><span data-stu-id="6d609-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="6d609-115">De plus, SQL Server utilise la collection de schémas XML associée, dans le cas de type `xml` , pour valider l’instance XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="6d609-116">Si l'instance XML est conforme au schéma, la base de données autorise le stockage de l'instance dans le système avec ses informations de type.</span><span class="sxs-lookup"><span data-stu-id="6d609-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="6d609-117">Sinon, elle rejette l'instance.</span><span class="sxs-lookup"><span data-stu-id="6d609-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="6d609-118">Vous pouvez utiliser la fonction intrinsèque XML_SCHEMA_NAMESPACE pour récupérer la collection de schémas stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="6d609-119">Pour plus d’informations, consultez [Afficher une collection de schémas XML stockée](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="6d609-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="6d609-120">Vous pouvez aussi utiliser la collection de schémas XML pour typer les variables, les paramètres et les colonnes XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="6d609-121">DDL pour la gestion des collections de schémas</span><span class="sxs-lookup"><span data-stu-id="6d609-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="6d609-122">Vous pouvez créer des collections de schémas XML dans la base de données et les associer à des variables et des colonnes de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="6d609-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="6d609-123">Pour gérer des collections de schémas dans la base de données, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit les instructions DDL suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d609-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="6d609-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Importe les composants de schéma dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="6d609-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifie les composants de schéma dans une collection de schémas XML existante.</span><span class="sxs-lookup"><span data-stu-id="6d609-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="6d609-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Supprime une collection de schémas XML complète et tous ses composants.</span><span class="sxs-lookup"><span data-stu-id="6d609-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="6d609-127">Pour utiliser une collection de schémas XML et les schémas qu'elle contient, vous devez d'abord créer la collection et les schémas à l'aide de l'instruction CREATE XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="6d609-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="6d609-128">Une fois la collection de schémas créée, vous pouvez ensuite créer des variables et des colonnes de type `xml` et y associer la collection de schémas.</span><span class="sxs-lookup"><span data-stu-id="6d609-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="6d609-129">Notez qu'après la création d'une collection de schémas, différents composants de schémas sont stockés dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="6d609-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="6d609-130">Vous pouvez également utiliser l'instruction ALTER XML SCHEMA COLLECTION pour ajouter des composants aux schémas existants ou pour ajouter de nouveaux schémas à une collection existante.</span><span class="sxs-lookup"><span data-stu-id="6d609-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="6d609-131">Pour supprimer la collection de schémas, utilisez l'instruction DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="6d609-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="6d609-132">Cela supprime tous les schémas contenus dans la collection et supprime l'objet collection.</span><span class="sxs-lookup"><span data-stu-id="6d609-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="6d609-133">Notez qu’avant de pouvoir supprimer une collection de schémas, les conditions décrites dans [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) doivent être remplies.</span><span class="sxs-lookup"><span data-stu-id="6d609-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="6d609-134">Description des composants de schémas</span><span class="sxs-lookup"><span data-stu-id="6d609-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="6d609-135">Lorsque vous utilisez l'instruction CREATE XML SCHEMA COLLECTION, différents composants de schémas sont importés dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="6d609-136">Les composants de schémas incluent des éléments de schémas, des attributs et des définitions de types.</span><span class="sxs-lookup"><span data-stu-id="6d609-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="6d609-137">Lorsque vous utilisez l'instruction DROP XML SCHEMA COLLECTION, vous supprimez l'intégralité de la collection.</span><span class="sxs-lookup"><span data-stu-id="6d609-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="6d609-138">CREATE XML SCHEMA COLLECTION enregistre les composants de schémas dans différentes tables système.</span><span class="sxs-lookup"><span data-stu-id="6d609-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="6d609-139">Imaginons, par exemple, le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="6d609-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="6d609-140">Le schéma précédent montre les différents types de composants qui peuvent être stockés dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="6d609-141">Il s'agit notamment de `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`et `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="6d609-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="6d609-142">Catégories de composant</span><span class="sxs-lookup"><span data-stu-id="6d609-142">Component Categories</span></span>  
 <span data-ttu-id="6d609-143">Les composants de schéma stockés dans la base de données appartiennent aux catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d609-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="6d609-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="6d609-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="6d609-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="6d609-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="6d609-146">TYPE (pour les types simples ou complexes)</span><span class="sxs-lookup"><span data-stu-id="6d609-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="6d609-147">ATTRIBUTEGROUP</span><span class="sxs-lookup"><span data-stu-id="6d609-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="6d609-148">MODELGROUP</span><span class="sxs-lookup"><span data-stu-id="6d609-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="6d609-149">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6d609-149">For example:</span></span>  
  
-   <span data-ttu-id="6d609-150">**SomeAttribute** est un composant ATTRIBUTE.</span><span class="sxs-lookup"><span data-stu-id="6d609-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="6d609-151">**SomeType**, **OrderType**et **CustomerType** sont des composants TYPE.</span><span class="sxs-lookup"><span data-stu-id="6d609-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="6d609-152">**Customer** est un composant ELEMENT.</span><span class="sxs-lookup"><span data-stu-id="6d609-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="6d609-153">Lorsque vous importez un schéma dans la base de données, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne stocke pas le schéma lui-même.</span><span class="sxs-lookup"><span data-stu-id="6d609-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="6d609-154">Au lieu de cela, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stocke les divers composants individuels.</span><span class="sxs-lookup"><span data-stu-id="6d609-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="6d609-155">Autrement dit, la balise \<Schema> n’est pas stockée ; seuls les composants qui y sont définis sont conservés.</span><span class="sxs-lookup"><span data-stu-id="6d609-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="6d609-156">Tous les éléments de schémas ne sont pas préservés.</span><span class="sxs-lookup"><span data-stu-id="6d609-156">All schema elements are not preserved.</span></span> <span data-ttu-id="6d609-157">Si la balise \<Schema> contient des attributs qui spécifient le comportement par défaut de ses composants, ces attributs sont déplacés vers les composants de schéma dans la balise pendant le processus d’importation, comme illustré dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="6d609-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="6d609-158">Nom de l’attribut</span><span class="sxs-lookup"><span data-stu-id="6d609-158">Attribute name</span></span>|<span data-ttu-id="6d609-159">Comportement</span><span class="sxs-lookup"><span data-stu-id="6d609-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="6d609-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="6d609-160">**attributeFormDefault**</span></span>|<span data-ttu-id="6d609-161">L'attribut **form** est appliqué à toutes les déclarations d'attributs du schéma où il n'est pas déjà présent et la valeur est définie à la valeur de l'attribut **attributeFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="6d609-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="6d609-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="6d609-162">**elementFormDefault**</span></span>|<span data-ttu-id="6d609-163">L'attribut **form** est appliqué à toutes les déclarations d'éléments du schéma où il n'est pas déjà présent et la valeur est définie à la valeur de l'attribut **elementFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="6d609-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="6d609-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="6d609-164">**blockDefault**</span></span>|<span data-ttu-id="6d609-165">L'attribut **block** est appliqué à toutes les déclarations d'éléments et définitions de types où il n'est pas déjà présent et la valeur est définie à la valeur de l'attribut **blockDefault** .</span><span class="sxs-lookup"><span data-stu-id="6d609-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="6d609-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="6d609-166">**finalDefault**</span></span>|<span data-ttu-id="6d609-167">L'attribut **final** est appliqué à toutes les déclarations d'éléments et définitions de types où il n'est pas déjà présent et la valeur est définie à la valeur de l'attribut **finalDefault** .</span><span class="sxs-lookup"><span data-stu-id="6d609-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="6d609-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="6d609-168">**targetNamespace**</span></span>|<span data-ttu-id="6d609-169">Les informations relatives aux composants qui appartiennent à l'espace de noms cible sont stockées dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="6d609-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="6d609-170">Autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="6d609-171">Vous devez disposer des autorisations nécessaires pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d609-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="6d609-172">créer/charger la collection de schémas XML ;</span><span class="sxs-lookup"><span data-stu-id="6d609-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="6d609-173">modifier la collection de schémas XML ;</span><span class="sxs-lookup"><span data-stu-id="6d609-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="6d609-174">supprimer la collection de schémas XML ;</span><span class="sxs-lookup"><span data-stu-id="6d609-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="6d609-175">Utiliser la collection de schémas XML pour taper des `xml` colonnes, des variables et des paramètres de type, ou l’utiliser dans des contraintes de table ou de colonne</span><span class="sxs-lookup"><span data-stu-id="6d609-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="6d609-176">Le modèle de sécurité SQL Server accorde l'autorisation CONTROL sur chaque objet.</span><span class="sxs-lookup"><span data-stu-id="6d609-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="6d609-177">Le bénéficiaire de cette autorisation obtient toutes les autres autorisations sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="6d609-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="6d609-178">Le propriétaire de l'objet a également toutes les autorisations sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="6d609-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="6d609-179">Le propriétaire et le bénéficiaire de l'autorisation CONTROL sur un objet peuvent accorder n'importe quelle autorisation sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="6d609-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="6d609-180">Un utilisateur qui n'est pas propriétaire et qui n'a pas l'autorisation CONTROL peut tout de même accorder l'autorisation sur un objet lorsque WITH GRANT OPTION est spécifié.</span><span class="sxs-lookup"><span data-stu-id="6d609-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="6d609-181">Par exemple, supposons que l'utilisateur A dispose de l'autorisation REFERENCES sur la collection de schémas S (par le biais de WITH GRANT OPTION), mais d'aucune autre autorisation sur S. L'utilisateur A peut attribuer à l'utilisateur B l'autorisation REFERENCES sur la collection de schémas S.</span><span class="sxs-lookup"><span data-stu-id="6d609-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="6d609-182">Le modèle de sécurité permet également aux autorisations de créer et d'utiliser des collections de schémas XML ou de transférer la propriété d'un utilisateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="6d609-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="6d609-183">Les rubriques suivantes décrivent les autorisations de collections de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="6d609-184">Accorder des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="6d609-185">Cette rubrique explique comment accorder des autorisations permettant de créer une collection de schémas XML et comment accorder des autorisations sur un objet de collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="6d609-186">Révoquer des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="6d609-187">Cette rubrique explique comment utiliser la révocation d'autorisation pour empêcher la création d'une collection de schémas XML et comment révoquer des autorisations sur un objet de collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="6d609-188">Refuser des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="6d609-189">Cette rubrique explique comment refuser des autorisations permettant de créer une collection de schémas XML et comment refuser l'autorisation sur un objet de collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="6d609-190">Obtention d'informations sur les schémas XML et les collections de schémas</span><span class="sxs-lookup"><span data-stu-id="6d609-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="6d609-191">Les collections de schémas XML sont répertoriées dans l'affichage catalogue sys.xml_schema_collections.</span><span class="sxs-lookup"><span data-stu-id="6d609-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="6d609-192">La collection de schémas XML « sys » est définie par le système.</span><span class="sxs-lookup"><span data-stu-id="6d609-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="6d609-193">Elle contient les espaces de noms prédéfinis qu'il est possible d'utiliser dans toutes les collections de schémas XML définies par l'utilisateur sans avoir à les charger explicitement.</span><span class="sxs-lookup"><span data-stu-id="6d609-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="6d609-194">Cette liste contient les espaces de noms pour xml, xs, xsi, fn et xdt.</span><span class="sxs-lookup"><span data-stu-id="6d609-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="6d609-195">Il existe deux autres affichages catalogue : sys.xml_schema_namespaces, qui répertorie tous les espaces de noms de chaque collection de schémas XML, et sys.xml_components, qui répertorie tous les composants de schéma XML de chaque schéma XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="6d609-196">La fonction intégrée **XML_SCHEMA_NAMESPACE**, *SchemaName, XmlSchemaCollectionName, namespace-URI*, produit une `xml` instance de type de données.</span><span class="sxs-lookup"><span data-stu-id="6d609-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="6d609-197">Cette instance contient des fragments de schéma XML pour les schémas qui sont contenus dans une collection de schémas XML, à l'exception des schémas XML prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="6d609-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="6d609-198">Pour répertorier le contenu d'une collection de schémas XML, vous pouvez au choix :</span><span class="sxs-lookup"><span data-stu-id="6d609-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="6d609-199">écrire des requêtes Transact-SQL sur les affichages catalogue appropriés pour les collections de schémas XML ;</span><span class="sxs-lookup"><span data-stu-id="6d609-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="6d609-200">utiliser la fonction intégrée **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="6d609-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="6d609-201">Vous pouvez appliquer des `xml` méthodes de type de données à la sortie de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="6d609-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="6d609-202">En revanche, vous ne pouvez pas modifier les schémas XML sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="6d609-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="6d609-203">Ces méthodes sont illustrées dans les exemples ci-après.</span><span class="sxs-lookup"><span data-stu-id="6d609-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="6d609-204">Exemple : Énumération des espaces de noms XML dans une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="6d609-205">Utilisez la requête suivante pour la collection de schémas XML « myCollection » :</span><span class="sxs-lookup"><span data-stu-id="6d609-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="6d609-206">Exemple : Énumération du contenu d’une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="6d609-207">L'instruction suivante énumère le contenu de la collection de schémas XML « myCollection » dans le schéma relationnel, dbo.</span><span class="sxs-lookup"><span data-stu-id="6d609-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="6d609-208">Les schémas XML individuels de la collection peuvent être obtenus en tant qu' `xml` instances de type de données en spécifiant l’espace de noms cible comme troisième argument pour **XML_SCHEMA_NAMESPACE ()**.</span><span class="sxs-lookup"><span data-stu-id="6d609-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="6d609-209">Cela est illustré par l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="6d609-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="6d609-210">Exemple : Extraction d’un schéma spécifique d’une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="6d609-211">L’instruction suivante extrait le schéma XML dont l’espace de noms cible est « <https://www.microsoft.com/books> » de la collection de schémas XML « myCollection » dans le schéma relationnel, dbo.</span><span class="sxs-lookup"><span data-stu-id="6d609-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="6d609-212">Interrogation des schémas XML</span><span class="sxs-lookup"><span data-stu-id="6d609-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="6d609-213">Vous pouvez interroger les schémas XML que vous avez chargés dans les collections de schémas XML en procédant ainsi :</span><span class="sxs-lookup"><span data-stu-id="6d609-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="6d609-214">Écrivez des requêtes Transact-SQL sur les affichages catalogue appropriés pour les espaces de noms de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="6d609-215">Créez une table qui contient une colonne de type `xml` pour stocker vos schémas XML et aussi les charger dans le système de type XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="6d609-216">Vous pouvez interroger la colonne XML à l'aide des méthodes de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="6d609-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="6d609-217">Vous pouvez aussi placer un index XML sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="6d609-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="6d609-218">Toutefois, dans ce cas, l'application doit assurer la cohérence entre les schémas XML stockés dans la colonne XML et le système de type XML.</span><span class="sxs-lookup"><span data-stu-id="6d609-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="6d609-219">Par exemple, si vous supprimez l'espace de noms du schéma XML du système de type XML, vous devez aussi le supprimer de la table pour garantir la cohérence.</span><span class="sxs-lookup"><span data-stu-id="6d609-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d609-220">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d609-220">See Also</span></span>  
 <span data-ttu-id="6d609-221">[Afficher une collection de schémas XML stockée](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="6d609-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="6d609-222">[Prétraiter un schéma pour fusionner des schémas inclus](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6d609-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="6d609-223">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="6d609-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
