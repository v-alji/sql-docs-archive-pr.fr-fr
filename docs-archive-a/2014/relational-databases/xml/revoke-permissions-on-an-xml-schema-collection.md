---
title: Révoquer des autorisations sur une collection de schémas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- revoking permissions [SQL Server]
ms.assetid: 4e542b70-2d56-4a65-8a39-96a1ed477ca6
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ab37c915f14207376e0c4a9582611bf8e65e0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697588"
---
# <a name="revoke-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="66c5b-102">Révoquer des autorisations sur une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="66c5b-102">Revoke Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="66c5b-103">Il est possible de retirer l'autorisation de créer une collection de schémas XML de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="66c5b-103">The permission to create an XML schema collection can be revoked by using one of the following:</span></span>  
  
-   <span data-ttu-id="66c5b-104">Retrait de l'autorisation ALTER pour le schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="66c5b-104">Revoke the ALTER permission for the relational schema.</span></span> <span data-ttu-id="66c5b-105">Ainsi, le principal ne peut pas créer de collection de schémas XML dans le schéma relationnel.</span><span class="sxs-lookup"><span data-stu-id="66c5b-105">Then, the principal cannot create an XML schema collection in the relational schema.</span></span> <span data-ttu-id="66c5b-106">Toutefois, le principal reste en mesure de le faire dans d'autres schémas relationnels de la même base de données.</span><span class="sxs-lookup"><span data-stu-id="66c5b-106">However, the principal can still do so in other relational schemas in the same database.</span></span>  
  
-   <span data-ttu-id="66c5b-107">Retrait de l'autorisation ALTER ANY SCHEMA sur la base de données pour le principal.</span><span class="sxs-lookup"><span data-stu-id="66c5b-107">Revoke the ALTER ANY SCHEMA permission on the database for the principal.</span></span> <span data-ttu-id="66c5b-108">Dans ce cas, le principal ne peut pas créer de collection de schémas XML dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="66c5b-108">Then, the principal cannot create an XML schema collection anywhere in the database.</span></span>  
  
-   <span data-ttu-id="66c5b-109">Retrait des autorisations CREATE XML SCHEMA COLLECTION ou ALTER XML SCHEMA COLLECTION sur la base de données pour le principal.</span><span class="sxs-lookup"><span data-stu-id="66c5b-109">Revoke the CREATE XML SCHEMA COLLECTION or ALTER XML SCHEMA COLLECTION permission on the database for the principal.</span></span> <span data-ttu-id="66c5b-110">Le principal est ainsi empêché d'importer une collection de schémas XML dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="66c5b-110">This prevents the principal from importing an XML schema collection within the database.</span></span> <span data-ttu-id="66c5b-111">Le retrait des autorisations ALTER ou CONTROL sur la base de données a le même effet.</span><span class="sxs-lookup"><span data-stu-id="66c5b-111">Revoking the ALTER or CONTROL permission on the database has the same effect.</span></span>  
  
