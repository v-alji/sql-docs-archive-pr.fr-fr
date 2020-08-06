---
title: Modification et traitement du modèle Market Basket (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600413"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="601d1-102">Modification et traitement du modèle de panier d'achat (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="601d1-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="601d1-103">Avant de traiter le modèle d’exploration de données d’association que vous avez créé, vous devez modifier les valeurs par défaut de deux des paramètres : *support* et *probabilité*.</span><span class="sxs-lookup"><span data-stu-id="601d1-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="601d1-104">La *prise en charge* définit le pourcentage de cas dans lesquels une règle doit exister avant d’être considérée comme valide.</span><span class="sxs-lookup"><span data-stu-id="601d1-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="601d1-105">Vous allez spécifier qu'une règle doit être présente dans au moins 1 pour cent des cas.</span><span class="sxs-lookup"><span data-stu-id="601d1-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="601d1-106">La probabilité définit la *probabilité* d’une association avant qu’elle soit considérée comme valide.</span><span class="sxs-lookup"><span data-stu-id="601d1-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="601d1-107">Vous prendrez en compte toute association ayant une probabilité d'au moins 10 pour cent.</span><span class="sxs-lookup"><span data-stu-id="601d1-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="601d1-108">Pour plus d’informations sur les effets de l’augmentation ou de la réduction de la prise en charge et de la probabilité, consultez informations techniques de référence sur l' [algorithme Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="601d1-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="601d1-109">Une fois que vous avez défini la structure et les paramètres du modèle d’exploration de données d' **Association** , vous devez traiter le modèle.</span><span class="sxs-lookup"><span data-stu-id="601d1-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="601d1-110">Pour modifier les paramètres du modèle d'association</span><span class="sxs-lookup"><span data-stu-id="601d1-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="601d1-111">Ouvrez l’onglet **modèles d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="601d1-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="601d1-112">Cliquez avec le bouton droit sur la colonne **Association** dans la grille du concepteur et sélectionnez **définir les paramètres d’algorithme pour ouvrir la boîte de dialogue Paramètres d’algorithme** .</span><span class="sxs-lookup"><span data-stu-id="601d1-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="601d1-113">Dans la colonne **valeur** de la boîte de dialogue **paramètres d’algorithme** , définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="601d1-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="601d1-114">MINIMUM_PROBABILITY = 0.1</span><span class="sxs-lookup"><span data-stu-id="601d1-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="601d1-115">MINIMUM_SUPPORT = 0.01</span><span class="sxs-lookup"><span data-stu-id="601d1-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="601d1-116">Pour traiter le modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="601d1-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="601d1-117">Dans le menu **modèle d’exploration de données** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , sélectionnez **traiter l’exploration de données et tous les modèles.**</span><span class="sxs-lookup"><span data-stu-id="601d1-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="601d1-118">Cliquez sur **Oui**pour répondre à l'avertissement qui vous invite à indiquer si vous souhaitez générer et déployer le projet.</span><span class="sxs-lookup"><span data-stu-id="601d1-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="601d1-119">La boîte **de dialogue traiter la structure d’exploration de données-Association** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="601d1-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="601d1-120">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="601d1-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="601d1-121">La boîte de dialogue **État d'avancement du traitement** s'affiche et présente les informations relatives au traitement du modèle.</span><span class="sxs-lookup"><span data-stu-id="601d1-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="601d1-122">Le traitement de la nouvelle structure et du nouveau modèle peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="601d1-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="601d1-123">Une fois le traitement terminé, cliquez sur **Fermer** pour quitter la boîte de dialogue **État d'avancement du traitement** .</span><span class="sxs-lookup"><span data-stu-id="601d1-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="601d1-124">Cliquez à nouveau sur **Fermer** pour quitter la boîte de dialogue **traiter la structure d’exploration de données-Association** .</span><span class="sxs-lookup"><span data-stu-id="601d1-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="601d1-125">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="601d1-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="601d1-126">Exploration des modèles de panier d’évolution &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="601d1-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="601d1-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="601d1-127">See Also</span></span>  
 [<span data-ttu-id="601d1-128">Exigences et considérations concernant le traitement &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="601d1-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
