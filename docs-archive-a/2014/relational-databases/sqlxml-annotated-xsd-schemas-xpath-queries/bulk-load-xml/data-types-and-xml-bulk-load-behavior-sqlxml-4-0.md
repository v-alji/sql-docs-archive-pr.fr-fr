---
title: Types de données et comportement de chargement en masse XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- bulk load [SQLXML], data types
- data types [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], data types
ms.assetid: d1ac1939-1f6c-4398-b7a7-a79ca608a4f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b03423f3bb88166d0d9ce5b0df450d4455e7ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611705"
---
# <a name="data-types-and-xml-bulk-load-behavior-sqlxml-40"></a><span data-ttu-id="2c74d-102">Types de données et comportement du chargement en masse XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2c74d-102">Data Types and XML Bulk Load Behavior (SQLXML 4.0)</span></span>
  <span data-ttu-id="2c74d-103">Les types de données spécifiés dans le schéma de mappage (type XSD ou XDR et `sql:datatype`) sont ignorés en général, sauf dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="2c74d-103">The data types that are specified in the mapping schema (XSD or XDR type and `sql:datatype`) are generally ignored, except in the following cases:</span></span>  
  
 <span data-ttu-id="2c74d-104">Dans XSD :</span><span class="sxs-lookup"><span data-stu-id="2c74d-104">In XSD:</span></span>  
  
-   <span data-ttu-id="2c74d-105">Si le type est `dateTime` ou `time`, vous devez spécifier `sql:datatype` car le chargement en masse XML effectue une conversion de données avant d'envoyer les données à Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c74d-105">If the type is `dateTime` or `time`, you must specify the `sql:datatype` because XML Bulk Load performs data conversion before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2c74d-106">Lorsque vous effectuez un chargement en masse dans une colonne de `uniqueidentifier` type dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et que la valeur xsd est un GUID qui comprend des accolades ({et}), vous devez spécifier **SQL : datatype = "uniqueidentifier"** pour supprimer les accolades avant que la valeur ne soit insérée dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="2c74d-106">When you are bulk loading into a column of `uniqueidentifier` type in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and the XSD value is a GUID that includes braces ({ and }), you must specify **sql:datatype="uniqueidentifier"** to remove the braces before the value is inserted into the column.</span></span> <span data-ttu-id="2c74d-107">Si `sql:datatype` n'est pas spécifié, la valeur est envoyée avec les accolades et l'insertion échoue.</span><span class="sxs-lookup"><span data-stu-id="2c74d-107">If `sql:datatype` is not specified, the value is sent with the braces and the insert fails.</span></span>  
  
 <span data-ttu-id="2c74d-108">Pour plus d’informations sur `sql:datatype` , consultez [forçages de type de données et l’annotation sql : DataType &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2c74d-108">For more information about `sql:datatype`, see [Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="2c74d-109">Dans XDR :</span><span class="sxs-lookup"><span data-stu-id="2c74d-109">In XDR:</span></span>  
  
-   <span data-ttu-id="2c74d-110">Si `dt:type` est `datetime`, `time`, `dateTime.tz` ou `time.tz`, vous devez spécifier les types de données `dt:type` et `sql:datatype` car le chargement en masse XML effectue une conversion de données avant d'envoyer les données à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c74d-110">If the `dt:type` is `datetime`, `time`, `dateTime.tz`, or `time.tz`, you must specify both the `dt:type` and `sql:datatype` data types because XML Bulk Load performs data conversion before it sends the data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2c74d-111">Si vos données XML sont de type `uuid` , `sql:datatype` doit être spécifié ; **DT : type = "UUID"** est également requis, sauf si les données sont des données de chaîne.</span><span class="sxs-lookup"><span data-stu-id="2c74d-111">If your XML data is of type `uuid`, `sql:datatype` must be specified; **dt:type="uuid"** is also required, unless the data is string data.</span></span> <span data-ttu-id="2c74d-112">Si vous ne spécifiez pas `dt:uuid`, le chargement en masse XML accepte les chaînes avec accolades (et les supprime si nécessaire).</span><span class="sxs-lookup"><span data-stu-id="2c74d-112">If you do not specify `dt:uuid`, XML Bulk Load accepts strings with braces (and removes them if needed).</span></span>  
  
-   <span data-ttu-id="2c74d-113">Si les données XML sont `bin.base64` ou `bin.hex`, vous devez spécifier le type de données XML avec `dt:type`.</span><span class="sxs-lookup"><span data-stu-id="2c74d-113">If the XML data is `bin.base64` or `bin.hex`, you must specify the XML data type with `dt:type`.</span></span> <span data-ttu-id="2c74d-114">Le chargement en masse XML charge ensuite les données dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sous la forme d'une représentation hexadécimale des données.</span><span class="sxs-lookup"><span data-stu-id="2c74d-114">XML Bulk Load then loads the data into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a hexadecimal representation of the data.</span></span>  
  
  
