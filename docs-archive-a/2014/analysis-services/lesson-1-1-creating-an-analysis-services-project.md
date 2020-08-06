---
title: Création d’un projet de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600304"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="84f56-102">Création d'un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="84f56-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="84f56-103">Dans la tâche suivante, vous utilisez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour créer un nouveau [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projet nommé `Analysis Services Tutorial` , en fonction du [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modèle de projet.</span><span class="sxs-lookup"><span data-stu-id="84f56-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="84f56-104">Un *projet* est une collection d'objets connexes.</span><span class="sxs-lookup"><span data-stu-id="84f56-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="84f56-105">Les projets existent au sein d'une solution, laquelle peut inclure un ou plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="84f56-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="84f56-106">Pour plus d’informations, consultez [Créer un projet Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="84f56-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="84f56-107">Pour créer un nouveau projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="84f56-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="84f56-108">Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server 2012**, puis cliquez sur **Outils de données SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="84f56-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="84f56-109">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environnement de développement s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="84f56-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="84f56-110">Dans la page de démarrage de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], cliquez sur **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="84f56-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="84f56-111">Dans la boîte de dialogue **Nouveau projet** , dans le volet **Modèles installés** , développez **Business Intelligence**et sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="84f56-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="84f56-112">Choisissez le modèle **Analysis Services Multidimensional and Data Mining Project** .</span><span class="sxs-lookup"><span data-stu-id="84f56-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="84f56-113">Au bas de la boîte de dialogue, notez que le nom par défaut et l'emplacement du projet, ainsi que le nom par défaut de la solution, sont générés.</span><span class="sxs-lookup"><span data-stu-id="84f56-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="84f56-114">Par défaut, un nouveau répertoire est créé pour la solution.</span><span class="sxs-lookup"><span data-stu-id="84f56-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="84f56-115">Remplacez le nom du projet par `Analysis Services Tutorial` , ce qui modifie également la zone **nom** de la solution, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84f56-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="84f56-116">Vous avez correctement créé le `Analysis Services Tutorial` projet, en fonction du modèle de **projet multidimensionnel et d’exploration de données Analysis Services** , dans une nouvelle solution qui est également nommée `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="84f56-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="84f56-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="84f56-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="84f56-118">Définition d’une source de données</span><span class="sxs-lookup"><span data-stu-id="84f56-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="84f56-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84f56-119">See Also</span></span>  
 <span data-ttu-id="84f56-120">[Création de modèles multidimensionnels à l’aide de SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="84f56-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="84f56-121">Créer un projet Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="84f56-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
