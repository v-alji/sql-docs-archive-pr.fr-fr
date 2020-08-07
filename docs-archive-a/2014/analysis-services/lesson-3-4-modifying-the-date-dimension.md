---
title: Modification de la dimension Date | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611390"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="2c778-102">Modification de la dimension Date</span><span class="sxs-lookup"><span data-stu-id="2c778-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="2c778-103">Dans les tâches de cette rubrique, vous allez créer une hiérarchie définie par l'utilisateur et vous allez modifier les noms de membre affichés pour les attributs Date, Month, Calendar Quarter et Calendar Semester.</span><span class="sxs-lookup"><span data-stu-id="2c778-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="2c778-104">Vous allez également définir des clés composites pour les attributs, contrôler l'ordre de tri des membres de dimension et définir les relations d'attributs.</span><span class="sxs-lookup"><span data-stu-id="2c778-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="2c778-105">Ajout d'un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="2c778-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="2c778-106">Vous pouvez ajouter un calcul nommé, c'est-à-dire une expression SQL qui est représentée sous la forme d'une colonne calculée, dans la table d'une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="2c778-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="2c778-107">L'expression apparaît et se comporte comme une colonne dans une table.</span><span class="sxs-lookup"><span data-stu-id="2c778-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="2c778-108">Les calculs nommés permettent d'étendre le schéma relationnel des tables existantes dans une vue de source des données, sans avoir à modifier la table dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="2c778-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="2c778-109">Pour plus d’informations, consultez [définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="2c778-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="2c778-110">Pour ajouter un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="2c778-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="2c778-111">Pour ouvrir la vue de source de données **Adventure Works DW 2012** , double-cliquez dessus dans le dossier **Vues des sources de données** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="2c778-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="2c778-112">En bas du volet **tables** , cliquez avec le bouton droit sur `Date` , puis cliquez sur **nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="2c778-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="2c778-113">Dans la boîte de dialogue **créer un calcul nommé** , tapez `SimpleDate` dans la zone **nom** de la colonne, puis tapez ou copiez-collez l' `DATENAME` instruction suivante dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="2c778-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="2c778-114">L'instruction `DATENAME` extrait les valeurs relatives à l'année, au mois et au jour à partir de la colonne FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="2c778-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="2c778-115">Vous utiliserez cette nouvelle colonne comme nom affiché de l'attribut FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="2c778-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="2c778-116">Cliquez sur **OK**, puis développez `Date` dans le volet **tables** .</span><span class="sxs-lookup"><span data-stu-id="2c778-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="2c778-117">Le `SimpleDate` calcul nommé s’affiche dans la liste des colonnes de la table de dates, avec une icône qui indique qu’il s’agit d’un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="2c778-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="2c778-118">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="2c778-119">Dans le volet **tables** , cliquez avec le bouton droit sur `Date` , puis cliquez sur Explorer les **données**.</span><span class="sxs-lookup"><span data-stu-id="2c778-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="2c778-120">Faites défiler vers la droite pour afficher la dernière colonne de la vue **Explorer la table Date** .</span><span class="sxs-lookup"><span data-stu-id="2c778-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="2c778-121">Notez que la `SimpleDate` colonne apparaît dans la vue de source de données, et que les données sont correctement concaténées à partir de plusieurs colonnes de la source de données sous-jacente, sans modifier la source de données d’origine.</span><span class="sxs-lookup"><span data-stu-id="2c778-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="2c778-122">Fermez la vue **Explorer la table Date** .</span><span class="sxs-lookup"><span data-stu-id="2c778-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="2c778-123">Utilisation du calcul nommé pour les noms des membres</span><span class="sxs-lookup"><span data-stu-id="2c778-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="2c778-124">Après avoir créé un calcul nommé dans la vue de source de données, vous pouvez utiliser le calcul nommé comme propriété d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="2c778-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="2c778-125">Pour utiliser le calcul nommé pour les noms des membres</span><span class="sxs-lookup"><span data-stu-id="2c778-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="2c778-126">Ouvrez le **Concepteur de dimensions** pour la dimension Date dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c778-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2c778-127">Pour ce faire, double-cliquez sur la `Date` dimension dans le nœud **Dimensions** de **Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="2c778-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="2c778-128">Dans le volet **Attributs** de l’onglet **Structure de dimension** , cliquez sur l’attribut **Date Key** .</span><span class="sxs-lookup"><span data-stu-id="2c778-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="2c778-129">Si la fenêtre Propriétés n’est pas ouverte, ouvrez-la, puis cliquez sur le bouton **Masquer automatiquement** dans la barre de titre afin qu’elle reste ouverte.</span><span class="sxs-lookup"><span data-stu-id="2c778-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="2c778-130">Cliquez sur le champ de propriété **NameColumn** en bas de la fenêtre, puis cliquez sur le bouton de navigation (**...**) pour ouvrir la boîte de dialogue **colonne de nom** .</span><span class="sxs-lookup"><span data-stu-id="2c778-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="2c778-131">Sélectionnez `SimpleDate` au bas de la liste **colonne source** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="2c778-132">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="2c778-133">Création d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2c778-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="2c778-134">Vous pouvez créer une hiérarchie en faisant glisser un attribut du volet **Attributes** vers le volet **Hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="2c778-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="2c778-135">Pour créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="2c778-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="2c778-136">Dans l’onglet **structure de dimension** du concepteur de dimensions pour la `Date` dimension, faites glisser l’attribut **année civile** du volet **attributs** vers le volet **hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="2c778-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="2c778-137">Faites glisser l’attribut **Calendar Semester** du volet **Attributs** vers la cellule **\<new level>** dans le volet **Hiérarchies** , sous le niveau **Calendar Year** .</span><span class="sxs-lookup"><span data-stu-id="2c778-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="2c778-138">Faites glisser l’attribut **Calendar Quarter** du volet **Attributs** vers la cellule **\<new level>** dans le volet **Hiérarchies** , sous le niveau **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="2c778-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="2c778-139">Faites glisser l’attribut **English Month Name** du volet **Attributs** vers la cellule **\<new level>** dans le volet **Hiérarchies** , sous le niveau **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="2c778-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="2c778-140">Faites glisser l’attribut **Date Key** du volet **Attributs** vers la cellule **\<new level>** dans le volet **Hiérarchies** , sous le niveau **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="2c778-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="2c778-141">Dans le volet **hiérarchies** , cliquez avec le bouton droit sur la barre de titre de la hiérarchie **hiérarchie** , cliquez sur **Renommer**, puis tapez `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="2c778-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="2c778-142">En utilisant le menu contextuel du clic droit, dans la `Calendar Date` hiérarchie, renommez le niveau **English Month Name** en `Calendar Month` , puis renommez le niveau de la **clé Date** en `Date` .</span><span class="sxs-lookup"><span data-stu-id="2c778-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="2c778-143">Supprimez l’attribut **Full Date Alternate Key** du volet **Attributs** , car vous ne l’utiliserez pas.</span><span class="sxs-lookup"><span data-stu-id="2c778-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="2c778-144">Cliquez sur **OK** dans la fenêtre de confirmation **Supprimer les objets** .</span><span class="sxs-lookup"><span data-stu-id="2c778-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="2c778-145">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="2c778-146">Définition des relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="2c778-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="2c778-147">Si les données sous-jacentes le prennent en charge, il est également conseillé de définir des relations d'attributs entre les attributs.</span><span class="sxs-lookup"><span data-stu-id="2c778-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="2c778-148">La définition de relations d'attributs accélère le traitement des dimensions, des partitions et des requêtes.</span><span class="sxs-lookup"><span data-stu-id="2c778-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="2c778-149">Pour définir les relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="2c778-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="2c778-150">Dans le **Concepteur de dimensions** pour la `Date` dimension, cliquez sur l’onglet **relations d’attributs** .</span><span class="sxs-lookup"><span data-stu-id="2c778-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="2c778-151">Dans le diagramme, cliquez avec le bouton droit sur l’attribut **English Month Name** puis cliquez sur **Nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="2c778-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="2c778-152">Dans la boîte de dialogue **Créer une relation d’attribut** , **l’Attribut source** est **English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="2c778-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="2c778-153">Définissez **l’Attribut associé** avec la valeur **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="2c778-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="2c778-154">Dans la liste **Type de relation** , définissez le type de relation sur **Rigide**.</span><span class="sxs-lookup"><span data-stu-id="2c778-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="2c778-155">Le type de relation est **Rigide** car les relations entre les membres ne changeront pas au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="2c778-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="2c778-156">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="2c778-157">Dans le diagramme, cliquez avec le bouton droit sur l’attribut **Calendar Quarter** , puis cliquez sur **Nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="2c778-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="2c778-158">Dans la boîte de dialogue **Créer une relation d’attribut** , **l’Attribut source** est **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="2c778-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="2c778-159">Définissez **l’Attribut associé** avec la valeur **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="2c778-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="2c778-160">Dans la liste **Type de relation** , définissez le type de relation sur **Rigide**.</span><span class="sxs-lookup"><span data-stu-id="2c778-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="2c778-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="2c778-162">Dans le diagramme, cliquez avec le bouton droit sur l’attribut **Calendar Semester** , puis cliquez sur **Nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="2c778-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="2c778-163">Dans la boîte de dialogue **Créer une relation d’attribut** , **l’Attribut source** est **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="2c778-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="2c778-164">Définissez **l’Attribut associé** avec la valeur **Calendar Year**.</span><span class="sxs-lookup"><span data-stu-id="2c778-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="2c778-165">Dans la liste **Type de relation** , définissez le type de relation sur **Rigide**.</span><span class="sxs-lookup"><span data-stu-id="2c778-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="2c778-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="2c778-167">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="2c778-168">Attribution de noms uniques aux membres de dimension</span><span class="sxs-lookup"><span data-stu-id="2c778-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="2c778-169">Dans cette tâche, vous allez créer des colonnes de nom conviviales qui seront utilisées par les attributs **EnglishMonthName**, **CalendarQuarter**et **CalendarSemester** .</span><span class="sxs-lookup"><span data-stu-id="2c778-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="2c778-170">Pour fournir des noms uniques aux membres de dimension</span><span class="sxs-lookup"><span data-stu-id="2c778-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="2c778-171">Pour basculer vers la vue de source de données \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , double-cliquez sur celle-ci dans le dossier **vues des sources de données** de Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="2c778-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="2c778-172">Dans le volet **tables** , cliquez avec le bouton droit sur `Date` , puis cliquez sur **nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="2c778-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="2c778-173">Dans la boîte de dialogue **créer un calcul nommé** , tapez `MonthName` dans la zone **nom** de la colonne, puis tapez ou copiez-collez l’instruction suivante dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="2c778-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="2c778-174">L'instruction concatène le mois et l'année dans une nouvelle colonne pour chaque mois de la table.</span><span class="sxs-lookup"><span data-stu-id="2c778-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="2c778-175">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2c778-176">Dans le volet **tables** , cliquez avec le bouton droit sur `Date` , puis cliquez sur **nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="2c778-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="2c778-177">Dans la boîte de dialogue **créer un calcul nommé** , tapez `CalendarQuarterDesc` dans la zone **nom** de la colonne, puis tapez ou copiez et collez le script SQL suivant dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="2c778-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="2c778-178">Ce script SQL concatène le trimestre calendaire et l'année dans une nouvelle colonne pour chaque trimestre de la table.</span><span class="sxs-lookup"><span data-stu-id="2c778-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="2c778-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="2c778-180">Dans le volet **tables** , cliquez avec le bouton droit sur `Date` , puis cliquez sur **nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="2c778-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="2c778-181">Dans la boîte de dialogue **créer un calcul nommé** , tapez `CalendarSemesterDesc` dans la zone **nom** de la colonne, puis tapez ou copiez et collez le script SQL suivant dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="2c778-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="2c778-182">Ce script SQL concatène le semestre calendaire et l'année dans une nouvelle colonne pour chaque semestre de la table.</span><span class="sxs-lookup"><span data-stu-id="2c778-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="2c778-183">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="2c778-184">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="2c778-185">Définition de propriété KeyColumns composite et définition de Colonne de nom</span><span class="sxs-lookup"><span data-stu-id="2c778-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="2c778-186">La propriété **KeyColumns** contient la colonne ou les colonnes qui représentent la clé pour l’attribut.</span><span class="sxs-lookup"><span data-stu-id="2c778-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="2c778-187">Dans cette tâche, vous allez définir une propriété **KeyColumns**composite.</span><span class="sxs-lookup"><span data-stu-id="2c778-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="2c778-188">Pour définir une propriété KeyColumns composite pour l'attribut English Month Name</span><span class="sxs-lookup"><span data-stu-id="2c778-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="2c778-189">Ouvrez l’onglet **Structure de dimension** pour la dimension Date.</span><span class="sxs-lookup"><span data-stu-id="2c778-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="2c778-190">Dans le volet **Attributs** , cliquez sur l’attribut **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="2c778-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="2c778-191">Dans la fenêtre **Propriétés** , cliquez dans le champ **KeyColumns** , puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="2c778-192">Dans la boîte de dialogue **colonnes clés** , dans la liste **colonnes disponibles** , sélectionnez la colonne **CalendarYear**, puis cliquez sur le **>** bouton.</span><span class="sxs-lookup"><span data-stu-id="2c778-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="2c778-193">Les colonnes **EnglishMonthName** et **CalendarYear** s’affichent maintenant dans la liste **Colonnes clés** .</span><span class="sxs-lookup"><span data-stu-id="2c778-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="2c778-194">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="2c778-195">Pour définir la propriété **NameColumn** de l’attribut **EnglishMonthName** , cliquez dans le champ **NameColumn** de la fenêtre des propriétés, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="2c778-196">Dans la boîte de dialogue **colonne de nom** , dans la liste **colonne source** , sélectionnez `MonthName` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="2c778-197">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="2c778-198">Pour définir la propriété KeyColumns composite pour l'attribut Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="2c778-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="2c778-199">Dans le volet **Attributs** , cliquez sur l’attribut **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="2c778-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="2c778-200">Dans la fenêtre **Propriétés** , cliquez dans le champ **KeyColumns** , puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="2c778-201">Dans la boîte de dialogue **colonnes clés** , dans la liste **colonnes disponibles** , sélectionnez la colonne **CalendarYear**, puis cliquez sur le **>** bouton.</span><span class="sxs-lookup"><span data-stu-id="2c778-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="2c778-202">Les colonnes **CalendarQuarter** et **CalendarYear** s’affichent maintenant dans la liste **Colonnes clés** .</span><span class="sxs-lookup"><span data-stu-id="2c778-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="2c778-203">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2c778-204">Pour définir la propriété **NameColumn** de l’attribut **Calendar Quarter** , cliquez dans le champ **NameColumn** de la fenêtre des propriétés, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="2c778-205">Dans la boîte de dialogue **colonne de nom** , dans la liste **colonne source** , sélectionnez `CalendarQuarterDesc` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2c778-206">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="2c778-207">Pour définir la propriété KeyColumns composite pour l'attribut Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="2c778-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="2c778-208">Dans le volet **Attributs** , cliquez sur l’attribut **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="2c778-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="2c778-209">Dans la fenêtre **Propriétés** , cliquez dans le champ **KeyColumns** , puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="2c778-210">Dans la boîte de dialogue **Colonnes clés** , dans la liste **Colonnes disponibles** , sélectionnez la colonne **CalendarYear**, puis cliquez sur le bouton **>** .</span><span class="sxs-lookup"><span data-stu-id="2c778-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="2c778-211">Les colonnes **CalendarSemester** et **CalendarYear** s’affichent maintenant dans la liste **Colonnes clés** .</span><span class="sxs-lookup"><span data-stu-id="2c778-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="2c778-212">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2c778-213">Pour définir la propriété **NameColumn** de l’attribut **Calendar Semester** , cliquez dans le champ **NameColumn** de la fenêtre des propriétés, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="2c778-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="2c778-214">Dans la boîte de dialogue **colonne de nom** , dans la liste **colonne source** , sélectionnez `CalendarSemesterDesc` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2c778-215">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="2c778-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="2c778-216">Déploiement et consultation des modifications</span><span class="sxs-lookup"><span data-stu-id="2c778-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="2c778-217">Une fois les attributs et les hiérarchies modifiés, vous devez déployer les modifications et retraiter les objets associés avant de pouvoir visualiser ces modifications.</span><span class="sxs-lookup"><span data-stu-id="2c778-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="2c778-218">Pour déployer et consulter les modifications</span><span class="sxs-lookup"><span data-stu-id="2c778-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="2c778-219">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2c778-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="2c778-220">Une fois que vous avez reçu le message le **déploiement est terminé** , cliquez sur l’onglet **navigateur** du **Concepteur de dimensions** pour la `Date` dimension, puis cliquez sur le bouton reconnecter de la barre d’outils du concepteur.</span><span class="sxs-lookup"><span data-stu-id="2c778-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="2c778-221">Sélectionnez **Calendar Quarter** dans la liste **Hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="2c778-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="2c778-222">Vérifiez les membres dans la hiérarchie d’attribut **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="2c778-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="2c778-223">Remarquez que les noms des membres de la hiérarchie d’attribut **Calendar Quarter** sont plus clairs et faciles à utiliser, car vous avez créé un calcul nommé utilisé comme nom.</span><span class="sxs-lookup"><span data-stu-id="2c778-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="2c778-224">Les membres existent maintenant dans la hiérarchie d’attribut **Calendar Quarter** pour chaque trimestre de chaque année.</span><span class="sxs-lookup"><span data-stu-id="2c778-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="2c778-225">Les membres ne sont pas triés par ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="2c778-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="2c778-226">Ils sont au contraire triés par trimestre, puis par année.</span><span class="sxs-lookup"><span data-stu-id="2c778-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="2c778-227">Au cours de la tâche suivante, vous allez modifier cela pour trier les membres de cette hiérarchie d'attributs par année, puis par trimestre.</span><span class="sxs-lookup"><span data-stu-id="2c778-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="2c778-228">Passez en revue les membres des hiérarchies d’attributs **English Month Name** et **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="2c778-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="2c778-229">Notez que les membres de ces hiérarchies ne sont pas non plus classés par ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="2c778-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="2c778-230">Ils sont au contraire triés par mois ou semestre, respectivement, puis par année.</span><span class="sxs-lookup"><span data-stu-id="2c778-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="2c778-231">Au cours de la tâche suivante, vous allez modifier cela pour changer l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="2c778-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="2c778-232">Modification de l'ordre de tri en changeant l'ordre des membres de clé composite</span><span class="sxs-lookup"><span data-stu-id="2c778-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="2c778-233">Dans cette tâche, vous allez modifier l'ordre de tri en modifiant l'ordre des clés qui composent la clé composite.</span><span class="sxs-lookup"><span data-stu-id="2c778-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="2c778-234">Pour modifier l'ordre des membres de clé composite</span><span class="sxs-lookup"><span data-stu-id="2c778-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="2c778-235">Ouvrez l’onglet **structure** de dimension du concepteur de dimensions pour la `Date` dimension, puis sélectionnez **semestre calendaire** dans le volet **attributs** .</span><span class="sxs-lookup"><span data-stu-id="2c778-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="2c778-236">Dans la fenêtre des propriétés, examinez la valeur de la propriété **OrderBy** .</span><span class="sxs-lookup"><span data-stu-id="2c778-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="2c778-237">La valeur est **Clé**.</span><span class="sxs-lookup"><span data-stu-id="2c778-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="2c778-238">Les membres de la hiérarchie d’attributs **Calendar Semester** sont triés en fonction de la valeur de leur clé.</span><span class="sxs-lookup"><span data-stu-id="2c778-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="2c778-239">Avec une clé composite, l'ordre des clés de membre est basé en premier sur la valeur de la première clé de membre, puis sur la valeur de la seconde clé de membre.</span><span class="sxs-lookup"><span data-stu-id="2c778-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="2c778-240">En d’autres termes, les membres de la hiérarchie d’attributs **Calendar Semester** sont triés en premier lieu par semestre, puis par année.</span><span class="sxs-lookup"><span data-stu-id="2c778-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="2c778-241">Dans la fenêtre des propriétés, cliquez sur le bouton de navigation (**...**) pour changer la valeur de la propriété **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="2c778-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="2c778-242">Dans la liste **Colonnes clés** de la boîte de dialogue **Colonnes clés** , vérifiez que **CalendarSemester** est sélectionné, puis cliquez sur la flèche du bas pour inverser l’ordre des membres de cette clé composite.</span><span class="sxs-lookup"><span data-stu-id="2c778-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="2c778-243">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="2c778-244">Les membres de la hiérarchie d'attributs sont maintenant triés en premier lieu par année, puis par semestre.</span><span class="sxs-lookup"><span data-stu-id="2c778-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="2c778-245">Sélectionnez **Calendar Quarter** dans le volet **Attributs** , puis cliquez sur le bouton de navigation (**...**) pour la propriété **KeyColumns** dans la fenêtre des propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c778-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="2c778-246">Dans la liste **Colonnes clés** de la boîte de dialogue **Colonnes clés** , vérifiez que **CalendarQuarter** est sélectionné, puis cliquez sur la flèche bas pour inverser l’ordre des membres de cette clé composite.</span><span class="sxs-lookup"><span data-stu-id="2c778-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="2c778-247">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="2c778-248">Les membres de la hiérarchie d'attributs sont maintenant triés en premier lieu par année, puis par trimestre.</span><span class="sxs-lookup"><span data-stu-id="2c778-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="2c778-249">Sélectionnez **English Month Name** dans le volet **Attributs** , puis cliquez sur le bouton de sélection (**...**) pour la propriété **KeyColumns** dans la fenêtre des propriétés.</span><span class="sxs-lookup"><span data-stu-id="2c778-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="2c778-250">Dans la liste **Colonnes clés** de la boîte de dialogue **Colonnes clés** , vérifiez que **EnglishMonthName** est sélectionné, puis cliquez sur la flèche bas pour inverser l’ordre des membres de cette clé composite.</span><span class="sxs-lookup"><span data-stu-id="2c778-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="2c778-251">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c778-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="2c778-252">Les membres de la hiérarchie d'attributs sont maintenant triés en premier lieu par année, puis par mois.</span><span class="sxs-lookup"><span data-stu-id="2c778-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="2c778-253">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2c778-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="2c778-254">Une fois le déploiement terminé, cliquez sur l’onglet **navigateur** dans le concepteur de dimensions pour la `Date` dimension.</span><span class="sxs-lookup"><span data-stu-id="2c778-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="2c778-255">Dans la barre d’outils de l’onglet **Navigateur** , cliquez sur le bouton Reconnecter.</span><span class="sxs-lookup"><span data-stu-id="2c778-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="2c778-256">Examinez les membres des hiérarchies d’attribut **Calendar Quarter** et **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="2c778-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="2c778-257">Notez que les membres de ces hiérarchies sont maintenant triés par ordre chronologique, par année, puis par trimestre ou semestre, respectivement.</span><span class="sxs-lookup"><span data-stu-id="2c778-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="2c778-258">Passez en revue les membres de la hiérarchie d’attributs **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="2c778-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="2c778-259">Notez que les membres de la hiérarchie sont maintenant triés d'abord par année, puis alphabétiquement par mois.</span><span class="sxs-lookup"><span data-stu-id="2c778-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="2c778-260">La raison en est que le type de données de la colonne EnglishCalendarMonth dans la vue de source des données est une colonne de chaîne, basée sur le type de données nvarchar dans la base de données relationnelle sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="2c778-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="2c778-261">Pour plus d’informations sur la façon de trier les mois chronologiquement au sein de chaque année, consultez [Tri des membres d’attribut sur la base d’un attribut secondaire](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="2c778-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2c778-262">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="2c778-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2c778-263">Exploration du cube déployé</span><span class="sxs-lookup"><span data-stu-id="2c778-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="2c778-264">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c778-264">See Also</span></span>  
 [<span data-ttu-id="2c778-265">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="2c778-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
