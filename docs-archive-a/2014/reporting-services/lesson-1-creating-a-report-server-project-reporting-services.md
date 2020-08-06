---
title: 'Leçon 1 : création d’un projet Report Server (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 675671ca-e6c9-48a2-82e9-386778f3a49f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a708e5114344e87edd620ef58bc50594a9b9ef8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710275"
---
# <a name="lesson-1-creating-a-report-server-project-reporting-services"></a><span data-ttu-id="ad3d4-102">Leçon 1 : Création d'un projet Report Server (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="ad3d4-102">Lesson 1: Creating a Report Server Project (Reporting Services)</span></span>
  <span data-ttu-id="ad3d4-103">Pour créer un rapport dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vous devez commencer par créer un projet Report Server dans lequel vous allez enregistrer votre fichier de définition de rapport (.rdl), ainsi que les autres fichiers de ressources dont vous avez besoin pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-103">To create a report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you must first create a report server project where you will save your report definition (.rdl) file and any other resource files that you need for your report.</span></span> <span data-ttu-id="ad3d4-104">Puis, vous créez le fichier réel de définition du rapport, et définissez une source de données pour votre rapport, un dataset et la mise en page du rapport.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-104">Then you will create the actual report definition file, define a data source for your report, define a dataset, and define the report layout.</span></span> <span data-ttu-id="ad3d4-105">Quand vous exécutez le rapport, les données réelles sont extraites et combinées avec la mise en page, puis restituées sur votre écran, à partir duquel vous pouvez les exporter, les imprimer ou les enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-105">When you run the report, the actual data is retrieved and combined with the layout, and then rendered on your screen, from where you can export it, print it, or save it.</span></span>  
  
 <span data-ttu-id="ad3d4-106">Dans cette leçon, vous allez apprendre à créer un projet Report Server dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad3d4-106">In this lesson, you will learn how to create a report server project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ad3d4-107">Un projet Report Server permet de créer des rapports qui s'exécutent sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-107">A report server project is used to create reports that run on a report server.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="ad3d4-108">Pour créer un projet Report Server</span><span class="sxs-lookup"><span data-stu-id="ad3d4-108">To create a report server project</span></span>  
  
1.  <span data-ttu-id="ad3d4-109">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] , puis cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Data Tools**.</span></span> <span data-ttu-id="ad3d4-110">S’il s’agit de la première fois que vous ouvrez [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , cliquez sur **paramètres Business Intelligence** pour les paramètres d’environnement par défaut.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-110">If this is the first time you have opened [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Business Intelligence Settings** for the default environment settings.</span></span>  
  
2.  <span data-ttu-id="ad3d4-111">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="ad3d4-112">Dans la liste **Modèles installés** , cliquez sur **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-112">In the **Installed Templates** list, click **Business Intelligence**.</span></span>  
  
4.  <span data-ttu-id="ad3d4-113">Cliquez sur **projet Report Server**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-113">Click **Report Server Project**.</span></span>  
  
5.  <span data-ttu-id="ad3d4-114">Dans **nom**, tapez **Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-114">In **Name**, type **Tutorial**.</span></span>  
  
6.  <span data-ttu-id="ad3d4-115">Cliquez sur **OK** pour créer le projet.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-115">Click **OK** to create the project.</span></span>  
  
     <span data-ttu-id="ad3d4-116">Le projet Didacticiel s'affiche dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-116">The Tutorial project is displayed in Solution Explorer.</span></span>  
  
### <a name="to-create-a-new-report-definition-file"></a><span data-ttu-id="ad3d4-117">Pour créer un nouveau fichier de définition de rapport</span><span class="sxs-lookup"><span data-stu-id="ad3d4-117">To create a new report definition file</span></span>  
  
1.  <span data-ttu-id="ad3d4-118">Dans Explorateur de solutions, cliquez avec le bouton droit sur **rapports**, pointez sur **Ajouter**, puis cliquez sur **nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-118">In Solution Explorer, right-click **Reports**, point to **Add**, and click **New Item**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad3d4-119">Si la fenêtre **Explorateur de solutions** n’est pas visible, dans le menu **Affichage** , cliquez sur **Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-119">If the **Solution Explorer** window is not visible, from the **View** menu, click **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="ad3d4-120">Dans la boîte de dialogue **Ajouter un nouvel élément** , sous **modèles**, cliquez sur **rapport**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-120">In the **Add New Item** dialog box, under **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="ad3d4-121">Dans la zone **Nom**, tapez **Sales Orders.rdl** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-121">In **Name**, type **Sales Orders.rdl** and then click **Add**.</span></span>  
  
     <span data-ttu-id="ad3d4-122">Le Concepteur de rapports s'ouvre et affiche le nouveau fichier .rdl en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-122">Report Designer opens and displays the new .rdl file in Design view.</span></span>  
  
 <span data-ttu-id="ad3d4-123">Le Concepteur de rapports est un composant [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] qui s'exécute dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad3d4-123">Report Designer is a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] component that runs in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ad3d4-124">Il comporte deux vues : **Conception** et **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-124">It has two views: **Design** and **Preview**.</span></span> <span data-ttu-id="ad3d4-125">Cliquez sur chacun des onglets pour passer d'une vue à une autre.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-125">Click each tab to change views.</span></span>  
  
 <span data-ttu-id="ad3d4-126">Vous définissez vos données dans le volet **Données du rapport** .</span><span class="sxs-lookup"><span data-stu-id="ad3d4-126">You define your data in the **Report Data** pane.</span></span> <span data-ttu-id="ad3d4-127">Vous définissez la mise en page de votre rapport en mode **Conception** .</span><span class="sxs-lookup"><span data-stu-id="ad3d4-127">You define your report layout in **Design** view.</span></span> <span data-ttu-id="ad3d4-128">Vous pouvez exécuter le rapport et visualiser son aspect en mode **Aperçu** .</span><span class="sxs-lookup"><span data-stu-id="ad3d4-128">You can run the report and see what it looks like in **Preview** view.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="ad3d4-129">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="ad3d4-129">Next Task</span></span>  
 <span data-ttu-id="ad3d4-130">Vous avez créé avec succès un projet de rapport appelé « Didacticiel » et ajouté un fichier de définition de rapport (.rdl) au projet de rapport.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-130">You have successfully created a report project called "Tutorial" and added a report definition (.rdl) file to the report project.</span></span> <span data-ttu-id="ad3d4-131">Vous allez ensuite spécifier la source de données à utiliser pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="ad3d4-131">Next, you will specify a data source to use for the report.</span></span> <span data-ttu-id="ad3d4-132">Consultez [Leçon 2 : Spécification des informations de connexion &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ad3d4-132">See [Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3d4-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad3d4-133">See Also</span></span>  
 [<span data-ttu-id="ad3d4-134">Créer un rapport de tableau de base &#40;Didacticiel SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ad3d4-134">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
