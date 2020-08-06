---
title: Accorder des autorisations sur une collection de schémas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696523"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="56b78-102">Accorder des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="56b78-103">Vous pouvez attribuer des autorisations de création d'une collection de schémas XML et accorder des autorisations sur un objet collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="56b78-104">Attribution d'autorisations de création d'une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="56b78-105">Pour créer une collection de schémas XML, les autorisations d'accès suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="56b78-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="56b78-106">Le principal requiert l'autorisation CREATE XML SCHEMA COLLECTION au niveau base de données.</span><span class="sxs-lookup"><span data-stu-id="56b78-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="56b78-107">Les collections de schéma XML étant étendues aux schémas relationnels, le principal doit également disposer de l'autorisation ALTER sur le schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="56b78-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="56b78-108">Les autorisations suivantes permettent à un principal de créer une collection de schémas XML dans un schéma relationnel d'une base de données hébergée sur un serveur :</span><span class="sxs-lookup"><span data-stu-id="56b78-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="56b78-109">Autorisation CONTROL sur le serveur</span><span class="sxs-lookup"><span data-stu-id="56b78-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="56b78-110">Autorisation ALTER ANY DATABASE sur le serveur</span><span class="sxs-lookup"><span data-stu-id="56b78-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="56b78-111">Autorisation ALTER sur la base de données</span><span class="sxs-lookup"><span data-stu-id="56b78-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="56b78-112">Autorisation CONTROL dans la base de données</span><span class="sxs-lookup"><span data-stu-id="56b78-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="56b78-113">Autorisations ALTER ANY SCHEMA et CREATE XML SCHEMA COLLECTION dans la base de données</span><span class="sxs-lookup"><span data-stu-id="56b78-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="56b78-114">Autorisation ALTER ou CONTROL sur le schéma relationnel et autorisation CREATE XML SCHEMA COLLECTION sur la base de données</span><span class="sxs-lookup"><span data-stu-id="56b78-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="56b78-115">Cette dernière méthode d'autorisations est utilisée dans l'exemple qui suit.</span><span class="sxs-lookup"><span data-stu-id="56b78-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="56b78-116">Le propriétaire du schéma relationnel devient propriétaire de la collection de schémas XML créée dans ce schéma.</span><span class="sxs-lookup"><span data-stu-id="56b78-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="56b78-117">Il bénéficie d'un contrôle complet sur la collection en question.</span><span class="sxs-lookup"><span data-stu-id="56b78-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="56b78-118">Il peut ainsi modifier la collection de schémas XML, typer une colonne xml ou supprimer la collection.</span><span class="sxs-lookup"><span data-stu-id="56b78-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="56b78-119">Attribution d'autorisations sur l'objet collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="56b78-120">Les autorisations suivantes peuvent s'attribuer sur la collection de schémas XML :</span><span class="sxs-lookup"><span data-stu-id="56b78-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="56b78-121">L'autorisation ALTER est nécessaire pour modifier le contenu d'une collection de schémas XML existante par le biais de l'instruction ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="56b78-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="56b78-122">L'autorisation CONTROL permet à un utilisateur d'effectuer n'importe quelle opération sur la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="56b78-123">L'autorisation TAKE OWNERSHIP est nécessaire pour transmettre la propriété de la collection de schémas XML d'un principal à un autre.</span><span class="sxs-lookup"><span data-stu-id="56b78-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="56b78-124">L'autorisation REFERENCES permet au principal d'utiliser la collection de schémas XML pour typer ou contraindre les colonnes de type `xml` des tables, des vues et des paramètres.</span><span class="sxs-lookup"><span data-stu-id="56b78-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="56b78-125">L'autorisation REFERENCES est également nécessaire si une collection de schémas XML fait référence à une autre.</span><span class="sxs-lookup"><span data-stu-id="56b78-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="56b78-126">L'autorisation VIEW DEFINITION permet au principal d'interroger le contenu de la collection de schémas XML par le biais de XML_SCHEMA_NAMESPACE ou des affichages catalogue, à condition que ce principal dispose également de l'une des autorisations ALTER, REFERENCES ou CONTROL sur la collection.</span><span class="sxs-lookup"><span data-stu-id="56b78-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="56b78-127">L'autorisation EXECUTE est nécessaire pour valider les valeurs insérées ou mises à jour par le principal par rapport à la collection de schémas XML qui type ou contraint les colonnes, les variables et les paramètres de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="56b78-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="56b78-128">Vous devez également disposer de cette autorisation pour interroger le contenu XML stocké dans ces colonnes et ces variables.</span><span class="sxs-lookup"><span data-stu-id="56b78-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56b78-129">Exemples</span><span class="sxs-lookup"><span data-stu-id="56b78-129">Examples</span></span>  
 <span data-ttu-id="56b78-130">Les scénarios proposés dans les exemples suivants illustrent le fonctionnement des autorisations sur les schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="56b78-131">Chaque exemple crée la base de données de test, les schémas relationnels et les connexions nécessaires.</span><span class="sxs-lookup"><span data-stu-id="56b78-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="56b78-132">Ces connexions reçoivent les autorisations nécessaires sur la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="56b78-133">Chaque exemple effectue le nettoyage nécessaire à la fin.</span><span class="sxs-lookup"><span data-stu-id="56b78-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="56b78-134">R.</span><span class="sxs-lookup"><span data-stu-id="56b78-134">A.</span></span> <span data-ttu-id="56b78-135">Attribution d'autorisations de création d'une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="56b78-136">L'exemple suivant montre comment accorder des autorisations pour qu'un principal puisse créer une collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="56b78-137">Il crée un exemple de base de données et un utilisateur de test, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="56b78-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="56b78-138">`TestLogin1` reçoit l’autorisation `ALTER` sur le schéma relationnel et l’autorisation `CREATE XML SCHEMA COLLECTION` sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="56b78-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="56b78-139">Avec ces autorisations, `TestLogin1` réussit à créer un exemple de collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="56b78-140">B.</span><span class="sxs-lookup"><span data-stu-id="56b78-140">B.</span></span> <span data-ttu-id="56b78-141">Attribution d'autorisations pour utiliser une collection de schémas XML existante</span><span class="sxs-lookup"><span data-stu-id="56b78-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="56b78-142">L'exemple suivant montre plus en détail le modèle d'autorisations pour la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="56b78-143">Il montre les différentes autorisations nécessaires à la création et à l'utilisation de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="56b78-144">Cet exemple crée une base de données de test et un utilisateur, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="56b78-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="56b78-145">`TestLogin1` crée une collection de schémas XML dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="56b78-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="56b78-146">La connexion crée ensuite une table et utilise la collection de schémas XML pour créer une colonne xml typée.</span><span class="sxs-lookup"><span data-stu-id="56b78-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="56b78-147">L'utilisateur insère ensuite les données et les interroge.</span><span class="sxs-lookup"><span data-stu-id="56b78-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="56b78-148">Toutes ces étapes nécessitent les autorisations de schéma nécessaires, comme illustré dans le code.</span><span class="sxs-lookup"><span data-stu-id="56b78-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="56b78-149">C.</span><span class="sxs-lookup"><span data-stu-id="56b78-149">C.</span></span> <span data-ttu-id="56b78-150">Attribution de l'autorisation ALTER sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="56b78-151">Un utilisateur doit avoir l'autorisation ALTER pour modifier une collection de schémas XML existante dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="56b78-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="56b78-152">L'exemple suivant indique comment accorder l'autorisation `ALTER` .</span><span class="sxs-lookup"><span data-stu-id="56b78-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="56b78-153">D.</span><span class="sxs-lookup"><span data-stu-id="56b78-153">D.</span></span> <span data-ttu-id="56b78-154">Attribution de l'autorisation TAKE OWNERSHIP sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="56b78-155">L'exemple suivant montre comment transférer la propriété des schémas XML d'un utilisateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="56b78-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="56b78-156">Pour rendre cet exemple plus intéressant, les utilisateurs manipulent différents schémas relationnels par défaut.</span><span class="sxs-lookup"><span data-stu-id="56b78-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="56b78-157">L'exemple réalise les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="56b78-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="56b78-158">Il crée une base de données contenant deux schémas relationnels, `dbo` et `myOtherDBSchema`).</span><span class="sxs-lookup"><span data-stu-id="56b78-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="56b78-159">Il crée deux utilisateurs, `TestLogin1` et `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="56b78-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="56b78-160">`TestLogin2` devient propriétaire du schéma relationnel `myOtherDBSchema` .</span><span class="sxs-lookup"><span data-stu-id="56b78-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="56b78-161">`TestLogin1` crée une collection de schémas XML dans le schéma relationnel `dbo` .</span><span class="sxs-lookup"><span data-stu-id="56b78-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="56b78-162">`TestLogin1` accorde ensuite l’autorisation `TAKE OWNERSHIP` sur la collection de schémas XML à `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="56b78-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="56b78-163">`TestLogin2` devient le propriétaire de la collection de schémas XML dans `myOtherDBSchema`, sans modifier le schéma relationnel de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="56b78-164">E.</span><span class="sxs-lookup"><span data-stu-id="56b78-164">E.</span></span> <span data-ttu-id="56b78-165">Attribution de l'autorisation VIEW DEFINITION sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="56b78-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="56b78-166">L'exemple suivant indique comment accorder des autorisations VIEW DEFINITION pour une collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="56b78-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="56b78-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56b78-167">See Also</span></span>  
 <span data-ttu-id="56b78-168">[Données XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="56b78-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="56b78-169">[Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="56b78-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="56b78-170">[Collections de schémas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="56b78-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="56b78-171">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="56b78-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
