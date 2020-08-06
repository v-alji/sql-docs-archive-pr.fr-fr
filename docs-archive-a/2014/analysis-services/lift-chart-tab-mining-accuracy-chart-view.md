---
title: Onglet graphique de courbes d’élévation (vue graphique d’analyse de précision de l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.liftchart.f1
ms.assetid: f1674e2e-d38e-40c7-b8d1-5585ce9a0168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cdad01ff3549140bf4fed606b1e8f9eaed10dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710936"
---
# <a name="lift-chart-tab-mining-accuracy-chart-view"></a><span data-ttu-id="f0c43-102">Onglet Graphique de courbes d'élévation (vue Graphique d'analyse de précision de l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="f0c43-102">Lift Chart Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="f0c43-103">Le volet **Graphique de courbes d’élévation** permet d’afficher un graphique qui compare tous les modèles d’exploration de données sélectionnés de la structure d’exploration de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f0c43-103">Use the **Lift Chart** pane to view a chart that compares all the selected mining models in the selected mining structure.</span></span>  
  
 <span data-ttu-id="f0c43-104">Si le modèle effectue la prédiction d'un attribut discret, le volet peut afficher un graphique de courbes d'élévation ou un graphique des bénéfices.</span><span class="sxs-lookup"><span data-stu-id="f0c43-104">If the model predicts a discrete attribute, the pane can display either a lift chart or a profit chart.</span></span> <span data-ttu-id="f0c43-105">Pour plus d’informations sur les graphiques de courbes d’élévation, consultez [Graphique de courbes d’élévation &#40;Analysis Services - Exploration de données&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f0c43-105">For information about lift charts, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="f0c43-106">Pour créer un graphique des bénéfices, vous devez fournir des informations supplémentaires sur le coût de l'implémentation des recommandations du modèle d'exploration de données, ainsi que sur le retour attendu.</span><span class="sxs-lookup"><span data-stu-id="f0c43-106">To create a profit chart, you must provide additional information about the cost of implementing the recommendations of the mining model, as well as the expected return.</span></span> <span data-ttu-id="f0c43-107">Pour plus d’informations, consultez [Graphique des bénéfices &#40;Analysis Services - Exploration de données&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f0c43-107">For more information, see [Profit Chart &#40;Analysis Services - Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="f0c43-108">Si le modèle effectue la prédiction d'un attribut continu, le volet affichera un graphique de nuage de points.</span><span class="sxs-lookup"><span data-stu-id="f0c43-108">If the model predicts a continuous attribute, the pane will display a scatter plot graph.</span></span>  
  
 <span data-ttu-id="f0c43-109">Pour obtenir des informations générales sur les méthodes de mesure de précision d’un modèle d’exploration de données, consultez [Graphique de courbes d’élévation &#40;Analysis Services - Exploration de données&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f0c43-109">For general information about methods of measuring the accuracy of a mining model, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0c43-110">Options</span><span class="sxs-lookup"><span data-stu-id="f0c43-110">Options</span></span>  
 <span data-ttu-id="f0c43-111">**Type de graphique**</span><span class="sxs-lookup"><span data-stu-id="f0c43-111">**Chart Type**</span></span>  
 <span data-ttu-id="f0c43-112">Définit le type de graphique à afficher dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="f0c43-112">Sets the type of chart to display in the viewer.</span></span> <span data-ttu-id="f0c43-113">Vous pouvez sélectionner **Graphique de courbes d’élévation** ou **Graphique des bénéfices**.</span><span class="sxs-lookup"><span data-stu-id="f0c43-113">You can select either **Lift Chart** or **Profit Chart**.</span></span>  
  
 <span data-ttu-id="f0c43-114">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="f0c43-114">**Settings**</span></span>  
 <span data-ttu-id="f0c43-115">Ouvre la boîte de dialogue **Paramètres du graphique des bénéfices** , que vous pouvez utiliser pour configurer un graphique des bénéfices.</span><span class="sxs-lookup"><span data-stu-id="f0c43-115">Opens the **Profit Chart Settings** dialog box, which you can use to configure a profit chart.</span></span>  
  
 <span data-ttu-id="f0c43-116">Le graphique des bénéfices n’est pas disponible si une colonne prédictible continue a été sélectionnée sous l’onglet **Mappage de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f0c43-116">The profit chart is not available if a continuous predictable column was selected in the **Column Mapping** tab.</span></span>  
  
 <span data-ttu-id="f0c43-117">**Copier**</span><span class="sxs-lookup"><span data-stu-id="f0c43-117">**Copy**</span></span>  
 <span data-ttu-id="f0c43-118">Copie le graphique dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="f0c43-118">Copies the chart to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c43-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0c43-119">See Also</span></span>  
 <span data-ttu-id="f0c43-120">[Concepteur graphique d’analyse de précision de l’exploration de données &#40;&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f0c43-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="f0c43-121">[Tâches de test et de validation et &#40;d’exploration de données&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f0c43-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="f0c43-122">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f0c43-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
