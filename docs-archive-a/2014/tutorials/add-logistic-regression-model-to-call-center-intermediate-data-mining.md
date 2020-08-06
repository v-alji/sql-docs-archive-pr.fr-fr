---
title: Ajout d’un modèle de régression logistique à la structure du centre d’appels (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704515"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="cc01e-102">Ajout d'un modèle de régression logistique à la structure de centre d'appels (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="cc01e-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="cc01e-103">En plus d'analyser les facteurs qui peuvent affecter le fonctionnement d'un centre d'appels, il vous a été demandé de fournir des recommandations spécifiques sur la façon dont le personnel peut améliorer la qualité de service.</span><span class="sxs-lookup"><span data-stu-id="cc01e-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="cc01e-104">Au cours de cette tâche, vous utiliserez la même structure d'exploration de données que celle que vous avez utilisée pour générer le modèle exploratoire et ajouter un modèle d'exploration de données qui sera utilisé pour créer des prédictions.</span><span class="sxs-lookup"><span data-stu-id="cc01e-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="cc01e-105">Dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], un modèle de régression logistique est basé sur l'algorithme MNN (Microsoft Neural Network) et fournit par conséquent la même souplesse et la même puissance qu'un modèle de réseau neuronal.</span><span class="sxs-lookup"><span data-stu-id="cc01e-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="cc01e-106">Toutefois, la régression logistique est particulièrement bien adaptée pour prévoir les résultats binaires.</span><span class="sxs-lookup"><span data-stu-id="cc01e-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="cc01e-107">Pour ce scénario, vous utiliserez la même structure d'exploration de données que celle utilisée pour le modèle de réseau neuronal.</span><span class="sxs-lookup"><span data-stu-id="cc01e-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="cc01e-108">Toutefois, vous personnaliserez le nouveau modèle pour cibler vos questions professionnelles.</span><span class="sxs-lookup"><span data-stu-id="cc01e-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="cc01e-109">Vous êtes intéressé par l'amélioration de la qualité de service et par la détermination du nombre d'opérateurs expérimentés dont vous avez besoin. Vous allez donc définir votre modèle pour prédire ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="cc01e-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="cc01e-110">Pour garantir que tous les modèles basés sur les données de centre d'appels soient aussi semblables que possible, vous utiliserez la même valeur initiale qu'auparavant.</span><span class="sxs-lookup"><span data-stu-id="cc01e-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="cc01e-111">La définition du paramètre de valeur initiale garantit que le modèle traite les données à partir du même point de départ et réduit les variations provoquées par les artefacts dans les données.</span><span class="sxs-lookup"><span data-stu-id="cc01e-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="cc01e-112">Pour ajouter un nouveau modèle d'exploration de données à la structure d'exploration de données de centre d'appels</span><span class="sxs-lookup"><span data-stu-id="cc01e-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="cc01e-113">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , dans Explorateur de solutions, cliquez avec le bouton droit sur la structure d’exploration de données, puis cliquez sur **Centre d’appels Binned (** et sélectionnez **ouvrir le concepteur**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="cc01e-114">Dans le concepteur d’exploration de données, cliquez sur l’onglet **modèles d’exploration** de données.</span><span class="sxs-lookup"><span data-stu-id="cc01e-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="cc01e-115">Cliquez sur **créer un modèle d’exploration de données connexe**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="cc01e-116">Dans la boîte de dialogue **nouveau modèle d’exploration de données** , pour **nom du modèle**, tapez `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="cc01e-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="cc01e-117">Pour **nom de l’algorithme**, sélectionnez **Microsoft logistique Regression**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="cc01e-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="cc01e-119">Le nouveau modèle d’exploration de données s’affiche sous l’onglet **modèles d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="cc01e-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="cc01e-120">Pour personnaliser le modèle de régression logistique</span><span class="sxs-lookup"><span data-stu-id="cc01e-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="cc01e-121">Dans la colonne du nouveau modèle d’exploration de données, `Call Center - LR` laissez l’ID de callcenter en tant que clé.</span><span class="sxs-lookup"><span data-stu-id="cc01e-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="cc01e-122">Remplacez la valeur de ServiceGrade et les opérateurs de niveau 2 par **Predict**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="cc01e-123">Ces colonnes seront utilisées aussi bien comme entrée que pour la prédiction.</span><span class="sxs-lookup"><span data-stu-id="cc01e-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="cc01e-124">Fondamentalement, vous créez deux modèles distincts sur les mêmes données : un qui prédit le nombre d'opérateurs et un qui prédit le niveau de service.</span><span class="sxs-lookup"><span data-stu-id="cc01e-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="cc01e-125">Remplacez toutes les autres colonnes par **entrée**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="cc01e-126">Pour spécifier la valeur initiale et traiter les modèles</span><span class="sxs-lookup"><span data-stu-id="cc01e-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="cc01e-127">Dans l’onglet **modèle d’exploration de données** , cliquez avec le bouton droit sur la colonne du modèle nommé Call Center-LR, puis sélectionnez définir les paramètres d' **algorithme**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="cc01e-128">Dans la ligne correspondant au paramètre HOLDOUT_SEED, cliquez sur la cellule vide sous **valeur**, puis tapez `1` .</span><span class="sxs-lookup"><span data-stu-id="cc01e-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="cc01e-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc01e-130">La valeur que vous choisissez comme valeur initiale n'a pas d'importance tant que vous utilisez la même valeur initiale pour tous les modèles associés.</span><span class="sxs-lookup"><span data-stu-id="cc01e-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="cc01e-131">Dans le menu **modèles d’exploration de données** , sélectionnez traiter l' **exploration de données et tous les modèles**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="cc01e-132">Cliquez sur **Oui** pour déployer le projet d’exploration de données mis à jour sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="cc01e-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="cc01e-133">Dans la boîte de dialogue **traiter le modèle d’exploration de données** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cc01e-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="cc01e-134">Cliquez sur **Fermer** pour fermer la boîte de dialogue **État d’avancement du traitement** , puis cliquez de nouveau sur **Fermer** dans la boîte de dialogue traiter le modèle d' **exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="cc01e-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cc01e-135">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="cc01e-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cc01e-136">Création de prédictions pour les modèles de centre d’appels &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="cc01e-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc01e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc01e-137">See Also</span></span>  
 [<span data-ttu-id="cc01e-138">Exigences et considérations concernant le traitement &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="cc01e-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
