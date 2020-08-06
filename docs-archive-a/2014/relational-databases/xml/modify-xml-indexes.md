---
title: Modifier les index XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696515"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="6ae68-102">Modifier les index XML</span><span class="sxs-lookup"><span data-stu-id="6ae68-102">Modify XML Indexes</span></span>
  <span data-ttu-id="6ae68-103">L’instruction DDL [!INCLUDE[tsql](../../includes/tsql-md.md)][ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) permet de modifier des index XML et non XML existants.</span><span class="sxs-lookup"><span data-stu-id="6ae68-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="6ae68-104">Les options ALTER INDEX ne sont cependant pas toutes disponibles aux index XML.</span><span class="sxs-lookup"><span data-stu-id="6ae68-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="6ae68-105">Les options suivantes ne sont pas valides si vous modifiez des index XML :</span><span class="sxs-lookup"><span data-stu-id="6ae68-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="6ae68-106">L'option de reconstruction et de définition de valeur IGNORE_DUP_KEY n'est pas valide dans le cas d'utilisation d'index XML.</span><span class="sxs-lookup"><span data-stu-id="6ae68-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="6ae68-107">L'option de reconstruction ONLINE doit toujours être définie sur OFF dans le cas d'index XML secondaires.</span><span class="sxs-lookup"><span data-stu-id="6ae68-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="6ae68-108">L'option DROP_EXISTING n'est pas autorisée dans l'instruction ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="6ae68-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="6ae68-109">Les modifications apportées à la contrainte de clé primaire de la table utilisateur ne se transmettent pas automatiquement aux index XML.</span><span class="sxs-lookup"><span data-stu-id="6ae68-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="6ae68-110">L'utilisateur doit dans ce cas supprimer les index XML en premier, puis les recréer.</span><span class="sxs-lookup"><span data-stu-id="6ae68-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="6ae68-111">Si l'option ALTER INDEX ALL est précisée, elle s'applique aussi bien aux index non XML qu'aux index XML.</span><span class="sxs-lookup"><span data-stu-id="6ae68-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="6ae68-112">Il se peut que les options d'indexation soient indiquées comme n'étant pas valides pour ces deux types d'index.</span><span class="sxs-lookup"><span data-stu-id="6ae68-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="6ae68-113">Dans ce cas, l'instruction entière est ignorée.</span><span class="sxs-lookup"><span data-stu-id="6ae68-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="6ae68-114">Exemple : Modification d’un index XML</span><span class="sxs-lookup"><span data-stu-id="6ae68-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="6ae68-115">Dans l'exemple suivant, un index XML est créé puis modifié en affectant la valeur `ALLOW_ROW_LOCKS` à l'option `OFF`.</span><span class="sxs-lookup"><span data-stu-id="6ae68-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="6ae68-116">Lorsque l'option `ALLOW_ROW_LOCKS` est ainsi définie sur `OFF`, les lignes ne sont pas verrouillées et l'accès aux index spécifiés est obtenu au moyen de verrous de niveau page et table.</span><span class="sxs-lookup"><span data-stu-id="6ae68-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="6ae68-117">Exemple : Désactivation et activation d’un index XML</span><span class="sxs-lookup"><span data-stu-id="6ae68-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="6ae68-118">Par défaut, un index XML est activé.</span><span class="sxs-lookup"><span data-stu-id="6ae68-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="6ae68-119">S'il est désactivé par la suite, les requêtes sur la colonne XML n'utilisent alors pas l'index XML.</span><span class="sxs-lookup"><span data-stu-id="6ae68-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="6ae68-120">Pour réactiver un index XML, passez par l'instruction `ALTER INDEX` avec l'option `REBUILD` .</span><span class="sxs-lookup"><span data-stu-id="6ae68-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ae68-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ae68-121">See Also</span></span>  
 [<span data-ttu-id="6ae68-122">Index XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae68-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
