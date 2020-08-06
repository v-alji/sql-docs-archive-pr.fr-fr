---
title: FORE_COLOR et contenu de BACK_COLOR (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- FORE_COLOR contents
- backgrounds [MDX]
- cells [MDX]
- colors [MDX]
- storing cell color information
- cell backgrounds
- BACK_COLOR contents
ms.assetid: ff8f40cb-2ac4-4fc2-9761-7f1b14c17c8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 748754ec3c90bb44392d7acb7de8f815be24086e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705604"
---
# <a name="fore_color-and-back_color-contents-mdx"></a><span data-ttu-id="0101b-102">Contenu de FORE_COLOR et BACK_COLOR (MDX)</span><span class="sxs-lookup"><span data-stu-id="0101b-102">FORE_COLOR and BACK_COLOR Contents (MDX)</span></span>
  <span data-ttu-id="0101b-103">Les propriétés de cellule `FORE_COLOR` et `BACK_COLOR` permettent de stocker les informations de couleur respectivement pour le texte et l'arrière-plan d'une cellule, selon le format rouge-vert-bleu (RVB) du système d'exploitation Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0101b-103">The `FORE_COLOR` and `BACK_COLOR` cell properties store color information for the text and the background of a cell, respectively, in the Microsoft Windows operating system red-green-blue (RGB) format.</span></span>  
  
 <span data-ttu-id="0101b-104">La gamme des valeurs valides pour une couleur RVB ordinaire va de zéro (0) à 16 777 215 (&H00FFFFFF).</span><span class="sxs-lookup"><span data-stu-id="0101b-104">The valid range for an ordinary RGB color is zero (0) to 16,777,215 (&H00FFFFFF).</span></span> <span data-ttu-id="0101b-105">L'octet de poids fort d'un nombre de cette plage est toujours égal à 0 ; les 3 octets de poids faible, de l'octet le moins significatif à l'octet le plus significatif, déterminent respectivement la quantité de rouge, de vert et de bleu.</span><span class="sxs-lookup"><span data-stu-id="0101b-105">The high byte of a number in this range always equals 0; the lower 3 bytes, from least to most significant byte, determine the amount of red, green, and blue, respectively.</span></span> <span data-ttu-id="0101b-106">Chacun des composants rouge, vert et bleu est représenté par un nombre compris entre 0 et 255 (&HFF).</span><span class="sxs-lookup"><span data-stu-id="0101b-106">The red, green, and blue components are each represented by a number between 0 and 255 (&HFF).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0101b-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0101b-107">See Also</span></span>  
 [<span data-ttu-id="0101b-108">Utilisation des propriétés de cellule &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0101b-108">Using Cell Properties &#40;MDX&#41;</span></span>](mdx-cell-properties-using-cell-properties.md)  
  
  
