---
title: Exploration et nettoyage des données | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600313"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="337ef-102">Exploration et nettoyage des données</span><span class="sxs-lookup"><span data-stu-id="337ef-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="337ef-103">La préparation des données est bien plus que le nettoyage des données.</span><span class="sxs-lookup"><span data-stu-id="337ef-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="337ef-104">N'oubliez pas que la façon dont les données sont préparées affecte également la façon dont les résultats sont interprétés.</span><span class="sxs-lookup"><span data-stu-id="337ef-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="337ef-105">La préparation des données implique les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="337ef-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="337ef-106">Exploration et vérification de la distribution des données.</span><span class="sxs-lookup"><span data-stu-id="337ef-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="337ef-107">Nettoyage des enregistrements incorrects et sélection des colonnes pour l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="337ef-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="337ef-108">Gestion des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="337ef-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="337ef-109">Placement des valeurs dans un conteneur ou agrégation des valeurs selon différents segments de temps.</span><span class="sxs-lookup"><span data-stu-id="337ef-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="337ef-110">Ajout d'étiquettes pour améliorer la simplicité d'utilisation des résultats.</span><span class="sxs-lookup"><span data-stu-id="337ef-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="337ef-111">Conversion des types de données ou classement des valeurs, le cas échéant, pour analyse.</span><span class="sxs-lookup"><span data-stu-id="337ef-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="337ef-112">Si vous débutez avec la modélisation des données, nous vous recommandons de lire la rubrique correspondante, [liste de contrôle de préparation pour l’exploration de données](checklist-of-preparation-for-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="337ef-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="337ef-113">Outils de préparation des données</span><span class="sxs-lookup"><span data-stu-id="337ef-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="337ef-114">Les compléments d’exploration de données pour Office incluent les outils suivants pour le nettoyage et la préparation des données :</span><span class="sxs-lookup"><span data-stu-id="337ef-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="337ef-115">Explorer les données</span><span class="sxs-lookup"><span data-stu-id="337ef-115">Explore Data</span></span>  
 <span data-ttu-id="337ef-116">Utilisez l’Assistant **exploration des données** pour ces tâches de préparation des données :</span><span class="sxs-lookup"><span data-stu-id="337ef-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="337ef-117">Afficher un aperçu de vos données et identifier les erreurs qui doivent être résolues avant l'analyse.</span><span class="sxs-lookup"><span data-stu-id="337ef-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="337ef-118">Collecter les statistiques utiles pour comprendre l'équilibre de la distribution des données et les tâches de nettoyage nécessaires.</span><span class="sxs-lookup"><span data-stu-id="337ef-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="337ef-119">Identifier les colonnes qui sont utiles pour l'analyse, et planifier la phase de modélisation des données.</span><span class="sxs-lookup"><span data-stu-id="337ef-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="337ef-120">[Explorez les&#41;de données &#40;SQL Server des compléments d’exploration de données ](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="337ef-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="337ef-121">Détecter et gérer les valeurs hors norme</span><span class="sxs-lookup"><span data-stu-id="337ef-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="337ef-122">L' **Assistant valeurs** hors norme graphe la distribution des valeurs dans vos données et vous permet de supprimer les valeurs extrêmes.</span><span class="sxs-lookup"><span data-stu-id="337ef-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="337ef-123">Utilisez l' **outil valeurs** hors norme pour les tâches de préparation des données suivantes :</span><span class="sxs-lookup"><span data-stu-id="337ef-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="337ef-124">Déterminer si les valeurs individuelles sont fiables, basées sur les modèles trouvés dans les données.</span><span class="sxs-lookup"><span data-stu-id="337ef-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="337ef-125">Examiner les valeurs inhabituelles, les supprimez ou les remplacer.</span><span class="sxs-lookup"><span data-stu-id="337ef-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="337ef-126">Définir l'étendue d'un modèle à une plage de valeurs spécifique.</span><span class="sxs-lookup"><span data-stu-id="337ef-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="337ef-127">Par exemple, si vous savez que vous avez des valeurs hors norme dans un magasin spécifique, supprimez cette valeur et obtenez un modèle qui améliore les prédictions d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="337ef-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="337ef-128">Valeurs hors norme [&#40;SQL Server les compléments d’exploration de données&#41;](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="337ef-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="337ef-129">Réétiqueter et placer les données dans un conteneur</span><span class="sxs-lookup"><span data-stu-id="337ef-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="337ef-130">L’Assistant **réétiqueter** regroupe les données par valeurs afin que vous puissiez modifier les étiquettes des données.</span><span class="sxs-lookup"><span data-stu-id="337ef-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="337ef-131">Utilisez l'outil Réétiqueter pour les tâches de préparation des données suivantes :</span><span class="sxs-lookup"><span data-stu-id="337ef-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="337ef-132">Modifier les codes numériques utilisés dans les résultats d'enquête en une description textuelle de la signification du code numérique.</span><span class="sxs-lookup"><span data-stu-id="337ef-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="337ef-133">Par exemple, vous pouvez remplacer des entrées de données telles que Sexe = 1 par Sexe = Féminin.</span><span class="sxs-lookup"><span data-stu-id="337ef-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="337ef-134">Placez les données dans un conteneur, en créant des groupes pour représenter des plages de nombres.</span><span class="sxs-lookup"><span data-stu-id="337ef-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="337ef-135">Par exemple, vous souhaiterez peut-être remplacer une colonne revenu des nombres par des étiquettes telles que **revenu-modéré** et **revenu-High**.</span><span class="sxs-lookup"><span data-stu-id="337ef-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="337ef-136">Réduisez les valeurs discrètes dans des catégories.</span><span class="sxs-lookup"><span data-stu-id="337ef-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="337ef-137">Par exemple, si vous disposez de trop de produits individuels pour détecter un schéma parmi les achats, vous pouvez essayer d'affecter des produits dans des catégories plus vastes.</span><span class="sxs-lookup"><span data-stu-id="337ef-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="337ef-138">Réétiqueter les compléments d’exploration de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="337ef-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="337ef-139">Nettoyer les données</span><span class="sxs-lookup"><span data-stu-id="337ef-139">Cleanse Data</span></span>  
 <span data-ttu-id="337ef-140">Le nettoyage de données comprend une grande variété d'activités, la plupart étant prises en charge par les compléments</span><span class="sxs-lookup"><span data-stu-id="337ef-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="337ef-141">Identifiez les valeurs nulles et déterminez si elles doivent être remplacées par une valeur réelle ou être gérées en tant que valeurs `Missing`.</span><span class="sxs-lookup"><span data-stu-id="337ef-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="337ef-142">Détectez les valeurs manquantes, puis supprimez-les ou imputez une valeur appropriée, comme une moyenne, une valeur NULL ou une autre valeur.</span><span class="sxs-lookup"><span data-stu-id="337ef-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="337ef-143">Explorez les &#40;de données SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="337ef-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="337ef-144">Réétiqueter les compléments d’exploration de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="337ef-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="337ef-145">Remplir à partir de l'exemple</span><span class="sxs-lookup"><span data-stu-id="337ef-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="337ef-146">Exemples de données</span><span class="sxs-lookup"><span data-stu-id="337ef-146">Sample Data</span></span>  
 <span data-ttu-id="337ef-147">L'Assistant Exemples de données fournit deux méthodes pour créer des jeux de données équilibrés pour des modèles d'apprentissage et de test.</span><span class="sxs-lookup"><span data-stu-id="337ef-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="337ef-148">**Échantillonnage aléatoire.**</span><span class="sxs-lookup"><span data-stu-id="337ef-148">**Random sampling.**</span></span> <span data-ttu-id="337ef-149">Utilisez cette option pour extraire un jeu de données représentatif d'un plus grand jeu de données, en vue de l'utiliser pour l'apprentissage ou le test.</span><span class="sxs-lookup"><span data-stu-id="337ef-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="337ef-150">Les compléments d’exploration de données utilisent l' *échantillonnage stratifié* pour s’assurer qu’un ensemble équilibré de valeurs est obtenu pour chaque variable échantillonnée.</span><span class="sxs-lookup"><span data-stu-id="337ef-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="337ef-151">**Suréchantillonnage.**</span><span class="sxs-lookup"><span data-stu-id="337ef-151">**Oversampling.**</span></span> <span data-ttu-id="337ef-152">Utilisez cette option si vous avez moins de données que vous ne le souhaiteriez pour le résultat, et que vous devez pondérer ces données de manière plus importante.</span><span class="sxs-lookup"><span data-stu-id="337ef-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="337ef-153">Par exemple, la fraude peut être relativement rare, mais vous pouvez suréchantillonner des cas impliquant de la fraude pour obtenir les données adéquates pour la modélisation.</span><span class="sxs-lookup"><span data-stu-id="337ef-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="337ef-154">[Exemples de données &#40;SQL Server&#41;des compléments d’exploration de données ](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="337ef-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337ef-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="337ef-155">See Also</span></span>  
 <span data-ttu-id="337ef-156">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="337ef-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="337ef-157">[Validation des modèles et utilisation de modèles pour la prédiction &#40;compléments d’exploration de données pour Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="337ef-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="337ef-158">Déploiement et mise à l’échelle des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="337ef-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
