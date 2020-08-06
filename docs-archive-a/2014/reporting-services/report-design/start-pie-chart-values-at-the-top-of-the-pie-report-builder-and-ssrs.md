---
title: Démarrer des valeurs de graphique à secteurs en haut du graphique à secteurs (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0e6fb59-ca4e-4d70-97cb-0ad183da21d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed010eeaf3e4d581cce2f7242144c4f73ec2895b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600511"
---
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a><span data-ttu-id="9d35a-102">Démarrer des valeurs de graphique à secteurs en haut du graphique à secteurs (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="9d35a-102">Start Pie Chart Values at the Top of the Pie (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9d35a-103">Par défaut dans les graphiques à secteurs, la première valeur du dataset démarre à 90 degrés à partir du haut du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="9d35a-103">By default in pie charts, the first value in the dataset starts at 90 degrees from the top of the pie.</span></span> <span data-ttu-id="9d35a-104">Vous souhaiterez peut-être que la première valeur démarre en haut.</span><span class="sxs-lookup"><span data-stu-id="9d35a-104">You may prefer that the first value start from the top.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a><span data-ttu-id="9d35a-105">Pour démarrer le graphique à secteurs en haut</span><span class="sxs-lookup"><span data-stu-id="9d35a-105">To Start the Pie Chart at the Top of the Pie</span></span>  
  
1.  <span data-ttu-id="9d35a-106">Cliquez sur les secteurs.</span><span class="sxs-lookup"><span data-stu-id="9d35a-106">Click the pie itself.</span></span>  
  
2.  <span data-ttu-id="9d35a-107">Si le volet **Propriétés** n'est pas ouvert, cliquez sur **Propriétés** sous l'onglet **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="9d35a-107">If the **Properties** pane is not open, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9d35a-108">Dans le volet **Propriétés** , sous **attributs personnalisés**, changez **piestartangle définie sur** de **0** à **270**.</span><span class="sxs-lookup"><span data-stu-id="9d35a-108">In the **Properties** pane, under **Custom Attributes**, change **PieStartAngle** from **0** to **270**.</span></span>  
  
4.  <span data-ttu-id="9d35a-109">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="9d35a-109">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="9d35a-110">La première valeur démarre à présent en haut du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="9d35a-110">The first value now starts at the top of the pie chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d35a-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d35a-111">See Also</span></span>  
 <span data-ttu-id="9d35a-112">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9d35a-112">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9d35a-113">Graphiques à secteurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9d35a-113">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
