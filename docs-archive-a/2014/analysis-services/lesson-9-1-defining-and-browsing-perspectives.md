---
title: Définition et exploration des perspectives | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703380"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="d17eb-102">Définition et exploration de perspectives</span><span class="sxs-lookup"><span data-stu-id="d17eb-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="d17eb-103">Une perspective peut simplifier l'affichage d'un cube à des fins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d17eb-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="d17eb-104">Par défaut, les utilisateurs peuvent voir tous les éléments d'un cube auquel ils sont autorisés à accéder.</span><span class="sxs-lookup"><span data-stu-id="d17eb-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="d17eb-105">Ce que les utilisateurs voient lorsqu'ils affichent l'intégralité d'un cube [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] est la perspective par défaut du cube.</span><span class="sxs-lookup"><span data-stu-id="d17eb-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="d17eb-106">Il peut s'avérer très difficile de naviguer à travers une vue du cube tout entier, surtout pour les utilisateurs auxquels il suffit d'interagir avec une petite partie du cube pour satisfaire leurs besoins en matière de décisionnel et de rapports.</span><span class="sxs-lookup"><span data-stu-id="d17eb-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="d17eb-107">Pour réduire l’apparente complexité d’un cube, vous pouvez créer des sous-ensembles visualisables du cube, appelés *perspectives*, qui ne montrent aux utilisateurs qu’une partie définie des groupes de mesures, des mesures, des dimensions, des attributs, des hiérarchies, des indicateurs de performance clés, des actions et des membres calculés du cube.</span><span class="sxs-lookup"><span data-stu-id="d17eb-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="d17eb-108">Cette opération est particulièrement utile lorsque vous travaillez avec des applications clientes qui n'ont pas été écrites pour une version précédente de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d17eb-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d17eb-109">Ces clients ignorent tout des dossiers d'affichage ou des perspectives, par exemple ; en revanche, une perspective s'affiche aux anciens clients comme s'il s'agissait d'un cube.</span><span class="sxs-lookup"><span data-stu-id="d17eb-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="d17eb-110">Pour plus d’informations, consultez [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), et [Perspectives dans les modèles multidimensionnels](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="d17eb-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d17eb-111">Une perspective n'est pas un mécanisme de sécurité, mais un outil pour améliorer le confort de travail de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d17eb-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="d17eb-112">Toute la sécurité d'une perspective est héritée du cube sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="d17eb-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="d17eb-113">Dans les tâches de cette rubrique, vous allez définir plusieurs perspectives différentes, puis parcourir le cube à travers chacune de ces nouvelles perspectives.</span><span class="sxs-lookup"><span data-stu-id="d17eb-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="d17eb-114">Définition d'une perspective Internet Sales</span><span class="sxs-lookup"><span data-stu-id="d17eb-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="d17eb-115">Ouvrez le Concepteur de cube pour le cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur l’onglet **Perspectives** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="d17eb-116">Tous les objets et leurs types d’objets apparaissent dans le volet **Perspectives** , comme le montre l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="d17eb-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d17eb-117">![Volet Perspectives du Concepteur de cube](../../2014/tutorials/media/l9-perspectives-1.gif "Volet Perspectives du Concepteur de cube")</span><span class="sxs-lookup"><span data-stu-id="d17eb-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="d17eb-118">Dans la barre d’outils de l’onglet **Perspectives** , cliquez sur **Nouvelle perspective** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="d17eb-119">Une nouvelle perspective apparaît dans la colonne **Nom de perspective** avec le nom de perspective par défaut de **Perspective**, comme le montre l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="d17eb-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="d17eb-120">Observez que les cases à cocher de tous les objets sont activées ; cette perspective est identique à la perspective par défaut de ce cube jusqu'à ce que vous désactiviez la case à cocher d'un objet.</span><span class="sxs-lookup"><span data-stu-id="d17eb-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="d17eb-121">![Nouvelle perspective dans la colonne Nom de perspective](../../2014/tutorials/media/l9-perspectives-2.gif "Nouvelle perspective dans la colonne Nom de perspective")</span><span class="sxs-lookup"><span data-stu-id="d17eb-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="d17eb-122">Remplacez le nom de la perspective par `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="d17eb-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="d17eb-123">Sur la ligne suivante, affectez à DefaultMeasure la valeur **Internet Sales-Sales Amount**.</span><span class="sxs-lookup"><span data-stu-id="d17eb-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="d17eb-124">Lorsqu'ils parcourront le cube à l'aide de cette perspective, les utilisateurs verront cette mesure, sauf s'ils en spécifient une autre.</span><span class="sxs-lookup"><span data-stu-id="d17eb-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17eb-125">Vous pouvez aussi définir la mesure par défaut pour la totalité du cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans la fenêtre Propriétés sous l’onglet **Structure de cube** pour le cube.</span><span class="sxs-lookup"><span data-stu-id="d17eb-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="d17eb-126">Désactivez la case à cocher pour les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="d17eb-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="d17eb-127">`Reseller Sales`Groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="d17eb-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-128">Groupe de mesures**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="d17eb-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-129">Groupe de mesures**Sales Quotas 1**</span><span class="sxs-lookup"><span data-stu-id="d17eb-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-130">Dimension de cube**Reseller**</span><span class="sxs-lookup"><span data-stu-id="d17eb-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-131">Dimension de cube**Reseller Geography**</span><span class="sxs-lookup"><span data-stu-id="d17eb-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-132">Dimension de cube**Sales Territory**</span><span class="sxs-lookup"><span data-stu-id="d17eb-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-133">Dimension de cube**Employee**</span><span class="sxs-lookup"><span data-stu-id="d17eb-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-134">Dimension de cube**Promotion**</span><span class="sxs-lookup"><span data-stu-id="d17eb-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-135">Indicateur de performance clé**Reseller Revenue**</span><span class="sxs-lookup"><span data-stu-id="d17eb-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="d17eb-136">Jeu nommé**Large Resellers**</span><span class="sxs-lookup"><span data-stu-id="d17eb-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="d17eb-137">Membre calculé**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="d17eb-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-138">Membre calculé**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="d17eb-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-139">Membre calculé**Reseller GPM**</span><span class="sxs-lookup"><span data-stu-id="d17eb-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-140">Membre calculé**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="d17eb-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-141">Membre calculé**Reseller Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="d17eb-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-142">Membre calculé**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="d17eb-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="d17eb-143">Ces objets ne concernent pas les ventes par Internet.</span><span class="sxs-lookup"><span data-stu-id="d17eb-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17eb-144">Dans chaque dimension, vous pouvez aussi sélectionner individuellement les hiérarchies définies par l'utilisateur et les attributs que vous souhaitez voir apparaître dans une perspective.</span><span class="sxs-lookup"><span data-stu-id="d17eb-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="d17eb-145">Définition d'une perspective Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="d17eb-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="d17eb-146">Dans la barre d’outils de l’onglet **Perspectives** , cliquez sur **Nouvelle perspective** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="d17eb-147">Remplacez le nom de la nouvelle perspective par `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="d17eb-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="d17eb-148">Définissez **Reseller Sales-Sales Amount** comme mesure par défaut.</span><span class="sxs-lookup"><span data-stu-id="d17eb-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="d17eb-149">Lorsqu'ils parcourront le cube dans cette perspective, les utilisateurs verront cette mesure, sauf s'ils en spécifient une autre.</span><span class="sxs-lookup"><span data-stu-id="d17eb-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="d17eb-150">Désactivez la case à cocher pour les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="d17eb-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="d17eb-151">`Internet Sales`Groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="d17eb-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-152">Groupe de mesures**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="d17eb-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-153">Dimension de cube**Customer**</span><span class="sxs-lookup"><span data-stu-id="d17eb-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-154">Dimension de cube**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="d17eb-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-155">Dimension de cube**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="d17eb-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-156">Action d’extraction**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="d17eb-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="d17eb-157">Membre calculé**Total Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="d17eb-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-158">Membre calculé**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="d17eb-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-159">Membre calculé**Internet GPM**</span><span class="sxs-lookup"><span data-stu-id="d17eb-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-160">Membre calculé**Total GPM**</span><span class="sxs-lookup"><span data-stu-id="d17eb-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-161">Membre calculé**Internet Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="d17eb-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="d17eb-162">Membre calculé**Total Sales Ratio to All Products**</span><span class="sxs-lookup"><span data-stu-id="d17eb-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="d17eb-163">Ces objets ne concernent pas les ventes de revendeurs.</span><span class="sxs-lookup"><span data-stu-id="d17eb-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="d17eb-164">Définition d'une perspective Sales Summary</span><span class="sxs-lookup"><span data-stu-id="d17eb-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="d17eb-165">Dans la barre d’outils de l’onglet **Perspectives** , cliquez sur **Nouvelle perspective** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="d17eb-166">Remplacez le nom de la nouvelle perspective par `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="d17eb-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17eb-167">Vous ne pouvez pas spécifier une mesure calculée comme mesure par défaut.</span><span class="sxs-lookup"><span data-stu-id="d17eb-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="d17eb-168">Désactivez la case à cocher pour les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="d17eb-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="d17eb-169">`Internet Sales`Groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="d17eb-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-170">`Reseller Sales`Groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="d17eb-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-171">Groupe de mesures**Internet Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="d17eb-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-172">Groupe de mesures**Sales Quotas**</span><span class="sxs-lookup"><span data-stu-id="d17eb-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-173">Groupe de mesures**Sales Quotas1**</span><span class="sxs-lookup"><span data-stu-id="d17eb-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="d17eb-174">Dimension de cube**Internet Sales Order Details**</span><span class="sxs-lookup"><span data-stu-id="d17eb-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-175">Dimension de cube**Sales Reason**</span><span class="sxs-lookup"><span data-stu-id="d17eb-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="d17eb-176">Action d’extraction**Internet Sales Details Drillthrough Action**</span><span class="sxs-lookup"><span data-stu-id="d17eb-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="d17eb-177">Activez la case à cocher pour les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="d17eb-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="d17eb-178">Mesure**Internet Sales Count**</span><span class="sxs-lookup"><span data-stu-id="d17eb-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="d17eb-179">Mesure**Reseller Sales Count**</span><span class="sxs-lookup"><span data-stu-id="d17eb-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="d17eb-180">Exploration du cube à travers chaque perspective</span><span class="sxs-lookup"><span data-stu-id="d17eb-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="d17eb-181">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="d17eb-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="d17eb-182">Une fois le déploiement terminé, cliquez sur l’onglet **Navigateur** , puis sur **Reconnexion** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="d17eb-183">Démarrez Excel.</span><span class="sxs-lookup"><span data-stu-id="d17eb-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="d17eb-184">L'analyse dans Excel vous invite à choisir la perspective à utiliser pour parcourir le modèle dans Excel, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="d17eb-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d17eb-185">![Objets pour la perspective Internet Sales](../../2014/tutorials/media/l9-perspectives-3.gif "Objets pour la perspective Internet Sales")</span><span class="sxs-lookup"><span data-stu-id="d17eb-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="d17eb-186">Sinon, vous pouvez ouvrir Excel à partir du menu Démarrer de Windows, définir une connexion à la base de données Analysis Services Tutorial sur localhost, et choisir une perspective l'Assistant Connexion de données, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="d17eb-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d17eb-187">![Assistant Connexion de données dans Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Assistant Connexion de données dans Excel")</span><span class="sxs-lookup"><span data-stu-id="d17eb-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="d17eb-188">Sélectionnez `Internet Sales` dans la liste **perspective** , puis examinez les mesures et les dimensions dans le volet métadonnées.</span><span class="sxs-lookup"><span data-stu-id="d17eb-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="d17eb-189">Observez que seuls les objets spécifiés pour la perspective Internet Sales apparaissent.</span><span class="sxs-lookup"><span data-stu-id="d17eb-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="d17eb-190">Dans le volet de métadonnées, développez **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="d17eb-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="d17eb-191">Notez que seul le `Internet Sales` groupe de mesures apparaît, ainsi que les membres calculés **Internet GPM** et **Internet Sales Ratio to All Products** .</span><span class="sxs-lookup"><span data-stu-id="d17eb-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="d17eb-192">Dans le modèle, sélectionnez à nouveau Excel.</span><span class="sxs-lookup"><span data-stu-id="d17eb-192">In the model, select Excel again.</span></span> <span data-ttu-id="d17eb-193">Sélectionnez `Sales Summary`.</span><span class="sxs-lookup"><span data-stu-id="d17eb-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="d17eb-194">Observez que dans chacun de ces groupes de mesures, une seule mesure apparaît, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="d17eb-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d17eb-195">![Mesures Internet Sales et Reseller Sales](../../2014/tutorials/media/l9-perspectives-4.gif "Mesures Internet Sales et Reseller Sales")</span><span class="sxs-lookup"><span data-stu-id="d17eb-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d17eb-196">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="d17eb-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d17eb-197">Définition et exploration de traductions</span><span class="sxs-lookup"><span data-stu-id="d17eb-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="d17eb-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d17eb-198">See Also</span></span>  
 <span data-ttu-id="d17eb-199">[Différente](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="d17eb-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="d17eb-200">Perspectives dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="d17eb-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
