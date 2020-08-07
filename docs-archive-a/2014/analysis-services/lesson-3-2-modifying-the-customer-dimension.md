---
title: Modification de la dimension Customer | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611989"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="036a2-102">Modification de la dimension Customer</span><span class="sxs-lookup"><span data-stu-id="036a2-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="036a2-103">Il existe différents moyens de rendre les dimensions d'un cube plus conviviales et plus fonctionnelles.</span><span class="sxs-lookup"><span data-stu-id="036a2-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="036a2-104">Dans les tâches dans cette rubrique, vous modifiez la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="036a2-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="036a2-105">Affectation d'un nouveau nom aux attributs</span><span class="sxs-lookup"><span data-stu-id="036a2-105">Renaming Attributes</span></span>  
 <span data-ttu-id="036a2-106">Vous pouvez modifier les noms d’attributs avec l’onglet **Structure de dimension** du Concepteur de dimensions.</span><span class="sxs-lookup"><span data-stu-id="036a2-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="036a2-107">Pour renommer un attribut</span><span class="sxs-lookup"><span data-stu-id="036a2-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="036a2-108">Basculez vers le **Concepteur de dimensions** pour la dimension Customer dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="036a2-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="036a2-109">Pour cela, double-cliquez sur la dimension **Customer** du nœud **Dimensions** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="036a2-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="036a2-110">Dans le volet **Attributs** , cliquez avec le bouton droit sur **English Country Region Name**et cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="036a2-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="036a2-111">Remplacez le nom de l’attribut par `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="036a2-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="036a2-112">Modifiez les noms des attributs suivants de la même manière :</span><span class="sxs-lookup"><span data-stu-id="036a2-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="036a2-113">Attribut d' **éducation anglais** -changer en`Education`</span><span class="sxs-lookup"><span data-stu-id="036a2-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="036a2-114">Attribut d' **occupation en anglais** -changer en`Occupation`</span><span class="sxs-lookup"><span data-stu-id="036a2-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="036a2-115">**State Province Name** attribut-change to`State-Province`</span><span class="sxs-lookup"><span data-stu-id="036a2-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="036a2-116">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="036a2-117">Création d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="036a2-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="036a2-118">Vous pouvez créer une hiérarchie en faisant glisser un attribut du volet **Attributes** vers le volet **Hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="036a2-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="036a2-119">Pour créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="036a2-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="036a2-120">Faites glisser l' `Country-Region` attribut du volet **attributs** vers le volet **hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="036a2-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="036a2-121">Faites glisser l' `State-Province` attribut du volet **attributs** vers la **\<new level>** cellule dans le volet **hiérarchies** , sous le `Country-Region` niveau.</span><span class="sxs-lookup"><span data-stu-id="036a2-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="036a2-122">Faites glisser l’attribut **City** du volet **attributs** vers la **\<new level>** cellule dans le **volet Hiérarchies** , sous le `State-Province` niveau.</span><span class="sxs-lookup"><span data-stu-id="036a2-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="036a2-123">Dans le volet **hiérarchies** de l’onglet **structure de dimension** , cliquez avec le bouton droit sur la barre de titre de la hiérarchie **hiérarchie** , sélectionnez **Renommer**, puis tapez `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="036a2-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="036a2-124">Le nom de la hiérarchie est maintenant `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="036a2-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="036a2-125">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="036a2-126">Ajout d'un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="036a2-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="036a2-127">Vous pouvez ajouter un calcul nommé, c'est-à-dire une expression SQL qui est représentée sous la forme d'une colonne calculée, dans la table d'une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="036a2-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="036a2-128">L'expression apparaît et se comporte comme une colonne dans une table.</span><span class="sxs-lookup"><span data-stu-id="036a2-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="036a2-129">Les calculs nommés permettent d'étendre le schéma relationnel des tables existantes dans une vue de source de données, sans avoir à modifier la table dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="036a2-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="036a2-130">Pour plus d’informations, consultez [définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="036a2-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="036a2-131">Pour ajouter un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="036a2-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="036a2-132">Ouvrez la vue de source de données \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* en double-cliquant dessus dans le dossier **vues des sources de données** de Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="036a2-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="036a2-133">Dans le volet **Tables** à gauche, cliquez avec le bouton droit sur **Customer**, puis cliquez sur **Nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="036a2-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="036a2-134">Dans la boîte de dialogue **créer un calcul nommé** , tapez `FullName` dans la zone **nom** de la colonne, puis tapez ou copiez-collez l' `CASE` instruction suivante dans la zone **expression** :</span><span class="sxs-lookup"><span data-stu-id="036a2-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="036a2-135">L' `CASE` instruction concatène les colonnes **FirstName**, **MiddleName**et **LastName** en une seule colonne que vous allez utiliser dans la dimension Customer comme nom affiché pour l’attribut **Customer** .</span><span class="sxs-lookup"><span data-stu-id="036a2-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="036a2-136">Cliquez sur **OK**, puis développez **Customer** dans le volet **Tables** .</span><span class="sxs-lookup"><span data-stu-id="036a2-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="036a2-137">Le `FullName` calcul nommé s’affiche dans la liste des colonnes de la table Customer, avec une icône qui indique qu’il s’agit d’un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="036a2-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="036a2-138">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="036a2-139">Dans le volet **Tables** , cliquez avec le bouton droit sur **Customer**, puis cliquez sur **Explorer les données**.</span><span class="sxs-lookup"><span data-stu-id="036a2-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="036a2-140">Vérifiez la dernière colonne de la vue **Explorer la table Customer** .</span><span class="sxs-lookup"><span data-stu-id="036a2-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="036a2-141">Notez que la `FullName` colonne apparaît dans la vue de source de données, et que les données sont correctement concaténées à partir de plusieurs colonnes de la source de données sous-jacente et sans modification de la source de données d’origine.</span><span class="sxs-lookup"><span data-stu-id="036a2-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="036a2-142">Fermez l'onglet **Explorer la table Customer** .</span><span class="sxs-lookup"><span data-stu-id="036a2-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="036a2-143">Utilisation du calcul nommé pour les noms des membres</span><span class="sxs-lookup"><span data-stu-id="036a2-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="036a2-144">Après avoir créé un calcul nommé dans la vue de la source de données, vous pouvez utiliser le calcul nommé comme propriété d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="036a2-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="036a2-145">Pour utiliser le calcul nommé pour les noms des membres</span><span class="sxs-lookup"><span data-stu-id="036a2-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="036a2-146">Affichez le Concepteur de dimensions pour la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="036a2-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="036a2-147">Dans le volet **Attributs** de l’onglet **Structure de dimension** , cliquez sur l’attribut **Customer Key** .</span><span class="sxs-lookup"><span data-stu-id="036a2-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="036a2-148">Ouvrez la fenêtre Propriétés et cliquez sur le bouton **Masquer automatiquement** de la barre de titre pour qu’elle reste ouverte.</span><span class="sxs-lookup"><span data-stu-id="036a2-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="036a2-149">Dans le champ **nom** de la propriété, tapez `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="036a2-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="036a2-150">Cliquez dans le champ de propriété **NameColumn** en bas, puis cliquez sur le bouton Parcourir (**...**) pour ouvrir la boîte de dialogue **colonne de nom** .</span><span class="sxs-lookup"><span data-stu-id="036a2-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="036a2-151">Sélectionnez `FullName` au bas de la liste **colonne source** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="036a2-152">Dans l’onglet structure de dimension, faites glisser l' `Full Name` attribut du volet **attributs** vers la **\<new level>** cellule dans le volet **hiérarchies** , sous le niveau **City** .</span><span class="sxs-lookup"><span data-stu-id="036a2-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="036a2-153">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="036a2-154">Définition de dossiers d'affichage</span><span class="sxs-lookup"><span data-stu-id="036a2-154">Defining Display Folders</span></span>  
 <span data-ttu-id="036a2-155">Vous pouvez utiliser les dossiers d'affichage pour grouper les hiérarchies d'utilisateur et d'attributs dans des arborescences afin d'augmenter la convivialité.</span><span class="sxs-lookup"><span data-stu-id="036a2-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="036a2-156">Pour définir les dossiers d'affichage</span><span class="sxs-lookup"><span data-stu-id="036a2-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="036a2-157">Ouvrez l’onglet **Structure de dimension** pour la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="036a2-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="036a2-158">Dans le volet **Attributs** , sélectionnez les attributs suivants en maintenant la touche Ctrl enfoncée pendant que vous cliquez sur chacun d’eux :</span><span class="sxs-lookup"><span data-stu-id="036a2-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="036a2-159">**Ville**</span><span class="sxs-lookup"><span data-stu-id="036a2-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="036a2-160">**Postal Code**</span><span class="sxs-lookup"><span data-stu-id="036a2-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="036a2-161">Dans la Fenêtre Propriétés, cliquez sur le champ de propriété **AttributeHierarchyDisplayFolder** en haut (vous devrez peut-être pointer dessus pour afficher le nom complet), puis tapez `Location` .</span><span class="sxs-lookup"><span data-stu-id="036a2-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="036a2-162">Dans le volet **hiérarchies** , cliquez sur `Customer Geography` , puis dans le fenêtre Propriétés à droite, sélectionnez `Location` comme valeur de la propriété **DisplayFolder** .</span><span class="sxs-lookup"><span data-stu-id="036a2-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="036a2-163">Dans le volet **Attributs** , sélectionnez les attributs suivants en maintenant la touche Ctrl enfoncée pendant que vous cliquez sur chacun d’eux :</span><span class="sxs-lookup"><span data-stu-id="036a2-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="036a2-164">**Commute Distance**</span><span class="sxs-lookup"><span data-stu-id="036a2-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="036a2-165">**Sexe**</span><span class="sxs-lookup"><span data-stu-id="036a2-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="036a2-166">**House Owner Flag**</span><span class="sxs-lookup"><span data-stu-id="036a2-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="036a2-167">**Marital Status**</span><span class="sxs-lookup"><span data-stu-id="036a2-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="036a2-168">**Number Cars Owned**</span><span class="sxs-lookup"><span data-stu-id="036a2-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="036a2-169">**Number Children At Home**</span><span class="sxs-lookup"><span data-stu-id="036a2-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="036a2-170">**Total Children**</span><span class="sxs-lookup"><span data-stu-id="036a2-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="036a2-171">**Yearly Income**</span><span class="sxs-lookup"><span data-stu-id="036a2-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="036a2-172">Dans la Fenêtre Propriétés, cliquez sur le champ de propriété **AttributeHierarchyDisplayFolder** en haut, puis tapez `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="036a2-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="036a2-173">Dans le volet **Attributs** , sélectionnez les attributs suivants en maintenant la touche Ctrl enfoncée pendant que vous cliquez sur chacun d’eux :</span><span class="sxs-lookup"><span data-stu-id="036a2-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="036a2-174">**Adresse e-mail**</span><span class="sxs-lookup"><span data-stu-id="036a2-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="036a2-175">**Téléphone**</span><span class="sxs-lookup"><span data-stu-id="036a2-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="036a2-176">Dans l’Fenêtre Propriétés, cliquez sur le champ de propriété **AttributeHierarchyDisplayFolder** et tapez `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="036a2-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="036a2-177">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="036a2-178">Définition de KeyColumns composite</span><span class="sxs-lookup"><span data-stu-id="036a2-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="036a2-179">La propriété **KeyColumns** contient la colonne ou les colonnes qui représentent la clé pour l’attribut.</span><span class="sxs-lookup"><span data-stu-id="036a2-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="036a2-180">Dans cette leçon, vous allez créer une clé composite pour la **ville** et les `State-Province` attributs.</span><span class="sxs-lookup"><span data-stu-id="036a2-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="036a2-181">Les clés composites peuvent être utiles lorsque vous devez identifier un attribut de façon unique.</span><span class="sxs-lookup"><span data-stu-id="036a2-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="036a2-182">Par exemple, lorsque vous définissez des relations d’attributs plus loin dans ce didacticiel, un attribut **City** doit identifier un attribut de façon unique `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="036a2-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="036a2-183">Toutefois, il peut y avoir plusieurs villes avec le même nom dans différents états.</span><span class="sxs-lookup"><span data-stu-id="036a2-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="036a2-184">Pour cette raison, vous allez créer une clé composite composée des colonnes **StateProvinceName** et **City** pour l’attribut **City** .</span><span class="sxs-lookup"><span data-stu-id="036a2-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="036a2-185">Pour plus d’informations, consultez [Modifier la propriété KeyColumn d’un attribut](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="036a2-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="036a2-186">Pour définir KeyColumns composite pour l'attribut Ville</span><span class="sxs-lookup"><span data-stu-id="036a2-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="036a2-187">Ouvrez l’onglet **Structure de dimension** pour la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="036a2-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="036a2-188">Dans le volet **Attributs** , cliquez sur l’attribut **City** .</span><span class="sxs-lookup"><span data-stu-id="036a2-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="036a2-189">Dans la fenêtre **Propriétés** , cliquez dans le champ **KeyColumns** en bas, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="036a2-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="036a2-190">Dans la boîte de dialogue **Colonnes clés** , dans la liste **Colonnes disponibles** , sélectionnez la colonne **StateProvinceName**, puis cliquez sur le bouton **>** .</span><span class="sxs-lookup"><span data-stu-id="036a2-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="036a2-191">Les colonnes **City** et **StateProvinceName** s’affichent maintenant dans la liste **Colonnes clés** .</span><span class="sxs-lookup"><span data-stu-id="036a2-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="036a2-192">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="036a2-193">Pour définir la propriété **NameColumn** de l’attribut **City** , cliquez dans le champ **NameColumn** de la fenêtre Propriétés, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="036a2-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="036a2-194">Dans la boîte de dialogue **Colonne de nom** , dans la liste **Colonne source** , sélectionnez **City**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="036a2-195">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="036a2-196">Pour définir KeyColumns composite pour l'attribut État-Province</span><span class="sxs-lookup"><span data-stu-id="036a2-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="036a2-197">Vérifiez que l’onglet **Structure de dimension** de la dimension Customer est ouvert.</span><span class="sxs-lookup"><span data-stu-id="036a2-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="036a2-198">Dans le volet **attributs** , cliquez sur l' `State-Province` attribut.</span><span class="sxs-lookup"><span data-stu-id="036a2-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="036a2-199">Dans la fenêtre **Propriétés** , cliquez dans le champ **KeyColumns** , puis cliquez sur le bouton Parcourir (**...**).</span><span class="sxs-lookup"><span data-stu-id="036a2-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="036a2-200">Dans la boîte de dialogue **Colonnes clés** , dans la liste **Colonnes disponibles** , sélectionnez la colonne **EnglishCountryRegionName**, puis cliquez sur le bouton **>** .</span><span class="sxs-lookup"><span data-stu-id="036a2-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="036a2-201">Les colonnes **EnglishCountryRegionName** et **StateProvinceName** s’affichent maintenant dans la liste **Colonnes clés** .</span><span class="sxs-lookup"><span data-stu-id="036a2-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="036a2-202">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="036a2-203">Pour définir la propriété **NameColumn** de l' `State-Province` attribut, cliquez sur le champ **NameColumn** dans la fenêtre Propriétés, puis cliquez sur le bouton de navigation (**...**).</span><span class="sxs-lookup"><span data-stu-id="036a2-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="036a2-204">Dans la boîte de dialogue **Colonne de nom** , dans la liste **Colonne source** , sélectionnez **StateProvinceName**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="036a2-205">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="036a2-206">Définition des relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="036a2-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="036a2-207">Si les données sous-jacentes le prennent en charge, il est également conseillé de définir des relations d'attributs entre les attributs.</span><span class="sxs-lookup"><span data-stu-id="036a2-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="036a2-208">La définition de relations d'attributs accélère le traitement des dimensions, des partitions et des requêtes.</span><span class="sxs-lookup"><span data-stu-id="036a2-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="036a2-209">Pour plus d’informations, consultez [Définir des relations d’attributs](multidimensional-models/attribute-relationships-define.md) et [Relations d’attributs](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="036a2-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="036a2-210">Pour définir les relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="036a2-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="036a2-211">Dans le **Concepteur de dimensions** pour la dimension Customer, cliquez sur l’onglet **relations d’attributs** . Vous devrez peut-être attendre.</span><span class="sxs-lookup"><span data-stu-id="036a2-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="036a2-212">Dans le diagramme, cliquez avec le bouton droit sur l’attribut **City** , puis sélectionnez **Nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="036a2-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="036a2-213">Dans la boîte de dialogue **Créer une relation d’attribut** , **l’Attribut source** est **City**.</span><span class="sxs-lookup"><span data-stu-id="036a2-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="036a2-214">Affectez à l' **attribut associé** la valeur `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="036a2-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="036a2-215">Dans la liste **Type de relation** , définissez le type de relation sur **Rigide**.</span><span class="sxs-lookup"><span data-stu-id="036a2-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="036a2-216">Le type de relation est **Rigide** car les relations entre les membres ne changeront pas au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="036a2-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="036a2-217">Par exemple, il serait exceptionnel qu'une ville fasse partie d'un autre état ou d'une autre province.</span><span class="sxs-lookup"><span data-stu-id="036a2-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="036a2-218">Dans le diagramme, cliquez avec le bouton droit sur l' `State-Province` attribut, puis sélectionnez **nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="036a2-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="036a2-219">Dans la boîte de dialogue **créer une relation d’attribut** , l' **attribut source** est `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="036a2-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="036a2-220">Affectez à l' **attribut associé** la valeur `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="036a2-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="036a2-221">Dans la liste **Type de relation** , définissez le type de relation sur **Rigide**.</span><span class="sxs-lookup"><span data-stu-id="036a2-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="036a2-222">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="036a2-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="036a2-223">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="036a2-224">Déploiement des modifications, traitement des objets et affichage des modifications</span><span class="sxs-lookup"><span data-stu-id="036a2-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="036a2-225">Une fois les attributs et les hiérarchies modifiés, vous devez déployer les modifications et retraiter les objets associés avant de pouvoir visualiser ces modifications.</span><span class="sxs-lookup"><span data-stu-id="036a2-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="036a2-226">Pour déployer les modifications, traiter les objets et visualiser les modifications</span><span class="sxs-lookup"><span data-stu-id="036a2-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="036a2-227">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="036a2-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="036a2-228">Après avoir reçu le message **Le déploiement est terminé** , cliquez sur l’onglet **Navigateur** du Concepteur de dimensions pour la dimension Customer, puis cliquez sur le bouton Reconnecter, à gauche de la barre d’outils du Concepteur.</span><span class="sxs-lookup"><span data-stu-id="036a2-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="036a2-229">Vérifiez que `Customer Geography` est sélectionné dans la liste **hiérarchie** , puis dans le volet navigateur, développez **tout**, puis **Australie**, **Nouvelle Galles du Sud**, puis **Coffs**.</span><span class="sxs-lookup"><span data-stu-id="036a2-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="036a2-230">Le navigateur affiche les clients dans la ville.</span><span class="sxs-lookup"><span data-stu-id="036a2-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="036a2-231">Basculez vers le **Concepteur de cube** pour le cube [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="036a2-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="036a2-232">Pour cela, double-cliquez sur le cube **Analysis Services Tutorial** dans le nœud **Cubes** de **l’Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="036a2-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="036a2-233">Cliquez sur l’onglet **Navigateur** , puis cliquez sur le bouton Reconnecter dans la barre d’outils du Concepteur.</span><span class="sxs-lookup"><span data-stu-id="036a2-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="036a2-234">Dans le volet **Groupe de mesures** , développez **Customer**.</span><span class="sxs-lookup"><span data-stu-id="036a2-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="036a2-235">Notez que sous Customer n'apparaît plus une longue liste d'attributs, mais uniquement les dossiers d'affichage et les attributs pour lesquels aucune valeur n'a été affectée pour les dossiers d'affichage.</span><span class="sxs-lookup"><span data-stu-id="036a2-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="036a2-236">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="036a2-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="036a2-237">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="036a2-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="036a2-238">Modification de la dimension Product</span><span class="sxs-lookup"><span data-stu-id="036a2-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="036a2-239">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="036a2-239">See Also</span></span>  
 <span data-ttu-id="036a2-240">[Référence des propriétés d’attribut de dimension](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="036a2-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="036a2-241">[Supprimer un attribut d’une dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="036a2-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="036a2-242">[Renommer un attribut](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="036a2-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="036a2-243">Définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="036a2-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
