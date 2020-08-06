---
title: Définition des propriétés d’attribut parent dans une hiérarchie parent-enfant | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611376"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="f17d2-102">Définition des propriétés d'attribut parent dans une hiérarchie parent-enfant</span><span class="sxs-lookup"><span data-stu-id="f17d2-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="f17d2-103">Une hiérarchie parent-enfant est une hiérarchie dans une dimension fondée sur deux colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="f17d2-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="f17d2-104">Ensemble, ces colonnes définissent les relations hiérarchiques entre les membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f17d2-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="f17d2-105">La première colonne, appelée *colonne des clés de membre*, identifie chaque membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="f17d2-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="f17d2-106">L’autre colonne, appelée *colonne parente*, identifie le parent de chaque membre de dimension.</span><span class="sxs-lookup"><span data-stu-id="f17d2-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="f17d2-107">La propriété **NamingTemplate** d’un attribut parent détermine le nom de chaque niveau de la hiérarchie parent-enfant et la propriété **MembersWithData** détermine si les données des membres parents doivent être affichées ou non.</span><span class="sxs-lookup"><span data-stu-id="f17d2-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="f17d2-108">Pour plus d’informations, consultez [hiérarchie parent-enfant](multidimensional-models/parent-child-dimension.md), [attributs dans les hiérarchies parent-enfant](multidimensional-models/parent-child-dimension-attributes.md) .</span><span class="sxs-lookup"><span data-stu-id="f17d2-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="f17d2-109">Lorsque vous utilisez l'Assistant Dimension pour créer une dimension, l'Assistant reconnaît les tables qui contiennent des relations parent-enfant et définit automatiquement la hiérarchie parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="f17d2-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="f17d2-110">Au cours des tâches de la présente rubrique, vous allez créer un modèle de nom qui définit le nom de chaque niveau de la hiérarchie parent-enfant dans la dimension **Employee** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="f17d2-111">Vous allez ensuite configurer l'attribut parent pour masquer toutes les données parent, de façon à ce que seules les ventes des membres de niveau feuille soient affichées.</span><span class="sxs-lookup"><span data-stu-id="f17d2-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="f17d2-112">Navigation dans la dimension Employee</span><span class="sxs-lookup"><span data-stu-id="f17d2-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="f17d2-113">Dans l’Explorateur de solutions, double-cliquez sur **Employee.dim** dans le dossier **Dimensions** pour ouvrir le Concepteur de dimensions pour la dimension Employee.</span><span class="sxs-lookup"><span data-stu-id="f17d2-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="f17d2-114">Cliquez sur l’onglet **Navigateur** , vérifiez que **Employees** est sélectionné dans la liste **Hiérarchie** , puis développez le membre **All Employees** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="f17d2-115">Notez que **Ken J. Sánchez** est le responsable du plus haut niveau dans cette hiérarchie parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="f17d2-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="f17d2-116">Sélectionnez le membre **Ken J. Sánchez** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="f17d2-117">Notez que le nom du niveau pour ce membre est **Level 02**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="f17d2-118">(Le nom du niveau apparaît après **Niveau actuel** , immédiatement au-dessus du membre **All Employees** .) Au cours de la tâche suivante, vous allez définir des noms plus descriptifs pour chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="f17d2-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="f17d2-119">Développez **Ken J. Sánchez** pour afficher les noms des employés qui travaillent sous l’autorité de ce responsable, puis sélectionnez **Brian S. Welcker** pour afficher le nom de ce niveau.</span><span class="sxs-lookup"><span data-stu-id="f17d2-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="f17d2-120">Notez que le nom du niveau pour ce membre est **Level 03**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="f17d2-121">Dans l’Explorateur de solutions, double-cliquez sur **Analysis Services Tutorial.cube** dans le dossier **Cubes** pour ouvrir le Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f17d2-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="f17d2-122">Cliquez sur l'onglet **Navigateur** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="f17d2-123">Cliquez sur l’icône Excel, puis cliquez **Activer** quand vous êtes invité à activer les connexions.</span><span class="sxs-lookup"><span data-stu-id="f17d2-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="f17d2-124">Dans la liste des champs de tableau croisé dynamique, développez **Reseller Sales**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="f17d2-125">Faites glisser **Reseller Sales-Sales Amount** vers la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="f17d2-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="f17d2-126">Dans la liste des champs de tableau croisé dynamique, développez **Employee**, puis faites glisser la hiérarchie **Employees** vers la zone **Lignes** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="f17d2-127">Tous les membres de la hiérarchie Employees sont ajoutés à la colonne A du rapport de tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="f17d2-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="f17d2-128">L'illustration suivante montre la hiérarchie Employees développée.</span><span class="sxs-lookup"><span data-stu-id="f17d2-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="f17d2-129">![Tableau croisé dynamique affichant la hiérarchie Employees](../../2014/tutorials/media/l4-employee-1.gif "Tableau croisé dynamique affichant la hiérarchie Employees")</span><span class="sxs-lookup"><span data-stu-id="f17d2-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="f17d2-130">Remarquez que les ventes faites par chaque responsable dans le niveau 03 sont également affichées dans le niveau 04.</span><span class="sxs-lookup"><span data-stu-id="f17d2-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="f17d2-131">C'est parce que chaque responsable est également employé d'un autre responsable.</span><span class="sxs-lookup"><span data-stu-id="f17d2-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="f17d2-132">Au cours de la tâche suivante, vous allez masquer les montants de ces ventes.</span><span class="sxs-lookup"><span data-stu-id="f17d2-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="f17d2-133">Modification des propriétés d'attribut parent dans la dimension Employee</span><span class="sxs-lookup"><span data-stu-id="f17d2-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="f17d2-134">Basculez vers le concepteur de dimensions pour la dimension **Employee** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="f17d2-135">Cliquez sur l’onglet **Structure de dimension** , puis sélectionnez la hiérarchie d’attributs **Employees** dans le volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="f17d2-136">Notez l'icône unique de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="f17d2-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="f17d2-137">Cette icône signifie que l'attribut est la clé parente dans une hiérarchie parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="f17d2-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="f17d2-138">Notez également, dans la fenêtre des propriétés, que la propriété **Usage** de l’attribut est définie comme **Parent**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="f17d2-139">Cette propriété a été définie par l'Assistant Dimension lors de la conception de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f17d2-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="f17d2-140">L'Assistant a détecté automatiquement la relation parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="f17d2-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="f17d2-141">Dans la fenêtre des propriétés, cliquez sur le bouton (**...**) dans la cellule de la propriété **NamingTemplate** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="f17d2-142">Dans la boîte de dialogue **Modèle de nom de niveau** , vous pouvez définir le modèle d’attribution de nom de niveau qui détermine les noms de niveau dans la hiérarchie parent-enfant que les utilisateurs voient quand ils parcourent les cubes.</span><span class="sxs-lookup"><span data-stu-id="f17d2-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="f17d2-143">Dans la deuxième ligne, la **\*** ligne, tapez **Employee \* Level** dans la colonne **Name** , puis cliquez sur la troisième ligne.</span><span class="sxs-lookup"><span data-stu-id="f17d2-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="f17d2-144">Sous **Résultat** , chaque niveau est maintenant appelé « Employee Level » suivi d’un numéro incrémenté séquentiellement.</span><span class="sxs-lookup"><span data-stu-id="f17d2-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="f17d2-145">L’illustration suivante montre les éléments qui ont changé dans la boîte de dialogue **Modèle de nom de niveau** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="f17d2-146">![Boîte de dialogue modèle de nom de niveau](../../2014/tutorials/media/l4-namingtemplate.gif "Boîte de dialogue Modèle de nom de niveau")</span><span class="sxs-lookup"><span data-stu-id="f17d2-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="f17d2-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-147">Click **OK**.</span></span>

