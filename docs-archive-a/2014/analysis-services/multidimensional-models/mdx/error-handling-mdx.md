---
title: Gestion des erreurs (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612572"
---
# <a name="error-handling-mdx"></a><span data-ttu-id="92457-102">Gestion des erreurs (MDX)</span><span class="sxs-lookup"><span data-stu-id="92457-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="92457-103">Chaque cube peut contrôler le mode de gestion des erreurs contenues dans un script MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="92457-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="92457-104">La gestion des erreurs s'effectue par l'intermédiaire de l'énumérateur `ScriptErrorHandlingMode`.</span><span class="sxs-lookup"><span data-stu-id="92457-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="92457-105">Les valeurs possibles pour cet énumérateur sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="92457-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="92457-106">Entraîne le déclenchement d’une erreur par le serveur lorsque [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] détecte une erreur dans le script MDX.</span><span class="sxs-lookup"><span data-stu-id="92457-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="92457-107">Amène le serveur à ignorer toutes les commandes du script MDX qui contiennent une erreur, notamment les erreurs de syntaxe, de résolution de nom, etc.</span><span class="sxs-lookup"><span data-stu-id="92457-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92457-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92457-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
