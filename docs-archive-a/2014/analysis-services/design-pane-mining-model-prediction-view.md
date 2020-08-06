---
title: Volet de conception (vue prévision de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702102"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="bc479-102">Volet Conception (vue Prévision de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="bc479-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="bc479-103">Le volet **Conception** contient le Générateur de requêtes de prédiction qui peut servir à créer des prédictions d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="bc479-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="bc479-104">Vous pouvez concevoir des requêtes de prédiction qui utilisent des tables de données d'entrée d'une vue de source de données, pour générer des prédictions en bloc, ou vous pouvez créer des requêtes singleton de prédiction qui vous permettent de fournir des valeurs individuelles.</span><span class="sxs-lookup"><span data-stu-id="bc479-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="bc479-105">Pour exécuter la requête et afficher les résultats, basculer vers l'affichage du résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="bc479-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="bc479-106">La vue **Requête** affiche la requête DMX (Data Mining Extensions) créée par le Générateur de requêtes de prévision.</span><span class="sxs-lookup"><span data-stu-id="bc479-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="bc479-107">Si vous connaissez DMX, vous pouvez personnaliser cette requête.</span><span class="sxs-lookup"><span data-stu-id="bc479-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc479-108">Si vous apportez des modifications manuelles à la requête, vous perdez les modifications lorsque vous repassez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="bc479-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="bc479-109">Pour enregistrer la requête DMX, vous pouvez copier celle-ci vers le Presse-papiers Windows puis la coller dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="bc479-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="bc479-110">**Pour plus d’informations :** [Requêtes d’exploration de données](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="bc479-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc479-111">Options</span><span class="sxs-lookup"><span data-stu-id="bc479-111">Options</span></span>  
 <span data-ttu-id="bc479-112">**Basculer vers l'affichage du résultat de la requête**</span><span class="sxs-lookup"><span data-stu-id="bc479-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="bc479-113">Sélectionnez cette option pour basculer entre les volets **Conception**, **Requête**et **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="bc479-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="bc479-114">Lorsque vous basculez vers le volet **Résultat** , la requête est exécutée.</span><span class="sxs-lookup"><span data-stu-id="bc479-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="bc479-115">**Enregistrer le résultat de la requête**</span><span class="sxs-lookup"><span data-stu-id="bc479-115">**Save the query result**</span></span>  
 <span data-ttu-id="bc479-116">Ouvre la boîte de dialogue **Enregistrer le résultat de la requête d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="bc479-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="bc479-117">**Requête singleton**</span><span class="sxs-lookup"><span data-stu-id="bc479-117">**Singleton query**</span></span>  
 <span data-ttu-id="bc479-118">Permet la création d'une requête singleton, dans laquelle vous pouvez fournir directement des valeurs pour la requête au lieu d'une table comme source des données connues.</span><span class="sxs-lookup"><span data-stu-id="bc479-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="bc479-119">Le tableau **Sélectionner une ou plusieurs tables d’entrée** est remplacé par un tableau **Entrée de requête singleton** .</span><span class="sxs-lookup"><span data-stu-id="bc479-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="bc479-120">**Actualiser les résultats de la requête**</span><span class="sxs-lookup"><span data-stu-id="bc479-120">**Refresh query results**</span></span>  
 <span data-ttu-id="bc479-121">Traite une nouvelle fois la requête de prévision.</span><span class="sxs-lookup"><span data-stu-id="bc479-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="bc479-122">Cette option est activée uniquement dans le volet **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="bc479-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="bc479-123">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="bc479-123">**Mining Model**</span></span>  
 <span data-ttu-id="bc479-124">Choisissez le modèle d'exploration de données sur lequel vous souhaitez baser vos prévisions.</span><span class="sxs-lookup"><span data-stu-id="bc479-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="bc479-125">**Sélectionner un modèle**</span><span class="sxs-lookup"><span data-stu-id="bc479-125">**Select Model**</span></span>  
 <span data-ttu-id="bc479-126">Ouvre la boîte de dialogue **Sélectionnez un modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="bc479-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="bc479-127">**Sélectionner une ou plusieurs tables d'entrée**</span><span class="sxs-lookup"><span data-stu-id="bc479-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="bc479-128">Affiche les tables d'entrée sélectionnées qui contiennent les données connues sur lesquelles baser les prévisions.</span><span class="sxs-lookup"><span data-stu-id="bc479-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="bc479-129">**Supprimer la table**</span><span class="sxs-lookup"><span data-stu-id="bc479-129">**Delete Table**</span></span>  
 <span data-ttu-id="bc479-130">Supprime la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bc479-130">Deletes the selected table.</span></span> <span data-ttu-id="bc479-131">Ce bouton est désactivé si aucune table n'a été sélectionnée ou si elle n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="bc479-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="bc479-132">**Sélectionner la table de cas**</span><span class="sxs-lookup"><span data-stu-id="bc479-132">**Select Case Table**</span></span>  
 <span data-ttu-id="bc479-133">Ouvre la boîte de dialogue **Sélectionner une table** .</span><span class="sxs-lookup"><span data-stu-id="bc479-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="bc479-134">Ce bouton s'affiche uniquement si aucune table de cas n'a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bc479-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="bc479-135">**Sélectionner la table imbriquée**</span><span class="sxs-lookup"><span data-stu-id="bc479-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="bc479-136">Ouvre la boîte de dialogue **Sélectionner une table** .</span><span class="sxs-lookup"><span data-stu-id="bc479-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="bc479-137">Ce bouton s'affiche uniquement si une table de cas a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bc479-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="bc479-138">Si la structure d'exploration de données associée ne contient pas de table imbriquée, ce bouton est désactivé.</span><span class="sxs-lookup"><span data-stu-id="bc479-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="bc479-139">**Modifier la jointure**</span><span class="sxs-lookup"><span data-stu-id="bc479-139">**Modify Join**</span></span>  
 <span data-ttu-id="bc479-140">Ouvre la boîte de dialogue **Spécifier la jointure imbriquée** .</span><span class="sxs-lookup"><span data-stu-id="bc479-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="bc479-141">Ce bouton est activé uniquement si la table imbriquée est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bc479-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="bc479-142">**Entrée de requête singleton**</span><span class="sxs-lookup"><span data-stu-id="bc479-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="bc479-143">Cette option est activée quand vous sélectionnez le bouton **Requête singleton** .</span><span class="sxs-lookup"><span data-stu-id="bc479-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="bc479-144">Elle contient les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc479-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="bc479-145">Valeur</span><span class="sxs-lookup"><span data-stu-id="bc479-145">Value</span></span>|<span data-ttu-id="bc479-146">Description</span><span class="sxs-lookup"><span data-stu-id="bc479-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc479-147">**Colonne du modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="bc479-147">**Mining Model Column**</span></span>|<span data-ttu-id="bc479-148">Affiche la liste des colonnes du modèle d’exploration de données sélectionné dans la table **Modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="bc479-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="bc479-149">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="bc479-149">**Value**</span></span>|<span data-ttu-id="bc479-150">Sélectionnez une valeur dans la liste qui contient tous les états possibles de la colonne du modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bc479-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="bc479-151">Si la colonne est une colonne de table imbriquée, la boîte de dialogue **Entrée de la table imbriquée** s’ouvre quand vous cliquez dans la cellule de la valeur.</span><span class="sxs-lookup"><span data-stu-id="bc479-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="bc479-152">**Source**</span><span class="sxs-lookup"><span data-stu-id="bc479-152">**Source**</span></span>  
 <span data-ttu-id="bc479-153">Sélectionnez la source qui contient le champ que vous allez utiliser pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="bc479-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="bc479-154">Vous pouvez utiliser le modèle d’exploration de données sélectionné dans la table **Modèle d’exploration de données** , la ou les tables d’entrée sélectionnées dans la table **Sélectionner une ou plusieurs tables d’entrée** , une fonction de prédiction ou une expression personnalisée.</span><span class="sxs-lookup"><span data-stu-id="bc479-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="bc479-155">Les colonnes des tables contenant le modèle d'exploration de données et des tables d'entrée peuvent être glissées et déplacées sur la cellule.</span><span class="sxs-lookup"><span data-stu-id="bc479-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="bc479-156">**Champ**</span><span class="sxs-lookup"><span data-stu-id="bc479-156">**Field**</span></span>  
 <span data-ttu-id="bc479-157">Sélectionnez une colonne dans la liste des colonnes dérivées de la table source.</span><span class="sxs-lookup"><span data-stu-id="bc479-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="bc479-158">Si vous avez sélectionné **Fonction de prédiction** dans **Source**, elle contient la fonction de prédiction disponible pour le modèle d’exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bc479-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="bc479-159">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="bc479-159">**Group**</span></span>  
 <span data-ttu-id="bc479-160">Utilisez cette option avec la colonne **et/ou** pour regrouper les expressions.</span><span class="sxs-lookup"><span data-stu-id="bc479-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="bc479-161">Par exemple : `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="bc479-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="bc479-162">**Et/ou**</span><span class="sxs-lookup"><span data-stu-id="bc479-162">**And/Or**</span></span>  
 <span data-ttu-id="bc479-163">Utilisez cette option pour créer une requête logique.</span><span class="sxs-lookup"><span data-stu-id="bc479-163">Use to create a logical query.</span></span> <span data-ttu-id="bc479-164">Par exemple : `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="bc479-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="bc479-165">**Critères/Argument**</span><span class="sxs-lookup"><span data-stu-id="bc479-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="bc479-166">Spécifiez une condition ou une expression utilisateur qui s'applique à la colonne.</span><span class="sxs-lookup"><span data-stu-id="bc479-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="bc479-167">Les colonnes des tables contenant le modèle d'exploration de données et des tables d'entrée peuvent être glissées et déplacées sur la cellule.</span><span class="sxs-lookup"><span data-stu-id="bc479-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc479-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc479-168">See Also</span></span>  
 <span data-ttu-id="bc479-169">[Informations de référence sur les instructions DMX&#41; &#40;Data Mining Extensions](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="bc479-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="bc479-170">[Interfaces de requête d’exploration de données](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bc479-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="bc479-171">Générateur de requêtes de prédiction &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bc479-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
