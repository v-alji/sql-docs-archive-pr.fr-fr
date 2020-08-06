---
title: 'Étape 1 : Génération de l’utilitaire de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605562"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="8406e-102">Étape 1 : Génération de l’utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="8406e-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="8406e-103">Au cours de cette tâche, vous allez configurer et générer un utilitaire de déploiement pour le projet Didacticiel de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8406e-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="8406e-104">Avant de générer l'utilitaire de déploiement, vous devez modifier les propriétés du projet Didacticiel de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8406e-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="8406e-105">La boîte de dialogue **Pages de propriétés du didacticiel de déploiement** vous permet de configurer ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="8406e-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="8406e-106">Dans cette boîte de dialogue, vous devez activer la possibilité de mettre à jour des configurations au cours du déploiement et spécifier que le processus de création génère un utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8406e-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="8406e-107">Après avoir défini les propriétés, vous allez générer le projet.</span><span class="sxs-lookup"><span data-stu-id="8406e-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="8406e-108">fournit un jeu de fenêtres que vous pouvez utiliser pour déboguer les packages.</span><span class="sxs-lookup"><span data-stu-id="8406e-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="8406e-109">Vous pouvez afficher les messages d'erreur, d'information et d'avertissement, effectuer le suivi du statut des packages lors de l'exécution ou afficher la progression et les résultats des processus de génération.</span><span class="sxs-lookup"><span data-stu-id="8406e-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="8406e-110">Pour cette leçon, vous allez utiliser la fenêtre de sortie pour afficher la progression et les résultats de la génération de l'utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8406e-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="8406e-111">Pour définir les propriétés de l'utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="8406e-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="8406e-112">Si [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] n’est pas déjà ouvert, dans le menu **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server**et cliquez sur **Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="8406e-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="8406e-113">Dans le menu **Fichier** , cliquez successivement sur **Ouvrir**, sur **Projet/Solution**, sur le dossier **Didacticiel de déploiement** et sur **Ouvrir**, puis double-cliquez sur **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="8406e-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="8406e-114">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur Didacticiel de déploiement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8406e-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8406e-115">Dans la boîte de dialogue **Pages de propriétés du didacticiel de déploiement** , développez Propriétés de configuration et cliquez sur Utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8406e-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="8406e-116">Dans le volet droit de la boîte de dialogue **pages de propriétés du didacticiel de déploiement** , vérifiez que a la valeur `AllowConfigurationChanges` `true` , affectez `CreateDeploymentUtility` à `true` la valeur, et mettez éventuellement à jour la valeur par défaut `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="8406e-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="8406e-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8406e-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="8406e-118">Pour générer l'utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="8406e-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="8406e-119">Dans l’Explorateur de solutions, cliquez sur **Didacticiel de déploiement**.</span><span class="sxs-lookup"><span data-stu-id="8406e-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="8406e-120">Dans le menu **Affichage** , cliquez sur **Sortie**.</span><span class="sxs-lookup"><span data-stu-id="8406e-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="8406e-121">Par défaut, la fenêtre de sortie se trouve dans le coin inférieur gauche de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8406e-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="8406e-122">Dans le menu **Générer** , cliquez sur **Générer le didacticiel de déploiement**.</span><span class="sxs-lookup"><span data-stu-id="8406e-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="8406e-123">Dans la fenêtre de sortie, vérifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8406e-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="8406e-124">Génération démarrée : projet SQL Integration Services : incrémentiel ...</span><span class="sxs-lookup"><span data-stu-id="8406e-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="8406e-125">Création de l'utilitaire de déploiement...</span><span class="sxs-lookup"><span data-stu-id="8406e-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="8406e-126">Utilitaire de déploiement créé.</span><span class="sxs-lookup"><span data-stu-id="8406e-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="8406e-127">Fin de la génération -- 0 erreur, 0 avertissement</span><span class="sxs-lookup"><span data-stu-id="8406e-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="8406e-128">========== Génération : 0 a réussi, 0 a échoué, 1 est à jour, 0 a été ignoré ==========</span><span class="sxs-lookup"><span data-stu-id="8406e-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="8406e-129">Dans le menu **Fichier** , cliquez sur **Quitter**.</span><span class="sxs-lookup"><span data-stu-id="8406e-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="8406e-130">Si vous êtes invité à enregistrer les modifications apportées aux éléments du didacticiel de déploiement, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8406e-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8406e-131">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="8406e-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8406e-132">Étape 2 : Vérification du bundle de déploiement</span><span class="sxs-lookup"><span data-stu-id="8406e-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="8406e-133">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8406e-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8406e-134">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="8406e-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8406e-135">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="8406e-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8406e-136">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="8406e-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8406e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8406e-137">See Also</span></span>  
 [<span data-ttu-id="8406e-138">Créer un utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="8406e-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
