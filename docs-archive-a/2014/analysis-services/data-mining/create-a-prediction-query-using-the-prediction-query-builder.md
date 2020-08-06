---
title: Créer une requête de prédiction à l’aide de la prédiction Générateur de requêtes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601784"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="9d144-102">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="9d144-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="9d144-103">Vous pouvez créer des requêtes de prédiction soit quand vous générez une solution d’exploration de données dans BI Development Studio, soit en cliquant avec le bouton droit sur un modèle d’exploration de données existant dans SQL Server Management Studio, puis en choisissant l’option **Générer une requête de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="9d144-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="9d144-104">Le **Générateur de requêtes de prédiction** dispose des trois modes de création suivants, que vous pouvez utiliser tour à tour en cliquant sur les icônes dans l’angle supérieur gauche.</span><span class="sxs-lookup"><span data-stu-id="9d144-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="9d144-105">**Concevez**</span><span class="sxs-lookup"><span data-stu-id="9d144-105">**Design**</span></span>  
  
-   <span data-ttu-id="9d144-106">**Requête**</span><span class="sxs-lookup"><span data-stu-id="9d144-106">**Query**</span></span>  
  
-   <span data-ttu-id="9d144-107">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="9d144-107">**Result**</span></span>  
  
 <span data-ttu-id="9d144-108">Le mode**Création** vous permet de générer une requête de prédiction en choisissant des données d’entrée, en mappant les données au modèle, puis en ajoutant des fonctions de prédiction dans les instructions que vous créez à l’aide de la grille.</span><span class="sxs-lookup"><span data-stu-id="9d144-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="9d144-109">La grille de création contient ces blocs de construction :</span><span class="sxs-lookup"><span data-stu-id="9d144-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="9d144-110">**Source**</span><span class="sxs-lookup"><span data-stu-id="9d144-110">**Source**</span></span>  
 <span data-ttu-id="9d144-111">Choisissez la source de la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="9d144-111">Choose the source of the new column.</span></span> <span data-ttu-id="9d144-112">Vous pouvez utiliser des colonnes du modèle d'exploration de données, les tables d'entrée incluses dans la vue de source de données, une fonction de prédiction ou une expression personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9d144-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="9d144-113">**Champ**</span><span class="sxs-lookup"><span data-stu-id="9d144-113">**Field**</span></span>  
 <span data-ttu-id="9d144-114">Détermine la colonne ou la fonction spécifique associée à la sélection dans la colonne **Source** .</span><span class="sxs-lookup"><span data-stu-id="9d144-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="9d144-115">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9d144-115">**Alias**</span></span>  
 <span data-ttu-id="9d144-116">Détermine comment la colonne doit être nommée dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="9d144-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="9d144-117">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="9d144-117">**Show**</span></span>  
 <span data-ttu-id="9d144-118">Détermine si la sélection dans la colonne **Source** doit être affichée dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="9d144-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="9d144-119">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="9d144-119">**Group**</span></span>  
 <span data-ttu-id="9d144-120">Utilise la colonne **et/ou** pour grouper des expressions à l’aide de parenthèses.</span><span class="sxs-lookup"><span data-stu-id="9d144-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="9d144-121">Par exemple, (expr1 ou expr2) et expr3.</span><span class="sxs-lookup"><span data-stu-id="9d144-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="9d144-122">**Et/ou**</span><span class="sxs-lookup"><span data-stu-id="9d144-122">**And/Or**</span></span>  
 <span data-ttu-id="9d144-123">Crée une logique dans la requête.</span><span class="sxs-lookup"><span data-stu-id="9d144-123">Creates logic in the query.</span></span> <span data-ttu-id="9d144-124">Par exemple, (expr1 ou expr2) et expr3.</span><span class="sxs-lookup"><span data-stu-id="9d144-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="9d144-125">**Critères/Argument**</span><span class="sxs-lookup"><span data-stu-id="9d144-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="9d144-126">Spécifie une condition ou une expression utilisateur qui s'applique à la colonne.</span><span class="sxs-lookup"><span data-stu-id="9d144-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="9d144-127">Vous pouvez faire glisser des colonnes à partir des tables dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="9d144-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="9d144-128">Le mode de**Requête** fournit un éditeur de texte qui vous donne un accès direct au langage DMX (Data Mining Extensions), ainsi qu’une vue des données d’entrée et des colonnes du modèle.</span><span class="sxs-lookup"><span data-stu-id="9d144-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="9d144-129">Quand vous sélectionnez le mode **Requête** , la grille que vous avez utilisée pour définir la requête est remplacée par un éditeur de texte de base.</span><span class="sxs-lookup"><span data-stu-id="9d144-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="9d144-130">Vous pouvez utiliser cet éditeur pour copier et enregistrer les requêtes que vous avez composées, ou pour coller les requêtes DMX existantes et du Presse-papiers, puis pour les exécuter.</span><span class="sxs-lookup"><span data-stu-id="9d144-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="9d144-131">La vue**Résultat** exécute la requête actuelle et affiche les résultats dans une grille.</span><span class="sxs-lookup"><span data-stu-id="9d144-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="9d144-132">Si les données sous-jacentes ont changé et que vous souhaitez réexécuter la requête, cliquez sur le bouton Lecture dans la barre d'état.</span><span class="sxs-lookup"><span data-stu-id="9d144-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="9d144-133">Vous pouvez concevoir une requête d'exploration de données à l'aide d'une combinaison d'outils visuels et de l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="9d144-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="9d144-134">Si vous apportez des modifications à la requête dans l’éditeur de texte et que vous revenez en mode **Création** , toutes les modifications sont perdues et la requête initiale créée par le Générateur de requêtes de prédiction est restaurée. Cette rubrique vous décrit pas à pas comment utiliser le Générateur de requêtes graphiques.</span><span class="sxs-lookup"><span data-stu-id="9d144-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="9d144-135">Pour créer une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="9d144-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="9d144-136">Cliquez sur **Prévision de modèle d’exploration de données** dans le Concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9d144-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="9d144-137">Cliquez sur **Sélectionner un modèle** dans la table **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="9d144-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="9d144-138">La boîte de dialogue **Sélectionner un modèle d’exploration de données** s’ouvre pour afficher toutes les structures d’exploration de données qui existent dans le projet actuel.</span><span class="sxs-lookup"><span data-stu-id="9d144-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="9d144-139">Sélectionnez le modèle pour lequel vous voulez créer une prédiction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d144-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9d144-140">Dans la table **Sélectionner une ou plusieurs tables d’entrée** , cliquez sur **Sélectionner la table de cas**.</span><span class="sxs-lookup"><span data-stu-id="9d144-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="9d144-141">La boîte de dialogue **Sélectionner une table** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="9d144-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="9d144-142">Dans la liste **Source de données** , sélectionnez la source de données qui contient les données pour lesquelles vous voulez créer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="9d144-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="9d144-143">Dans la zone **Nom de la table/vue** , sélectionnez la table qui contient les données pour lesquelles vous voulez créer une prédiction, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d144-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9d144-144">Une fois la table d'entrée sélectionnée, le Générateur de requêtes de prédiction crée un mappage par défaut entre le modèle d'exploration de données et la table d'entrée en fonction des noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="9d144-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="9d144-145">Pour supprimer un mappage, cliquez pour sélectionner la ligne qui lie la colonne de la table **Modèle d’exploration de données** à la colonne associée de la table **Sélectionner une ou plusieurs tables d’entrée** et appuyez sur Suppr.</span><span class="sxs-lookup"><span data-stu-id="9d144-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="9d144-146">Vous pouvez également créer des mappages manuellement. Pour ce faire, cliquez sur une colonne dans la table **Sélectionner une ou plusieurs tables d’entrée** et faites-la glisser vers la colonne correspondante dans la table **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="9d144-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="9d144-147">Ajoutez à la grille Générateur de requêtes de prédiction n'importe quelles combinaisons constituées des trois types d'informations suivants :</span><span class="sxs-lookup"><span data-stu-id="9d144-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="9d144-148">Colonnes prédictibles de la zone **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="9d144-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="9d144-149">Toute combinaison de colonnes d’entrée de la zone **Sélectionner une ou plusieurs tables d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="9d144-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="9d144-150">Fonctions de prédiction</span><span class="sxs-lookup"><span data-stu-id="9d144-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="9d144-151">Exécutez la requête en cliquant sur le premier bouton de la barre d’outils de l’onglet **Prévision de modèle d’exploration de données** et en sélectionnant **Résultat**.</span><span class="sxs-lookup"><span data-stu-id="9d144-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d144-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d144-152">See Also</span></span>  
 <span data-ttu-id="9d144-153">[Créer une requête singleton dans le concepteur d’exploration de données](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9d144-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="9d144-154">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="9d144-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
