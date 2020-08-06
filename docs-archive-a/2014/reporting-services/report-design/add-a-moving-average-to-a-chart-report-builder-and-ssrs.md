---
title: Ajouter une moyenne mobile à un graphique (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600546"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="4090e-102">Ajouter une moyenne mobile à un graphique (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="4090e-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4090e-103">Une moyenne mobile est une moyenne des données de votre série, calculée sur une période de temps définie.</span><span class="sxs-lookup"><span data-stu-id="4090e-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="4090e-104">La moyenne mobile peut être indiquée sur le graphique pour identifier les tendances significatives.</span><span class="sxs-lookup"><span data-stu-id="4090e-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="4090e-105">La formule de moyenne mobile est l'indicateur de prix le plus populaire utilisé dans les analyses techniques.</span><span class="sxs-lookup"><span data-stu-id="4090e-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="4090e-106">De nombreuses autres formules, y compris la moyenne, la médiane et l'écart type, peuvent également être dérivées d'une série sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="4090e-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="4090e-107">Lors de la spécification d'une moyenne mobile, chaque formule peut comporter un ou plusieurs paramètres qui doivent être spécifiés.</span><span class="sxs-lookup"><span data-stu-id="4090e-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="4090e-108">Lorsqu'une formule de moyenne mobile est ajoutée en mode Création, la série de lignes ajoutée est uniquement un espace réservé visuel.</span><span class="sxs-lookup"><span data-stu-id="4090e-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="4090e-109">Le graphique calculera les points de données de chaque formule pendant le traitement des rapports.</span><span class="sxs-lookup"><span data-stu-id="4090e-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="4090e-110">La prise en charge intégrée des courbes de tendance n’est pas disponible dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4090e-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="4090e-111">Pour ajouter une moyenne mobile calculée à une série sur le graphique</span><span class="sxs-lookup"><span data-stu-id="4090e-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="4090e-112">Cliquez avec le bouton droit sur un champ dans la zone **Valeurs** , puis cliquez sur **Ajouter une série calculée**.</span><span class="sxs-lookup"><span data-stu-id="4090e-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="4090e-113">La boîte de dialogue **Propriétés de la série calculée** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4090e-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="4090e-114">Sélectionnez l’option **Moyenne mobile** dans la liste déroulante **Formule** .</span><span class="sxs-lookup"><span data-stu-id="4090e-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="4090e-115">Spécifiez une valeur entière pour la **Période** qui représente la période de la moyenne mobile.</span><span class="sxs-lookup"><span data-stu-id="4090e-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4090e-116">La période est le nombre de jours utilisés pour calculer une moyenne mobile.</span><span class="sxs-lookup"><span data-stu-id="4090e-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="4090e-117">Si les valeurs de date/d'heure ne sont pas spécifiées sur l'axe des abscisses, la période est représentée par le nombre de points de données utilisés pour calculer une moyenne mobile.</span><span class="sxs-lookup"><span data-stu-id="4090e-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="4090e-118">S'il n'existe qu'un seul point de données, la formule de moyenne mobile n'effectue pas de calcul.</span><span class="sxs-lookup"><span data-stu-id="4090e-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="4090e-119">La moyenne mobile est calculée en commençant par le deuxième point.</span><span class="sxs-lookup"><span data-stu-id="4090e-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="4090e-120">Si vous spécifiez l'option **Démarrer à partir du premier point** , le graphique démarrera la moyenne mobile au niveau du premier point.</span><span class="sxs-lookup"><span data-stu-id="4090e-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="4090e-121">S'il n'existe qu'un seul point de données, le point dans la moyenne mobile calculée sera identique au premier point dans votre série d'origine.</span><span class="sxs-lookup"><span data-stu-id="4090e-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4090e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4090e-122">See Also</span></span>  
 <span data-ttu-id="4090e-123">[Mise en forme d’un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4090e-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4090e-124">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4090e-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4090e-125">Ajouter des points vides au graphique &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4090e-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