6.  <span data-ttu-id="f17d2-148">Dans la fenêtre des propriétés de l’attribut **Employees** , dans la cellule de la propriété **MembersWithData** , sélectionnez **NonLeafDataHidden** pour remplacer cette valeur par l’attribut **Employees** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="f17d2-149">Les données associées à des membres de niveau non-feuille de la hiérarchie parent-enfant sont masquées.</span><span class="sxs-lookup"><span data-stu-id="f17d2-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="f17d2-150">Navigation dans la dimension Employee avec les attributs modifiés</span><span class="sxs-lookup"><span data-stu-id="f17d2-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="f17d2-151">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="f17d2-152">Une fois le déploiement terminé, affichez le Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Reconnexion** dans la barre d’outils de l’onglet **Navigateur** .</span><span class="sxs-lookup"><span data-stu-id="f17d2-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="f17d2-153">Cliquez sur l'icône Excel, puis **Activer**.</span><span class="sxs-lookup"><span data-stu-id="f17d2-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="f17d2-154">Faites glisser **Reseller Sales-Sales Amount** vers la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="f17d2-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="f17d2-155">Faites glisser la hiérarchie **Employees** vers la zone Étiquettes de ligne.</span><span class="sxs-lookup"><span data-stu-id="f17d2-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="f17d2-156">L'illustration suivante montre les modifications apportées à la hiérarchie Employees.</span><span class="sxs-lookup"><span data-stu-id="f17d2-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="f17d2-157">Notez que Stephen Y. Jiang n’apparaît plus comme employé de lui-même.</span><span class="sxs-lookup"><span data-stu-id="f17d2-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="f17d2-158">![Hiérarchie Employees modifiée](../../2014/tutorials/media/l4-employee-2.png "Hiérarchie Employees modifiée")</span><span class="sxs-lookup"><span data-stu-id="f17d2-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="f17d2-159">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="f17d2-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="f17d2-160">Regroupement automatique des membres d'attribut</span><span class="sxs-lookup"><span data-stu-id="f17d2-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="f17d2-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f17d2-161">See Also</span></span>
 <span data-ttu-id="f17d2-162">Attributs de [hiérarchie parent-enfant](multidimensional-models/parent-child-dimension.md) [dans les hiérarchies parent-enfant](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="f17d2-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


