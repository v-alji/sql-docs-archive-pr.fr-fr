---
title: Procédure pas à pas sur le diagramme d’arbre de décision (compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604267"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="941be-102">Procédure pas à pas sur le diagramme d’arbre de décision (compléments d’exploration de données)</span><span class="sxs-lookup"><span data-stu-id="941be-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="941be-103">Si vous avez créé un modèle d'arbre de décision, vous pouvez créer un diagramme personnalisé dans Visio à l'aide de la forme Arbre de décision ou de la forme Réseau de dépendances.</span><span class="sxs-lookup"><span data-stu-id="941be-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="941be-104">Cette rubrique décrit les personnalisations que vous pouvez effectuer à l’aide de la forme **arbre de décision** et de ces contrôles :</span><span class="sxs-lookup"><span data-stu-id="941be-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="941be-105">Contrôles de rendu pour le diagramme d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="941be-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="941be-106">Ces options font partie de l **'Assistant arbre de décision** qui est lancé lorsque vous déposez une forme dans l’espace de travail Visio.</span><span class="sxs-lookup"><span data-stu-id="941be-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="941be-107">Barre d’outils de **disposition d’exploration de données**</span><span class="sxs-lookup"><span data-stu-id="941be-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="941be-108">Ces options sont ajoutées à l'espace de travail Visio pour vous aider à interagir avec la forme.</span><span class="sxs-lookup"><span data-stu-id="941be-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="941be-109">Créer un diagramme d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="941be-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="941be-110">Vous déposez la forme arbre de décision sur la page Visio pour lancer l' **Assistant Création de forme arbre de décision Visio** et définir les options du diagramme.</span><span class="sxs-lookup"><span data-stu-id="941be-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="941be-111">Utiliser l'Assistant Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="941be-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="941be-112">Si les **formes d’exploration de données Microsoft** ne s’affichent pas dans la liste **formes** , cliquez sur **autres formes**, sélectionnez **ouvrir le stencil**, puis ouvrez le modèle à partir de l’emplacement d’installation par défaut.</span><span class="sxs-lookup"><span data-stu-id="941be-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="941be-113">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="941be-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="941be-114">Faites glisser la forme **arbre de décision** sur la page.</span><span class="sxs-lookup"><span data-stu-id="941be-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="941be-115">Sur la page d’accueil de l **'Assistant Création de forme arbre de décision Visio**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="941be-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="941be-116">Dans la page **Sélectionner une source de données** de l' **Assistant cluster**, choisissez une connexion à un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] serveur dont vous souhaitez visualiser le modèle.</span><span class="sxs-lookup"><span data-stu-id="941be-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="941be-117">Sélectionnez un modèle d’exploration de données approprié, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="941be-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="941be-118">Ce type de diagramme prend en charge les modèles créés à l'aide de l'algorithme Decision Trees ou Linear Regression.</span><span class="sxs-lookup"><span data-stu-id="941be-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="941be-119">Dans la page **Sélectionner l’arbre de décision** , choisissez une arborescence individuelle à afficher.</span><span class="sxs-lookup"><span data-stu-id="941be-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="941be-120">Une arborescence modélise les interactions qui mènent à un résultat particulier que vous avez modélisé. par conséquent, même si votre modèle contient plusieurs résultats, vous ne pouvez afficher qu’une seule arborescence à la fois.</span><span class="sxs-lookup"><span data-stu-id="941be-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="941be-121">Dans la boîte de dialogue **Sélectionner un arbre de décision** , vous pouvez également définir ces options de rendu :</span><span class="sxs-lookup"><span data-stu-id="941be-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="941be-122">**Profondeur de rendu maximum**</span><span class="sxs-lookup"><span data-stu-id="941be-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="941be-123">Utilisez cette option pour contrôler le nombre de nœuds qui sont affichés.</span><span class="sxs-lookup"><span data-stu-id="941be-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="941be-124">Un arbre de décision peut être très profond, ce qui entraîne la création d'un diagramme qui ne tient pas sur la page.</span><span class="sxs-lookup"><span data-stu-id="941be-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="941be-125">Utilisez ce contrôle pour vous concentrer sur les nœuds situés les plus à gauche, qui sont les plus importants.</span><span class="sxs-lookup"><span data-stu-id="941be-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="941be-126">La valeur par défaut est trois niveaux de nœuds.</span><span class="sxs-lookup"><span data-stu-id="941be-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="941be-127">**Sélectionner la couleur et le texte à afficher pour les valeurs**</span><span class="sxs-lookup"><span data-stu-id="941be-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="941be-128">Choisissez la couleur qui représentera chacun des résultats.</span><span class="sxs-lookup"><span data-stu-id="941be-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="941be-129">Si vous ne spécifiez pas de couleurs, elles sont générées automatiquement avec les couleurs des thèmes vidéo actuels.</span><span class="sxs-lookup"><span data-stu-id="941be-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="941be-130">Cliquez sur **avancé** pour personnaliser les options suivantes pour chacun des nœuds du diagramme de l’arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="941be-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="941be-131">**Variable d’ombrage** et **État**</span><span class="sxs-lookup"><span data-stu-id="941be-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="941be-132">Sélectionnez le résultat cible que vous souhaitez afficher dans le diagramme d'arborescence.</span><span class="sxs-lookup"><span data-stu-id="941be-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="941be-133">**Afficher l'histogramme**</span><span class="sxs-lookup"><span data-stu-id="941be-133">**Show Histogram**</span></span>  
     <span data-ttu-id="941be-134">Ajoute un graphique à chaque nœud qui affiche les règles qui définissent ce nœud.</span><span class="sxs-lookup"><span data-stu-id="941be-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="941be-135">**Afficher l'étiquette**</span><span class="sxs-lookup"><span data-stu-id="941be-135">**Show Label**</span></span>  
     <span data-ttu-id="941be-136">Ajoute des noms de colonne à l'histogramme.</span><span class="sxs-lookup"><span data-stu-id="941be-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="941be-137">**Afficher la probabilité**</span><span class="sxs-lookup"><span data-stu-id="941be-137">**Show Probability**</span></span>  
     <span data-ttu-id="941be-138">Affiche la probabilité de chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="941be-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="941be-139">**Afficher la prise en charge**</span><span class="sxs-lookup"><span data-stu-id="941be-139">**Show Support**</span></span>  
     <span data-ttu-id="941be-140">Affiche la prise en charge de chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="941be-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="941be-141">**Afficher le pied**</span><span class="sxs-lookup"><span data-stu-id="941be-141">**Show Footer**</span></span>  
     <span data-ttu-id="941be-142">Ajoute un pied de page qui additionne toutes les valeurs affichées.</span><span class="sxs-lookup"><span data-stu-id="941be-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="941be-143">**Afficher l'en-tête**</span><span class="sxs-lookup"><span data-stu-id="941be-143">**Show Header**</span></span>  
     <span data-ttu-id="941be-144">Affiche les en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="941be-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="941be-145">**Afficher les états sans aucune prise en charge**</span><span class="sxs-lookup"><span data-stu-id="941be-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="941be-146">Vous permet d'afficher les valeurs manquantes.</span><span class="sxs-lookup"><span data-stu-id="941be-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="941be-147">Cliquez sur **Terminer** pour créer le graphique.</span><span class="sxs-lookup"><span data-stu-id="941be-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="941be-148">Dans certains environnements, les connecteurs dans le graphique peuvent ne pas être rendus dans Office 2013.</span><span class="sxs-lookup"><span data-stu-id="941be-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="941be-149">Explorer et modifier le diagramme terminé</span><span class="sxs-lookup"><span data-stu-id="941be-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="941be-150">Une fois que vous avez terminé l' **Assistant Création de forme arbre de décision Visio**, Visio crée un diagramme d’arborescence sur la page qui affiche graphiquement les règles qui mènent au résultat prédit.</span><span class="sxs-lookup"><span data-stu-id="941be-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="941be-151">Vous pouvez continuer à modifier la forme en utilisant les contrôles suivants pour les diagrammes d'arbre de décision :</span><span class="sxs-lookup"><span data-stu-id="941be-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="941be-152">Utilisation des menus d'options d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="941be-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="941be-153">Cliquez sur le ruban **compléments** , puis affichez l’une des barres d’outils personnalisées utilisées pour travailler avec les diagrammes d’exploration de données :</span><span class="sxs-lookup"><span data-stu-id="941be-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="941be-154">**Disposition**</span><span class="sxs-lookup"><span data-stu-id="941be-154">**Layout**</span></span>  
     <span data-ttu-id="941be-155">Optimise la disposition de l'arborescence pour qu'elle tienne sur la page active.</span><span class="sxs-lookup"><span data-stu-id="941be-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="941be-156">**Redimensionner la page**</span><span class="sxs-lookup"><span data-stu-id="941be-156">**Resize Page**</span></span>  
     <span data-ttu-id="941be-157">Ce contrôle a été conçu pour les versions HTML antérieures.</span><span class="sxs-lookup"><span data-stu-id="941be-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="941be-158">Utilisez plutôt les contrôles de redimensionnement de page Visio,</span><span class="sxs-lookup"><span data-stu-id="941be-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="941be-159">**Description**</span><span class="sxs-lookup"><span data-stu-id="941be-159">**Description**</span></span>  
     <span data-ttu-id="941be-160">Lorsqu'un nœud de l'arborescence est sélectionné, cliquez sur cette option pour afficher des détails sur les cas du nœud.</span><span class="sxs-lookup"><span data-stu-id="941be-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="941be-161">Utilisez l’option **redisposition** de la page du ruban **conception** de Visio pour expérimenter différentes dispositions d’arborescence.</span><span class="sxs-lookup"><span data-stu-id="941be-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="941be-162">Utilisez l’option **connecteurs** sous l’onglet **conception** pour modifier les connecteurs utilisés entre les nœuds dans l’arborescence.</span><span class="sxs-lookup"><span data-stu-id="941be-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="941be-163">Utilisez le contrôle **panoramique et zoom** , dans la zone **volet de tâches** du ruban **affichage** Visio, pour vous concentrer sur une zone particulière du diagramme.</span><span class="sxs-lookup"><span data-stu-id="941be-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="941be-164">Cliquez avec le bouton droit sur un nœud dans l'arborescence et faites un choix parmi ces options de menu contextuel spécifiques aux diagrammes d'arbre de décision :</span><span class="sxs-lookup"><span data-stu-id="941be-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="941be-165">**Améliorer la mise en page**</span><span class="sxs-lookup"><span data-stu-id="941be-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="941be-166">Répartit les nœuds équitablement sur la page et ajuste l'affichage de celle-ci pour présenter tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="941be-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="941be-167">**Déplacer les enfants vers la nouvelle page**</span><span class="sxs-lookup"><span data-stu-id="941be-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="941be-168">Déplace les enfants du nœud actuellement sélectionné vers une nouvelle page.</span><span class="sxs-lookup"><span data-stu-id="941be-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="941be-169">**Réduire les nœuds enfants**</span><span class="sxs-lookup"><span data-stu-id="941be-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="941be-170">Masque les enfants du nœud actuellement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="941be-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="941be-171">**Développez les nœuds enfants**</span><span class="sxs-lookup"><span data-stu-id="941be-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="941be-172">Affiche les enfants du nœud sélectionné.</span><span class="sxs-lookup"><span data-stu-id="941be-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941be-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="941be-173">See Also</span></span>  
 [<span data-ttu-id="941be-174">Dépannage des diagrammes d’exploration de données Visio &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="941be-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
