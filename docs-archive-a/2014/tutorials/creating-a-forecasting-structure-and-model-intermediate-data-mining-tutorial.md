---
title: Création d’une structure et d’un modèle de prévision (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694888"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="bfeec-102">Création d'une structure et d'un modèle de prévision (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="bfeec-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="bfeec-103">Ensuite, vous utiliserez l'Assistant Exploration de données pour créer une nouvelle structure d'exploration de données et un nouveau modèle d'exploration de données basés sur la vue de source de données que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="bfeec-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="bfeec-104">Au cours de cette tâche, vous spécifierez que le modèle d'exploration de données doit utiliser l'algorithme MTS ([!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series).</span><span class="sxs-lookup"><span data-stu-id="bfeec-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="bfeec-105">Pour créer une structure d'exploration de données de prévision</span><span class="sxs-lookup"><span data-stu-id="bfeec-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="bfeec-106">Dans Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , cliquez avec le bouton droit sur **structures d’exploration de données** et sélectionnez **nouvelle structure d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="bfeec-107">Dans la page **Assistant Exploration de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="bfeec-108">Sur la page **Sélectionner la méthode de définition** , vérifiez que **à partir de la base de données relationnelle ou de l’entrepôt de données existant** est sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bfeec-109">Dans la page **créer la structure d’exploration de données** , sous **quelle technique d’exploration de données voulez-vous utiliser ?**, sélectionnez **séries chronologiques Microsoft**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="bfeec-110">Dans la page **Sélectionner une vue de source de données** , sous vues de sources de **données disponibles**, sélectionnez **SalesByRegion**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="bfeec-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="bfeec-112">Dans la page **spécifier les types des tables** , vérifiez que la case à cocher dans la colonne **cas** de la table vTimeSeries est sélectionnée, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="bfeec-113">Dans la page **spécifier les données d’apprentissage** , activez les cases à cocher dans la colonne **clé** pour les colonnes ModelRegion et ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="bfeec-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="bfeec-114">La colonne ReportingDate doit être sélectionnée par défaut, parce que vous avez spécifié cette colonne en tant que clé primaire logique lorsque vous avez créé la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="bfeec-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="bfeec-115">En ajoutant ModelRegion comme deuxième clé, vous indiquez à l'algorithme de créer une série chronologique distincte pour chaque combinaison de modèle et région répertoriée dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="bfeec-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="bfeec-116">Activez les cases à cocher dans les colonnes **d’entrée** et **prévisibles** pour la quantité, la colonne, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="bfeec-117">En sélectionnant **prévisible**, vous indiquez que vous souhaitez créer des prévisions sur les données de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="bfeec-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="bfeec-118">Toutefois, étant donné que vous souhaitez baser les prévisions sur des données passées, vous devez également ajouter la colonne en tant qu'entrée.</span><span class="sxs-lookup"><span data-stu-id="bfeec-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="bfeec-119">Dans la page **spécifier le type de contenu et de données des colonnes**, passez en revue les sélections.</span><span class="sxs-lookup"><span data-stu-id="bfeec-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="bfeec-120">La colonne ModelRegion est désignée en tant que colonne **clé** et la colonne ReportingDate est automatiquement désignée comme colonne **Key Time** .</span><span class="sxs-lookup"><span data-stu-id="bfeec-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="bfeec-121">Il ne peut y avoir qu'une seule occurrence de chaque type de clé.</span><span class="sxs-lookup"><span data-stu-id="bfeec-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="bfeec-122">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="bfeec-123">Dans la page **fin de l’Assistant** , pour nom de la **structure d’exploration de données**, tapez `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="bfeec-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfeec-124">L'option permettant d'activer l'extraction n'est pas disponible pour les modèles de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="bfeec-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="bfeec-125">Dans **nom du modèle d’exploration de données**, tapez `Forecasting` , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="bfeec-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="bfeec-126">Le concepteur d’exploration de données s’ouvre pour afficher la structure d’exploration de données `Forecasting` que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="bfeec-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bfeec-127">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="bfeec-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bfeec-128">Modification de la structure de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="bfeec-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfeec-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bfeec-129">See Also</span></span>  
 <span data-ttu-id="bfeec-130">[Concepteur d’exploration de données](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="bfeec-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="bfeec-131">Algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="bfeec-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
