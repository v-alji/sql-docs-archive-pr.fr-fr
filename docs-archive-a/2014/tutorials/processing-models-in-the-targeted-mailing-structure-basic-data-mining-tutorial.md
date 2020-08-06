---
title: Traitement des modèles dans la structure de publipostage ciblée (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699054"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="82cc0-102">Traitement de modèles dans la structure de publipostage ciblé (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="82cc0-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="82cc0-103">Avant de pouvoir consulter ou utiliser les modèles d'exploration de données que vous avez créés, vous devez déployer le projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et traiter la structure d'exploration de données et les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="82cc0-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="82cc0-104">Le *déploiement* envoie le projet à un serveur et crée tous les objets de ce projet sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="82cc0-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="82cc0-105">Le *traitement* remplit [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] des objets avec des données provenant de sources de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="82cc0-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="82cc0-106">Les modèles ne peuvent pas être utilisés tant qu'ils n'ont pas été déployés et traités.</span><span class="sxs-lookup"><span data-stu-id="82cc0-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="82cc0-107">En outre, lorsque vous apportez des modifications au modèle, notamment lorsque vous ajoutez de nouvelles données, vous devez redéployer et retraiter les modèles.</span><span class="sxs-lookup"><span data-stu-id="82cc0-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="82cc0-108">Garantir la cohérence avec HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="82cc0-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="82cc0-109">Lorsque vous déployez un projet et traitez la structure et les modèles, les lignes individuelles dans votre structure de données sont assignées au jeu d'apprentissage ou au jeu de test selon une valeur de départ numérique.</span><span class="sxs-lookup"><span data-stu-id="82cc0-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="82cc0-110">Par défaut, la valeur de départ numérique est calculée selon des attributs de la structure de données.</span><span class="sxs-lookup"><span data-stu-id="82cc0-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="82cc0-111">Cependant, si vous modifiez certains aspects de votre modèle, la valeur de départ change, ce qui génère des résultats légèrement différents.</span><span class="sxs-lookup"><span data-stu-id="82cc0-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="82cc0-112">Par conséquent, pour garantir que vos résultats sont les mêmes que ceux décrits ici, nous attribuons arbitrairement une *valeur de départ exclusion* fixe de `12` .</span><span class="sxs-lookup"><span data-stu-id="82cc0-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="82cc0-113">La valeur de départ d'exclusion est utilisée pour initialiser l'algorithme d'échantillonnage et garantit que les données sont partitionnées à peu près de la même manière pour toutes les structures d'exploration de données et leurs modèles.</span><span class="sxs-lookup"><span data-stu-id="82cc0-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="82cc0-114">Cette valeur n'affecte pas le nombre de cas dans le jeu d'apprentissage ; elle garantit simplement que la même méthode de partitionnement est utilisée à chaque création du modèle.</span><span class="sxs-lookup"><span data-stu-id="82cc0-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="82cc0-115">Pour plus d’informations sur la valeur initiale de exclusion, consultez [jeux de données d’apprentissage et de test](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="82cc0-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="82cc0-116">Pour définir la valeur initiale d'exclusion</span><span class="sxs-lookup"><span data-stu-id="82cc0-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="82cc0-117">Cliquez sur l’onglet **structure d’exploration** de données ou l’onglet modèles d' **exploration** de données du concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82cc0-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="82cc0-118">Le **MiningStructure de publipostage ciblé** s’affiche dans le volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="82cc0-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="82cc0-119">Assurez-vous que le volet **Propriétés** est ouvert en appuyant sur **F4**.</span><span class="sxs-lookup"><span data-stu-id="82cc0-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="82cc0-120">Vérifiez que **CacheMode** est défini sur **KeepTrainingCases**.</span><span class="sxs-lookup"><span data-stu-id="82cc0-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="82cc0-121">Entrez `12` pour **HoldoutSeed**.</span><span class="sxs-lookup"><span data-stu-id="82cc0-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="82cc0-122">Déploiement et traitement des modèles</span><span class="sxs-lookup"><span data-stu-id="82cc0-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="82cc0-123">Dans le concepteur d’exploration de données, vous pouvez décider quels objets traiter, en fonction de l’étendue des modifications apportées à votre modèle ou aux données sous-jacentes :</span><span class="sxs-lookup"><span data-stu-id="82cc0-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="82cc0-124">Pour cette tâche, étant donné que les données et les modèles sont nouveaux, vous allez traiter la structure et tous les modèles en même temps.</span><span class="sxs-lookup"><span data-stu-id="82cc0-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="82cc0-125">Pour déployer le projet et traiter tous les modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="82cc0-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="82cc0-126">Dans le menu **modèle d’exploration de données** , sélectionnez traiter l' **exploration de données et tous les modèles**.</span><span class="sxs-lookup"><span data-stu-id="82cc0-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="82cc0-127">Si vous avez modifié la structure, un message vous demande de créer et de déployer le projet avant de traiter les modèles.</span><span class="sxs-lookup"><span data-stu-id="82cc0-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="82cc0-128">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="82cc0-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="82cc0-129">Cliquez sur **exécuter** dans la boîte de dialogue **traitement de la structure d’exploration de données-Publipostage ciblé** .</span><span class="sxs-lookup"><span data-stu-id="82cc0-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="82cc0-130">La boîte de dialogue **État d’avancement du traitement** s’ouvre avec les informations sur le traitement des modèles.</span><span class="sxs-lookup"><span data-stu-id="82cc0-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="82cc0-131">Le temps nécessaire au traitement des modèles varie en fonction de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82cc0-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="82cc0-132">Cliquez sur **Fermer** dans la boîte de dialogue **État d’avancement du traitement** une fois que les modèles ont été traités.</span><span class="sxs-lookup"><span data-stu-id="82cc0-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="82cc0-133">Cliquez sur **Fermer** dans la boîte de dialogue traitement de la **structure d’exploration \<structure> de données-** .</span><span class="sxs-lookup"><span data-stu-id="82cc0-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="82cc0-134">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="82cc0-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="82cc0-135">Ajout de nouveaux modèles à la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82cc0-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="82cc0-136">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="82cc0-136">Next Lesson</span></span>  
 [<span data-ttu-id="82cc0-137">Leçon 4 : exploration des modèles de publipostage ciblés &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82cc0-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="82cc0-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82cc0-138">See Also</span></span>  
 [<span data-ttu-id="82cc0-139">Exigences et considérations concernant le traitement &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="82cc0-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
