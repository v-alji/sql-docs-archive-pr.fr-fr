---
title: Modification de la dimension Product | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611389"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="bb78b-102">Modification de la dimension Product</span><span class="sxs-lookup"><span data-stu-id="bb78b-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="bb78b-103">Au cours des tâches de cette rubrique, vous allez utiliser un calcul nommé pour fournir des noms plus descriptifs pour les lignes de produits, définir une hiérarchie dans la dimension Product et spécifier le nom de membre (All) pour la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="bb78b-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="bb78b-104">Vous regroupez également les attributs dans des dossiers d'affichage.</span><span class="sxs-lookup"><span data-stu-id="bb78b-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="bb78b-105">Ajout d'un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="bb78b-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="bb78b-106">Vous pouvez ajouter un calcul nommé à une table dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="bb78b-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="bb78b-107">Dans la tâche suivante, vous créez un calcul nommé qui affiche le nom de la ligne du produit complet.</span><span class="sxs-lookup"><span data-stu-id="bb78b-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="bb78b-108">Pour ajouter un calcul nommé</span><span class="sxs-lookup"><span data-stu-id="bb78b-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="bb78b-109">Pour ouvrir la vue de source de données **Adventure Works DW 2012** , double-cliquez sur **Adventure Works DW 2012** dans le dossier **Vues des sources de données** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="bb78b-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="bb78b-110">En bas du volet Schéma, cliquez avec le bouton droit sur l’en-tête de la table **Product** , puis cliquez sur **Nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="bb78b-111">Dans la boîte de dialogue **créer un calcul nommé** , tapez `ProductLineName` dans la zone **nom** de la colonne.</span><span class="sxs-lookup"><span data-stu-id="bb78b-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="bb78b-112">Dans la zone **Expression** , tapez ou copiez l’instruction **CASE** suivante :</span><span class="sxs-lookup"><span data-stu-id="bb78b-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="bb78b-113">Cette instruction **CASE** crée des noms conviviaux pour chaque ligne de produits dans le cube.</span><span class="sxs-lookup"><span data-stu-id="bb78b-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="bb78b-114">Cliquez sur **OK** pour créer le `ProductLineName` calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="bb78b-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="bb78b-115">Cela peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="bb78b-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="bb78b-116">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="bb78b-117">Modification de la propriété NameColumn d'un attribut</span><span class="sxs-lookup"><span data-stu-id="bb78b-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="bb78b-118">Pour modifier la valeur de la propriété NameColumn d'un attribut</span><span class="sxs-lookup"><span data-stu-id="bb78b-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="bb78b-119">Affichez le Concepteur de dimensions pour la dimension Product.</span><span class="sxs-lookup"><span data-stu-id="bb78b-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="bb78b-120">Pour cela, double-cliquez sur la dimension **Product** du nœud **Dimensions** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="bb78b-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="bb78b-121">Dans le volet **Attributs** de l’onglet **Structure de dimension** , sélectionnez **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="bb78b-122">Dans le Fenêtre Propriétés sur le côté droit de l’écran, cliquez sur le champ de propriété **NameColumn** en bas de la fenêtre, puis cliquez sur le bouton de navigation (**...**) pour ouvrir la boîte de dialogue **colonne de nom** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="bb78b-123">(Il peut être nécessaire de cliquer sur l’onglet **Propriétés** à droite de l’écran pour ouvrir la fenêtre Propriétés.)</span><span class="sxs-lookup"><span data-stu-id="bb78b-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="bb78b-124">Sélectionnez `ProductLineName` au bas de la liste **colonne source** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bb78b-125">Le champ NameColumn contient maintenant le texte, **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="bb78b-126">Les membres de la hiérarchie d’attributs **Product Line** affichent maintenant le nom complet de la ligne de produits et non plus le nom abrégé.</span><span class="sxs-lookup"><span data-stu-id="bb78b-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="bb78b-127">Dans le volet **Attributs** de l’onglet **Structure de dimension** , sélectionnez **Product Key**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="bb78b-128">Dans la Fenêtre Propriétés, cliquez sur le champ de propriété **NameColumn** , puis cliquez sur le bouton de navigation (**...**) pour ouvrir la boîte de dialogue **colonne de nom** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="bb78b-129">Sélectionnez **EnglishProductName** dans la liste **Colonne source** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bb78b-130">Le champ NameColumn contient maintenant le texte **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="bb78b-131">Dans le Fenêtre Propriétés, faites défiler la liste vers le haut, cliquez sur le champ de propriété **Name** , puis tapez `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="bb78b-132">Création d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="bb78b-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="bb78b-133">Pour créer une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="bb78b-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="bb78b-134">Faites glisser l’attribut **Product Line** du volet **Attributs** vers le volet **Hiérarchies** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="bb78b-135">Faites glisser l’attribut **Model Name** du volet **Attributs** vers la cellule **\<new level>** dans le volet **Hiérarchies** , sous le niveau **Product Line** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="bb78b-136">Faites glisser l' `Product Name` attribut du volet **attributs** vers la **\<new level>** cellule dans le volet **hiérarchies** , sous le niveau nom du **modèle** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="bb78b-137">(Vous avez renommé Product Key en Product Name dans la section précédente.)</span><span class="sxs-lookup"><span data-stu-id="bb78b-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="bb78b-138">Dans le volet **hiérarchies** de l’onglet **structure de dimension** , cliquez avec le bouton droit sur la barre de titre de la hiérarchie **hiérarchie** , cliquez sur **Renommer**, puis tapez `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="bb78b-139">Le nom de la hiérarchie est maintenant `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="bb78b-140">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="bb78b-141">Spécification de noms de dossiers et de noms de membres pour le niveau All</span><span class="sxs-lookup"><span data-stu-id="bb78b-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="bb78b-142">Pour spécifier les noms de dossiers et de membres</span><span class="sxs-lookup"><span data-stu-id="bb78b-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="bb78b-143">Dans le volet **Attributs** , sélectionnez les attributs suivants en maintenant la touche Ctrl enfoncée pendant que vous cliquez sur chacun d’eux :</span><span class="sxs-lookup"><span data-stu-id="bb78b-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="bb78b-144">**Classe**</span><span class="sxs-lookup"><span data-stu-id="bb78b-144">**Class**</span></span>  
  
    -   <span data-ttu-id="bb78b-145">**Couleur**</span><span class="sxs-lookup"><span data-stu-id="bb78b-145">**Color**</span></span>  
  
    -   <span data-ttu-id="bb78b-146">**Jours de fabrication**</span><span class="sxs-lookup"><span data-stu-id="bb78b-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="bb78b-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="bb78b-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="bb78b-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="bb78b-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="bb78b-149">**Taille**</span><span class="sxs-lookup"><span data-stu-id="bb78b-149">**Size**</span></span>  
  
    -   <span data-ttu-id="bb78b-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="bb78b-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="bb78b-151">**Style**</span><span class="sxs-lookup"><span data-stu-id="bb78b-151">**Style**</span></span>  
  
    -   <span data-ttu-id="bb78b-152">**Poids**</span><span class="sxs-lookup"><span data-stu-id="bb78b-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="bb78b-153">Dans le champ de propriété **AttributeHierarchyDisplayFolder** de l’fenêtre Propriétés, tapez `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="bb78b-154">Vous avez maintenant groupé ces attributs dans un seul dossier d'affichage.</span><span class="sxs-lookup"><span data-stu-id="bb78b-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="bb78b-155">Dans le volet **Attributs** , sélectionnez les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="bb78b-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="bb78b-156">**Dealer Price**</span><span class="sxs-lookup"><span data-stu-id="bb78b-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="bb78b-157">**List Price**</span><span class="sxs-lookup"><span data-stu-id="bb78b-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="bb78b-158">**Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="bb78b-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="bb78b-159">Dans la cellule de propriété **AttributeHierarchyDisplayFolder** de la fenêtre Propriétés, tapez `Financial` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="bb78b-160">Vous avez maintenant groupé ces attributs dans un deuxième dossier d'affichage.</span><span class="sxs-lookup"><span data-stu-id="bb78b-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="bb78b-161">Dans le volet **Attributs** , sélectionnez les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="bb78b-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="bb78b-162">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="bb78b-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="bb78b-163">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="bb78b-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="bb78b-164">**État**</span><span class="sxs-lookup"><span data-stu-id="bb78b-164">**Status**</span></span>  
  
