---
title: Transformer les colonnes existantes en colonnes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600693"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="c9a6d-102">Transformer les colonnes existantes en colonnes XML</span><span class="sxs-lookup"><span data-stu-id="c9a6d-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="c9a6d-103">L'instruction ALTER TABLE prend en charge le type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="c9a6d-104">Par exemple, vous pouvez modifier n'importe quelle colonne de type chaîne au type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="c9a6d-105">Dans ces cas-là, les documents contenus dans la colonne doivent être corrects.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="c9a6d-106">En outre, si vous convertissez la colonne du type chaîne dans le type xml typé, les documents de la colonne sont validés par rapport aux schémas XSD spécifiés.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="c9a6d-107">Vous pouvez convertir une colonne de type `xml` non typée en colonne XML typée.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="c9a6d-108">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c9a6d-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c9a6d-109">Le script sera exécuté sur la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] car la collection de schémas XML, `Production.ProductDescriptionSchemaCollection`, est créée dans le cadre de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9a6d-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="c9a6d-110">Dans l'exemple précédent, toutes les instances stockées dans la colonne sont validées et typées par rapport aux schémas XSD de la collection spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="c9a6d-111">Si la colonne contient une ou plusieurs instances XML non valides au regard du schéma spécifié, l'instruction `ALTER TABLE` échoue et vous ne pouvez pas convertir la colonne XML non typée en colonne XML typée.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9a6d-112">Si une table est volumineuse, la modification d'une colonne de type `xml` peut s'avérer coûteuse.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="c9a6d-113">En effet, le système doit vérifier que chaque document est correct et, s'il s'agit d'un document XML typé, il doit le valider.</span><span class="sxs-lookup"><span data-stu-id="c9a6d-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="c9a6d-114">Pour plus d’informations sur le XML typé, consultez [Comparer du XML typé et du XML non typé](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c9a6d-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
