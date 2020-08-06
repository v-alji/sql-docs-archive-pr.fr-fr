---
title: Exécuter un package dans SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696920"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="3bd64-102">Exécuter un package dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="3bd64-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="3bd64-103">Les packages sont exécutés le plus souvent dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pendant le développement, le débogage et le test des packages.</span><span class="sxs-lookup"><span data-stu-id="3bd64-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="3bd64-104">Quand vous exécutez un package à partir du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , il est exécuté immédiatement.</span><span class="sxs-lookup"><span data-stu-id="3bd64-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="3bd64-105">Pendant qu’un package s’exécute, le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] affiche la progression de l’exécution sous l’onglet **Progression** . Vous pouvez afficher l'heure de début et de fin du package et de ses tâches et conteneurs, ainsi que des informations sur les tâches et les conteneurs du package ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="3bd64-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="3bd64-106">Quand un package a terminé son exécution, les informations sur l’exécution restent disponibles sous l’onglet **Résultats d’exécution** . Pour plus d’informations, consultez la section « Rapport de progression » dans la rubrique [Débogage du flux de contrôle](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="3bd64-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="3bd64-107">**Déploiement au moment du design**.</span><span class="sxs-lookup"><span data-stu-id="3bd64-107">**Design-time deployment**.</span></span> <span data-ttu-id="3bd64-108">Lorsqu'un package est exécuté dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], il est créé, puis déployé dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="3bd64-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="3bd64-109">Avant d'exécuter le package, vous pouvez spécifier le dossier dans lequel il est déployé.</span><span class="sxs-lookup"><span data-stu-id="3bd64-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="3bd64-110">Si vous ne spécifiez aucun dossier, le dossier **bin** est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="3bd64-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="3bd64-111">Ce type de déploiement est appelé déploiement au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="3bd64-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="3bd64-112">Pour exécuter un package dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="3bd64-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="3bd64-113">Dans l’Explorateur de solutions, si votre solution contient plusieurs projets, cliquez avec le bouton droit sur le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package, puis cliquez sur **Définir en tant qu’objet de démarrage** pour définir le projet de démarrage.</span><span class="sxs-lookup"><span data-stu-id="3bd64-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="3bd64-114">Dans l’Explorateur de solutions, si votre projet contient plusieurs packages, cliquez avec le bouton droit sur un package, puis cliquez sur **Définir en tant qu’objet de démarrage** pour définir le package de démarrage.</span><span class="sxs-lookup"><span data-stu-id="3bd64-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="3bd64-115">Pour exécuter un package, utilisez l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="3bd64-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="3bd64-116">Ouvrez le package à exécuter, puis cliquez sur **Démarrer le débogage** dans la barre de menus ou appuyez sur F5.</span><span class="sxs-lookup"><span data-stu-id="3bd64-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="3bd64-117">Une fois l'exécution du package terminée, appuyez sur Maj+F5 pour revenir au mode Création.</span><span class="sxs-lookup"><span data-stu-id="3bd64-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="3bd64-118">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le package, puis cliquez sur **Exécuter le package**.</span><span class="sxs-lookup"><span data-stu-id="3bd64-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="3bd64-119">Pour spécifier un dossier différent pour le déploiement au moment du design</span><span class="sxs-lookup"><span data-stu-id="3bd64-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="3bd64-120">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le dossier de projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package à exécuter, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3bd64-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3bd64-121">Dans la boîte de dialogue **\<project name>Pages de propriétés de** , cliquez sur **Générer**.</span><span class="sxs-lookup"><span data-stu-id="3bd64-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="3bd64-122">Mettez à jour la valeur de la propriété OutputPath pour indiquer le dossier que vous souhaitez utiliser pour le déploiement au moment du design, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bd64-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd64-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bd64-123">See Also</span></span>  
 <span data-ttu-id="3bd64-124">[Exécution de projets et de packages](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3bd64-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="3bd64-125">Packages Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3bd64-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