6.  <span data-ttu-id="bb78b-165">Dans la cellule de propriété **AttributeHierarchyDisplayFolder** de la fenêtre Propriétés, tapez `History` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="bb78b-166">Vous avez maintenant groupé ces attributs dans un troisième dossier d'affichage.</span><span class="sxs-lookup"><span data-stu-id="bb78b-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="bb78b-167">Sélectionnez la `Product Model Lines` hiérarchie dans le volet **hiérarchies** , puis remplacez la valeur de la propriété **AllMemberName** dans la fenêtre Propriétés par `All Products` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="bb78b-168">Cliquez sur une zone ouverte du volet **hiérarchies** , puis modifiez la propriété **AttributeAllMemberName** en haut de la fenêtre Propriétés en `All Products` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="bb78b-169">Ceci vous permet de modifier les propriétés de la dimension Product.</span><span class="sxs-lookup"><span data-stu-id="bb78b-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="bb78b-170">Vous pouvez aussi cliquer sur **Product** en haut de la liste des attributs dans le volet **Attributs** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="bb78b-171">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="bb78b-172">Définition des relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="bb78b-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="bb78b-173">Si les données sous-jacentes le prennent en charge, il est également conseillé de définir des relations d'attributs entre les attributs.</span><span class="sxs-lookup"><span data-stu-id="bb78b-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="bb78b-174">La définition de relations d'attributs accélère le traitement des dimensions, des partitions et des requêtes.</span><span class="sxs-lookup"><span data-stu-id="bb78b-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="bb78b-175">Pour plus d’informations, consultez [Définir des relations d’attributs](multidimensional-models/attribute-relationships-define.md) et [Relations d’attributs](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="bb78b-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="bb78b-176">Pour définir les relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="bb78b-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="bb78b-177">Dans le **Concepteur de dimensions** pour la dimension Product, cliquez sur l’onglet **Relations d’attributs** .</span><span class="sxs-lookup"><span data-stu-id="bb78b-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="bb78b-178">Dans le diagramme, cliquez avec le bouton droit sur l’attribut **Model Name** puis sélectionnez **Nouvelle relation d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="bb78b-179">Dans la boîte de dialogue **Créer une relation d’attribut** , **l’Attribut source** est **Model Name**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="bb78b-180">Définissez **l’Attribut associé** sur **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="bb78b-181">Dans la liste **Type de relation** , laissez le type de relation défini sur **Flexible** car les relations entre les membres peuvent changer au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="bb78b-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="bb78b-182">Par exemple, un modèle de produit peut se retrouver déplacé vers une autre ligne de produits.</span><span class="sxs-lookup"><span data-stu-id="bb78b-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="bb78b-183">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bb78b-184">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="bb78b-185">Vérification des modifications apportées à la dimension Product</span><span class="sxs-lookup"><span data-stu-id="bb78b-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="bb78b-186">Pour vérifier les modifications apportées à la dimension Product</span><span class="sxs-lookup"><span data-stu-id="bb78b-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="bb78b-187">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="bb78b-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="bb78b-188">Après avoir reçu le message **Le déploiement est terminé** , cliquez sur l’onglet **Navigateur** du **Concepteur de dimensions** pour la dimension **Product** , puis cliquez sur le bouton Reconnecter de la barre d’outils du Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bb78b-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="bb78b-189">Vérifiez que `Product Model Lines` est sélectionné dans la liste **hiérarchie** , puis développez `All Products` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="bb78b-190">Notez que le nom du membre **All** apparaît sous la forme `All Products` .</span><span class="sxs-lookup"><span data-stu-id="bb78b-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="bb78b-191">Cela est dû au fait que vous avez modifié la propriété **AllMemberName** de la hiérarchie en `All Products` plus tôt dans la leçon.</span><span class="sxs-lookup"><span data-stu-id="bb78b-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="bb78b-192">De même, les membres du niveau **Product Line** ont maintenant des noms conviviaux, au lieu d’abréviations d’une seule lettre.</span><span class="sxs-lookup"><span data-stu-id="bb78b-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bb78b-193">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="bb78b-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bb78b-194">Modification de la dimension Date</span><span class="sxs-lookup"><span data-stu-id="bb78b-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb78b-195">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb78b-195">See Also</span></span>  
 <span data-ttu-id="bb78b-196">[Définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb78b-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="bb78b-197">[Créer des hiérarchies définies par l’utilisateur](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="bb78b-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="bb78b-198">Configurer le niveau &#40;Tous&#41; des hiérarchies d’attributs</span><span class="sxs-lookup"><span data-stu-id="bb78b-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
