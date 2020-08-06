---
title: Ajout d’une vue de source de données pour la prévision (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704504"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="4f795-102">Ajout d'une vue de source de données à des fins de prévision (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="4f795-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="4f795-103">Au cours de cette tâche, vous allez ajouter une vue de source de données qui sera utilisée pour le scénario de prévision.</span><span class="sxs-lookup"><span data-stu-id="4f795-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="4f795-104">Un modèle de prévision requiert que les données contiennent une colonne pouvant être utilisée pour identifier des étapes dans une série chronologique.</span><span class="sxs-lookup"><span data-stu-id="4f795-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="4f795-105">Si vous envisagez d'analyser plusieurs séries de données, toutes les séries doivent se terminer à la même date ou heure.</span><span class="sxs-lookup"><span data-stu-id="4f795-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="4f795-106">Pour ajouter une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="4f795-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="4f795-107">Dans Explorateur de solutions, cliquez avec le bouton droit sur **vues de source de données**, puis sélectionnez **nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="4f795-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="4f795-108">Sur la page **Bienvenue dans l'Assistant Sources de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f795-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4f795-109">Dans la page **Sélectionner une source de données** , sous **sources de données relationnelles**, sélectionnez la source de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] données.</span><span class="sxs-lookup"><span data-stu-id="4f795-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="4f795-110">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f795-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f795-111">Si vous ne disposez pas de cette source de données, vous trouverez les étapes nécessaires à la création de la source de données dans le didacticiel sur l' [exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4f795-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="4f795-112">Sur la page **Sélectionner des tables et des vues** , sélectionnez la table vTimeSeries (DBO), puis cliquez sur la flèche droite pour l’ajouter à la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="4f795-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="4f795-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4f795-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4f795-114">Dans la page **fin de l’Assistant** , la vue de source de données est nommée par défaut [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f795-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="4f795-115">Remplacez le nom par **SalesByRegion**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4f795-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="4f795-116">Le concepteur de vue de source de données s’ouvre et la vue de source de données **SalesByRegion** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4f795-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="4f795-117">Utilisation de la vue de source de données</span><span class="sxs-lookup"><span data-stu-id="4f795-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="4f795-118">Une fois que vous avez créé la vue de source de données, pour explorer les données, vous pouvez procéder des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f795-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="4f795-119">Cliquez avec le bouton droit sur la table vTimeSeries dans le concepteur, puis sélectionnez **Explorer les données** pour ouvrir la table sélectionnée dans une grille.</span><span class="sxs-lookup"><span data-stu-id="4f795-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="4f795-120">Cliquez sur **options d’échantillonnage** , puis utilisez la boîte de dialogue Options d’exploration de **données** pour modifier la méthode d’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="4f795-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="4f795-121">Cliquez sur **Actualiser** pour charger les données dans la table à l’aide des nouveaux paramètres d’option.</span><span class="sxs-lookup"><span data-stu-id="4f795-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="4f795-122">Par exemple, vous pouvez spécifier le nombre de lignes à générer dans l’exemple ou choisir les n premières lignes.</span><span class="sxs-lookup"><span data-stu-id="4f795-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="4f795-123">Cliquez avec le bouton droit sur la table vTimeSeries, puis sélectionnez **Propriétés** pour affecter un nouveau nom à la table.</span><span class="sxs-lookup"><span data-stu-id="4f795-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="4f795-124">Vous pouvez également sélectionner des colonnes individuelles dans la vue de source de données et modifier les propriétés des colonnes.</span><span class="sxs-lookup"><span data-stu-id="4f795-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="4f795-125">Cliquez n'importe où dans la zone de conception de la vue de source de données pour créer une nouvelle requête et lui affecter un nom, pour créer des relations entre des tables, ou pour modifier la disposition de la zone de conception.</span><span class="sxs-lookup"><span data-stu-id="4f795-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="4f795-126">Cliquez avec le bouton droit sur une table et sélectionnez **nouveau calcul nommé** pour créer des colonnes dérivées, y compris les agrégations.</span><span class="sxs-lookup"><span data-stu-id="4f795-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="4f795-127">Vous pouvez également ajouter de nouvelles tables et des vues à partir de la source de données dans cette vue.</span><span class="sxs-lookup"><span data-stu-id="4f795-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="4f795-128">Dans la tâche suivante, vous allez explorer les données de série chronologique et déterminer la meilleure colonne à utiliser comme identificateur de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="4f795-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="4f795-129">Vous allez également apprendre à gérer les écarts dans les données de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="4f795-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4f795-130">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4f795-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4f795-131">Comprendre la configuration requise pour un modèle de série chronologique &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="4f795-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f795-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f795-132">See Also</span></span>  
 [<span data-ttu-id="4f795-133">Algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="4f795-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
