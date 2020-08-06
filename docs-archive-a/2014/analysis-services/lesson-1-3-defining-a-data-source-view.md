---
title: Définition d’une vue de source de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600301"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="ba636-102">Définition d'une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="ba636-102">Defining a Data Source View</span></span>
  <span data-ttu-id="ba636-103">L'étape qui suit la définition des sources de données que vous utiliserez dans un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] consiste généralement à définir une vue de source de données pour le projet.</span><span class="sxs-lookup"><span data-stu-id="ba636-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="ba636-104">Une vue de source de données est une vue unique et unifiée des métadonnées des tables et des vues spécifiées que la source de données définit dans le projet.</span><span class="sxs-lookup"><span data-stu-id="ba636-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="ba636-105">Le stockage des métadonnées dans la vue de source de données permet d'utiliser ces métadonnées au cours de la phase de développement sans avoir besoin de disposer d'une connexion ouverte à une source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="ba636-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="ba636-106">Pour plus d’informations, consultez [Vues de sources de données dans les modèles multidimensionnels](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="ba636-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="ba636-107">Au cours de la tâche suivante, vous définissez une vue de source de données qui contient cinq tables de la source de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="ba636-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="ba636-108">Pour définir une nouvelle vue de source de données</span><span class="sxs-lookup"><span data-stu-id="ba636-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="ba636-109">Dans l’Explorateur de solutions (à droite de la fenêtre de Microsoft Visual Studio), cliquez avec le bouton droit sur **Vues des sources de données**, puis cliquez sur **Nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="ba636-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="ba636-110">Sur la page **Bienvenue dans l'Assistant Sources de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ba636-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="ba636-111">La page **Sélectionner une source de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ba636-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="ba636-112">Sous **Sources de données relationnelles**, la source de données **Adventure Works DW 2012** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba636-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="ba636-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ba636-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba636-114">Pour créer une vue de source de données basée sur plusieurs sources de données, vous devez d’abord définir une vue de source de données basée sur une seule source de données.</span><span class="sxs-lookup"><span data-stu-id="ba636-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="ba636-115">Cette source de données est alors appelée la source de données principale.</span><span class="sxs-lookup"><span data-stu-id="ba636-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="ba636-116">Vous pouvez ensuite ajouter des tables et des vues à partir d'une source de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="ba636-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="ba636-117">Quand vous concevez des dimensions qui contiennent des attributs basés sur des tables associées dans plusieurs sources de données, vous pouvez avoir besoin de définir une source de données [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comme source de données principale pour utiliser ses fonctionnalités de moteur de requête distribuée.</span><span class="sxs-lookup"><span data-stu-id="ba636-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="ba636-118">Dans la page **Sélectionner des tables et des vues** , sélectionnez des tables et des vues dans la liste des objets disponibles de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba636-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="ba636-119">Vous pouvez filtrer cette liste pour sélectionner plus facilement les tables et les vues.</span><span class="sxs-lookup"><span data-stu-id="ba636-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba636-120">Cliquez sur le bouton agrandissement dans l'angle supérieur droit afin que la fenêtre couvre le plein écran.</span><span class="sxs-lookup"><span data-stu-id="ba636-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="ba636-121">Vous pouvez alors consulter plus facilement la liste complète des objets disponibles.</span><span class="sxs-lookup"><span data-stu-id="ba636-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="ba636-122">Dans la liste **Objets disponibles** , sélectionnez les objets suivants.</span><span class="sxs-lookup"><span data-stu-id="ba636-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="ba636-123">Vous pouvez sélectionner plusieurs tables en maintenant enfoncée la touche Ctrl :</span><span class="sxs-lookup"><span data-stu-id="ba636-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="ba636-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="ba636-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="ba636-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="ba636-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="ba636-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="ba636-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="ba636-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="ba636-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="ba636-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="ba636-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="ba636-129">Cliquez sur cette **>** option pour ajouter les tables sélectionnées à la liste **objets inclus** .</span><span class="sxs-lookup"><span data-stu-id="ba636-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="ba636-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ba636-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="ba636-131">Dans le champ Nom, vérifiez que **Adventure Works DW 2012** s’affiche, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ba636-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="ba636-132">La vue de source de données **Adventure Works DW 2012** apparaît dans le dossier **Vues des sources de données** dans l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="ba636-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="ba636-133">Le contenu de la vue de source de données s'affiche également dans le Concepteur de vues de source de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba636-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ba636-134">Ce Concepteur contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ba636-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="ba636-135">Un volet **Diagramme** dans lequel les tables et leurs relations sont représentées graphiquement.</span><span class="sxs-lookup"><span data-stu-id="ba636-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="ba636-136">Un volet **Tables** dans lequel les tables et leurs éléments de schéma sont affichés dans une arborescence.</span><span class="sxs-lookup"><span data-stu-id="ba636-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="ba636-137">Un volet **Bibliothèque de diagrammes** dans lequel vous pouvez créer des sous-diagrammes pour afficher des sous-ensembles de la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="ba636-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="ba636-138">Une barre d'outils qui est spécifique au Concepteur de vues de source de données.</span><span class="sxs-lookup"><span data-stu-id="ba636-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="ba636-139">Cliquez sur le bouton [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span><span class="sxs-lookup"><span data-stu-id="ba636-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="ba636-140">Pour afficher à 50 % les tables dans le volet **Diagramme** , cliquez sur l’icône **Zoom** de la barre d’outils du Concepteur de vues de sources de données.</span><span class="sxs-lookup"><span data-stu-id="ba636-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="ba636-141">Cela permet de masquer les détails des colonnes de chaque table.</span><span class="sxs-lookup"><span data-stu-id="ba636-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="ba636-142">Pour masquer l’Explorateur de solutions, cliquez sur le bouton **Masquer automatiquement** , qui correspond à l’icône en forme de punaise sur la barre de titre.</span><span class="sxs-lookup"><span data-stu-id="ba636-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="ba636-143">Pour afficher à nouveau l'Explorateur de solutions, positionnez votre pointeur sur l'onglet Explorateur de solutions le long du côté droit de l'environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="ba636-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="ba636-144">Pour afficher l’Explorateur de solutions, recliquez sur le bouton **Masquer automatiquement** .</span><span class="sxs-lookup"><span data-stu-id="ba636-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="ba636-145">Si les fenêtres ne sont pas masquées par défaut, cliquez sur **Masquer automatiquement** dans la barre de titre des fenêtres Propriétés et Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="ba636-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="ba636-146">Vous pouvez maintenant consulter toutes les tables et leurs relations dans le volet **Diagramme** .</span><span class="sxs-lookup"><span data-stu-id="ba636-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="ba636-147">Notez qu'il existe trois relations entre la table FactInternetSales et la table DimDate.</span><span class="sxs-lookup"><span data-stu-id="ba636-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="ba636-148">Chaque vente est associée à trois dates : une date de commande, une date d'échéance et une date de livraison.</span><span class="sxs-lookup"><span data-stu-id="ba636-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="ba636-149">Pour afficher les détails d’une relation, double-cliquez sur la flèche de la relation dans le volet **Diagramme** .</span><span class="sxs-lookup"><span data-stu-id="ba636-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ba636-150">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ba636-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ba636-151">Modification des noms de tables par défaut</span><span class="sxs-lookup"><span data-stu-id="ba636-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba636-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba636-152">See Also</span></span>  
 [<span data-ttu-id="ba636-153">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="ba636-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
