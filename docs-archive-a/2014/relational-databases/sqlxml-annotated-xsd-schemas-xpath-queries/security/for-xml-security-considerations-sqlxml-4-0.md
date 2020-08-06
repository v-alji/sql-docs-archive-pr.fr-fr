---
title: Considérations relatives à la sécurité XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612733"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="66b28-102">Considérations relatives à la sécurité de FOR XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="66b28-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="66b28-103">Le mode AUTO de FOR XML génère une hiérarchie XML dans laquelle les noms d'éléments sont mappés aux noms de tables et les noms d'attributs sont mappés aux noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="66b28-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="66b28-104">Les informations de colonne et de table de la base de données sont de ce fait exposées.</span><span class="sxs-lookup"><span data-stu-id="66b28-104">This exposes the database table and column information.</span></span> <span data-ttu-id="66b28-105">Vous pouvez masquer les informations de la base de données lorsque vous utilisez le mode AUTO (mise en forme côté serveur) en spécifiant des alias de table et de colonne dans la requête.</span><span class="sxs-lookup"><span data-stu-id="66b28-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="66b28-106">Ces alias sont retournés dans le document XML résultant comme noms d'éléments et noms d'attributs.</span><span class="sxs-lookup"><span data-stu-id="66b28-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="66b28-107">Par exemple, la requête suivante spécifie le mode AUTO. La mise en forme XML est par conséquent réalisée sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="66b28-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="66b28-108">Dans le document XML résultant, les alias sont utilisés pour les noms d'éléments et les noms d'attributs :</span><span class="sxs-lookup"><span data-stu-id="66b28-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="66b28-109">Lorsque vous utilisez le mode NESTED (mise en forme côté client), les alias sont retournés uniquement pour les attributs figurant dans le document XML résultant.</span><span class="sxs-lookup"><span data-stu-id="66b28-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="66b28-110">Les noms des tables de base sont toujours retournés comme noms d'éléments.</span><span class="sxs-lookup"><span data-stu-id="66b28-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="66b28-111">Par exemple, la requête suivante spécifie le mode NESTED.</span><span class="sxs-lookup"><span data-stu-id="66b28-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="66b28-112">Dans le document XML résultant, les noms des tables de base sont retournés comme noms d'éléments et les alias de tables ne sont pas utilisés :</span><span class="sxs-lookup"><span data-stu-id="66b28-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
