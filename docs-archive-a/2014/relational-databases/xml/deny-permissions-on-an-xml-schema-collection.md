---
title: Refuser des autorisations sur une collection de schémas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600681"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="2547a-102">Refuser des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2547a-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="2547a-103">Les autorisations de créer une collection de schémas XML ou d'en utiliser qui existe déjà peuvent être refusées.</span><span class="sxs-lookup"><span data-stu-id="2547a-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="2547a-104">Refus de l'autorisation de créer une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2547a-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="2547a-105">Vous pouvez refuser l'autorisation de créer une collection de schémas XML en suivant l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2547a-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="2547a-106">en refusant l'autorisation ALTER sur le schéma relationnel ;</span><span class="sxs-lookup"><span data-stu-id="2547a-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="2547a-107">en refusant l'autorisation CONTROL sur le schéma relationnel pour refuser toute autorisation sur le schéma relationnel et les objets qu'il contient ;</span><span class="sxs-lookup"><span data-stu-id="2547a-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="2547a-108">en refusant l'autorisation ALTER ANY SCHEMA sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="2547a-109">Dans ce cas, le principal ne peut créer de collection de schémas XML nulle part dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="2547a-110">Il est important de savoir que refuser les autorisations ALTER ou CONTROL sur la base de données revient à refuser toutes les autorisations sur tous les objets de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="2547a-111">Refus d'autorisations sur un objet de collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2547a-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="2547a-112">Nous vous présentons maintenant les autorisations qui peuvent être refusées sur une collection de schémas XML existante, ainsi que les conséquences d'un tel refus :</span><span class="sxs-lookup"><span data-stu-id="2547a-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="2547a-113">Le refus de l'autorisation ALTER empêche le principal de modifier le contenu de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="2547a-114">Le refus de l'autorisation CONTROL empêche le principal d'effectuer une quelconque opération sur la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="2547a-115">Le refus de l'autorisation REFERENCES empêche le principal de typer les colonnes et les paramètres ou d'en contraindre le type xml à l'aide de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="2547a-116">Le principal perd également la faculté de pouvoir faire référence à la collection mentionnée ci-dessus dans d'autres collections de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="2547a-117">Le refus de l'autorisation VIEW DEFINITION empêche le principal d'afficher le contenu de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="2547a-118">Le refus de l'autorisation EXECUTE empêche le principal d'insérer ou de mettre à jour les valeurs des colonnes, des variables et des paramètres typés ou contraints par la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="2547a-119">Le principal perd également la faculté de d'interroger les valeurs de ces mêmes colonnes et variables de type xml.</span><span class="sxs-lookup"><span data-stu-id="2547a-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2547a-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="2547a-120">Examples</span></span>  
 <span data-ttu-id="2547a-121">Les scénarios proposés dans les exemples suivants montrent le fonctionnement des autorisations sur les schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="2547a-122">Chaque exemple crée la base de données de test, les schémas relationnels et les connexions nécessaires.</span><span class="sxs-lookup"><span data-stu-id="2547a-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="2547a-123">Ces connexions reçoivent les autorisations nécessaires sur la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="2547a-124">Chaque exemple procède au nettoyage qui s'impose à la fin de la procédure.</span><span class="sxs-lookup"><span data-stu-id="2547a-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="2547a-125">R.</span><span class="sxs-lookup"><span data-stu-id="2547a-125">A.</span></span> <span data-ttu-id="2547a-126">Scénario pour empêcher un utilisateur de créer une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2547a-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="2547a-127">Une des méthodes pour empêcher un utilisateur de créer une collection de schémas XML consiste à lui refuser l'autorisation ALTER sur un schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="2547a-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="2547a-128">Cela est illustré par l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2547a-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="2547a-129">Cet exemple crée un utilisateur `TestLogin1`et une base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="2547a-130">Il crée également un schéma relationnel, en plus du schéma `dbo` , dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="2547a-131">L'autorisation `CREATE XML SCHEMA` de départ permet à l'utilisateur de créer une collection de schémas n'importe où dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="2547a-132">L'exemple refuse ensuite l'autorisation `ALTER` à l'utilisateur sur l'un des schémas relationnels.</span><span class="sxs-lookup"><span data-stu-id="2547a-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="2547a-133">L'utilisateur ne peut donc plus créer de collection de schémas XML dans ce schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="2547a-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
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
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="2547a-134">B.</span><span class="sxs-lookup"><span data-stu-id="2547a-134">B.</span></span> <span data-ttu-id="2547a-135">Refus d'autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="2547a-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="2547a-136">L'exemple suivant montre comment une autorisation spécifique sur une collection de schémas XML existante peut être refusée à une connexion.</span><span class="sxs-lookup"><span data-stu-id="2547a-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="2547a-137">Dans cet exemple, une connexion de test se voit refuser l'autorisation REFERENCES sur une collection de schémas XML existante.</span><span class="sxs-lookup"><span data-stu-id="2547a-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="2547a-138">Cet exemple crée un utilisateur `TestLogin1`et une base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="2547a-139">Il crée également un schéma relationnel, en plus du schéma `dbo` , dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="2547a-140">L'autorisation `CREATE XML SCHEMA` de départ permet à l'utilisateur de créer une collection de schémas n'importe où dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2547a-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="2547a-141">L'autorisation `REFERENCES` sur la collection de schémas XML permet à `TestLogin1` d'utiliser le schéma lors de la création d'une colonne `xml` typée dans une table.</span><span class="sxs-lookup"><span data-stu-id="2547a-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="2547a-142">Si l'autorisation `REFERENCES` sur la collection de schémas XML est refusée, elle empêche `TestLogin1` de faire appel à la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2547a-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
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
  
## <a name="see-also"></a><span data-ttu-id="2547a-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2547a-143">See Also</span></span>  
 <span data-ttu-id="2547a-144">[Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="2547a-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="2547a-145">[Collections de schémas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2547a-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="2547a-146">[Spécifications et limitations relatives aux collections de schémas XML sur le serveur](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="2547a-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="2547a-147">[DENY – refus d’autorisations d’objet &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2547a-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="2547a-148">[GRANT – octroi d’autorisations d’objet &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2547a-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="2547a-149">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2547a-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
