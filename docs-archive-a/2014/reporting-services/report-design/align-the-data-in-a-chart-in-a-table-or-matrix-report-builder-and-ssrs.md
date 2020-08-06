---
title: Aligner les données d’un graphique dans une table ou une matrice (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 75137575-d1bf-46d6-8527-5afc85eea5e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4278cd9f0dd5526770b43d2c6d94a8b87158cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613336"
---
# <a name="align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs"></a><span data-ttu-id="bc30a-102">Aligner les données d'un graphique dans une table ou une matrice (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="bc30a-102">Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bc30a-103">Les graphiques sparkline et les barres de données sont des graphiques simples de petite taille qui communiquent beaucoup d'informations avec peu de détails superflus.</span><span class="sxs-lookup"><span data-stu-id="bc30a-103">Sparklines and data bars are small, simple charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="bc30a-104">Lorsque vous activez cette option, les valeurs dans vos graphiques sparkline et barres de données sont alignées dans les différentes cellules de la table ou matrice, même s'il manque des valeurs dans les données sur lesquelles ils sont basés.</span><span class="sxs-lookup"><span data-stu-id="bc30a-104">When you check this option, the values in your sparklines and data bars will align across the different cells in the table or matrix, even if there are missing values in the data they are based on.</span></span>  
  
 <span data-ttu-id="bc30a-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="bc30a-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="bc30a-106">Dans cette image, l'histogramme affiche les ventes quotidiennes pour chaque employé.</span><span class="sxs-lookup"><span data-stu-id="bc30a-106">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="bc30a-107">Notez que les jours pendant lesquels un employé ne génère aucun chiffre d'affaires, le graphique laisse un espace et aligne les jours suivants horizontalement.</span><span class="sxs-lookup"><span data-stu-id="bc30a-107">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days horizontally.</span></span> <span data-ttu-id="bc30a-108">Il aligne également les graphiques verticalement en définissant les tailles des différents graphiques les unes par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="bc30a-108">It also aligns the charts vertically by making the sizes of the different charts relative to each other.</span></span> <span data-ttu-id="bc30a-109">Pour plus d’informations, consultez [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc30a-109">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="align-the-data-in-a-sparkline-or-data-bar"></a><span data-ttu-id="bc30a-110">Aligner les données dans un graphique sparkline ou une barre de données</span><span class="sxs-lookup"><span data-stu-id="bc30a-110">Align the data in a sparkline or data bar</span></span>  
  
1.  <span data-ttu-id="bc30a-111">Cliquez dans le graphique sparkline ou la barre de données, puis choisissez **Propriétés de l’axe horizontal** ou **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="bc30a-111">Click in the sparkline or data bar, and then click **Horizontal Axis Properties** or **Vertical Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="bc30a-112">Sous l’onglet **Options de l’axe** , cochez la case **Aligner les axes dans** puis, dans la zone déroulante, sélectionnez le groupe sur lequel aligner l’axe.</span><span class="sxs-lookup"><span data-stu-id="bc30a-112">On the **Axis Options** tab, check the **Align axes in** box, and then in the dropdown box, select the group on which to align the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc30a-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc30a-113">See Also</span></span>  
 <span data-ttu-id="bc30a-114">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc30a-114">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bc30a-115">Ajouter des graphiques sparkline et des barres de données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc30a-115">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](add-sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