## <a name="revoking-permissions-on-an-existing-xml-schema-collection-object"></a><span data-ttu-id="66c5b-112">Retrait des autorisations sur un objet Collection de schémas XML existant</span><span class="sxs-lookup"><span data-stu-id="66c5b-112">Revoking Permissions on an Existing XML Schema Collection Object</span></span>  
 <span data-ttu-id="66c5b-113">Voici les autorisations qu'il est possible de retirer sur une collection de schémas XML, ainsi que les résultats qui en découlent :</span><span class="sxs-lookup"><span data-stu-id="66c5b-113">Following are the permissions that can be revoked on an XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="66c5b-114">En cas de retrait de l'autorisation ALTER, un principal n'a plus le droit de modifier le contenu de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-114">Revoking the ALTER permission revokes a principal's ability to modify the content of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="66c5b-115">En cas de retrait de l'autorisation TAKE OWNERSHIP, un principal n'a plus le droit de transférer l'appartenance de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-115">Revoking the TAKE OWNERSHIP permission revokes a principal's ability to transfer ownership of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="66c5b-116">En cas de retrait de l'autorisation REFERENCES, un principal n'a plus le droit d'utiliser une collection de schémas XML pour modifier le type ou la contrainte des colonnes de type xml, dans les tables et les vues, ou des paramètres.</span><span class="sxs-lookup"><span data-stu-id="66c5b-116">Revoking the REFERENCES permission revokes a principal's ability to use the XML schema collection for typing or constraining xml type columns, in tables and views, and parameters.</span></span> <span data-ttu-id="66c5b-117">De plus, elle n'a plus l'autorisation de faire référence à cette collection de schémas à partir d'autres collections de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-117">It also revokes the permission to refer to this schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="66c5b-118">En cas de retrait de l'autorisation VIEW DEFINITION, un principal n'a plus le droit de consulter le contenu d'une collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-118">Revoking the VIEW DEFINITION permission revokes a principal's ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="66c5b-119">En cas de retrait de l'autorisation EXECUTE, un principal n'a plus le droit d'insérer ni de mettre à jour des valeurs dans des colonnes, des variables et des paramètres typés ou contraints par la collection XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-119">Revoking the EXECUTE permission revokes a principal's ability to insert or update values in columns, variables, and parameters that are typed or constrained by the XML collection.</span></span> <span data-ttu-id="66c5b-120">De plus, elle n'a plus la possibilité de lancer une requête sur ces colonnes, variables ou paramètres de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="66c5b-120">It also revokes the ability to query such **xml** type columns, variables, or parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="66c5b-121">Exemples</span><span class="sxs-lookup"><span data-stu-id="66c5b-121">Examples</span></span>  
 <span data-ttu-id="66c5b-122">Les scénarios proposés dans les exemples suivants illustrent le fonctionnement des autorisations sur les schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-122">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="66c5b-123">Chaque exemple crée la base de données de test, les schémas relationnels et les connexions nécessaires.</span><span class="sxs-lookup"><span data-stu-id="66c5b-123">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="66c5b-124">Ces connexions reçoivent les autorisations nécessaires sur la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-124">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="66c5b-125">Chaque exemple procède au nettoyage qui s'impose à la fin de la procédure.</span><span class="sxs-lookup"><span data-stu-id="66c5b-125">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-revoking-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="66c5b-126">R.</span><span class="sxs-lookup"><span data-stu-id="66c5b-126">A.</span></span> <span data-ttu-id="66c5b-127">Retrait des autorisations de créer une collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="66c5b-127">Revoking permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="66c5b-128">Cet exemple crée une connexion et un exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="66c5b-128">This example creates a login and a sample database.</span></span> <span data-ttu-id="66c5b-129">Il ajoute également un schéma relationnel à la base de données.</span><span class="sxs-lookup"><span data-stu-id="66c5b-129">It also adds a relational schema in the database.</span></span> <span data-ttu-id="66c5b-130">Au départ, la connexion bénéficie d'une autorisation ALTER sur les deux schémas relationnels et des autorisations voulues pour créer des collections de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-130">Initially, the login is granted ALTER permission on both relational schemas and other necessary permissions to create XML schema collections.</span></span> <span data-ttu-id="66c5b-131">Ensuite, l'exemple retire l'autorisation ALTER sur l'un des schémas relationnels de la base de données</span><span class="sxs-lookup"><span data-stu-id="66c5b-131">The example then revokes the ALTER permission on one of the relational schemas in the database.</span></span> <span data-ttu-id="66c5b-132">de façon à empêcher la connexion de créer une collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="66c5b-132">This prevents the login from creating an XML schema collection.</span></span>  
  
```  
setuser  
go  
create login TestLogin1 with password='SQLSvrPwd1'  
go  
create database SampleDBForSchemaPermissions  
go  
use SampleDBForSchemaPermissions  
go  
-- Create another relational schema in the db (in addition to dbo schema)  
CREATE SCHEMA myOtherDBSchema  
go  
CREATE USER TestLogin1  
go  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed  
-- CREATE XML SCHEMA is a database level permission  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
go  
-- Now TestLogin1 can import an XML schema collection in both relational schemas.  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- TestLogin1 can create XML schema collection in myOtherDBSchema relational schema  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- Let us drop XML schema collections from both relational schemas  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
go  
DROP XML SCHEMA COLLECTION dbo.myTestSchemaCollection  
go  
-- now REVOKE permission from TestLogin1 to alter myOtherDBSchema  
setuser  
go  
REVOKE ALTER ON SCHEMA::myOtherDBSchema FROM TestLogin1  
go  
-- now TestLogin1 cannot create xml schema collection in myOtherDBSchema  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- TestLogin1 can still create XML schema collections in dbo  
-- It cannot create XML schema collections anywhere in the database  
-- if we REVOKE CREATE XML SCHEMA COLLECTION permission  
SETUSER  
go  
REVOKE CREATE XML SCHEMA COLLECTION FROM TestLogin1  
go  
  
setuser 'TestLogin1'  
go  
-- the following now should fail  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- Final cleanup  
SETUSER  
go  
USE master  
go  
DROP DATABASE SampleDBForSchemaPermissions  
go  
DROP LOGIN TestLogin1  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="66c5b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66c5b-133">See Also</span></span>  
 <span data-ttu-id="66c5b-134">[Données XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66c5b-134">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="66c5b-135">[Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="66c5b-135">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="66c5b-136">[Collections de schémas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66c5b-136">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="66c5b-137">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="66c5b-137">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
