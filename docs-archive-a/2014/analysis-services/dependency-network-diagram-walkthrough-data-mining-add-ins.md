---
title: Procédure pas à pas relative à un diagramme de réseau de dépendances (compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613683"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="d6e51-102">Procédure pas à pas Diagramme Réseau de dépendances (Compléments d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="d6e51-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="d6e51-103">Plusieurs types de modèles d'exploration de données différents utilisent un graphique de réseau comme manière d'explorer les relations dans les données.</span><span class="sxs-lookup"><span data-stu-id="d6e51-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="d6e51-104">Vous pouvez importer ces modèles dans Visio à l’aide de la forme **réseau de dépendances** , puis continuer à personnaliser et améliorer la disposition.</span><span class="sxs-lookup"><span data-stu-id="d6e51-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="d6e51-105">Les **formes d’exploration de données pour Visio** incluent les contrôles personnalisés suivants pour l’utilisation des diagrammes de réseau de dépendances :</span><span class="sxs-lookup"><span data-stu-id="d6e51-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="d6e51-106">Contrôles de rendu du graphique de réseau</span><span class="sxs-lookup"><span data-stu-id="d6e51-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="d6e51-107">Ces options font partie de l'Assistant qui est exécuté lorsque vous déposez une forme dans l'espace de travail Visio.</span><span class="sxs-lookup"><span data-stu-id="d6e51-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="d6e51-108">Barre d’outils de **disposition d’exploration de données**</span><span class="sxs-lookup"><span data-stu-id="d6e51-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="d6e51-109">Ces options sont ajoutées à l'espace de travail Visio pour vous aider à interagir avec le graphique de réseau de dépendances.</span><span class="sxs-lookup"><span data-stu-id="d6e51-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="d6e51-110">Créer un graphique de réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="d6e51-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="d6e51-111">Vous déposez une forme sur la page Visio pour lancer l' **Assistant Création de forme réseau de dépendances Visio** et définir les options du diagramme.</span><span class="sxs-lookup"><span data-stu-id="d6e51-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="d6e51-112">Utiliser l'Assistant Création de forme Réseau de dépendances Visio</span><span class="sxs-lookup"><span data-stu-id="d6e51-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="d6e51-113">Si les **formes d’exploration de données Microsoft** ne s’affichent pas dans la liste **formes** , cliquez sur **autres formes**, sélectionnez **ouvrir le stencil**, puis ouvrez le modèle à partir de l’emplacement d’installation par défaut.</span><span class="sxs-lookup"><span data-stu-id="d6e51-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="d6e51-114">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="d6e51-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="d6e51-115">Faites glisser la forme **réseau de dépendances** sur la page pour démarrer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="d6e51-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="d6e51-116">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d6e51-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="d6e51-117">Sur la page d’accueil de l **'Assistant Création d’une forme réseau de dépendances Visio**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d6e51-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6e51-118">Dans la page **Sélectionner une source de données** de l' **Assistant Création de forme réseau de dépendances Visio**, choisissez une connexion à un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] serveur qui possède le modèle que vous souhaitez visualiser.</span><span class="sxs-lookup"><span data-stu-id="d6e51-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="d6e51-119">Sélectionnez un modèle d’exploration de données approprié, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d6e51-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="d6e51-120">Pour sélectionner un modèle approprié, vous pouvez examiner le nom, la description, les colonnes et le type de données dans le volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="d6e51-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="d6e51-121">Cette forme prend en charge les modèles créés à l'aide des algorithmes suivants :</span><span class="sxs-lookup"><span data-stu-id="d6e51-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="d6e51-122">Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="d6e51-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="d6e51-123">Arbres de décision</span><span class="sxs-lookup"><span data-stu-id="d6e51-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="d6e51-124">Règles d'association</span><span class="sxs-lookup"><span data-stu-id="d6e51-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="d6e51-125">Sur la page, **sélectionnez les nœuds à afficher**, personnalisez la taille du graphique et, éventuellement, filtrez pour inclure uniquement certains nœuds.</span><span class="sxs-lookup"><span data-stu-id="d6e51-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="d6e51-126">Avec un jeu de données volumineux, un graphique de dépendance peut devenir énorme et contenir de nombreux objets associés, représentés sous forme de *nœuds*.</span><span class="sxs-lookup"><span data-stu-id="d6e51-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="d6e51-127">En utilisant cette boîte de dialogue, vous pouvez créer un graphique de réseau personnalisé qui contient uniquement les nœuds dignes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="d6e51-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="d6e51-128">[espace réservé art]</span><span class="sxs-lookup"><span data-stu-id="d6e51-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="d6e51-129">**Nombre de nœud à extraire**</span><span class="sxs-lookup"><span data-stu-id="d6e51-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="d6e51-130">Si le modèle contient un nombre inférieur au nombre spécifié de nœuds, ce paramètre n'a aucun effet.</span><span class="sxs-lookup"><span data-stu-id="d6e51-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="d6e51-131">Si le modèle contient un nombre de nœuds supérieur au nombre spécifié, seuls les nœuds les plus forts sont affichés.</span><span class="sxs-lookup"><span data-stu-id="d6e51-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="d6e51-132">**Le nom contient**</span><span class="sxs-lookup"><span data-stu-id="d6e51-132">**Name contains**</span></span>  
     <span data-ttu-id="d6e51-133">Laissez cette zone vide et cliquez sur la flèche verte pour extraire tous les nœuds du modèle.</span><span class="sxs-lookup"><span data-stu-id="d6e51-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="d6e51-134">Sinon, tapez une chaîne et cliquez sur la flèche verte pour retourner uniquement les nœuds qui contiennent la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d6e51-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="d6e51-135">La plupart des modèles que vous pouvez créer avec les exemples de données ne sont pas volumineux ; par conséquent, pour cet exemple, augmentez le nombre de nœuds à 10, puis cliquez sur la flèche verte pour exécuter une requête et obtenir la liste de tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="d6e51-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="d6e51-136">Cliquez sur **avancé** pour définir les options d’ombrage et de forme du graphique.</span><span class="sxs-lookup"><span data-stu-id="d6e51-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="d6e51-137">Cliquez sur **Fermer** pour quitter la boîte de dialogue Options **avancées** , puis cliquez sur **Terminer** pour créer le graphique.</span><span class="sxs-lookup"><span data-stu-id="d6e51-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="d6e51-138">Explorer et modifier le diagramme terminé</span><span class="sxs-lookup"><span data-stu-id="d6e51-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="d6e51-139">Une fois que Visio a créé le graphique de dépendances de réseau, vous pouvez continuer à modifier et à améliorer le graphique en utilisant les fonctionnalités de Visio.</span><span class="sxs-lookup"><span data-stu-id="d6e51-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="d6e51-140">Le graphique suivant montre la disposition par défaut d'un graphique de réseau de dépendances.</span><span class="sxs-lookup"><span data-stu-id="d6e51-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="d6e51-141">[espace réservé art]</span><span class="sxs-lookup"><span data-stu-id="d6e51-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="d6e51-142">Utilisez le contrôle **panoramique et zoom** , dans la zone **volet de tâches** du ruban **affichage** Visio, pour vous concentrer sur une section du graphique et vous déplacer dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="d6e51-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="d6e51-143">Faites des essais avec différentes dispositions graphiques fournies par l’option de **page redisposition** Visio.</span><span class="sxs-lookup"><span data-stu-id="d6e51-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="d6e51-144">Cliquez sur le ruban **compléments** , puis affichez l’une des barres d’outils personnalisées utilisées pour travailler avec les diagrammes d’exploration de données :</span><span class="sxs-lookup"><span data-stu-id="d6e51-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="d6e51-145">**Disposition**</span><span class="sxs-lookup"><span data-stu-id="d6e51-145">**Layout**</span></span>  
     <span data-ttu-id="d6e51-146">Optimise la disposition des nœuds sur la page et modifie l'affichage pour que tous les nœuds soient visibles.</span><span class="sxs-lookup"><span data-stu-id="d6e51-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="d6e51-147">**Redimensionner la page**</span><span class="sxs-lookup"><span data-stu-id="d6e51-147">**Resize Page**</span></span>  
     <span data-ttu-id="d6e51-148">Modifie la taille de la page pour que tous les nœuds soient visibles.</span><span class="sxs-lookup"><span data-stu-id="d6e51-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="d6e51-149">**Résistance du bord**</span><span class="sxs-lookup"><span data-stu-id="d6e51-149">**Edge Strength**</span></span>  
     <span data-ttu-id="d6e51-150">Fait basculer l'affichage de la résistance du bord de l'ensemble du graphique.</span><span class="sxs-lookup"><span data-stu-id="d6e51-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="d6e51-151">Un bord représente une connexion entre des nœuds.</span><span class="sxs-lookup"><span data-stu-id="d6e51-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="d6e51-152">Vous pouvez utiliser le curseur pour exclure les connexions qui ne sont pas fortes.</span><span class="sxs-lookup"><span data-stu-id="d6e51-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="d6e51-153">**Curseur**</span><span class="sxs-lookup"><span data-stu-id="d6e51-153">**Slider**</span></span>  
     <span data-ttu-id="d6e51-154">Le **curseur** vous permet de contrôler la force des relations affichées dans le diagramme du réseau de dépendances.</span><span class="sxs-lookup"><span data-stu-id="d6e51-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="d6e51-155">Chaque nœud du graphique représente un état.</span><span class="sxs-lookup"><span data-stu-id="d6e51-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="d6e51-156">Une flèche représente une transition entre deux états et la probabilité associée à la transition.</span><span class="sxs-lookup"><span data-stu-id="d6e51-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="d6e51-157">Pour réduire le nombre de nœuds dans le graphique, déplacez le curseur vers le haut.</span><span class="sxs-lookup"><span data-stu-id="d6e51-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="d6e51-158">Pour augmenter le nombre de nœuds dans le graphique, déplacez le curseur vers le bas.</span><span class="sxs-lookup"><span data-stu-id="d6e51-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="d6e51-159">**Ajouter des éléments**</span><span class="sxs-lookup"><span data-stu-id="d6e51-159">**Add Items**</span></span>  
     <span data-ttu-id="d6e51-160">Ouvre la boîte de dialogue **Sélectionner les nœuds à afficher** pour vous permettre de sélectionner de nouveaux nœuds à ajouter au graphique.</span><span class="sxs-lookup"><span data-stu-id="d6e51-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="d6e51-161">Vous pouvez créer des graphiques simples ou élaborés, à votre convenance, puis ajouter des annotations, tout en restant connecté au modèle.</span><span class="sxs-lookup"><span data-stu-id="d6e51-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="d6e51-162">[espace réservé aux graphiques]</span><span class="sxs-lookup"><span data-stu-id="d6e51-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d6e51-163">La mise en surbrillance des nœuds dépendants et d'autres options de menu contextuel qui étaient disponibles dans les versions précédentes des compléments ne fonctionnent pas dans Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d6e51-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e51-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6e51-164">See Also</span></span>  
 [<span data-ttu-id="d6e51-165">Dépannage des diagrammes d’exploration de données Visio &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d6e51-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
