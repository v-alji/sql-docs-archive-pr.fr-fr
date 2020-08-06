---
title: Utilisation de l’extraction sur les données de structure (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600370"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="62314-102">Utilisation de l'extraction sur les données de structure (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="62314-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="62314-103">Dans le cadre de leur campagne de publicité, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] envoie un courrier de publipostage à des clients potentiels dans la tranche d'âge 34-40 ans.</span><span class="sxs-lookup"><span data-stu-id="62314-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="62314-104">Le service marketing souhaite également adresser ce courrier aux clients ayant acheté des vélos dans [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] il y a plus de cinq ans.</span><span class="sxs-lookup"><span data-stu-id="62314-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="62314-105">Dans cette leçon vous allez identifier les clients ayant des vélos anciens et extraire leurs informations de contact.</span><span class="sxs-lookup"><span data-stu-id="62314-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="62314-106">Ces informations ne sont pas incluses dans le modèle, mais sont incluses dans la structure.</span><span class="sxs-lookup"><span data-stu-id="62314-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="62314-107">Pour extraire les informations de contact, vous allez d'abord vérifier que l'extraction est activée pour la structure puis vous utiliserez l'extraction pour extraire les noms et adresses des clients ciblés.</span><span class="sxs-lookup"><span data-stu-id="62314-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="62314-108">Pour activer l'extraction sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="62314-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="62314-109">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans l'onglet **Modèles d'exploration de données** du Concepteur d'exploration de données, cliquez avec le bouton droit sur le modèle **TM_Decision_Tree** , et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="62314-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="62314-110">Dans les fenêtres Propriétés, cliquez sur **AllowDrillthrough**et sélectionnez **True**.</span><span class="sxs-lookup"><span data-stu-id="62314-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="62314-111">Sous l'onglet Modèles d'exploration de données, cliquez avec le bouton droit sur le modèle et sélectionnez **Traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="62314-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="62314-112">Pour plus d’informations, consultez [requêtes d’extraction &#40;exploration de données&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="62314-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="62314-113">Pour afficher des données d'extraction à partir d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="62314-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="62314-114">Dans le Concepteur d'exploration de données, cliquez sur l'onglet **Visionneuse de modèle d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="62314-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="62314-115">Sélectionnez le modèle **TM_Decision_Tree** dans la liste **Modèle d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="62314-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="62314-116">Remplacez la valeur d' **arrière-plan** par `1` .</span><span class="sxs-lookup"><span data-stu-id="62314-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="62314-117">Ce faisant, vous affichez uniquement la partie du modèle qui est associée au client qui a acheté des vélos.</span><span class="sxs-lookup"><span data-stu-id="62314-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="62314-118">Sélectionnez la Visionneuse d'arborescences Microsoft dans la liste **Visionneuse** .</span><span class="sxs-lookup"><span data-stu-id="62314-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="62314-119">Cela force la visionneuse à actualiser avec les nouvelles conditions de filtre.</span><span class="sxs-lookup"><span data-stu-id="62314-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="62314-120">Localisez ensuite le nœud **Age >= 34 et <41** , puis cliquez avec le bouton droit sur le nœud.</span><span class="sxs-lookup"><span data-stu-id="62314-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="62314-121">Sélectionnez **Extraire**, puis sélectionnez **Colonnes de structure et de modèle** pour ouvrir la fenêtre **Extraire** .</span><span class="sxs-lookup"><span data-stu-id="62314-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="62314-122">Faites défiler jusqu'à la colonne **Structure.Date First Purchase** pour consulter les dates d'achat pour les vélos anciens.</span><span class="sxs-lookup"><span data-stu-id="62314-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="62314-123">Pour copier les données vers le Presse-papiers, cliquez avec le bouton droit sur une ligne dans la table et sélectionnez **Copier tout**.</span><span class="sxs-lookup"><span data-stu-id="62314-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="62314-124">Félicitations, vous avez terminé le didacticiel sur l'exploration de données de base.</span><span class="sxs-lookup"><span data-stu-id="62314-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="62314-125">Maintenant que vous maîtrisez les outils d'exploration de données, nous vous recommandons de compléter également le didacticiel intermédiaire sur l'exploration de données qui montre comment créer des modèles pour la prévision, l'analyse du panier d'achat et Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="62314-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="62314-126">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="62314-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="62314-127">Création de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="62314-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="62314-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62314-128">See Also</span></span>  
 [<span data-ttu-id="62314-129">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="62314-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
