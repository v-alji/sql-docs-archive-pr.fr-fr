---
title: Assistant Déploiement de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705288"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="db2c6-102">Assistant Déploiement d’Integration Services</span><span class="sxs-lookup"><span data-stu-id="db2c6-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="db2c6-103">L'Assistant Déploiement d'[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] déploie des projets dans le catalogue SSISDB sur une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à l'aide du modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="db2c6-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="db2c6-104">Pour démarrer l' [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Assistant déploiement à partir d’un projet ouvert dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , sélectionnez **déployer** dans le menu **projet** .</span><span class="sxs-lookup"><span data-stu-id="db2c6-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="db2c6-105">Pour démarrer l’Assistant dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , développez le nœud **Integration Services catalogues**  >  **SSISDB** dans l’Explorateur d’objets, cliquez avec le bouton droit sur le dossier **projets** , puis cliquez sur **déployer le projet**.</span><span class="sxs-lookup"><span data-stu-id="db2c6-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="db2c6-106">L'Assistant effectue les quatre étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="db2c6-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="db2c6-107">Cliquez sur **suivant** pour passer à l’étape suivante, ou sur **précédent** pour revenir à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="db2c6-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="db2c6-108">**Sélectionnez source** -sélectionnez le [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projet que vous souhaitez déployer.</span><span class="sxs-lookup"><span data-stu-id="db2c6-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="db2c6-109">**Sélectionner** la destination : sélectionnez la destination du projet.</span><span class="sxs-lookup"><span data-stu-id="db2c6-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="db2c6-110">**Consulter** : affiche vos sélections.</span><span class="sxs-lookup"><span data-stu-id="db2c6-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="db2c6-111">**Déployer/résultats** -déploie le projet et affiche les résultats.</span><span class="sxs-lookup"><span data-stu-id="db2c6-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="db2c6-112">Sélectionner la source</span><span class="sxs-lookup"><span data-stu-id="db2c6-112">Select Source</span></span>  
 <span data-ttu-id="db2c6-113">Pour déployer un fichier de déploiement de projet que vous avez créé, sélectionnez **fichier de déploiement de projet** , puis entrez le chemin d’accès au fichier. ISPAC ou cliquez sur **Parcourir** pour le trouver dans le [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] dossier du projet.</span><span class="sxs-lookup"><span data-stu-id="db2c6-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="db2c6-114">Pour déployer un projet qui réside dans le catalogue [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , sélectionnez **Catalogue Integration Services**, puis entrez le nom du serveur et le chemin d'accès au projet au sein du catalogue.</span><span class="sxs-lookup"><span data-stu-id="db2c6-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="db2c6-115">Si vous démarrez l'Assistant dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], l'Assistant sélectionne ensuite par défaut le projet ouvert en tant que source et ignore cette étape.</span><span class="sxs-lookup"><span data-stu-id="db2c6-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="db2c6-116">Pour revenir à cette étape et sélectionner une autre source, cliquez sur **précédent** ou sur **Sélectionner une source** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="db2c6-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="db2c6-117">Sélectionner la destination</span><span class="sxs-lookup"><span data-stu-id="db2c6-117">Select Destination</span></span>  
 <span data-ttu-id="db2c6-118">Pour sélectionner le dossier de destination du projet dans le catalogue [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , entrez l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou cliquez sur **Parcourir** pour sélectionner un serveur dans une liste de serveurs.</span><span class="sxs-lookup"><span data-stu-id="db2c6-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="db2c6-119">Entrez le chemin d'accès au projet dans SSISDB ou cliquez sur **Parcourir** pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="db2c6-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="db2c6-120">Si vous démarrez l'Assistant dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], l'Assistant sélectionne ensuite par défaut l'instance de serveur connectée et entre le chemin d'accès du projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="db2c6-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="db2c6-121">Vous pouvez modifier ces valeurs pour déployer le projet dans un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="db2c6-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="db2c6-122">Révision</span><span class="sxs-lookup"><span data-stu-id="db2c6-122">Review</span></span>  
 <span data-ttu-id="db2c6-123">L'Assistant vous permet de vérifier les paramètres que vous avez sélectionnés avant de déployer le projet.</span><span class="sxs-lookup"><span data-stu-id="db2c6-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="db2c6-124">Vous pouvez modifier vos sélections en cliquant sur **Précédent**ou en cliquant sur l'une des étapes dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="db2c6-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="db2c6-125">Déployer/Résultats</span><span class="sxs-lookup"><span data-stu-id="db2c6-125">Deploy/Results</span></span>  
 <span data-ttu-id="db2c6-126">Lorsque vous cliquez sur **déployer** à partir de la page **vérifier** , le projet est déployé et la page **résultats** affiche la réussite ou l’échec de chaque action.</span><span class="sxs-lookup"><span data-stu-id="db2c6-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="db2c6-127">Si l'action échoue, cliquez sur **Échec** dans la colonne **Résultat** pour afficher une explication de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="db2c6-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="db2c6-128">Cliquez sur **enregistrer le rapport...** pour enregistrer les résultats dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="db2c6-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="db2c6-129">Cliquez sur **Fermer** pour quitter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="db2c6-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2c6-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db2c6-130">See Also</span></span>  
 <span data-ttu-id="db2c6-131">[Déployer des projets sur Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="db2c6-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="db2c6-132">Déploiement de projets et de packages</span><span class="sxs-lookup"><span data-stu-id="db2c6-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
