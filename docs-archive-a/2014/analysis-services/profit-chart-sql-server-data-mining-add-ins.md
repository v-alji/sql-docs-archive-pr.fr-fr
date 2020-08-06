---
title: Graphique des bénéfices (compléments d’exploration de données SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605747"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="e8bed-102">Graphique des bénéfices (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e8bed-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="e8bed-103">![Bouton Graphique des bénéfices sur le ruban Exploration de données](media/dmc-profitchart.gif "Bouton Graphique des bénéfices sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="e8bed-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="e8bed-104">Un graphique des bénéfices représente l'augmentation de bénéfices estimée qui est associée à l'utilisation d'un modèle d'exploration de données pour déterminer les clients qu'une entreprise doit contacter dans un scénario professionnel.</span><span class="sxs-lookup"><span data-stu-id="e8bed-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="e8bed-105">L'axe Y du graphique représente les bénéfices, tandis que l'axe X représente le pourcentage de la population que l'entreprise a contactée.</span><span class="sxs-lookup"><span data-stu-id="e8bed-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="e8bed-106">Un graphique des bénéfices classique montre une augmentation des bénéfices jusqu'à un certain point, après lequel les bénéfices diminuent plus le nombre d'individus contactés augmente.</span><span class="sxs-lookup"><span data-stu-id="e8bed-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="e8bed-107">Configuration du graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="e8bed-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="e8bed-108">Si le graphique d'analyse évalue uniquement la probabilité de la validité ou non des prédictions, le graphique des bénéfices intègre des données concrètes sur les conséquences liées à la mise en œuvre d'une prédiction.</span><span class="sxs-lookup"><span data-stu-id="e8bed-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="e8bed-109">Cette opération est possible en prenant en compte les facteurs suivants que vous spécifiez lors de l'exécution de l'Assistant : </span><span class="sxs-lookup"><span data-stu-id="e8bed-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="e8bed-110">**Habitants**</span><span class="sxs-lookup"><span data-stu-id="e8bed-110">**Population**</span></span>  
  
     <span data-ttu-id="e8bed-111">Nombre de cas dans le jeu de données qui est utilisé pour créer le graphique de courbes d'élévation.</span><span class="sxs-lookup"><span data-stu-id="e8bed-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="e8bed-112">Par exemple, le nombre de clients potentiels.</span><span class="sxs-lookup"><span data-stu-id="e8bed-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="e8bed-113">**Coût fixe**</span><span class="sxs-lookup"><span data-stu-id="e8bed-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="e8bed-114">Coût fixe associé au problème professionnel.</span><span class="sxs-lookup"><span data-stu-id="e8bed-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="e8bed-115">En ce qui concerne une solution de publipostage ciblé, le coût ne dépend pas de variables telles que le nombre d'appels téléphoniques effectués ou le nombre de courriers publicitaires de publipostage envoyés.</span><span class="sxs-lookup"><span data-stu-id="e8bed-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="e8bed-116">**Coût individuel**</span><span class="sxs-lookup"><span data-stu-id="e8bed-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="e8bed-117">Coûts s'ajoutant au coût fixe, qui peuvent être associés à chaque client contacté.</span><span class="sxs-lookup"><span data-stu-id="e8bed-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="e8bed-118">Par exemple, les courriers publicitaires de publipostage ou les appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="e8bed-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="e8bed-119">**Revenu par personne**</span><span class="sxs-lookup"><span data-stu-id="e8bed-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="e8bed-120">Revenu associé à chaque vente réussie.</span><span class="sxs-lookup"><span data-stu-id="e8bed-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="e8bed-121">Utilisation de l'Assistant Graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="e8bed-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="e8bed-122">Pour créer un graphique des bénéfices, vous devez référencer un modèle d'exploration de données existant.</span><span class="sxs-lookup"><span data-stu-id="e8bed-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="e8bed-123">Vous pouvez parcourir les modèles pour trouver un modèle qui correspond à vos données en cliquant sur **gérer les modèles** ou sur **Parcourir** pour afficher des détails sur l’algorithme utilisé et les colonnes du modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e8bed-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="e8bed-124">Pour plus d’informations, consultez [parcours des modèles dans Excel &#40;SQL Server des compléments d’exploration de données&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) et [gérer des modèles &#40;SQL Server compléments d’exploration de données&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e8bed-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="e8bed-125">Pour créer un graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="e8bed-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="e8bed-126">Sélectionnez un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="e8bed-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="e8bed-127">Spécifiez la colonne à prévoir et une valeur cible, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e8bed-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="e8bed-128">Sélectionnez les données source qui sont les données transmises par le modèle pour créer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="e8bed-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="e8bed-129">Vous pouvez ainsi explorer les mêmes données utilisées pour créer le modèle.</span><span class="sxs-lookup"><span data-stu-id="e8bed-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="e8bed-130">Mappez les colonnes dans la nouvelle date (source) aux colonnes utilisées dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e8bed-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="e8bed-131">Si les noms de colonne sont similaires, l'Assistant les mappe automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e8bed-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="e8bed-132">Entrez les informations de coût requises par l'Assistant : le coût fixe, le coût individuel, le remplissage et le revenu attendu.</span><span class="sxs-lookup"><span data-stu-id="e8bed-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="e8bed-133">Si vous le souhaitez, vous pouvez entrer une série de coûts graduée (cliquez sur le bouton Parcourir **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="e8bed-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="e8bed-134">Par exemple, vous pouvez abaisser les coûts d'un publipostage en augmentant le nombre d'éléments envoyés, ce qui vous permet d'entrer un coût différent selon le nombre d'éléments, l'Assistant ajuste automatiquement les coûts pour chaque taille d'échantillon.</span><span class="sxs-lookup"><span data-stu-id="e8bed-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="e8bed-135">L'Assistant crée un graphique qui inclut l'analyse coût-bénéfice du modèle.</span><span class="sxs-lookup"><span data-stu-id="e8bed-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="e8bed-136">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e8bed-136">Requirements</span></span>  
 <span data-ttu-id="e8bed-137">Si vous prévoyez une valeur numérique discrète, vous devez sélectionner la valeur cible exacte à prévoir.</span><span class="sxs-lookup"><span data-stu-id="e8bed-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="e8bed-138">Fonctionnement du graphique des bénéfices</span><span class="sxs-lookup"><span data-stu-id="e8bed-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="e8bed-139">Le graphique des bénéfices contient une ligne verticale grise que vous pouvez déplacer en cliquant à un emplacement dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="e8bed-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="e8bed-140">La **légende d’exploration de données** affiche un score, le remplissage correct et la probabilité de prédiction associée à l’emplacement de la ligne grise sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="e8bed-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="e8bed-141">Si vous sélectionnez le point des bénéfices maximaux dans le graphique en utilisant la ligne grise, vous pouvez utiliser la valeur de probabilité de prédiction pour déterminer un seuil de probabilité lié au fait de contacter un client.</span><span class="sxs-lookup"><span data-stu-id="e8bed-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="e8bed-142">Par exemple, si le sommet de la courbe des bénéfices se trouve à 55 % de remplissage et que la probabilité de prédiction associée est de 20 %, cela indique que pour réaliser des bénéfices maximaux, vous devez contacter uniquement les clients dont la réponse est prévue avec une probabilité de 20 % ou plus.</span><span class="sxs-lookup"><span data-stu-id="e8bed-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bed-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8bed-143">See Also</span></span>  
 [<span data-ttu-id="e8bed-144">Validation des modèles et utilisation de modèles pour la prédiction &#40;compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e8bed-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
