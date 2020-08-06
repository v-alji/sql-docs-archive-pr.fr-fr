---
title: Tâches de test et validation et procédures (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- predictive modeling [Analysis Services]
- mining structures [Analysis Services], predictive modeling
- Mining Accuracy Chart [Analysis Services], how-to topics
- mining models [Analysis Services], predictive modeling
- predictive accuracy [data mining]
ms.assetid: 3a0b4dc9-5b64-4be1-aa5f-6ff26f43dbf8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10844a7d39e49ab595eb25bb56ed3f4f5d415565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613691"
---
# <a name="testing-and-validation-tasks-and-how-tos-data-mining"></a><span data-ttu-id="b572b-102">Tâches de test et validation et procédures (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="b572b-102">Testing and Validation Tasks and How-tos (Data Mining)</span></span>
  <span data-ttu-id="b572b-103">Vous pouvez utiliser l’onglet **Graphique d’analyse de précision de l’exploration de données** du Concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour comparer la précision prédictive des modèles d’exploration de données dans la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b572b-103">You can use the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to compare the predictive accuracy of the mining models in your mining structure.</span></span>  
  
 <span data-ttu-id="b572b-104">Vous pouvez créer quatre types de graphiques :</span><span class="sxs-lookup"><span data-stu-id="b572b-104">You can create four kinds of charts:</span></span>  
  
-   <span data-ttu-id="b572b-105">Graphique de courbes d’élévation</span><span class="sxs-lookup"><span data-stu-id="b572b-105">Lift chart</span></span>  
  
-   <span data-ttu-id="b572b-106">Graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="b572b-106">Profit chart</span></span>  
  
-   <span data-ttu-id="b572b-107">Matrice de classification</span><span class="sxs-lookup"><span data-stu-id="b572b-107">Classification matrix</span></span>  
  
-   <span data-ttu-id="b572b-108">Rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="b572b-108">Cross-validation report</span></span>  
  
 <span data-ttu-id="b572b-109">Les trois premiers graphiques utilisent l’onglet **Sélection d’entrée** pour définir les données utilisées pour générer le graphique.</span><span class="sxs-lookup"><span data-stu-id="b572b-109">The first three charts use the **Input Selection** tab to define the data that is used for generating the chart.</span></span>  
  
 <span data-ttu-id="b572b-110">Le graphique de validation croisée est créé à l’aide d’entrées supplémentaires, disponibles sous l’onglet **validation croisée** . Pour plus d’informations, consultez [validation croisée &#40;Analysis Services d’exploration de données&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b572b-110">The Cross-validation chart is created by using additional inputs, available on the **Cross-Validation** tab. For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="b572b-111">Pour plus d’informations sur la façon d’utiliser le graphique d’analyse de précision de l’exploration des données, consultez [Test et validation &#40;exploration de données&#41;](testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b572b-111">For more information about how to use the mining accuracy chart, see [Testing and Validation &#40;Data Mining&#41;](testing-and-validation-data-mining.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b572b-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b572b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b572b-113">Créer un graphique de courbes d'élévation, un graphique des bénéfices ou une matrice de classification</span><span class="sxs-lookup"><span data-stu-id="b572b-113">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>](create-a-lift-chart-profit-chart-or-classification-matrix.md)  
  
-   [<span data-ttu-id="b572b-114">Créer un rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="b572b-114">Create a Cross-Validation Report</span></span>](create-a-cross-validation-report.md)  
  
-   [<span data-ttu-id="b572b-115">Choisir et mapper les données de test du modèle</span><span class="sxs-lookup"><span data-stu-id="b572b-115">Choose and Map Model Testing Data</span></span>](choose-and-map-model-testing-data.md)  
  
-   [<span data-ttu-id="b572b-116">Appliquer des filtres aux données de test du modèle</span><span class="sxs-lookup"><span data-stu-id="b572b-116">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
-   [<span data-ttu-id="b572b-117">Choisir la colonne à utiliser pour tester un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b572b-117">Choose the Column to Use for Testing a Mining Model</span></span>](choose-the-column-to-use-for-testing-a-mining-model.md)  
  
-   [<span data-ttu-id="b572b-118">Utilisation des données de table imbriquée comme entrée pour un graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="b572b-118">Using Nested Table Data as an Input for an Accuracy Chart</span></span>](using-nested-table-data-as-an-input-for-an-accuracy-chart.md)  
  
  
