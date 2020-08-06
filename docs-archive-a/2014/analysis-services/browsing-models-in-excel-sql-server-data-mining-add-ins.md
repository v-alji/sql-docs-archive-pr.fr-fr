---
title: Exploration des modèles dans Excel (compléments d’exploration de données SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602545"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="16de1-102">Exploration des modèles dans Excel (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="16de1-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="16de1-103">![Bouton Parcourir le modèle sur le ruban Exploration de données](media/dmc-browse.gif "Bouton Parcourir le modèle sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="16de1-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="16de1-104">L'exploration visuelle du modèle représente généralement la méthode la plus facile et la plus rapide pour comprendre les règles et les relations découvertes par l'analyse.</span><span class="sxs-lookup"><span data-stu-id="16de1-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="16de1-105">En utilisant le client d'exploration de données pour Excel, vous avez la possibilité de parcourir à la fois les modèles temporaires créés pendant la session Excel active, ainsi que les modèles stockés dans une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16de1-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="16de1-106">Pour parcourir un modèle, sélectionnez un modèle et sa structure associée dans la liste des modèles disponibles ; le complément choisit automatiquement la visionneuse appropriée à l'algorithme d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="16de1-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="16de1-107">Vous pouvez découvrir les tendances les plus intéressantes, filtrer le modèle d'exploration de données terminé et copier des graphiques et des données dans Excel ou Visio.</span><span class="sxs-lookup"><span data-stu-id="16de1-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="16de1-108">Utilisation de l'Assistant Parcourir le modèle</span><span class="sxs-lookup"><span data-stu-id="16de1-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="16de1-109">Cliquez sur l’onglet **exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="16de1-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="16de1-110">Dans le groupe **utilisation du modèle** , cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="16de1-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="16de1-111">Dans la boîte de dialogue **Sélectionner le modèle** , choisissez un modèle d’exploration de données dans la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="16de1-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="16de1-112">L’Assistant ouvre une fenêtre **Parcourir** appropriée au type de modèle que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="16de1-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="16de1-113">Liste des visionneuses d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="16de1-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="16de1-114">En fonction de l’algorithme d’exploration de données que vous avez utilisé lors de la création du modèle, la fenêtre **Parcourir** est légèrement différente.</span><span class="sxs-lookup"><span data-stu-id="16de1-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="16de1-115">Elle peut inclure des graphiques pour faciliter l'interprétation des résultats, des légendes contenant des informations supplémentaires et des contrôles pour interagir avec les données.</span><span class="sxs-lookup"><span data-stu-id="16de1-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="16de1-116">Les rubriques suivantes fournissent des recommandations concernant l'utilisation de chacune des visionneuses, notamment des conseils sur l'interprétation des graphiques complexes, et la manière de modifier, de copier ou d'utiliser les résultats.</span><span class="sxs-lookup"><span data-stu-id="16de1-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="16de1-117">Exploration d'un modèle d'exploration de données Règles d'association</span><span class="sxs-lookup"><span data-stu-id="16de1-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="16de1-118">Exploration d'un modèle de clustering</span><span class="sxs-lookup"><span data-stu-id="16de1-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="16de1-119">Exploration d'un modèle Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="16de1-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="16de1-120">Exploration d'un modèle de prévision</span><span class="sxs-lookup"><span data-stu-id="16de1-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="16de1-121">Navigation dans un modèle Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="16de1-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="16de1-122">Exploration d'un modèle MNN (Microsoft Neural Network)</span><span class="sxs-lookup"><span data-stu-id="16de1-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="16de1-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16de1-123">See Also</span></span>  
 <span data-ttu-id="16de1-124">[Affichage des modèles d’exploration de données dans Visio &#40;les compléments d’exploration de données&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="16de1-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="16de1-125">Gérer les modèles &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="16de1-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
