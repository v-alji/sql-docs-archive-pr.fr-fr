---
title: Résoudre les problèmes liés aux graphiques (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702439"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="33096-102">Résoudre les problèmes liés aux graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="33096-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="33096-103">Ces problèmes peuvent être utiles lors de l'utilisation de graphiques.</span><span class="sxs-lookup"><span data-stu-id="33096-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="33096-104">Pourquoi est-ce que mon graphique compte, au lieu d'additionner, les valeurs sur l'axe des ordonnées ?</span><span class="sxs-lookup"><span data-stu-id="33096-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="33096-105">La plupart des types de graphiques requièrent des valeurs numériques le long de l'axe des ordonnées, qui est en général l'axe des Y, pour qu'ils se dessinent correctement.</span><span class="sxs-lookup"><span data-stu-id="33096-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="33096-106">Si le type de données du champ de valeur est `String`, le graphique ne peut pas afficher de valeur numérique, y compris en présence de chiffres dans les champs.</span><span class="sxs-lookup"><span data-stu-id="33096-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="33096-107">À la place, le graphique affiche le nombre total de lignes qui contiennent une valeur dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="33096-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="33096-108">Pour éviter ce problème, assurez-vous que les champs que vous utilisez pour les séries de valeurs sont destinés à contenir des données numériques, par opposition aux champs de chaîne qui sont destinés à contenir des nombres mis en forme.</span><span class="sxs-lookup"><span data-stu-id="33096-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33096-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33096-109">See Also</span></span>  
 [<span data-ttu-id="33096-110">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="33096-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
