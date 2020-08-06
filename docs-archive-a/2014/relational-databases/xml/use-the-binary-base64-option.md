---
title: Utiliser l’option BINARY BASE64 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706267"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="62295-102">Utiliser l'option BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="62295-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="62295-103">Si l'option BINARY BASE64 est spécifiée dans la requête, les données binaires sont renvoyées dans un format encodé en base 64.</span><span class="sxs-lookup"><span data-stu-id="62295-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="62295-104">Par défaut, si l'option BINARY BASE64 n'est pas spécifiée, le mode AUTO prend en charge l'encodage URL des données binaires.</span><span class="sxs-lookup"><span data-stu-id="62295-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="62295-105">Dans ce cas, au lieu de données binaires, une référence à une URL relative vers la racine virtuelle de la base de données dans laquelle la requête est exécutée est renvoyée.</span><span class="sxs-lookup"><span data-stu-id="62295-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="62295-106">Cette référence permet d'accéder aux données binaires réelles lors les opérations ultérieures à l'aide de la requête dbobject SQLXML ISAPI.</span><span class="sxs-lookup"><span data-stu-id="62295-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="62295-107">La requête doit fournir suffisamment d'informations, telles que des colonnes clés primaires, pour identifier l'image.</span><span class="sxs-lookup"><span data-stu-id="62295-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="62295-108">Lors de la spécification d'une requête, si un alias est utilisé pour la colonne binaire de la vue, il est renvoyé dans l'encodage URL des données binaires.</span><span class="sxs-lookup"><span data-stu-id="62295-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="62295-109">Dans les opérations suivantes, l'alias ne signifie rien et l'encodage URL ne peut pas être utilisé pour extraire l'image.</span><span class="sxs-lookup"><span data-stu-id="62295-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="62295-110">Par conséquent, n'utilisez pas d'alias lors de l'interrogation d'une vue à l'aide du mode FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="62295-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="62295-111">Par exemple, dans une requête SELECT, la conversion d'une colonne en type de données d'objet blob en fait une entité temporaire puisqu'elle perd les noms de table et de colonne qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="62295-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="62295-112">De ce fait, les requêtes exprimées en mode AUTO génèrent une erreur car elles ne savent pas où placer cette valeur dans la hiérarchie XML.</span><span class="sxs-lookup"><span data-stu-id="62295-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="62295-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="62295-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="62295-114">Cette requête produit une erreur en raison de la conversion en type de données d'objet blob.</span><span class="sxs-lookup"><span data-stu-id="62295-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="62295-115">La solution consiste à ajouter l'option BINARY BASE64 dans la clause FOR XML.</span><span class="sxs-lookup"><span data-stu-id="62295-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="62295-116">Si vous supprimez la conversion, la requête produit les résultats escomptés :</span><span class="sxs-lookup"><span data-stu-id="62295-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="62295-117">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="62295-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="62295-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62295-118">See Also</span></span>  
 [<span data-ttu-id="62295-119">Utiliser le mode AUTO avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="62295-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
