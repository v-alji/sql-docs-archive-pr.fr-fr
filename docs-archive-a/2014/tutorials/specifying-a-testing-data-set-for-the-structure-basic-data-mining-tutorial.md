---
title: Spécification d’un jeu de données de test pour la structure (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600404"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="ab30f-102">Spécification d'un jeu de données de test pour la structure (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="ab30f-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ab30f-103">Dans les écrans finals de l'Assistant Exploration de données, vous allez diviser vos données en un jeu de test et un jeu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="ab30f-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="ab30f-104">Vous nommerez ensuite votre structure et activerez l'extraction sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="ab30f-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="ab30f-105">Spécification d'un jeu de test</span><span class="sxs-lookup"><span data-stu-id="ab30f-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="ab30f-106">La séparation des données en jeux d'apprentissage et de test lorsque vous créez une structure d'exploration de données permet d'évaluer facilement l'exactitude des modèles d'exploration de données que vous créerez ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ab30f-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="ab30f-107">Pour plus d’informations sur les jeux de test, consultez [jeux de données d’apprentissage et de test](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ab30f-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="ab30f-108">Pour spécifier le jeu de test</span><span class="sxs-lookup"><span data-stu-id="ab30f-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="ab30f-109">Sur la page **créer un jeu de test** , pour **pourcentage de données à tester**, laissez la valeur par défaut `30` .</span><span class="sxs-lookup"><span data-stu-id="ab30f-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="ab30f-110">Pour le **nombre maximal de cas dans le jeu de données de test**, tapez `1000` .</span><span class="sxs-lookup"><span data-stu-id="ab30f-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="ab30f-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="ab30f-112">Spécification de l'extraction</span><span class="sxs-lookup"><span data-stu-id="ab30f-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="ab30f-113">L'extraction peut être activée sur les modèles et sur les structures.</span><span class="sxs-lookup"><span data-stu-id="ab30f-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="ab30f-114">La case à cocher dans cette boîte de dialogue active l'extraction sur le modèle nommé.</span><span class="sxs-lookup"><span data-stu-id="ab30f-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="ab30f-115">Une fois le modèle traité, vous serez en mesure d'extraire des informations détaillées des données d'apprentissage qui ont été utilisées pour créer le modèle.</span><span class="sxs-lookup"><span data-stu-id="ab30f-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="ab30f-116">Si la structure sous-jacente d'exploration de données a été également configurée pour autoriser l'extraction, vous pouvez récupérer des informations détaillées des cas du modèle et de la structure d'exploration de données, y compris des colonnes non incluses dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ab30f-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="ab30f-117">Pour plus d’informations, consultez [Requêtes d’extraction &#40;exploration de données&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ab30f-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="ab30f-118">Pour nommer le modèle et la structure et spécifier l'extraction</span><span class="sxs-lookup"><span data-stu-id="ab30f-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="ab30f-119">Dans la page **fin de l’Assistant** , dans nom de la **structure d’exploration de données**, tapez `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="ab30f-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="ab30f-120">Dans **nom du modèle d’exploration de données**, tapez `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="ab30f-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="ab30f-121">Activez la case à cocher **autoriser l’extraction** .</span><span class="sxs-lookup"><span data-stu-id="ab30f-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="ab30f-122">Passez en revue le volet de **visualisation** .</span><span class="sxs-lookup"><span data-stu-id="ab30f-122">Review the **Preview** pane.</span></span> <span data-ttu-id="ab30f-123">Notez que seules les colonnes sélectionnées en tant que **clé**, **entrée** ou **prédiction** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="ab30f-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="ab30f-124">Les autres colonnes que vous avez sélectionnées (par exemple, AddressLine1) ne sont pas utilisées pour générer le modèle mais seront disponibles dans la structure sous-jacente et pourront être interrogées à l'issue du traitement et du déploiement du modèle.</span><span class="sxs-lookup"><span data-stu-id="ab30f-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="ab30f-125">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="ab30f-126">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="ab30f-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="ab30f-127">Spécification du type de données et du type de contenu &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ab30f-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ab30f-128">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="ab30f-128">Next Lesson</span></span>  
 [<span data-ttu-id="ab30f-129">Leçon 3 : Ajout et traitement des modèles</span><span class="sxs-lookup"><span data-stu-id="ab30f-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab30f-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab30f-130">See Also</span></span>  
 <span data-ttu-id="ab30f-131">[Activer l’extraction pour un modèle d’exploration de données](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="ab30f-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="ab30f-132">[Requêtes d’extraction &#40;l’exploration de données&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ab30f-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="ab30f-133">Spécifiez les données d’apprentissage &#40;l’Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ab30f-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
