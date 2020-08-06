---
title: Ajouter ou supprimer des marges dans un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703871"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="e8287-102">Ajouter ou supprimer des marges dans un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e8287-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e8287-103">Dans les histogrammes et les nuages de points, le graphique ajoute automatiquement des marges latérales aux extrémités de l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="e8287-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="e8287-104">Dans les graphiques à barres, le graphique ajoute automatiquement des marges latérales aux extrémités de l'axe des ordonnées.</span><span class="sxs-lookup"><span data-stu-id="e8287-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="e8287-105">Dans tous les autres types de graphiques, aucune marge latérale n'est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="e8287-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="e8287-106">Vous ne pouvez pas modifier la taille de la marge.</span><span class="sxs-lookup"><span data-stu-id="e8287-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="e8287-107">Cette rubrique ne s'applique pas aux types de graphiques à secteurs, en anneau, en entonnoir ni en pyramide.</span><span class="sxs-lookup"><span data-stu-id="e8287-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="e8287-108">Pour activer ou désactiver les marges latérales</span><span class="sxs-lookup"><span data-stu-id="e8287-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="e8287-109">Cliquez avec le bouton droit sur l’axe, puis sélectionnez **Propriétés de l’axe**.</span><span class="sxs-lookup"><span data-stu-id="e8287-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="e8287-110">La boîte de dialogue **Propriétés de l’axe vertical** ou **Propriétés de l’axe** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e8287-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="e8287-111">Dans la page **Options de l’axe** , définissez la propriété **Marges latérales** :</span><span class="sxs-lookup"><span data-stu-id="e8287-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="e8287-112">**Automatique** Le graphique détermine s’il faut ajouter une marge latérale en fonction du type de graphique.</span><span class="sxs-lookup"><span data-stu-id="e8287-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="e8287-113">**Désactivé** Les graphiques à barres, histogrammes et nuages de points n’ont pas de marges latérales.</span><span class="sxs-lookup"><span data-stu-id="e8287-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8287-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8287-114">See Also</span></span>  
 <span data-ttu-id="e8287-115">[Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8287-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8287-116">[Boîte de dialogue Propriétés de l’axe, Options de l’axe &#40;Générateur de rapports et SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8287-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8287-117">[Spécifier un intervalle d’axe &#40;Générateur de rapports et SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8287-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8287-118">[Mettre en forme les étiquettes des axes en tant que dates ou devises &#40;Générateur de rapports et SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8287-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e8287-119">Graphiques (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e8287-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
