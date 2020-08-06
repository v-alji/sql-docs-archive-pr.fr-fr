---
title: Mettre en forme les étiquettes des axes en tant que dates ou devises (Générateur de rapports et SSRS)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603836"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="f1a68-102">Mettre en forme les étiquettes des axes en tant que dates ou devises (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="f1a68-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f1a68-103">Lorsque vous affichez des valeurs DateTime correctement mises en forme sur un axe, un graphique affiche automatiquement ces valeurs comme des jours.</span><span class="sxs-lookup"><span data-stu-id="f1a68-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="f1a68-104">Pour spécifier un intervalle de date/d'heure pour l'axe des X, tel qu'un intervalle de mois ou d'heures, vous devez mettre en forme les étiquettes de l'axe et affecter une date ou un intervalle de temps valide au type de l'intervalle d'axe.</span><span class="sxs-lookup"><span data-stu-id="f1a68-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1a68-105">Dans les histogrammes et les nuages de points, l'axe horizontal (ou axe des X) est l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="f1a68-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="f1a68-106">Dans les graphiques à barres, l'axe vertical (ou axe des Y) est l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="f1a68-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="f1a68-107">Pour mettre correctement en forme les intervalles de temps, les valeurs affichées sur l’axe des X doivent prendre la valeur d’un type de données <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="f1a68-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="f1a68-108">Si votre champ a un type de données <xref:System.String>, le graphique ne calcule pas les intervalles comme dates ou heures.</span><span class="sxs-lookup"><span data-stu-id="f1a68-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="f1a68-109">Pour plus d’informations, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f1a68-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f1a68-110">Lorsqu'une valeur numérique est ajoutée à l'axe des Y, par défaut, le graphique ne met pas en forme le nombre avant de l'afficher.</span><span class="sxs-lookup"><span data-stu-id="f1a68-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="f1a68-111">Si votre champ numérique est un chiffre de ventes, envisagez de mettre en forme les nombres comme devises pour améliorer la lisibilité du graphique.</span><span class="sxs-lookup"><span data-stu-id="f1a68-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="f1a68-112">Pour mettre en forme les étiquettes de l'axe des X comme intervalles mensuels</span><span class="sxs-lookup"><span data-stu-id="f1a68-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="f1a68-113">Cliquez avec le bouton droit sur l’axe horizontal (axe des X) du graphique, puis sélectionnez **Propriétés de l’axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="f1a68-114">Dans la boîte de dialogue **Propriétés de l’axe horizontal** , sélectionnez **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="f1a68-115">Dans la liste **Catégorie** , sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="f1a68-116">Dans la liste **Type** , sélectionnez un format de date à appliquer aux étiquettes de l’axe des X.</span><span class="sxs-lookup"><span data-stu-id="f1a68-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="f1a68-117">Sélectionnez **Options de l’axe**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="f1a68-118">Dans **Intervalle**, tapez **1**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="f1a68-119">Dans la propriété **Type d’intervalle** , sélectionnez **Mois**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1a68-120">Si vous ne spécifiez pas de type d'intervalle, le graphique calcule des intervalles en termes de jours.</span><span class="sxs-lookup"><span data-stu-id="f1a68-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="f1a68-121">Pour mettre en forme les étiquettes de l'axe des Y à l'aide d'un format monétaire</span><span class="sxs-lookup"><span data-stu-id="f1a68-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="f1a68-122">Cliquez avec le bouton droit sur l’axe vertical (axe des Y) du graphique, puis sélectionnez **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="f1a68-123">Dans la boîte de dialogue **Propriétés de l’axe vertical** , sélectionnez **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="f1a68-124">Dans la liste **Catégorie** , sélectionnez **Devise**.</span><span class="sxs-lookup"><span data-stu-id="f1a68-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="f1a68-125">Dans la liste **Symbole** , sélectionnez un format monétaire à appliquer aux étiquettes de l’axe des Y.</span><span class="sxs-lookup"><span data-stu-id="f1a68-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1a68-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1a68-126">See Also</span></span>  
 <span data-ttu-id="f1a68-127">[Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1a68-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f1a68-128">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1a68-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f1a68-129">[Spécifier une échelle logarithmique &#40;Générateur de rapports et SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1a68-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f1a68-130">Spécifier un intervalle d’axe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f1a68-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
