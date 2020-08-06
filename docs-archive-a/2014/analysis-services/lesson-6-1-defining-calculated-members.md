---
title: Définition des membres calculés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604235"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="ffec4-102">Définition des membres calculés</span><span class="sxs-lookup"><span data-stu-id="ffec4-102">Defining Calculated Members</span></span>
  <span data-ttu-id="ffec4-103">Les membres calculés sont les membres d'une dimension ou d'un groupe de mesures qui sont définis à l'aide d'une combinaison de données de cube, d'opérateurs arithmétiques, de nombres et de fonctions.</span><span class="sxs-lookup"><span data-stu-id="ffec4-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="ffec4-104">Par exemple, vous pouvez créer un membre calculé qui additionne deux mesures physiques dans le cube.</span><span class="sxs-lookup"><span data-stu-id="ffec4-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="ffec4-105">Les définitions de membre calculé sont stockées dans les cubes, mais leurs valeurs sont calculées lors du traitement des requêtes.</span><span class="sxs-lookup"><span data-stu-id="ffec4-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="ffec4-106">Pour créer un membre calculé, utilisez la commande **Nouveau membre calculé** , disponible sous l'onglet **Calculs** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="ffec4-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="ffec4-107">Vous pouvez créer un membre calculé au sein d'une dimension, y compris la dimension de mesures.</span><span class="sxs-lookup"><span data-stu-id="ffec4-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="ffec4-108">Vous pouvez aussi placer un membre calculé dans un dossier d'affichage dans la boîte de dialogue **Propriétés de calcul** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="ffec4-109">Pour plus d’informations, consultez [Calculs](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculs dans les modèles multidimensionnels](multidimensional-models/calculations-in-multidimensional-models.md)et [Créer des membres calculés](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="ffec4-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="ffec4-110">Dans les tâches de cette rubrique, vous définissez des mesures calculées pour permettre aux utilisateurs d'afficher le pourcentage de marge brute et les ratios des ventes pour les ventes par Internet, les ventes de revendeurs et l'ensemble des ventes.</span><span class="sxs-lookup"><span data-stu-id="ffec4-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="ffec4-111">Définition de calculs pour agréger des mesures physiques</span><span class="sxs-lookup"><span data-stu-id="ffec4-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="ffec4-112">Ouvrez le Concepteur de cube pour le cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur l'onglet **Calculs** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="ffec4-113">Notez la présence de la commande par défaut CALCULATE dans le volet **Expressions de calcul** et dans le volet **Organisateur de script** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="ffec4-114">Cette commande spécifie que les mesures du cube doivent être agrégées en fonction de la valeur qui est spécifiée par leurs propriétés AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="ffec4-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="ffec4-115">Les valeurs de mesure sont généralement additionnées mais peuvent aussi être comptées ou agrégées d'une autre manière.</span><span class="sxs-lookup"><span data-stu-id="ffec4-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="ffec4-116">L'image suivante montre l'onglet **Calculs** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="ffec4-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="ffec4-117">![Onglet Calculs du Concepteur de cube](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Onglet Calculs du Concepteur de cube")</span><span class="sxs-lookup"><span data-stu-id="ffec4-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="ffec4-118">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="ffec4-119">Un nouveau formulaire apparaît dans le volet **Expressions de calcul** pour vous permettre de définir les propriétés de ce nouveau membre calculé.</span><span class="sxs-lookup"><span data-stu-id="ffec4-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="ffec4-120">Le nouveau membre apparaît aussi dans le volet **Organisateur de script** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="ffec4-121">L'image suivante montre le formulaire qui apparaît dans le volet **Expressions de calcul** lorsque vous cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="ffec4-122">![Formulaire du volet des expressions de calcul](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Formulaire du volet des expressions de calcul")</span><span class="sxs-lookup"><span data-stu-id="ffec4-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="ffec4-123">Dans la zone **nom** , remplacez le nom de la mesure calculée par `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="ffec4-124">Si le nom d'un membre calculé contient un espace, le nom du membre calculé doit être placé entre crochets.</span><span class="sxs-lookup"><span data-stu-id="ffec4-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="ffec4-125">Dans la liste **Hiérarchie parente** , notez que, par défaut, un nouveau membre calculé est créé dans la dimension **Mesures** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="ffec4-126">Souvent, un membre calculé dans la dimension Mesures est également appelé mesure calculée.</span><span class="sxs-lookup"><span data-stu-id="ffec4-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="ffec4-127">Sous l'onglet **Métadonnées** , dans le volet **Outils de calcul** de l'onglet **Calculs** , développez **Mesures** , puis développez **Internet Sales** pour afficher les métadonnées du groupe de mesures **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="ffec4-128">Vous pouvez faire glisser des métadonnées depuis le volet **Outils de calcul** jusqu’à la zone **Expression** , puis ajouter des opérateurs et d’autres éléments pour créer des expressions MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="ffec4-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="ffec4-129">Ou bien, vous pouvez taper l'expression MDX directement dans la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ffec4-130">Si le volet **Outils de calcul** ne contient pas de métadonnées, cliquez sur **Reconnexion** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="ffec4-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="ffec4-131">Si cette opération ne donne pas de résultats, il se peut que vous deviez traiter le cube ou démarrer une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffec4-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="ffec4-132">Faites glisser **Internet Sales-Sales Amount** depuis l’onglet **Métadonnées** du volet **Outils de calcul** jusqu’à la zone **Expression** dans le volet **Expressions de calcul** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="ffec4-133">Dans la zone **Expression** , tapez un signe plus (`+`) après **[Measures].[Internet Sales-Sales Amount]**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="ffec4-134">Sous l’onglet **Métadonnées** dans le volet **Outils de calcul** , développez **Reseller Sales**, puis faites glisser **Reseller Sales-Sales Amount** dans la zone **Expression** du volet **Expressions de calcul** après le signe plus (+).</span><span class="sxs-lookup"><span data-stu-id="ffec4-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="ffec4-135">Dans la liste **chaîne de format** , sélectionnez **devise.**</span><span class="sxs-lookup"><span data-stu-id="ffec4-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="ffec4-136">Dans la liste **Comportement non vide** , cochez les cases pour **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ffec4-137">Les mesures que vous spécifiez dans la liste **Comportement non vide** sont utilisées pour résoudre les requêtes NON EMPTY dans les expressions MDX.</span><span class="sxs-lookup"><span data-stu-id="ffec4-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="ffec4-138">Quand vous spécifiez une ou plusieurs mesures dans la liste **Comportement non vide** , [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] traite le membre calculé comme s’il était vide si toutes les mesures spécifiées sont vides.</span><span class="sxs-lookup"><span data-stu-id="ffec4-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="ffec4-139">Si la propriété **Comportement non vide** n’est pas définie, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] doit évaluer le membre calculé lui-même pour déterminer s’il est vide.</span><span class="sxs-lookup"><span data-stu-id="ffec4-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="ffec4-140">L'image suivante montre le volet **Expressions de calcul** rempli à l'aide des paramètres que vous avez spécifiés dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="ffec4-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="ffec4-141">![Volet des expressions de calcul rempli](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Volet des expressions de calcul rempli")</span><span class="sxs-lookup"><span data-stu-id="ffec4-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="ffec4-142">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Mode Script**, puis examinez le script de calcul dans le volet **Expressions de calcul** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="ffec4-143">Remarquez que le nouveau calcul est ajouté à l'expression CALCULATE initiale ; les différents calculs sont séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="ffec4-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="ffec4-144">Observez également qu'un commentaire apparaît au début du script de calcul.</span><span class="sxs-lookup"><span data-stu-id="ffec4-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="ffec4-145">L'ajout de commentaires au script de calcul pour les groupes de calculs constitue une méthode conseillée, car elle facilite la compréhension des scripts de calcul complexes.</span><span class="sxs-lookup"><span data-stu-id="ffec4-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="ffec4-146">Ajoutez une nouvelle ligne au script de calcul après la commande **Calculate;** et avant le script de calcul que vous venez d'ajouter, puis ajoutez le texte suivant au script sur sa propre ligne :</span><span class="sxs-lookup"><span data-stu-id="ffec4-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="ffec4-147">L'image suivante montre les scripts de calcul tels qu'ils doivent apparaître dans le volet **Expressions de calcul** à ce stade dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="ffec4-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="ffec4-148">![Scripts dans le volet des expressions de calcul](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts dans le volet des expressions de calcul")</span><span class="sxs-lookup"><span data-stu-id="ffec4-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="ffec4-149">Dans la barre d’outils de l’onglet **calculs** , cliquez sur **mode formulaire**, vérifiez que `[Total Sales Amount]` est sélectionné dans le volet **organisateur de script** , puis cliquez sur **nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="ffec4-150">Changez le nom de ce nouveau membre calculé en `[Total Product Cost]` , puis créez l’expression suivante dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="ffec4-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="ffec4-151">Dans la liste **Chaîne de format** , sélectionnez **Devise**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="ffec4-152">Dans la liste **Comportement non vide** , cochez les cases pour **Internet Sales-Total Product Cost** et **Reseller Sales-Total Product Cost**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ffec4-153">Vous avez ainsi défini deux membres calculés, qui sont tous deux visibles dans le volet **Organisateur de script** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="ffec4-154">Ces membres calculés peuvent être utilisés par d'autres calculs que vous définissez plus loin dans le script de calcul.</span><span class="sxs-lookup"><span data-stu-id="ffec4-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="ffec4-155">Vous pouvez afficher la définition d'un membre calculé en le sélectionnant dans le volet **Organisateur de script** ; la définition du membre calculé apparaîtra dans le volet **Expressions de calcul** en Mode Formulaire.</span><span class="sxs-lookup"><span data-stu-id="ffec4-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="ffec4-156">Les membres calculés qui viennent d'être définis n'apparaîtront pas dans le volet **Outils de calcul** tant que ces objets n'auront pas été déployés.</span><span class="sxs-lookup"><span data-stu-id="ffec4-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="ffec4-157">Les calculs ne nécessitent pas de traitement.</span><span class="sxs-lookup"><span data-stu-id="ffec4-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="ffec4-158">Définition de calculs de marge brute</span><span class="sxs-lookup"><span data-stu-id="ffec4-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="ffec4-159">Vérifiez que `[Total Product Cost]` est sélectionné dans le volet **organisateur de script** , puis cliquez sur **nouveau membre calculé** dans la barre d’outils de l’onglet **calculs** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="ffec4-160">Dans la zone **nom** , remplacez le nom de cette nouvelle mesure calculée par `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="ffec4-161">Dans la zone **Expression** , créez l'expression MDX suivante :</span><span class="sxs-lookup"><span data-stu-id="ffec4-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="ffec4-162">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="ffec4-163">Dans la liste **Comportement non vide** , cochez la case pour **Internet Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ffec4-164">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="ffec4-165">Dans la zone **nom** , remplacez le nom de cette nouvelle mesure calculée par `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="ffec4-166">Dans la zone **Expression** , créez l'expression MDX suivante :</span><span class="sxs-lookup"><span data-stu-id="ffec4-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="ffec4-167">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="ffec4-168">Dans la liste **Comportement non vide** , cochez la case pour **Reseller Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="ffec4-169">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="ffec4-170">Dans la zone **nom** , remplacez le nom de cette mesure calculée par `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="ffec4-171">Dans la zone **Expression** , créez l'expression MDX suivante :</span><span class="sxs-lookup"><span data-stu-id="ffec4-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="ffec4-172">Remarquez que ce membre calculé référence d'autres membres calculés.</span><span class="sxs-lookup"><span data-stu-id="ffec4-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="ffec4-173">Ce membre calculé est valide car il sera calculé après les membres calculés auxquels il fait référence.</span><span class="sxs-lookup"><span data-stu-id="ffec4-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="ffec4-174">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="ffec4-175">Dans la liste **Comportement non vide** , cochez les cases pour **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="ffec4-176">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Mode Script** et examinez les trois calculs que vous avez ajoutés au script de calcul.</span><span class="sxs-lookup"><span data-stu-id="ffec4-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="ffec4-177">Ajoutez une nouvelle ligne au script de calcul immédiatement avant le `[Internet GPM]` calcul, puis ajoutez le texte suivant au script sur sa propre ligne :</span><span class="sxs-lookup"><span data-stu-id="ffec4-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="ffec4-178">L'image suivante montre le volet **Expressions** avec les trois nouveaux calculs.</span><span class="sxs-lookup"><span data-stu-id="ffec4-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="ffec4-179">![Nouveaux calculs dans le volet des expressions de calcul](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Nouveaux calculs dans le volet des expressions de calcul")</span><span class="sxs-lookup"><span data-stu-id="ffec4-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="ffec4-180">Définition des calculs de pourcentage du total</span><span class="sxs-lookup"><span data-stu-id="ffec4-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="ffec4-181">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Mode formulaire**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="ffec4-182">Dans le volet **organisateur de script** , sélectionnez, puis cliquez sur `[Total GPM]` **nouveau membre calculé** dans la barre d’outils de l’onglet **calculs** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="ffec4-183">Le fait de cliquer sur le membre calculé final dans le volet **Organisateur de script** avant de cliquer sur **Nouveau membre calculé** garantit que le nouveau membre calculé sera entré à la fin du script.</span><span class="sxs-lookup"><span data-stu-id="ffec4-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="ffec4-184">Les scripts s'exécutent dans l'ordre où ils apparaissent dans le volet **Organisateur de script** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="ffec4-185">Remplacez le nom de ce nouveau membre calculé par `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="ffec4-186">Tapez l'expression suivante dans la zone **Expression** :</span><span class="sxs-lookup"><span data-stu-id="ffec4-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="ffec4-187">Cette expression MDX calcule la contribution de chaque produit au total des ventes par Internet.</span><span class="sxs-lookup"><span data-stu-id="ffec4-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="ffec4-188">L'instruction Case et la fonction IS EMPTY excluent la division par zéro lorsqu'un produit n'a pas de ventes.</span><span class="sxs-lookup"><span data-stu-id="ffec4-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="ffec4-189">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="ffec4-190">Dans la liste **Comportement non vide** , cochez la case pour **Internet Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="ffec4-191">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="ffec4-192">Remplacez le nom de ce membre calculé par `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="ffec4-193">Tapez l'expression suivante dans la zone **Expression** :</span><span class="sxs-lookup"><span data-stu-id="ffec4-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="ffec4-194">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="ffec4-195">Dans la liste **Comportement non vide** , cochez la case pour **Reseller Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="ffec4-196">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="ffec4-197">Remplacez le nom de ce membre calculé par `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="ffec4-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="ffec4-198">Tapez l'expression suivante dans la zone **Expression** :</span><span class="sxs-lookup"><span data-stu-id="ffec4-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="ffec4-199">Dans la liste **Chaîne de format** , sélectionnez **Pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="ffec4-200">Dans la liste **Comportement non vide** , cochez les cases pour **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="ffec4-201">Dans la barre d'outils de l'onglet **Calculs** , cliquez sur **Mode Script**et examinez les trois calculs que vous avez ajoutés au script de calcul.</span><span class="sxs-lookup"><span data-stu-id="ffec4-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="ffec4-202">Ajoutez une nouvelle ligne au script de calcul immédiatement avant le `[Internet Sales Ratio to All Products]` calcul, puis ajoutez le texte suivant au script sur sa propre ligne :</span><span class="sxs-lookup"><span data-stu-id="ffec4-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="ffec4-203">À présent, vous avez défini au total huit membres calculés, qui sont visibles dans le volet **Organisateur de script** lorsque vous travaillez en mode Formulaire.</span><span class="sxs-lookup"><span data-stu-id="ffec4-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="ffec4-204">Exploration des nouveaux membres calculés</span><span class="sxs-lookup"><span data-stu-id="ffec4-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="ffec4-205">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="ffec4-206">Après avoir déployé le didacticiel, cliquez sur l'onglet **Navigateur** , puis sur **Reconnexion**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="ffec4-207">Cliquez sur l'icône Excel, puis **Activer**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="ffec4-208">Dans le volet **Liste de champs de tableau croisé dynamique** , développez le dossier **Valeurs** pour afficher les nouveaux membres calculés de la dimension de mesures.</span><span class="sxs-lookup"><span data-stu-id="ffec4-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="ffec4-209">Faites glisser **Total Sales Amount** vers la zone Valeurs, puis examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="ffec4-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="ffec4-210">Faites glisser les mesures **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount** des groupes de mesures **Internet Sales** et **Reseller Sales** vers la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="ffec4-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="ffec4-211">Observez que la mesure **Total Sales Amount** est la somme de la mesure **Internet Sales-Sales Amount** et de la mesure **Reseller Sales-Sales Amount** .</span><span class="sxs-lookup"><span data-stu-id="ffec4-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="ffec4-212">Ajoutez la hiérarchie **Product Categories** définie par l’utilisateur à la zone de filtre de la zone **Filtre de rapport** , puis filtrez les données par **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="ffec4-213">Notez que la mesure **Total Sales Amount** est calculée pour la catégorie de ventes de produit **Mountain Bikes** en fonction des mesures **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount** pour **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="ffec4-214">Ajoutez la hiérarchie définie par l’utilisateur **Date.Calendar Date** à la zone d’étiquettes de ligne, puis examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="ffec4-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="ffec4-215">Notez que la mesure **Total Sales Amount** pour chaque année fiscale est calculée pour la catégorie de ventes de produit **Mountain Bikes** en fonction des mesures **Internet Sales-Sales Amount** et **Reseller Sales-Sales Amount** pour **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="ffec4-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="ffec4-216">Ajoutez les mesures **Total GPM**, **Internet GPM**et **Reseller GPM** à la zone Valeurs, puis examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="ffec4-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="ffec4-217">Observez que la marge brute pour les ventes de revendeurs est nettement plus faible que pour les ventes par Internet, comme l'illustre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="ffec4-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="ffec4-218">![Volet de données affichant les ventes du revendeur](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Volet de données affichant les ventes du revendeur")</span><span class="sxs-lookup"><span data-stu-id="ffec4-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="ffec4-219">Ajoutez les mesures **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**et **Reseller Sales Ratio to All Products** à la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="ffec4-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="ffec4-220">Observez que le ratio des ventes de vélos tout terrain sur les ventes de tous les produits a augmenté dans le temps pour les ventes par Internet, mais diminue progressivement pour les ventes de revendeurs.</span><span class="sxs-lookup"><span data-stu-id="ffec4-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="ffec4-221">Notez également que le ratio des ventes de vélos tout terrain sur les ventes de tous les produits est plus faible dans les ventes de revendeurs que dans les ventes par Internet.</span><span class="sxs-lookup"><span data-stu-id="ffec4-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="ffec4-222">À la place de **Mountain Bikes** , utilisez le filtre **Bikes**et examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="ffec4-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="ffec4-223">Observez que la marge brute pour tous les vélos vendus par des revendeurs est négative parce que les vélos de cyclotourisme et les vélos de route sont vendus à perte.</span><span class="sxs-lookup"><span data-stu-id="ffec4-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="ffec4-224">Changez de filtre en spécifiant **Accessories**, puis examinez les résultats.</span><span class="sxs-lookup"><span data-stu-id="ffec4-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="ffec4-225">Observez que la vente d'accessoires augmente dans le temps, mais qu'elle ne représente qu'une petite partie des ventes totales.</span><span class="sxs-lookup"><span data-stu-id="ffec4-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="ffec4-226">Notez également que la marge brute des accessoires est supérieure à celle des vélos.</span><span class="sxs-lookup"><span data-stu-id="ffec4-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ffec4-227">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ffec4-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ffec4-228">Définition de jeux nommés</span><span class="sxs-lookup"><span data-stu-id="ffec4-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="ffec4-229">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffec4-229">See Also</span></span>  
 <span data-ttu-id="ffec4-230">[Touchant](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="ffec4-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="ffec4-231">[Calculs dans les modèles multidimensionnels](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="ffec4-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="ffec4-232">Créer des membres calculés</span><span class="sxs-lookup"><span data-stu-id="ffec4-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
