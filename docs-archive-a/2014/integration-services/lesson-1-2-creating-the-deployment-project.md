---
title: 'Étape 2 : Création du projet de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605590"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="999ec-102">Étape 2 : Création du projet de déploiement</span><span class="sxs-lookup"><span data-stu-id="999ec-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="999ec-103">Dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], l'unité déployable est un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="999ec-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="999ec-104">Avant de pouvoir déployer les packages, vous devez créer un nouveau projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et ajouter à ce projet tous les packages et les fichiers annexes que vous souhaitez déployer avec les packages.</span><span class="sxs-lookup"><span data-stu-id="999ec-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="999ec-105">Pour créer le projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="999ec-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="999ec-106">Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, sur **Microsoft SQL Server**, puis cliquez sur **SQL Server SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="999ec-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="999ec-107">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet** pour créer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="999ec-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="999ec-108">Dans la boîte de dialogue **Nouveau projet** , sélectionnez **Projet Integration Services** dans le volet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="999ec-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="999ec-109">Dans la zone **Nom** , remplacez le nom par défaut par **Didacticiel de déploiement**.</span><span class="sxs-lookup"><span data-stu-id="999ec-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="999ec-110">Vous pouvez éventuellement désactiver la case à cocher **Créer le répertoire pour la solution** .</span><span class="sxs-lookup"><span data-stu-id="999ec-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="999ec-111">Acceptez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder au dossier que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="999ec-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="999ec-112">Dans la boîte de dialogue **Emplacement du projet** , cliquez sur le dossier, puis sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="999ec-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="999ec-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="999ec-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="999ec-114">Par défaut, un package vide, nommé Package.dtsx, est créé et ajouté à votre projet.</span><span class="sxs-lookup"><span data-stu-id="999ec-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="999ec-115">Cependant, vous ne pourrez pas utiliser ce package ; à la place, vous allez ajouter des packages existants au projet.</span><span class="sxs-lookup"><span data-stu-id="999ec-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="999ec-116">Dans la mesure où tous les packages d'un projet sont inclus dans le déploiement, vous devez supprimer le fichier Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="999ec-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="999ec-117">Pour ce faire, cliquez dessus avec le bouton droit, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="999ec-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="999ec-118">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="999ec-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="999ec-119">Étape 3 : Ajout de packages et d’autres fichiers</span><span class="sxs-lookup"><span data-stu-id="999ec-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="999ec-120">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="999ec-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="999ec-121">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="999ec-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="999ec-122">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="999ec-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="999ec-123">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="999ec-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999ec-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="999ec-124">See Also</span></span>  
 [<span data-ttu-id="999ec-125">Projets Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="999ec-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
