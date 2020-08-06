---
title: Assistant Prévision (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602422"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="bddf6-102">Assistant Prévisions (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="bddf6-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="bddf6-103">![Assistant Association sur le ruban Exploration de données](media/dmc-forecast.gif "Assistant Association sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="bddf6-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="bddf6-104">L'Assistant Prévision vous permet de prévoir des valeurs dans une série chronologique.</span><span class="sxs-lookup"><span data-stu-id="bddf6-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="bddf6-105">Cet Assistant utilise l'algorithme MTS ([!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series), un algorithme de régression utilisé pour prévoir les colonnes continues telles que les ventes de produits.</span><span class="sxs-lookup"><span data-stu-id="bddf6-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="bddf6-106">Chaque modèle de prévision doit contenir une série de cas qui correspond à la colonne différenciant les points d'une séquence.</span><span class="sxs-lookup"><span data-stu-id="bddf6-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="bddf6-107">Par exemple, si vous utilisez des données historiques pour prédire les ventes sur une période de plusieurs mois, vous devez utiliser une colonne contenant une série de dates comme série de cas.</span><span class="sxs-lookup"><span data-stu-id="bddf6-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="bddf6-108">Vous pouvez créer des prédictions à partir du modèle de prévision sans fournir de nouvelles données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="bddf6-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="bddf6-109">L’outil [prévision &#40;table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) , dans le ruban **analyser** , vous permet également de créer des modèles de prévision, mais il est moins personnalisable et ne peut utiliser que des données dans les tables Excel.</span><span class="sxs-lookup"><span data-stu-id="bddf6-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="bddf6-110">Utilisation de l'Assistant Prévision</span><span class="sxs-lookup"><span data-stu-id="bddf6-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="bddf6-111">Dans le ruban **exploration de données** , cliquez sur **prévision**.</span><span class="sxs-lookup"><span data-stu-id="bddf6-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="bddf6-112">Dans **Sélectionner les données source**, choisissez le tableau, la plage ou la source de données externe Excel à utiliser comme entrées.</span><span class="sxs-lookup"><span data-stu-id="bddf6-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="bddf6-113">Si vous utilisez une source de données externe, vous pouvez définir une vue personnalisée ou des requêtes et les enregistrer en tant que source de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bddf6-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="bddf6-114">Dans la page **prévision** , pour **horodatage**, sélectionnez une colonne qui contient une valeur numérique unique (y compris des valeurs de date et d’heure) qui peut être utilisée comme série de cas.</span><span class="sxs-lookup"><span data-stu-id="bddf6-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="bddf6-115">La source de données doit être triée par ordre croissant dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="bddf6-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="bddf6-116">Si vos données n’ont pas une telle colonne, vous pouvez utiliser l’option \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="bddf6-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="bddf6-117">L'Assistant ajoutera une colonne d'ordre unique pour les données d'entrée ; par conséquent, vous devez vous assurer que les données sont triées comme vous le souhaitez avant d'exécuter l'assistant et de choisir cette option.</span><span class="sxs-lookup"><span data-stu-id="bddf6-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="bddf6-118">Si vous le souhaitez, vous pouvez cliquer sur **paramètres** et personnaliser le comportement du modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="bddf6-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="bddf6-119">Les modèles de prévision prennent en charge plusieurs algorithmes différents :</span><span class="sxs-lookup"><span data-stu-id="bddf6-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="bddf6-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="bddf6-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="bddf6-121">ARTXP (un type de modèle de régression)</span><span class="sxs-lookup"><span data-stu-id="bddf6-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="bddf6-122">ARTXP et ARIMA combinés</span><span class="sxs-lookup"><span data-stu-id="bddf6-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="bddf6-123">Pour plus d’informations sur les différences, consultez informations techniques de référence sur l' [algorithme MTS (Microsoft Time Series](data-mining/microsoft-time-series-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="bddf6-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="bddf6-124">Vous pouvez également ajouter des indicateurs de périodicité, spécifiant des options de lissage, et personnaliser les options de régression pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="bddf6-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="bddf6-125">Dans la page **Terminer** , indiquez un nom descriptif pour votre jeu de données et votre modèle, puis définissez les options suivantes qui contrôlent la façon dont vous travaillez avec le modèle terminé :</span><span class="sxs-lookup"><span data-stu-id="bddf6-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="bddf6-126">**Parcourir le modèle**.</span><span class="sxs-lookup"><span data-stu-id="bddf6-126">**Browse model**.</span></span> <span data-ttu-id="bddf6-127">Lorsque cette option est sélectionnée, dès que l’Assistant a terminé de traiter le modèle, il ouvre une fenêtre **Parcourir** pour vous aider à explorer les résultats.</span><span class="sxs-lookup"><span data-stu-id="bddf6-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="bddf6-128">Le contenu de la visionneuse dépend du type de modèle que vous créez.</span><span class="sxs-lookup"><span data-stu-id="bddf6-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="bddf6-129">Pour plus d’informations, consultez [exploration d’un modèle de prévision](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="bddf6-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="bddf6-130">**Activer l’extraction**.</span><span class="sxs-lookup"><span data-stu-id="bddf6-130">**Enable drillthrough**.</span></span> <span data-ttu-id="bddf6-131">Sélectionnez cette option pour examiner les données sous-jacentes du modèle terminé.</span><span class="sxs-lookup"><span data-stu-id="bddf6-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="bddf6-132">Cette option est disponible uniquement si vous créez un modèle d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="bddf6-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="bddf6-133">**Utilisez le modèle temporaire**.</span><span class="sxs-lookup"><span data-stu-id="bddf6-133">**Use temporary model**.</span></span> <span data-ttu-id="bddf6-134">Si cette option est sélectionnée, le modèle ne sera pas enregistré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="bddf6-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="bddf6-135">Lorsque vous fermez Excel, les modèles temporaires sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="bddf6-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="bddf6-136">Spécifications</span><span class="sxs-lookup"><span data-stu-id="bddf6-136">Requirements</span></span>  
 <span data-ttu-id="bddf6-137">Vos données doivent inclure au moins une colonne pouvant être utilisée en tant que série chronologique.</span><span class="sxs-lookup"><span data-stu-id="bddf6-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="bddf6-138">Les valeurs de cette colonne doivent être uniques et continues, autrement dit, il ne doit pas y avoir d’écarts.</span><span class="sxs-lookup"><span data-stu-id="bddf6-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="bddf6-139">Avant d'exécuter l'assistant, triez les données de la colonne de série chronologique par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="bddf6-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="bddf6-140">Si vos données ne contiennent pas de colonne de date ou d'heure, vous pouvez utiliser une série numérique arbitraire ou laisser l'assistant s'en charger.</span><span class="sxs-lookup"><span data-stu-id="bddf6-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="bddf6-141">Si vous laissez l'assistant créer la colonne d'ordre de la série, assurez-vous que les autres colonnes sont triées dans l'ordre souhaité avant de démarrer l'assistant.</span><span class="sxs-lookup"><span data-stu-id="bddf6-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddf6-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bddf6-142">See Also</span></span>  
 <span data-ttu-id="bddf6-143">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="bddf6-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="bddf6-144">[Outils d’analyse de table &#40;de prévision pour Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="bddf6-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="bddf6-145">Exploration d'un modèle de prévision</span><span class="sxs-lookup"><span data-stu-id="bddf6-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
