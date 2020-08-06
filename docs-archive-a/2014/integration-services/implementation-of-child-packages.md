---
title: Implémentation des packages enfants | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698453"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="423a8-102">Implémentation de packages enfants</span><span class="sxs-lookup"><span data-stu-id="423a8-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="423a8-103">Quand vous implémentez un équilibrage de charge avec [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], des packages enfants sont installés sur d’autres serveurs pour tirer parti du temps UC ou serveur disponible.</span><span class="sxs-lookup"><span data-stu-id="423a8-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="423a8-104">Pour créer et exécuter les packages enfants, les opérations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="423a8-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="423a8-105">Conception des packages enfants.</span><span class="sxs-lookup"><span data-stu-id="423a8-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="423a8-106">Déplacement des packages sur le serveur distant.</span><span class="sxs-lookup"><span data-stu-id="423a8-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="423a8-107">Création d'un travail de SQL Server Agent sur le serveur distant qui contient une étape exécutant le package enfant.</span><span class="sxs-lookup"><span data-stu-id="423a8-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="423a8-108">Test et débogage du travail de SQL Server Agent et des packages enfants.</span><span class="sxs-lookup"><span data-stu-id="423a8-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="423a8-109">Lorsque vous concevez les packages enfants, les packages n'ont pas de limites dans leur conception, et vous pouvez inclure toutes les fonctionnalités souhaitées.</span><span class="sxs-lookup"><span data-stu-id="423a8-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="423a8-110">Cependant, si le package accède à des données, vous devez vous assurer que le serveur qui exécute le package a accès aux données.</span><span class="sxs-lookup"><span data-stu-id="423a8-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="423a8-111">Pour identifier le package parent qui exécute les packages enfants, dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , cliquez avec le bouton droit sur le package dans l’Explorateur de solutions et sélectionnez **Package de point d’entrée**.</span><span class="sxs-lookup"><span data-stu-id="423a8-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="423a8-112">Une fois que les packages enfants ont été conçus, l'étape suivante consiste à les déployer sur les serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="423a8-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="423a8-113">Déplacement du package enfant sur le serveur distant.</span><span class="sxs-lookup"><span data-stu-id="423a8-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="423a8-114">Il existe plusieurs façons de déplacer des packages sur d'autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="423a8-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="423a8-115">Les deux méthodes suggérées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="423a8-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="423a8-116">Exportation des packages à l'aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="423a8-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="423a8-117">Déploiement de packages en créant un utilitaire de déploiement pour le projet qui contient les packages que vous voulez déployer, puis en exécutant l'Assistant Installation de package pour installer les packages sur le système de fichiers ou sur une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="423a8-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="423a8-118">Pour plus d’informations, consultez [déploiement de packages &#40;&#41;SSIS ](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="423a8-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="423a8-119">Vous devez recommencer le déploiement sur chaque serveur distant à utiliser.</span><span class="sxs-lookup"><span data-stu-id="423a8-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="423a8-120">Création des travaux de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="423a8-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="423a8-121">Une fois que les packages enfants ont été déployés sur les divers serveurs, créez un travail de SQL Server Agent sur chaque serveur contenant un package enfant.</span><span class="sxs-lookup"><span data-stu-id="423a8-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="423a8-122">Le travail de SQL Server Agent contient une étape qui exécute le package enfant lors de l'appel de l'agent du travail.</span><span class="sxs-lookup"><span data-stu-id="423a8-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="423a8-123">Les travaux de SQL Server Agent ne sont pas des travaux planifiés ; ils exécutent les packages enfants uniquement lorsqu'ils sont appelés par le package parent.</span><span class="sxs-lookup"><span data-stu-id="423a8-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="423a8-124">La notification de la réussite ou de l'échec du travail au package parent reflète la réussite ou l'échec du travail de SQL Server Agent et l'aboutissement de son appel, et non la réussite ou l'échec du package enfant ou son éventuelle exécution.</span><span class="sxs-lookup"><span data-stu-id="423a8-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="423a8-125">Débogage des travaux de SQL Server Agent et des packages enfants.</span><span class="sxs-lookup"><span data-stu-id="423a8-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="423a8-126">Vous pouvez tester les travaux de SQL Server Agent et leurs packages enfants à l'aide de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="423a8-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="423a8-127">Exécution de chaque package enfant dans le concepteur SSIS, en cliquant sur **Déboguer**  /  **exécuter sans débogage**.</span><span class="sxs-lookup"><span data-stu-id="423a8-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="423a8-128">Exécution du travail individuel de SQL Server Agent sur l’ordinateur distant à l’aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], pour vérifier que le package fonctionne.</span><span class="sxs-lookup"><span data-stu-id="423a8-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="423a8-129">Pour plus d’informations sur la résolution des problèmes liés aux packages que vous exécutez à partir des travaux de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, consultez [Un package SSIS ne s’exécute pas lorsque vous appelez le package SSIS à partir d’une étape de travail de SQL Server Agent](https://support.microsoft.com/kb/918760) dans la Base de connaissances du support technique [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="423a8-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="423a8-130">SQL Server Agent vérifie l'accès au sous-système pour un proxy et donne accès au proxy à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="423a8-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="423a8-131">Vous pouvez créer un proxy dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="423a8-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="423a8-132">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="423a8-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="423a8-133">Exécuter un package sur le serveur SSIS à l’aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="423a8-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="423a8-134">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="423a8-134">Related Content</span></span>  
  
-   <span data-ttu-id="423a8-135">Entrée de blog, [SSIS : accès aux variables dans un package parent](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), sur andyleonard. blog.</span><span class="sxs-lookup"><span data-stu-id="423a8-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="423a8-136">Article, [tâche d’exécution de package](../integration-services/control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="423a8-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
