---
title: Créer un rapport de validation croisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694839"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="83004-102">Créer un rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="83004-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="83004-103">Cette rubrique vous guide tout au long de la création d'un rapport de validation croisée à l'aide de l'onglet Graphique d'analyse de précision dans le Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83004-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="83004-104">Pour obtenir des informations d’ordre général sur l’apparence du rapport de validation croisée et sur les mesures statistiques qu’il inclut, consultez [Validation croisée &#40;Analysis Services - Exploration de données&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="83004-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="83004-105">Un rapport de validation croisée est fondamentalement différent d'un graphique d'analyse de précision, tel qu'un graphique de courbes d'élévation ou une matrice de classification.</span><span class="sxs-lookup"><span data-stu-id="83004-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="83004-106">La validation croisée évalue la distribution globale des données utilisées dans un modèle ou une structure ; par conséquent, vous ne spécifiez pas de jeu de données de test.</span><span class="sxs-lookup"><span data-stu-id="83004-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="83004-107">La validation croisée utilise toujours uniquement les données d'origine exploitées pour l'apprentissage du modèle ou la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83004-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="83004-108">La validation croisée ne peut être exécutée que par rapport à des résultats prédictibles uniques.</span><span class="sxs-lookup"><span data-stu-id="83004-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="83004-109">Si la structure prend en charge des modèles qui ont des attributs prédictibles différents, vous devez créer des rapports distincts pour chaque sortie prédictible.</span><span class="sxs-lookup"><span data-stu-id="83004-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="83004-110">Seuls les modèles ayant un rapport avec la structure actuellement sélectionnée sont disponibles pour la validation croisée.</span><span class="sxs-lookup"><span data-stu-id="83004-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="83004-111">Si la structure actuellement sélectionnée prend en charge une combinaison de modèles de clustering et d’autres modèles, quand vous cliquez sur **Obtenir les résultats**, la procédure stockée de validation croisée charge automatiquement les modèles qui ont la même colonne prédite et ignorent les modèles de clustering qui ne partagent pas le même attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="83004-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="83004-112">Vous pouvez créer un rapport de validation croisée sur un modèle de clustering qui n'a pas d'attribut prédictible uniquement si la structure d'exploration de données ne prend en charge aucun autre attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="83004-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="83004-113">Sélectionner une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="83004-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="83004-114">Ouvrez le Concepteur d'exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83004-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="83004-115">Dans l'Explorateur de solutions, ouvrez la base de données qui contient la structure ou le modèle auquel est destiné le rapport que vous créez.</span><span class="sxs-lookup"><span data-stu-id="83004-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="83004-116">Double-cliquez sur la structure d'exploration de données pour ouvrir la structure et ses modèles associés dans le Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83004-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="83004-117">Cliquez sur l'onglet **Graphique d'analyse de précision de l'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="83004-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="83004-118">Cliquez sur l'onglet **Validation croisée** .</span><span class="sxs-lookup"><span data-stu-id="83004-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="83004-119">Définir les options de validation croisée</span><span class="sxs-lookup"><span data-stu-id="83004-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="83004-120">Sous l'onglet **Validation croisée** , pour **Nombre de replis**, cliquez sur la flèche vers le bas pour sélectionner un nombre entre 1 et 10.</span><span class="sxs-lookup"><span data-stu-id="83004-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="83004-121">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="83004-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="83004-122">Le **Nombre de replis** représente le nombre des partitions qui seront créées dans le jeu de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="83004-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="83004-123">Si vous définissez le Nombre de replis à 1, le jeu d'apprentissage est utilisé sans partitionnement.</span><span class="sxs-lookup"><span data-stu-id="83004-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="83004-124">Pour **Attribut cible**, cliquez sur la flèche vers le bas et sélectionnez une colonne dans la liste.</span><span class="sxs-lookup"><span data-stu-id="83004-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="83004-125">Si le modèle est un modèle de clustering, sélectionnez **#Cluster** pour indiquer que le modèle n’a pas d’attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="83004-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="83004-126">Notez que la valeur, **#Cluster**, est disponible uniquement quand la structure d’exploration de données ne prend pas en charge d’autres types d’attributs prédictibles.</span><span class="sxs-lookup"><span data-stu-id="83004-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="83004-127">Vous ne pouvez sélectionner qu'un seul attribut prédictible par rapport.</span><span class="sxs-lookup"><span data-stu-id="83004-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="83004-128">Par défaut, tous les modèles connexes qui ont le même attribut prédictible sont inclus dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="83004-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="83004-129">Pour **Nombre maximal de cas**, entrez un nombre qui est assez grand pour fournir un exemple représentatif de données lorsque les données sont fractionnées parmi le nombre spécifié de plis.</span><span class="sxs-lookup"><span data-stu-id="83004-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="83004-130">Si le nombre est supérieur au nombre de cas dans le jeu d'apprentissage du modèle, tous les cas sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="83004-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="83004-131">Si le jeu de données d'apprentissage est très important, la définition de la valeur de **Nombre maximal de cas** limite le nombre total de cas traités, et permet au rapport de se terminer plus vite.</span><span class="sxs-lookup"><span data-stu-id="83004-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="83004-132">Cependant, vous ne devez pas définir une valeur trop basse pour **Nombre maximal de cas** au risque de manquer de données suffisantes pour la validation croisée.</span><span class="sxs-lookup"><span data-stu-id="83004-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="83004-133">Éventuellement, pour **État cible**, tapez la valeur de l'attribut prédictible que vous souhaitez modéliser.</span><span class="sxs-lookup"><span data-stu-id="83004-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="83004-134">Par exemple, si la colonne (Bike Buyer) a deux valeurs possibles, 1 (Oui) et 2 (Non), vous pouvez entrer la valeur 1 pour évaluer la précision du modèle uniquement pour le résultat souhaité.</span><span class="sxs-lookup"><span data-stu-id="83004-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="83004-135"> Si vous n'entrez pas de valeur, l'option **Seuil cible** n'est pas disponible, et le modèle est évalué pour toutes les valeurs possibles de l'attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="83004-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="83004-136">Éventuellement, pour **Seuil cible**, tapez un nombre décimal entre 0 et 1 pour spécifier la probabilité minimale nécessaire à une prédiction pour être comptabilisée comme exacte.</span><span class="sxs-lookup"><span data-stu-id="83004-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="83004-137">Pour obtenir des conseils supplémentaires sur la manière de définir des seuils de probabilité, consultez [Mesures dans le rapport de validation croisée](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="83004-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="83004-138">Cliquez sur **Obtenir les résultats**.</span><span class="sxs-lookup"><span data-stu-id="83004-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="83004-139">Imprimer le rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="83004-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="83004-140">Cliquez avec le bouton droit sur le rapport complété sous l’onglet **Validation croisée** .</span><span class="sxs-lookup"><span data-stu-id="83004-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="83004-141">Dans le menu contextuel, cliquez sur **Imprimer** ou **Aperçu avant impression** pour afficher d'abord un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="83004-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="83004-142">Créer une copie du rapport dans Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="83004-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="83004-143">Cliquez avec le bouton droit sur le rapport complété sous l’onglet **Validation croisée** .</span><span class="sxs-lookup"><span data-stu-id="83004-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="83004-144">Dans le menu contextuel, cliquez sur **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="83004-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="83004-145">Cliquez avec le bouton droit sur le texte sélectionné, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="83004-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="83004-146">Collez la sélection dans un classeur Excel ouvert.</span><span class="sxs-lookup"><span data-stu-id="83004-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="83004-147">Si vous utilisez l'option **Coller** , le rapport est collé dans Excel au format HTML, ce qui conserve la mise en forme des lignes et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="83004-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="83004-148">Si vous collez le rapport en utilisant les options **Collage spécial** pour le texte ou le texte Unicode, le rapport est collé au format séparé par des lignes.</span><span class="sxs-lookup"><span data-stu-id="83004-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83004-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83004-149">See Also</span></span>  
 [<span data-ttu-id="83004-150">Mesures dans le rapport de validation croisée</span><span class="sxs-lookup"><span data-stu-id="83004-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
