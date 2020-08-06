---
title: Assistant cluster (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603136"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="8dceb-102">Assistant Cluster (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="8dceb-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="8dceb-103">![Assistant Cluster sur le ruban Exploration de données](media/dmc-cluster.gif "Assistant Cluster sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="8dceb-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="8dceb-104">L'Assistant Cluster vous aide à créer un modèle de clustering qui détecte les lignes partageant des caractéristiques similaires et les regroupe pour maximiser la distance entre les groupes.</span><span class="sxs-lookup"><span data-stu-id="8dceb-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="8dceb-105">Cet Assistant permet de rechercher des séquences dans tous les types de données.</span><span class="sxs-lookup"><span data-stu-id="8dceb-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="8dceb-106">L'Assistant Cluster utilise l'algorithme de gestion de clusters Microsoft et peut être largement personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8dceb-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="8dceb-107">Il fonctionne sur des données existantes à partir d'une table Excel, d'une plage Excel ou d'une requête [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dceb-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="8dceb-108">Les fonctionnalités similaires sont fournies par l’outil [détecter les catégories](detect-categories-table-analysis-tools-for-excel.md) , fourni dans les outils d’analyse de table pour Excel.</span><span class="sxs-lookup"><span data-stu-id="8dceb-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="8dceb-109">Toutefois, l'outil Détecter les catégories ne peut pas être personnalisé et doit utiliser les données de tables Excel.</span><span class="sxs-lookup"><span data-stu-id="8dceb-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="8dceb-110">Utilisation de l'Assistant Cluster</span><span class="sxs-lookup"><span data-stu-id="8dceb-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="8dceb-111">Dans le ruban exploration de données, cliquez sur **cluster**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="8dceb-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="8dceb-112">Dans la page **Sélectionner les données source** , sélectionnez une table ou une plage Excel.</span><span class="sxs-lookup"><span data-stu-id="8dceb-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="8dceb-113">Ou spécifiez une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="8dceb-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="8dceb-114">Si vous utilisez une source de données externe, vous pouvez créer des vues personnalisées ou coller un texte de requête personnalisée, et enregistrer le jeu de données en tant que source de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dceb-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="8dceb-115">Sur la page **clustering** , vous pouvez personnaliser la façon dont le modèle est généré.</span><span class="sxs-lookup"><span data-stu-id="8dceb-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="8dceb-116">Pour le **nombre de segments**, vous pouvez indiquer à l’Assistant de créer un nombre fixe de catégories ou le laisser détecter automatiquement le nombre optimal de regroupements.</span><span class="sxs-lookup"><span data-stu-id="8dceb-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="8dceb-117">Passez en revue la liste des colonnes dans la liste **colonnes d’entrée** , puis désélectionnez les colonnes qui ne sont pas utiles pour créer des modèles.</span><span class="sxs-lookup"><span data-stu-id="8dceb-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="8dceb-118">Les colonnes à exclure comprennent les numéros d'ID, les noms des clients, etc.</span><span class="sxs-lookup"><span data-stu-id="8dceb-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="8dceb-119">Si vous le souhaitez, cliquez sur **paramètres** pour modifier les paramètres d’algorithme et personnaliser le comportement du modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="8dceb-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="8dceb-120">Dans la page **fractionner les données en jeux d’apprentissage et jeux de test** , spécifiez la quantité de données à conserver pour le test.</span><span class="sxs-lookup"><span data-stu-id="8dceb-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="8dceb-121">Le reste est toujours utilisé pour l'apprentissage du modèle.</span><span class="sxs-lookup"><span data-stu-id="8dceb-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="8dceb-122">Le paramètre par défaut est 30 % de données de test et 70 % de données de formation.</span><span class="sxs-lookup"><span data-stu-id="8dceb-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="8dceb-123">Dans la page **Terminer** , indiquez un nom descriptif pour votre jeu de données et votre modèle, puis définissez les options suivantes qui contrôlent la façon dont vous travaillez avec le modèle terminé :</span><span class="sxs-lookup"><span data-stu-id="8dceb-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="8dceb-124">**Parcourir le modèle**.</span><span class="sxs-lookup"><span data-stu-id="8dceb-124">**Browse model**.</span></span> <span data-ttu-id="8dceb-125">Lorsque cette option est sélectionnée, dès que l’Assistant a terminé de traiter le modèle, il ouvre une fenêtre **Parcourir** pour vous aider à explorer les résultats.</span><span class="sxs-lookup"><span data-stu-id="8dceb-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="8dceb-126">Le contenu de la visionneuse dépend du type de modèle que vous créez.</span><span class="sxs-lookup"><span data-stu-id="8dceb-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="8dceb-127">Pour plus d’informations, consultez [exploration d’un modèle de clustering](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="8dceb-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="8dceb-128">**Activer l’extraction**.</span><span class="sxs-lookup"><span data-stu-id="8dceb-128">**Enable drillthrough**.</span></span> <span data-ttu-id="8dceb-129">Sélectionnez cette option pour examiner les données sous-jacentes du modèle terminé.</span><span class="sxs-lookup"><span data-stu-id="8dceb-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="8dceb-130">Cette option est disponible uniquement si vous créez un modèle d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="8dceb-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="8dceb-131">**Utilisez le modèle temporaire**.</span><span class="sxs-lookup"><span data-stu-id="8dceb-131">**Use temporary model**.</span></span> <span data-ttu-id="8dceb-132">Si cette option est sélectionnée, le modèle ne sera pas enregistré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="8dceb-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="8dceb-133">Lorsque vous fermez Excel, les modèles temporaires sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="8dceb-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="8dceb-134">Pour plus d'informations sur les modèles de clustering</span><span class="sxs-lookup"><span data-stu-id="8dceb-134">More about Clustering Models</span></span>  
 <span data-ttu-id="8dceb-135">Vous pouvez modifier l’algorithme de clustering utilisé par cet Assistant en cliquant sur **avancé** et en utilisant la boîte de dialogue **paramètres d’algorithme** .</span><span class="sxs-lookup"><span data-stu-id="8dceb-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="8dceb-136">L'algorithme de gestion de clusters Microsoft fournit les méthodes de clustering suivantes :</span><span class="sxs-lookup"><span data-stu-id="8dceb-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="8dceb-137">K-means - évolutif ou non évolutif.</span><span class="sxs-lookup"><span data-stu-id="8dceb-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="8dceb-138">EM (Expectation Maximization) - évolutif ou non évolutif.</span><span class="sxs-lookup"><span data-stu-id="8dceb-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="8dceb-139">Vous pouvez également utiliser le paramètre CLUSTER_SEED pour contrôler la valeur de départ et vous assurer que les modèles répétés utilisant le même jeu de données ont les mêmes résultats.</span><span class="sxs-lookup"><span data-stu-id="8dceb-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="8dceb-140">Spécifications</span><span class="sxs-lookup"><span data-stu-id="8dceb-140">Requirements</span></span>  
 <span data-ttu-id="8dceb-141">Pour utiliser l'Assistant Cluster, vous devez être connecté à une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dceb-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="8dceb-142">Pour plus d’informations, consultez [se connecter à des données sources &#40;client d’exploration de données pour Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8dceb-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dceb-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8dceb-143">See Also</span></span>  
 <span data-ttu-id="8dceb-144">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="8dceb-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="8dceb-145">Détecter les catégories &#40;les outils d’analyse de table pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8dceb-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
