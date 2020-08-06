---
title: Ajout de nouveaux modèles à la structure de publipostage ciblée (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704503"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="61c17-102">Ajout de nouveaux modèles à la structure de publipostage ciblé (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="61c17-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="61c17-103">Dans cette tâche, vous allez définir deux modèles supplémentaires à l’aide de l’onglet **modèles d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="61c17-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="61c17-104">Vous allez utiliser l'algorithme MNB (Microsoft Naive Bayes) et l'algorithme de gestion de clusters Microsoft pour créer les modèles.</span><span class="sxs-lookup"><span data-stu-id="61c17-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="61c17-105">Ces deux algorithmes sont sélectionnés en raison de leur capacité à prédire une valeur discrète (c.-à-d., un achat de vélo).</span><span class="sxs-lookup"><span data-stu-id="61c17-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="61c17-106">Pour plus d’informations sur ces algorithmes, consultez [algorithme de clustering Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) et [algorithme Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span><span class="sxs-lookup"><span data-stu-id="61c17-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="61c17-107">Pour créer un modèle d'exploration de données Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="61c17-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="61c17-108">Basculez vers l’onglet **modèles d’exploration** de données du concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61c17-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="61c17-109">Notez que le concepteur affiche deux colonnes, une pour la structure d’exploration de données et une pour le `TM_Decision_Tree` modèle d’exploration de données que vous avez créée dans la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="61c17-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="61c17-110">Cliquez avec le bouton droit sur la colonne **structure** et sélectionnez **nouveau modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="61c17-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="61c17-111">Dans la boîte de dialogue **nouveau modèle d’exploration de données** , dans **nom du modèle**, tapez `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="61c17-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="61c17-112">Dans **nom de l’algorithme**, sélectionnez **clustering Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="61c17-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="61c17-113">Le nouveau modèle s’affiche maintenant sous l’onglet **modèles d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="61c17-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="61c17-114">Ce modèle, créé à l’aide de l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme de clustering, regroupe les clients ayant des caractéristiques similaires en clusters et prédit l’achat de bicyclettes pour chaque cluster.</span><span class="sxs-lookup"><span data-stu-id="61c17-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="61c17-115">Bien que vous puissiez modifier l’utilisation des colonnes et les propriétés du nouveau modèle, aucune modification du `TM_Clustering` modèle n’est nécessaire pour ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="61c17-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="61c17-116">Pour créer un modèle d'exploration de données Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="61c17-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="61c17-117">Sous l’onglet **modèles d’exploration** de données du concepteur d’exploration de données, cliquez avec le bouton droit sur la colonne de **structure** clickthe, puis sélectionnez **nouveau modèle d’exploration**de données.</span><span class="sxs-lookup"><span data-stu-id="61c17-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="61c17-118">Dans la boîte de dialogue **nouveau modèle d’exploration de données** , sous **nom du modèle**, tapez `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="61c17-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="61c17-119">Dans **nom de l’algorithme**, sélectionnez **Microsoft Naive Bayes**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="61c17-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="61c17-120">Un message s’affiche, indiquant que l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme Naive Bayes ne prend pas en charge les colonnes **Age** et **Yearly Income** , qui sont continues.</span><span class="sxs-lookup"><span data-stu-id="61c17-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="61c17-121">Cliquez sur **Oui** pour accuser réception du message et continuer.</span><span class="sxs-lookup"><span data-stu-id="61c17-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="61c17-122">Un nouveau modèle apparaît sous l’onglet **modèles d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="61c17-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="61c17-123">Bien que vous puissiez modifier l’utilisation des colonnes et les propriétés de tous les modèles de cet onglet, aucune modification du `TM_NaiveBayes` modèle n’est nécessaire pour ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="61c17-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="61c17-124">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="61c17-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="61c17-125">Traitement des modèles dans la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="61c17-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="61c17-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61c17-126">See Also</span></span>  
 <span data-ttu-id="61c17-127">[Ajouter des modèles d’exploration de données à une structure &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="61c17-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="61c17-128">[Concepteur d’exploration de données](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="61c17-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="61c17-129">Déplacement d'objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="61c17-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
