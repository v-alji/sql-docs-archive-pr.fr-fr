---
title: Appliquer un filtre à un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612015"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="88c39-102">Appliquer un filtre à un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="88c39-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="88c39-103">Si votre structure d'exploration de données contient une table imbriquée, vous pouvez appliquer un filtre à la table de cas, à la table imbriquée, ou aux deux.</span><span class="sxs-lookup"><span data-stu-id="88c39-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="88c39-104">La procédure suivante indique comment créer les deux types de filtres : filtres de cas et filtres sur les lignes de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="88c39-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="88c39-105">La condition sur la table de cas restreint les clients à ceux dont le revenu se situe entre 30000 et 40000.</span><span class="sxs-lookup"><span data-stu-id="88c39-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="88c39-106">La condition sur la table imbriquée restreint les clients à ceux qui n'ont pas acheté d'élément particulier.</span><span class="sxs-lookup"><span data-stu-id="88c39-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="88c39-107">La condition de filtre complète créée dans cet exemple se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="88c39-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="88c39-108">Pour créer un filtre de cas sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="88c39-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="88c39-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans l'Explorateur de solutions, cliquez sur la structure d'exploration de données qui contient le modèle d'exploration de données à filtrer.</span><span class="sxs-lookup"><span data-stu-id="88c39-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="88c39-110">Cliquez sur l'onglet **Modèles d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="88c39-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="88c39-111">Sélectionnez le modèle et cliquez avec le bouton droit pour ouvrir le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="88c39-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="88c39-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="88c39-112">-or-</span></span>  
  
     <span data-ttu-id="88c39-113">Sélectionnez le modèle.</span><span class="sxs-lookup"><span data-stu-id="88c39-113">Select the model.</span></span> <span data-ttu-id="88c39-114">Puis, dans le menu **Modèle d'exploration de données** , sélectionnez **Définir le filtre de modèle**.</span><span class="sxs-lookup"><span data-stu-id="88c39-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="88c39-115">Dans la boîte de dialogue **Filtre de modèle** , cliquez sur la ligne supérieure dans la grille, dans la zone de texte **Colonne de la structure d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="88c39-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="88c39-116">Si la source de données contient une table plate unique, la liste déroulante affiche uniquement les noms des colonnes dans cette table.</span><span class="sxs-lookup"><span data-stu-id="88c39-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="88c39-117">Si la structure d'exploration de données contient plusieurs tables, la liste affiche les noms des tables sources.</span><span class="sxs-lookup"><span data-stu-id="88c39-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="88c39-118">Les noms de colonne n'apparaissent pas jusqu'à ce qu'une table ait été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="88c39-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="88c39-119">Si la structure d'exploration de données contient une table de cas et une table imbriquée, la liste déroulante affiche des colonnes de la table de cas et le nom de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="88c39-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="88c39-120">Sélectionnez une colonne dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="88c39-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="88c39-121">L'icône située à gauche de la zone de texte change pour indiquer que l'élément sélectionné est une table ou une colonne.</span><span class="sxs-lookup"><span data-stu-id="88c39-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="88c39-122">Cliquez sur la zone de texte **Opérateur** et sélectionnez un opérateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="88c39-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="88c39-123">Les opérateurs valides changent selon le type de données de la colonne que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="88c39-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="88c39-124">Cliquez sur la zone de texte **Valeur** et tapez une valeur dans la zone.</span><span class="sxs-lookup"><span data-stu-id="88c39-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="88c39-125">Par exemple, sélectionnez `Income` en tant que colonne, sélectionnez l’opérateur supérieur à (>), puis tapez `30000` .</span><span class="sxs-lookup"><span data-stu-id="88c39-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="88c39-126">Cliquez sur la ligne suivante dans la grille.</span><span class="sxs-lookup"><span data-stu-id="88c39-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="88c39-127">La condition de filtre que vous avez créée est ajoutée automatiquement à la zone de texte Expression.</span><span class="sxs-lookup"><span data-stu-id="88c39-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="88c39-128">Par exemple : `[Income] > '30000'`</span><span class="sxs-lookup"><span data-stu-id="88c39-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="88c39-129">Cliquez sur la zone de texte **AND/OR** dans la ligne suivante de la grille pour ajouter une condition.</span><span class="sxs-lookup"><span data-stu-id="88c39-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="88c39-130">Par exemple, pour créer une condition BETWEEN, sélectionnez `AND` dans la liste déroulante d’opérandes logiques.</span><span class="sxs-lookup"><span data-stu-id="88c39-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="88c39-131">Sélectionnez un opérateur et tapez une valeur comme décrit dans les étapes 7 et 8.</span><span class="sxs-lookup"><span data-stu-id="88c39-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="88c39-132">Par exemple, sélectionnez `Income` à nouveau en tant que colonne, sélectionnez l’opérateur inférieur à (<), puis tapez `40000` .</span><span class="sxs-lookup"><span data-stu-id="88c39-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="88c39-133">Cliquez sur la ligne suivante dans la grille.</span><span class="sxs-lookup"><span data-stu-id="88c39-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="88c39-134">La condition de filtre dans la zone de texte Expression est automatiquement mise à jour pour inclure la nouvelle condition.</span><span class="sxs-lookup"><span data-stu-id="88c39-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="88c39-135">L'expression complétée se présente comme suit : `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="88c39-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="88c39-136">Pour ajouter un filtre sur la table imbriquée dans un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="88c39-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="88c39-137">Dans la boîte de dialogue \*\* \<name> filtre de modèle\*\* , cliquez sur une ligne vide dans la grille sous colonne de la **structure d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="88c39-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="88c39-138">Sélectionnez le nom de la table imbriquée dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="88c39-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="88c39-139">L'icône située à gauche de la zone de texte change pour indiquer que l'élément sélectionné est le nom d'une table.</span><span class="sxs-lookup"><span data-stu-id="88c39-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="88c39-140">Cliquez sur la zone de texte **Opérateur** et sélectionnez **Contient** ou **Ne contient pas**.</span><span class="sxs-lookup"><span data-stu-id="88c39-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="88c39-141">Ce sont les seules conditions disponibles pour la table imbriquée dans la boîte de dialogue **Filtre de modèle** , car vous restreignez la table de cas uniquement aux cas qui contiennent une certaine valeur dans la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="88c39-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="88c39-142">Vous allez définir la valeur pour la condition sur la table imbriquée lors de l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="88c39-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="88c39-143">Cliquez sur la zone **valeur** , puis sur le bouton **(...)** pour générer une expression.</span><span class="sxs-lookup"><span data-stu-id="88c39-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="88c39-144">La boîte de dialogue \*\* \<name> filtre\*\* s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="88c39-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="88c39-145">Cette boîte de dialogue peut définir des conditions uniquement sur la table actuelle, qui est la table imbriquée dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="88c39-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="88c39-146">Cliquez sur la zone **Colonne de la structure d'exploration de données** et sélectionnez un nom de colonne dans les listes déroulantes des colonnes de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="88c39-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="88c39-147">Cliquez sur **Opérateur** et sélectionnez un opérateur dans la liste d'opérateurs valides pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="88c39-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="88c39-148">Cliquez sur **Valeur** et tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="88c39-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="88c39-149">Par exemple, pour **colonne de la structure d’exploration de données,** sélectionnez `Model` .</span><span class="sxs-lookup"><span data-stu-id="88c39-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="88c39-150">Pour **opérateur**, sélectionnez `<>` , puis tapez la valeur `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="88c39-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="88c39-151">Cette condition crée l'expression de filtre suivante :</span><span class="sxs-lookup"><span data-stu-id="88c39-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="88c39-152">Puisque le nombre d'attributs de table imbriquée est potentiellement illimité, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne fournit pas de liste de valeurs possibles à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="88c39-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="88c39-153">Vous devez taper la valeur exacte.</span><span class="sxs-lookup"><span data-stu-id="88c39-153">You must type the exact value.</span></span> <span data-ttu-id="88c39-154">En outre, vous ne pouvez pas utiliser d'opérateur LIKE dans une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="88c39-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="88c39-155">Ajoutez d’autres conditions si nécessaire, en combinant les conditions en sélectionnant `AND` ou `OR` dans la zone **et/ou** à gauche de la grille **conditions** .</span><span class="sxs-lookup"><span data-stu-id="88c39-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="88c39-156">Dans la boîte de dialogue **Filtre de modèle** , examinez les conditions que vous avez créées en utilisant la boîte de dialogue **Filtre** .</span><span class="sxs-lookup"><span data-stu-id="88c39-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="88c39-157">Les conditions pour la table imbriquée sont ajoutées aux conditions pour la table de cas, tandis que le jeu complet de conditions de filtre est affiché dans la zone de texte **Expression** .</span><span class="sxs-lookup"><span data-stu-id="88c39-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="88c39-158">Cliquez éventuellement sur **Modifier la requête** pour modifier manuellement l'expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="88c39-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88c39-159">Si vous modifiez manuellement quelque partie que ce soit d'une expression de filtre, la grille est alors désactivée et vous devez utiliser l'expression de filtre en mode édition de texte uniquement.</span><span class="sxs-lookup"><span data-stu-id="88c39-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="88c39-160">Pour restaurer le mode de modification de grille, vous devez effacer l'expression de filtre et recommencer.</span><span class="sxs-lookup"><span data-stu-id="88c39-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="88c39-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88c39-161">See Also</span></span>  
 <span data-ttu-id="88c39-162">[Filtres pour les modèles d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="88c39-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="88c39-163">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="88c39-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="88c39-164">Supprimer un filtre d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="88c39-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
