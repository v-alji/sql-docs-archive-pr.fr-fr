---
title: Valeurs hors norme (compléments d’exploration de données SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710895"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="3243b-102">Valeurs hors norme (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3243b-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="3243b-103">![Assistant Valeurs hors norme sur le ruban Exploration de données](media/dmc-outliers.gif "Assistant Valeurs hors norme sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="3243b-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="3243b-104">Une valeur hors *norme signifie une* valeur de données problématique pour l’une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="3243b-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="3243b-105">La valeur se trouve en dehors de la plage prévue.</span><span class="sxs-lookup"><span data-stu-id="3243b-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="3243b-106">Les données ont été entrées de façon incorrecte.</span><span class="sxs-lookup"><span data-stu-id="3243b-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="3243b-107">La valeur est manquante.</span><span class="sxs-lookup"><span data-stu-id="3243b-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="3243b-108">Les données se composent d'un espace ou de tout autre chaîne de valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="3243b-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="3243b-109">La valeur est exacte, mais à l'extérieure de la distribution et peut avoir un impact significatif sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="3243b-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="3243b-110">Le Client d'exploration de données pour Excel vous aide à détecter ces données, puis met à jour les valeurs ou les supprime.</span><span class="sxs-lookup"><span data-stu-id="3243b-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="3243b-111">Par exemple, remplacez des valeurs hors normes par une moyenne mathématique ou supprimez des lignes qui contiennent des valeurs potentiellement incorrectes.</span><span class="sxs-lookup"><span data-stu-id="3243b-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="3243b-112">Gestion des observations aberrantes</span><span class="sxs-lookup"><span data-stu-id="3243b-112">Handling Outliers</span></span>  
 <span data-ttu-id="3243b-113">L’Assistant **suppression** des valeurs hors norme vous propose plusieurs outils pour gérer les valeurs hors norme de manière appropriée :</span><span class="sxs-lookup"><span data-stu-id="3243b-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="3243b-114">Tout d'abord, vous pouvez explorer les données afin de mieux comprendre la distribution des valeurs et la relation des observations aberrantes et des autres données.</span><span class="sxs-lookup"><span data-stu-id="3243b-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="3243b-115">Par exemple, vous pouvez utiliser la tâche **Explorer les données** pour examiner et corriger les valeurs.</span><span class="sxs-lookup"><span data-stu-id="3243b-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="3243b-116">L’Assistant **suppression** des valeurs hors norme affiche également un graphique, une ligne ou un graphique à barres, pour vous aider à comprendre la distribution de toutes les valeurs.</span><span class="sxs-lookup"><span data-stu-id="3243b-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="3243b-117">Ensuite, vous pouvez utiliser l' **Assistant valeurs** hors norme pour supprimer ou modifier les valeurs hors norme.</span><span class="sxs-lookup"><span data-stu-id="3243b-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="3243b-118">La méthode qui vous utilisez varie selon que les valeurs sont discrètes ou continues.</span><span class="sxs-lookup"><span data-stu-id="3243b-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="3243b-119">L'Assistant affiche des valeurs discrètes dans un graphique à barres, où chaque barre représente une valeur spécifique et la hauteur de la barre indique le nombre de cas pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="3243b-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="3243b-120">En faisant glisser le contrôle de seuil sur le graphique, vous pouvez éliminer les barres qui représentent des groupes de valeurs extrêmes ou mauvaises.</span><span class="sxs-lookup"><span data-stu-id="3243b-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="3243b-121">L'Assistant affiche ou des valeurs continues sur un graphique à barres ou un graphique en courbes.</span><span class="sxs-lookup"><span data-stu-id="3243b-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="3243b-122">Dans le graphique en courbes, la valeur est représentée sur l'axe des abscisses (X) et le nombre de valeurs sur l'axe des ordonnées (Y).</span><span class="sxs-lookup"><span data-stu-id="3243b-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="3243b-123">Vous pouvez contrôler s’il faut supprimer ou conserver les valeurs aux extrémités inférieure et supérieure du graphique en modifiant les valeurs **minimale** et **maximale** , ou en faisant glisser les barres.</span><span class="sxs-lookup"><span data-stu-id="3243b-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="3243b-124">Lorsque vous modifiez les paramètres de valeurs minimales et maximales, les données qui seront supprimées sont signalées par un ombrage dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="3243b-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="3243b-125">Après avoir sélectionné les observations aberrantes à utiliser, vous indiquez à l'Assistant comment les gérer.</span><span class="sxs-lookup"><span data-stu-id="3243b-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="3243b-126">Vous pouvez supprimer les lignes qui contiennent les valeurs d'observation aberrante ou vous pouvez spécifier une valeur de remplacement, telle qu'une moyenne, une valeur null ou une autre valeur de votre choix.</span><span class="sxs-lookup"><span data-stu-id="3243b-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="3243b-127">Enfin, l'Assistant vous propose des options pour afficher les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="3243b-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="3243b-128">Vous pouvez remplacer les données d'origine par les nouvelles valeurs, ajouter une nouvelle colonne au tableau qui contient les nouvelles valeurs ou créer une nouvelle feuille de calcul qui contient les données mises à jour.</span><span class="sxs-lookup"><span data-stu-id="3243b-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="3243b-129">Utilisation de l'Assistant Suppression des observations aberrantes</span><span class="sxs-lookup"><span data-stu-id="3243b-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="3243b-130">Dans le ruban **exploration de données** , cliquez sur nettoyer les **données**, **puis sélectionnez valeurs**hors norme.</span><span class="sxs-lookup"><span data-stu-id="3243b-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="3243b-131">Dans la boîte de dialogue **Sélectionner les données source** , sélectionnez une table de données Excel ou une plage de cellules, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3243b-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="3243b-132">Vous ne pouvez pas utiliser **l’Assistant valeurs** hors norme sur des données externes, sauf si vous le copiez d’abord dans Excel.</span><span class="sxs-lookup"><span data-stu-id="3243b-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="3243b-133">Dans la boîte de dialogue **Sélectionner une colonne** , sélectionnez une **seule** colonne.</span><span class="sxs-lookup"><span data-stu-id="3243b-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="3243b-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3243b-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="3243b-135">Dans la boîte de dialogue **spécifier les seuils** , examinez la distribution des données.</span><span class="sxs-lookup"><span data-stu-id="3243b-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="3243b-136">Si la colonne contient des valeurs discrètes, l'Assistant affiche un histogramme contenant le nombre de chaque valeur discrète.</span><span class="sxs-lookup"><span data-stu-id="3243b-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="3243b-137">En supposant que les valeurs hors norme sont de rares valeurs, vous pouvez les filtrer en modifiant la valeur **minimale** .</span><span class="sxs-lookup"><span data-stu-id="3243b-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="3243b-138">Si la colonne contient des données numériques, vous pouvez cliquer sur le bouton **afficher comme discret** ou sur le bouton **afficher en tant que numérique** pour basculer entre l’affichage des valeurs dans un graphique à barres ou un graphique en courbes.</span><span class="sxs-lookup"><span data-stu-id="3243b-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="3243b-139">Dans la boîte de dialogue **spécifier les seuils** , choisissez la plage de données que vous souhaitez conserver en tapant une valeur minimale et maximale, ou en faisant glisser les barres de curseur.</span><span class="sxs-lookup"><span data-stu-id="3243b-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="3243b-140">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3243b-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3243b-141">Dans la boîte de dialogue **gestion des** valeurs hors norme, indiquez si vous souhaitez que les valeurs soient supprimées ou remplacées, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3243b-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="3243b-142">Dans la boîte de dialogue **Sélectionner la destination** , spécifiez l’emplacement où vous souhaitez enregistrer les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="3243b-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="3243b-143">Options connexes</span><span class="sxs-lookup"><span data-stu-id="3243b-143">Related Options</span></span>  
 <span data-ttu-id="3243b-144">L'Assistant fournit ces options :</span><span class="sxs-lookup"><span data-stu-id="3243b-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="3243b-145">**Options**</span><span class="sxs-lookup"><span data-stu-id="3243b-145">**Options**</span></span>|<span data-ttu-id="3243b-146">**Commentaire**</span><span class="sxs-lookup"><span data-stu-id="3243b-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3243b-147">**Sélectionner une colonne**</span><span class="sxs-lookup"><span data-stu-id="3243b-147">**Select Column**</span></span>|<span data-ttu-id="3243b-148">Vous pouvez travailler avec une seule colonne à la fois.</span><span class="sxs-lookup"><span data-stu-id="3243b-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="3243b-149">**Spécifier la gestion des seuils**</span><span class="sxs-lookup"><span data-stu-id="3243b-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="3243b-150">Définissez un seuil en utilisant **minimum** pour exclure les valeurs qui se trouvent dans moins de lignes que la valeur de seuil.</span><span class="sxs-lookup"><span data-stu-id="3243b-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="3243b-151">Initialement, la valeur **minimale** est égale à la valeur ayant le moins de lignes et vous ne pouvez pas définir la valeur minimale inférieure à cette valeur.</span><span class="sxs-lookup"><span data-stu-id="3243b-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="3243b-152">**Gestion des valeurs hors norme**</span><span class="sxs-lookup"><span data-stu-id="3243b-152">**Outlier Handling**</span></span>|<span data-ttu-id="3243b-153">Si vous décidez de supprimer des valeurs hors norme, modifiez les données dans la feuille de calcul active, ou créez une copie des données dans une nouvelle feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="3243b-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3243b-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3243b-154">See Also</span></span>  
 [<span data-ttu-id="3243b-155">Explorez les &#40;de données SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3243b-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
