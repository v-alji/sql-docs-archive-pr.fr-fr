---
title: Choisir un type de graphique d’exactitude et définir des options de graphique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604302"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="5b2cf-102">Choisir un type de graphique d'analyse de précision et définir des options de graphique</span><span class="sxs-lookup"><span data-stu-id="5b2cf-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="5b2cf-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]fournit plusieurs méthodes pour déterminer la validité de vos modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="5b2cf-104">Le type de graphique d'analyse de précision que vous pouvez créer pour chaque modèle ou structure dépend des facteurs suivants :</span><span class="sxs-lookup"><span data-stu-id="5b2cf-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="5b2cf-105">Le type d'algorithme utilisé pour créer le modèle</span><span class="sxs-lookup"><span data-stu-id="5b2cf-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="5b2cf-106">Le type de données de l'attribut prédictible</span><span class="sxs-lookup"><span data-stu-id="5b2cf-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="5b2cf-107">Le nombre d'attributs prédictibles à mesurer</span><span class="sxs-lookup"><span data-stu-id="5b2cf-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="5b2cf-108">Cette rubrique fournit une vue d'ensemble des différents graphiques d'analyse de précision.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="5b2cf-109">**Remarque** Les graphiques et leurs définitions ne sont pas enregistrés.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="5b2cf-110">Si vous fermez la fenêtre qui contient un graphique, vous devez créer à nouveau le graphique.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="5b2cf-111">Types de graphiques d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="5b2cf-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="5b2cf-112">En fonction du type de graphique que vous choisissez, vous avez la possibilité de configurer d'autres options, de parcourir le graphique ou de copier le graphique dans le Presse-papiers et de travailler avec les données dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="5b2cf-113">Graphique de courbes d’élévation</span><span class="sxs-lookup"><span data-stu-id="5b2cf-113">Lift chart</span></span>  
 <span data-ttu-id="5b2cf-114">Une fois que vous avez configuré les options des modèles et les données de test, cliquez sur l’onglet **Graphique de courbes d’élévation** pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="5b2cf-115">Vous pouvez également copier le graphique dans le Presse-papiers, ou afficher les détails de courbes de tendance ou de points de données individuels dans la légende d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="5b2cf-116">Graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="5b2cf-116">Profit Chart</span></span>  
 <span data-ttu-id="5b2cf-117">Une fois que vous avez configuré les options des modèles et les données de test, cliquez sur l’onglet **Graphique de courbes d’élévation** , sélectionnez **Graphique des bénéfices** dans la liste **Type de graphique** pour définir des options de graphique des bénéfices, puis cliquez sur **OK** pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="5b2cf-118">Vous pouvez utiliser la boîte de dialogue **Paramètres du graphique des bénéfices** autant de fois que vous le souhaitez pour essayer différentes options de coût et réafficher le graphique.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="5b2cf-119">La légende d'exploration de données contient des informations détaillées sur les bénéfices estimés pour chaque modèle.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="5b2cf-120">Vous pouvez également copier le graphique et le contenu de la légende d'exploration de données dans le Presse-papiers pour les utiliser dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="5b2cf-121">Nuage de points</span><span class="sxs-lookup"><span data-stu-id="5b2cf-121">Scatter Plot</span></span>  
 <span data-ttu-id="5b2cf-122">Si vous avez sélectionné le type de modèle approprié, quand vous cliquez sur l’onglet **Graphique de courbes d’élévation** , le type de graphique est défini automatiquement sur **Nuage de points** et un nuage de points s’affiche.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="5b2cf-123">Aucune configuration supplémentaire n'est possible.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-123">No further configuration is possible.</span></span> <span data-ttu-id="5b2cf-124">Vous pouvez également copier le graphique dans le Presse-papiers et coller le graphique en tant que graphique dans Excel ou une autre application.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="5b2cf-125">Matrice de classification</span><span class="sxs-lookup"><span data-stu-id="5b2cf-125">Classification Matrix</span></span>  
 <span data-ttu-id="5b2cf-126">Pour une matrice de classification, utilisez l’onglet **Sélection d’entrée** pour choisir les modèles et les données de test, puis cliquez sur l’onglet **Matrice de classification** pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="5b2cf-127">Le contenu d'une matrice de classification est identique pour tous les types de modèles et ne peut pas être configuré.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="5b2cf-128">Vous pouvez copier les données du graphique dans le Presse-papiers, puis les utiliser dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="5b2cf-129">Rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="5b2cf-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="5b2cf-130">Pour un rapport de validation croisée, après avoir sélectionné une structure d’exploration de données ou un modèle d’exploration de données dans l’Explorateur de solutions, cliquez sur l’onglet **Validation croisée** , configurez toutes les options pertinentes, puis cliquez sur **Obtenir les résultats** pour générer le rapport.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="5b2cf-131">Aucune configuration supplémentaire n'est possible.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="5b2cf-132">Le format du rapport de validation croisée est le même pour tous les types de modèles, et ne peut pas être configuré.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="5b2cf-133">Toutefois, le contenu du rapport diffère en fonction du type de modèle que vous analysez et du type de données de l'attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="5b2cf-134">Vous pouvez également copier les résultats du rapport dans le Presse-papiers et utiliser les données dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5b2cf-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
