---
title: Créer une requête singleton dans le concepteur d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601782"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="a446e-102">créer une requête singleton dans le Concepteur d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="a446e-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="a446e-103">Une requête singleton est utile si vous voulez créer une prédiction pour un seul cas.</span><span class="sxs-lookup"><span data-stu-id="a446e-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="a446e-104">Pour plus d’informations sur les requêtes singleton, consultez [Requêtes d’exploration de données](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a446e-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="a446e-105">Sous l’onglet **Prévision de modèle d’exploration de données** du Concepteur d’exploration de données, vous pouvez créer différents types de requêtes.</span><span class="sxs-lookup"><span data-stu-id="a446e-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="a446e-106">Vous pouvez créer une requête en utilisant le concepteur ou en tapant des instructions DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="a446e-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="a446e-107">Vous pouvez également utiliser le concepteur pour commencer, puis modifier la requête créée en modifiant les instructions DMX ou en ajoutant une clause WHERE ou ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="a446e-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="a446e-108">Pour basculer entre l'affichage de conception de requête et l'affichage du texte de la requête, cliquez sur le premier bouton dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="a446e-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="a446e-109">Lorsque vous vous trouvez dans la vue de texte de requête, vous pouvez afficher le code créé par le Générateur de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="a446e-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="a446e-110">Vous pouvez également exécuter la requête, la modifier et exécuter la requête modifiée.</span><span class="sxs-lookup"><span data-stu-id="a446e-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="a446e-111">Toutefois, la requête modifiée n'est pas conservée si vous réaffichez la vue de conception de requête.</span><span class="sxs-lookup"><span data-stu-id="a446e-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="a446e-112">Le code suivant montre un exemple de requête singleton sur le modèle de publipostage ciblé TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="a446e-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="a446e-113">Les étapes suivantes expliquent comment créer cette requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="a446e-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="a446e-114">Pour créer une requête singleton à l'aide du Concepteur d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="a446e-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="a446e-115">Cliquez sur **Prévision de modèle d’exploration de données** dans le Concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="a446e-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="a446e-116">Cliquez sur **Sélectionner un modèle** dans la table **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="a446e-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="a446e-117">La boîte de dialogue **Sélectionner un modèle d’exploration de données** s’ouvre pour afficher toutes les structures d’exploration de données qui existent dans le projet actuel.</span><span class="sxs-lookup"><span data-stu-id="a446e-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="a446e-118">Sélectionnez le modèle à utiliser pour créer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="a446e-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="a446e-119">Par exemple, pour créer l’exemple de code donné au début de cette rubrique, sélectionnez TM_Decision_Tree, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a446e-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a446e-120">Cliquez sur **Requête singleton** dans la barre d’outils de l’onglet **Prévision de modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="a446e-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="a446e-121">La table **Entrée de requête singleton** s’affiche dans l’onglet avec les colonnes mappées automatiquement aux colonnes de la table **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="a446e-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="a446e-122">Dans la table **Entrée de requête singleton** , sélectionnez les valeurs dans la colonne **Valeur** pour décrire le cas pour lequel vous voulez créer une prévision.</span><span class="sxs-lookup"><span data-stu-id="a446e-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="a446e-123">Par exemple, sélectionnez **2** pour **nombre d’enfants à la résidence**, puis tapez `45` pour **Age**.</span><span class="sxs-lookup"><span data-stu-id="a446e-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="a446e-124">Faites glisser une colonne prévisible de la table **modèle d’exploration de données** vers la colonne **source** au bas de l’onglet. Si vous le souhaitez, vous pouvez taper un alias pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="a446e-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="a446e-125">Par exemple, faites glisser **Bike Buyer** vers la colonne **Source** .</span><span class="sxs-lookup"><span data-stu-id="a446e-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="a446e-126">Ajoutez des fonctions supplémentaires à la requête en sélectionnant **Fonction de prédiction** ou **Expression personnalisée** dans la liste déroulante de la colonne **Source** .</span><span class="sxs-lookup"><span data-stu-id="a446e-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="a446e-127">Par exemple, cliquez sur **Fonction de prédiction**et sélectionnez **PredictProbability**.</span><span class="sxs-lookup"><span data-stu-id="a446e-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="a446e-128">Cliquez sur **Critères/Argument** dans la ligne **PredictProbability** , puis tapez le nom de la colonne à prédire et éventuellement une valeur spécifique à prédire.</span><span class="sxs-lookup"><span data-stu-id="a446e-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="a446e-129">Par exemple, tapez `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="a446e-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="a446e-130">Cliquez sur la zone **Alias** dans la ligne **PredictProbability** , puis tapez un nom pour faire référence à la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="a446e-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="a446e-131">Par exemple, tapez `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="a446e-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="a446e-132">Cliquez sur **Basculer vers l’affichage du résultat de la requête** dans la barre d’outils de l’onglet **Prévision de modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="a446e-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="a446e-133">Un nouvel écran s'affiche avec le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="a446e-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="a446e-134">Pour examiner l’instruction DMX que vous venez de créer, cliquez sur **SQL**.</span><span class="sxs-lookup"><span data-stu-id="a446e-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a446e-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a446e-135">See Also</span></span>  
 [<span data-ttu-id="a446e-136">Requêtes de prédiction &#40;Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="a446e-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
