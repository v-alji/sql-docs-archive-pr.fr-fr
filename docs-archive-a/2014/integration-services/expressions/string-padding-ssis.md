---
title: Remplissage des chaînes (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701364"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="29539-102">Remplissage des chaînes (SSIS)</span><span class="sxs-lookup"><span data-stu-id="29539-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="29539-103">L'évaluateur d'expression ne vérifie pas si une chaîne contient des espaces de début et de fin et ne complète pas les chaînes pour qu'elles aient la même longueur avant de les comparer.</span><span class="sxs-lookup"><span data-stu-id="29539-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="29539-104">Pour compléter une chaîne dans une expression, vous pouvez concaténer des valeurs de colonne et des chaînes vides à l'aide de l'opérateur « + ».</span><span class="sxs-lookup"><span data-stu-id="29539-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="29539-105">Pour plus d’informations, consultez [+ &#40;Concaténer&#41; &#40;expression SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="29539-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="29539-106">Par contre, si vous souhaitez supprimer des espaces, l'évaluateur d'expression met à votre disposition les fonctions LTRIM, RTRIM et TRIM, qui permettent de supprimer les espaces de début et/ou de fin.</span><span class="sxs-lookup"><span data-stu-id="29539-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="29539-107">Pour plus d’informations, consultez [LTRIM &#40;Expression SSIS&#41;](trim-ssis-expression.md), [RTRIM &#40;Expression SSIS&#41;](rtrim-ssis-expression.md)[TRIM &#40;Expression SSIS&#41;](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="29539-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29539-108">Le nombre de la fonction LEN inclut les espaces de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="29539-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="29539-109">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="29539-109">Related Content</span></span>  
 <span data-ttu-id="29539-110">Article technique, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), sur pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="29539-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
