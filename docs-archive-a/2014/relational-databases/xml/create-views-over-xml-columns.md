---
title: Créer des vues sur les colonnes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706295"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="30cdd-102">Créer des vues sur les colonnes XML</span><span class="sxs-lookup"><span data-stu-id="30cdd-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="30cdd-103">Vous pouvez utiliser une colonne de type `xml` pour créer des vues.</span><span class="sxs-lookup"><span data-stu-id="30cdd-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="30cdd-104">L'exemple suivant crée une vue dans laquelle la valeur d'une colonne de type `xml` est extraite à l'aide de la méthode `value()` du type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="30cdd-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="30cdd-105">Exécutez la requête suivante sur la vue :</span><span class="sxs-lookup"><span data-stu-id="30cdd-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="30cdd-106">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="30cdd-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="30cdd-107">Notez les points suivants à propos de l'utilisation du type de données `xml` pour créer des vues :</span><span class="sxs-lookup"><span data-stu-id="30cdd-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="30cdd-108">Le type de données XML peut être créé dans une vue matérialisée.</span><span class="sxs-lookup"><span data-stu-id="30cdd-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="30cdd-109">Il ne peut pas être basé sur une méthode du type de données xml.</span><span class="sxs-lookup"><span data-stu-id="30cdd-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="30cdd-110">En revanche, il peut être converti en une collection de schémas XML différente de la colonne de type xml de la table de base.</span><span class="sxs-lookup"><span data-stu-id="30cdd-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="30cdd-111">Le type de données `xml` ne peut pas être utilisé dans les vues partitionnées distribuées.</span><span class="sxs-lookup"><span data-stu-id="30cdd-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="30cdd-112">Les prédicats SQL exécutés contre la vue ne seront pas poussés dans le XQuery de la définition de vue.</span><span class="sxs-lookup"><span data-stu-id="30cdd-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="30cdd-113">Les méthodes de type de données XML dans une vue ne peuvent pas être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="30cdd-113">XML data type methods in a view are not updatable.</span></span>  
  
  
