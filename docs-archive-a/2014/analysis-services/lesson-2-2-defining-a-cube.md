---
title: Définition d’un cube | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600280"
---
# <a name="defining-a-cube"></a><span data-ttu-id="28748-102">Définition d'un cube</span><span class="sxs-lookup"><span data-stu-id="28748-102">Defining a Cube</span></span>
  <span data-ttu-id="28748-103">L'Assistant Cube vous aide à définir les groupes de mesures et les dimensions d'un cube.</span><span class="sxs-lookup"><span data-stu-id="28748-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="28748-104">Dans la tâche suivante, vous allez utiliser l'Assistant Cube pour générer un cube.</span><span class="sxs-lookup"><span data-stu-id="28748-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="28748-105">Pour définir un cube et ses propriétés</span><span class="sxs-lookup"><span data-stu-id="28748-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="28748-106">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Cubes**, puis cliquez sur **Nouveau cube**.</span><span class="sxs-lookup"><span data-stu-id="28748-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="28748-107">L'Assistant Cube apparaît.</span><span class="sxs-lookup"><span data-stu-id="28748-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="28748-108">Dans la page **Bienvenue dans l’Assistant Cube** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="28748-109">Dans la page **Sélectionner la méthode de création** , vérifiez que l’option **Utiliser des tables existantes** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="28748-110">Dans la page **Sélectionner les tables de groupes de mesures** , vérifiez que la vue de source des données **Adventure Works DW 2012** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28748-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="28748-111">Cliquez sur **Suggérer** pour que l’Assistant Cube suggère les tables à utiliser pour créer les groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="28748-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="28748-112">L’Assistant examine les tables et suggère **InternetSales** comme table de groupes de mesures.</span><span class="sxs-lookup"><span data-stu-id="28748-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="28748-113">Les tables de groupes de mesures, également appelées tables de faits, contiennent les mesures qui présentent un intérêt particulier pour vous, comme le nombre d’unités vendues.</span><span class="sxs-lookup"><span data-stu-id="28748-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="28748-114">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="28748-115">Dans la page **Sélectionner des mesures** , vérifiez les mesures sélectionnées dans le groupe de mesures **Internet Sales** , puis désactivez les cases à cocher correspondant aux mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="28748-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="28748-116">**Promotion Key**</span><span class="sxs-lookup"><span data-stu-id="28748-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="28748-117">**Currency Key**</span><span class="sxs-lookup"><span data-stu-id="28748-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="28748-118">**Sales Territory Key**</span><span class="sxs-lookup"><span data-stu-id="28748-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="28748-119">**Revision Number**</span><span class="sxs-lookup"><span data-stu-id="28748-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="28748-120">Par défaut, l'Assistant sélectionne comme mesures toutes les colonnes numériques de la table de faits qui ne sont pas liées à des dimensions.</span><span class="sxs-lookup"><span data-stu-id="28748-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="28748-121">Toutefois, ces quatre colonnes ne sont pas vraiment des mesures.</span><span class="sxs-lookup"><span data-stu-id="28748-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="28748-122">Les trois premières sont des valeurs clé qui lient la table de faits aux tables de dimension qui ne sont pas utilisées dans la première version de ce cube.</span><span class="sxs-lookup"><span data-stu-id="28748-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="28748-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="28748-124">Dans la page **Sélectionner des dimensions existantes** , vérifiez que la dimension **Date** que vous avez créée précédemment est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="28748-125">Dans la page **Sélectionner de nouvelles dimensions** , sélectionnez les nouvelles dimensions à créer.</span><span class="sxs-lookup"><span data-stu-id="28748-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="28748-126">Pour cela, vérifiez que les cases **Customer**, **Geography**et **Product** sont cochées, puis décochez la case **InternetSales** .</span><span class="sxs-lookup"><span data-stu-id="28748-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="28748-127">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="28748-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="28748-128">Dans la page **fin de l’Assistant** , remplacez le nom du cube par `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="28748-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="28748-129">Dans le volet Aperçu, vous pouvez voir le groupe de mesures **InternetSales** et ses mesures.</span><span class="sxs-lookup"><span data-stu-id="28748-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="28748-130">Vous pouvez également voir les dimensions **Date**, **Customer** et **Product** .</span><span class="sxs-lookup"><span data-stu-id="28748-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="28748-131">Cliquez sur **Terminer** pour terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="28748-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="28748-132">Dans l’Explorateur de solutions, dans le projet Didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] apparaît dans le dossier **Cubes** et les dimensions de base de données Customer et Product apparaissent dans le dossier **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="28748-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="28748-133">De plus, au centre de l'environnement de développement, l'onglet Structure de cube affiche le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28748-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="28748-134">Dans la barre d’outils de l’onglet Structure de cube, choisissez un niveau de **Zoom** de 50 % pour voir plus facilement les tables de dimension et de faits du cube.</span><span class="sxs-lookup"><span data-stu-id="28748-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="28748-135">Notez que la table de faits est jaune et que les tables de dimension sont bleues.</span><span class="sxs-lookup"><span data-stu-id="28748-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="28748-136">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="28748-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="28748-137">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="28748-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="28748-138">Ajout d'attributs aux dimensions</span><span class="sxs-lookup"><span data-stu-id="28748-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="28748-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28748-139">See Also</span></span>  
 <span data-ttu-id="28748-140">[Cubes dans les modèles multidimensionnels](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="28748-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="28748-141">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="28748-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
