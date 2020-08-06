---
title: Prise en charge d’espace de noms en mode PATH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696512"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="e49cd-102">Prise en charge d'espace de noms en mode PATH</span><span class="sxs-lookup"><span data-stu-id="e49cd-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="e49cd-103">La prise en charge des espaces de noms en mode PATH est fournie à l'aide de WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="e49cd-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="e49cd-104">Par exemple, la requête suivante démontre l'utilisation de la syntaxe WITH NAMESPACES pour déclarer un espace de noms ("a:") qui peut ensuite être utilisé dans l'instruction SELECT ultérieure :</span><span class="sxs-lookup"><span data-stu-id="e49cd-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="e49cd-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="e49cd-105">Examples</span></span>  
 <span data-ttu-id="e49cd-106">Ces exemples montrent comment utiliser le mode PATH pour générer un document XML à partir d'une requête SELECT.</span><span class="sxs-lookup"><span data-stu-id="e49cd-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="e49cd-107">Nombre de ces requêtes sont spécifiées par rapport aux documents XML des instructions de fabrication de bicyclettes stockés dans la colonne Instructions de la table ProductModel.</span><span class="sxs-lookup"><span data-stu-id="e49cd-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49cd-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e49cd-108">See Also</span></span>  
 [<span data-ttu-id="e49cd-109">Utiliser le mode PATH avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="e49cd-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
