---
title: Création d’un modèle Sequence Clustering associé (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703567"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="208d1-102">Création d'un modèle Sequence Clustering associé (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="208d1-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="208d1-103">Au cours de votre exploration du modèle Sequence Clustering, vous avez appris que d'autres attributs tels que Region ou Income ont de fortes répercussions sur les modèles ; par conséquent, pour mieux comprendre les séquences, vous allez créer un modèle Sequence Clustering associé et supprimer les attributs en rapport avec les caractéristiques démographiques des clients.</span><span class="sxs-lookup"><span data-stu-id="208d1-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="208d1-104">Au cours de cette tâche, vous allez créer une copie du modèle Sequence Clustering régional, puis supprimer du modèle toutes les colonnes qui ne sont pas directement en rapport avec les séquences.</span><span class="sxs-lookup"><span data-stu-id="208d1-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="208d1-105">Le nouveau modèle va contenir les mêmes colonnes que le modèle d'exploration de données sur lequel il se base.</span><span class="sxs-lookup"><span data-stu-id="208d1-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="208d1-106">Toutefois, vous n'avez pas besoin de supprimer les colonnes de la structure d'exploration de données ; spécifiez simplement que le nouveau modèle d'exploration de données ignore ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="208d1-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="208d1-107">Pour faire une copie du modèle Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="208d1-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="208d1-108">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , dans le concepteur d’exploration de données, cliquez sur l’onglet **modèles d’exploration** de données.</span><span class="sxs-lookup"><span data-stu-id="208d1-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="208d1-109">Cliquez avec le bouton droit sur le modèle que vous souhaitez copier, puis sélectionnez **nouveau modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="208d1-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="208d1-110">Dans la boîte de dialogue **nouveau modèle d’exploration de données** , tapez un nom de modèle, puis sélectionnez Microsoft `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="208d1-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="208d1-111">Pour ce didacticiel, tapez le nom `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="208d1-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="208d1-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="208d1-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="208d1-113">Pour supprimer des colonnes du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="208d1-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="208d1-114">Dans l’onglet **modèle d’exploration de données** , dans la colonne du nouveau modèle nommé Sequence Clustering, cliquez sur la ligne correspondant à l’attribut **revenu Group** , puis sélectionnez **Ignorer**.</span><span class="sxs-lookup"><span data-stu-id="208d1-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="208d1-115">Répétez cette étape pour la **région**d’attribut.</span><span class="sxs-lookup"><span data-stu-id="208d1-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="208d1-116">Cliquez sur le signe plus (+) en regard du nom de la table, **v Assoc SEQ Line Items**, pour développer la table et afficher les colonnes de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="208d1-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="208d1-117">Le nouveau modèle doit comporter uniquement les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="208d1-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="208d1-118">**NumberKey de commande**</span><span class="sxs-lookup"><span data-stu-id="208d1-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="208d1-119">**Clé de numéro de ligne**</span><span class="sxs-lookup"><span data-stu-id="208d1-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="208d1-120">**Prédiction de modèle**</span><span class="sxs-lookup"><span data-stu-id="208d1-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="208d1-121">Pour traiter le nouveau modèle Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="208d1-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="208d1-122">Sous l’onglet **modèle d’exploration de données** , cliquez avec le bouton droit sur le nouveau modèle nommé `Sequence Clustering` , puis sélectionnez **traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="208d1-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="208d1-123">Étant donné que le nouveau modèle d'exploration de données simplifié est basé sur une structure qui a déjà été traitée, vous n'avez pas besoin de retraiter la structure.</span><span class="sxs-lookup"><span data-stu-id="208d1-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="208d1-124">Vous pouvez traiter simplement le nouveau modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="208d1-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="208d1-125">Cliquez sur **Oui** pour déployer le projet d’exploration de données mis à jour sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="208d1-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="208d1-126">Dans la boîte de dialogue **traiter le modèle d’exploration de données** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="208d1-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="208d1-127">Cliquez sur **Fermer** pour fermer la boîte de dialogue **État d’avancement du traitement** , puis cliquez de nouveau sur **Fermer** dans la boîte de dialogue traiter le modèle d' **exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="208d1-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="208d1-128">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="208d1-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="208d1-129">Création de prédictions sur un modèle Sequence Clustering &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="208d1-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="208d1-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="208d1-130">See Also</span></span>  
 [<span data-ttu-id="208d1-131">Exigences et considérations concernant le traitement &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="208d1-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
