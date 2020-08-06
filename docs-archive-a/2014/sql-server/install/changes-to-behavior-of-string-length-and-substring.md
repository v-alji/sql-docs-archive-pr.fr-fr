---
title: Modifications du comportement de String-Length et substring | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604965"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="f392d-102">Modifications du comportement de string-length et substring</span><span class="sxs-lookup"><span data-stu-id="f392d-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="f392d-103">La [fonction de longueur de chaîne &#40;xquery&#41;](/sql/xquery/functions-on-string-values-string-length) et la [fonction de sous-chaîne &#40;fonctions XQuery&#41;](/sql/xquery/functions-on-string-values-substring) peuvent retourner des résultats différents lorsqu’elles sont utilisées avec des bases de données XML qui contiennent des caractères de substitution.</span><span class="sxs-lookup"><span data-stu-id="f392d-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f392d-104">Description</span><span class="sxs-lookup"><span data-stu-id="f392d-104">Description</span></span>  
 <span data-ttu-id="f392d-105">Lorsqu’une base de données est configurée pour être compatible avec [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , le comportement de la [fonction de longueur de chaîne &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) et la [fonction de sous-chaîne &#40;fonctions de&#41;XQuery](/sql/xquery/functions-on-string-values-substring) change lors du traitement de caractères Unicode supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f392d-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="f392d-106">Chaque caractère Unicode supplémentaire, qui est défini en ayant un point de code supérieur à U+FFFF, est compté comme un caractère par ces fonctions au lieu de deux, comme c'était le cas dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="f392d-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="f392d-107">Pour plus d'informations sur les caractères de substitution, consultez [Surrogates and Supplementary Characters (en anglais)](https://go.microsoft.com/fwlink/?LinkId=178317).</span><span class="sxs-lookup"><span data-stu-id="f392d-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f392d-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f392d-108">See Also</span></span>  
 <span data-ttu-id="f392d-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f392d-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f392d-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="f392d-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
