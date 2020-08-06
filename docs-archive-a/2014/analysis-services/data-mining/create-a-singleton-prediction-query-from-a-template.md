---
title: Créer une requête singleton de prédiction à partir d’un modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601783"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="8da7c-102">Créer une requête singleton de prédiction à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="8da7c-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="8da7c-103">Une requête singleton est utile lorsque vous avez un modèle que vous souhaitez utiliser pour la prédiction, mais que vous ne souhaitez pas le mapper à un jeu de données d’entrée externe ou effectuer des prédictions en bloc.</span><span class="sxs-lookup"><span data-stu-id="8da7c-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="8da7c-104">Avec une requête singleton, vous pouvez fournir une ou plusieurs valeurs au modèle et immédiatement consulter la valeur prédite.</span><span class="sxs-lookup"><span data-stu-id="8da7c-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="8da7c-105">Par exemple, la requête DMX suivante représente une requête singleton sur le modèle de publipostage ciblé TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="8da7c-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="8da7c-106">La procédure qui suit explique comment utiliser l'Explorateur de modèles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer rapidement cette requête.</span><span class="sxs-lookup"><span data-stu-id="8da7c-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="8da7c-107">Pour ouvrir les modèles Analysis Services dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8da7c-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8da7c-108">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="8da7c-109">Cliquez sur l’icône du cube pour ouvrir les modèles **Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="8da7c-110">Pour ouvrir un modèle de requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="8da7c-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="8da7c-111">Dans la liste de modèles Analysis Server de **l’Explorateur de modèles**, développez **DMX**, puis **Requêtes de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="8da7c-112">Double-cliquez sur **Prédiction singleton**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="8da7c-113">Dans la boîte de dialogue **Se connecter à Analysis Services** , tapez le nom du serveur qui dispose de l'instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenant le modèle d'exploration de données à interroger.</span><span class="sxs-lookup"><span data-stu-id="8da7c-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="8da7c-114">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="8da7c-115">Le modèle s'ouvre dans la base de données spécifiée, avec un modèle d'exploration de données Explorateur d'objets qui contient des fonctions d'exploration de données et une liste de structures d'exploration de données et de modèles connexes.</span><span class="sxs-lookup"><span data-stu-id="8da7c-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="8da7c-116">Pour personnaliser le modèle de requête singleton</span><span class="sxs-lookup"><span data-stu-id="8da7c-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="8da7c-117">Dans le modèle, cliquez sur la liste déroulante **Bases de données disponibles** , puis sélectionnez une instance d’Analysis Service dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8da7c-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="8da7c-118">Dans la liste **Modèle d'exploration de données** , sélectionnez le modèle d'exploration de données à interroger.</span><span class="sxs-lookup"><span data-stu-id="8da7c-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="8da7c-119">La liste des colonnes dans le modèle d'exploration de données s'affiche dans le volet **Métadonnées** de l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="8da7c-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="8da7c-120">Dans le menu **Requête** , sélectionnez **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="8da7c-121">Dans la ligne **liste de sélection** , tapez \* pour retourner toutes les colonnes, ou tapez une liste de colonnes et d’expressions délimitée par des virgules pour retourner des colonnes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8da7c-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="8da7c-122">Si vous tapez \*, la colonne prédictible est retournée, ainsi que toutes les colonnes auxquelles vous fournissez de nouvelles valeurs à l'étape 6.</span><span class="sxs-lookup"><span data-stu-id="8da7c-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="8da7c-123">Pour l’exemple de code présenté au début de cette rubrique, la ligne de **liste de sélection** a la valeur \*.</span><span class="sxs-lookup"><span data-stu-id="8da7c-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="8da7c-124">Dans la ligne **modèle d'exploration de données** , tapez le nom du modèle d'exploration de données extrait de la liste des modèles d'exploration de données qui apparaissent dans l' **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="8da7c-125">Pour l’exemple de code présenté au début de cette rubrique, la ligne du **modèle d’exploration de données** a été définie sur le nom, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="8da7c-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="8da7c-126">Dans la ligne **valeur** , tapez la nouvelle valeur des données pour lesquelles vous souhaitez effectuer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="8da7c-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="8da7c-127">Pour l’exemple de code présenté au début de cette rubrique, la ligne **valeur** a été définie sur `2` pour prédire le comportement d’achat de vélo en fonction du nombre d’enfants à la base.</span><span class="sxs-lookup"><span data-stu-id="8da7c-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="8da7c-128">Dans la ligne **colonne** , tapez le nom de la colonne du modèle d'exploration de données à laquelle les nouvelles données doivent être mappées.</span><span class="sxs-lookup"><span data-stu-id="8da7c-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="8da7c-129">Pour l’exemple de code présenté au début de cette rubrique, la ligne de la **colonne** a la valeur `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="8da7c-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8da7c-130">Lorsque vous utilisez la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** , vous n'avez pas besoin de mettre le nom de colonne entre crochets.</span><span class="sxs-lookup"><span data-stu-id="8da7c-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="8da7c-131">Les crochets seront ajoutés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="8da7c-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="8da7c-132">Laissez l' **alias d’entrée** sous la forme `t` .</span><span class="sxs-lookup"><span data-stu-id="8da7c-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="8da7c-133">Dans le volet de texte de requête, recherchez le tilde rouge sous la virgule et les points de suspension qui indiquent une erreur de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="8da7c-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="8da7c-134">Supprimez les points de suspension et ajoutez une condition de requête supplémentaire de votre choix.</span><span class="sxs-lookup"><span data-stu-id="8da7c-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="8da7c-135">Si vous n'ajoutez pas d'autres conditions, supprimez la virgule.</span><span class="sxs-lookup"><span data-stu-id="8da7c-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="8da7c-136">Dans l’exemple de code présenté au début de cette rubrique, la condition de requête supplémentaire a la valeur `'45' as [Age]`.</span><span class="sxs-lookup"><span data-stu-id="8da7c-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="8da7c-137">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8da7c-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da7c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8da7c-138">See Also</span></span>  
 [<span data-ttu-id="8da7c-139">Création de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="8da7c-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
