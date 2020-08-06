---
title: Comprendre les fichiers d’entrée utilisés pour créer le script de déploiement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605828"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="530cc-102">Précisions sur les fichiers d'entrée utilisés pour créer le script de déploiement</span><span class="sxs-lookup"><span data-stu-id="530cc-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="530cc-103">Lorsque vous générez un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] génère des fichiers XML pour le projet.</span><span class="sxs-lookup"><span data-stu-id="530cc-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="530cc-104">place ces fichiers XML dans le dossier de sortie du projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="530cc-104">puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="530cc-105">Par défaut, les sorties sont envoyées au dossier \Bin.</span><span class="sxs-lookup"><span data-stu-id="530cc-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="530cc-106">Le tableau suivant répertorie les fichiers XML que crée [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="530cc-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="530cc-107">Fichier XMLA</span><span class="sxs-lookup"><span data-stu-id="530cc-107">XMLA file</span></span>|<span data-ttu-id="530cc-108">Description</span><span class="sxs-lookup"><span data-stu-id="530cc-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="530cc-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="530cc-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="530cc-110">Contient les définitions déclaratives de tous les objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] du projet.</span><span class="sxs-lookup"><span data-stu-id="530cc-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="530cc-111">\<*project name*>. deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="530cc-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="530cc-112">Contient le nom de l'instance et de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans lesquelles les objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] seront créés.</span><span class="sxs-lookup"><span data-stu-id="530cc-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="530cc-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="530cc-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="530cc-114">Contient des paramètres spécifiques à l'environnement, par exemple des informations sur la connexion à une source de données et les emplacements de stockage des objets.</span><span class="sxs-lookup"><span data-stu-id="530cc-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="530cc-115">Les paramètres de ce fichier remplacent les paramètres dans le \<*project name*> fichier. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="530cc-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="530cc-116">\<*project name*>. deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="530cc-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="530cc-117">Contient des options de déploiement qui déterminent, par exemple, si le déploiement est transactionnel et si les objets déployés doivent être traités après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="530cc-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="530cc-118">ne stocke jamais les mots de passe dans ses fichiers de projet.</span><span class="sxs-lookup"><span data-stu-id="530cc-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="530cc-119">Modification des fichiers d'entrée</span><span class="sxs-lookup"><span data-stu-id="530cc-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="530cc-120">La modification des valeurs dans les fichiers d’entrée, ou les valeurs récupérées à partir des fichiers d’entrée, permet de modifier la destination du déploiement, les paramètres de configuration et les options de déploiement sans modifier la totalité du \<*project name*> fichier. asdatabase (ou un fichier de script XMLA entier si vous générez un script à partir d’une [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données existante).</span><span class="sxs-lookup"><span data-stu-id="530cc-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="530cc-121">La possibilité de modifier des fichiers individuels vous permet de créer facilement des scripts de déploiement différents selon les buts poursuivis.</span><span class="sxs-lookup"><span data-stu-id="530cc-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="530cc-122">Les rubriques suivantes expliquent comment modifier des valeurs dans les divers fichiers d'entrée :</span><span class="sxs-lookup"><span data-stu-id="530cc-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="530cc-123">Spécification de la cible d'installation</span><span class="sxs-lookup"><span data-stu-id="530cc-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="530cc-124">Spécification des options de déploiement de partitions et de rôles</span><span class="sxs-lookup"><span data-stu-id="530cc-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="530cc-125">Spécification de paramètres de configuration pour le déploiement de solutions</span><span class="sxs-lookup"><span data-stu-id="530cc-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="530cc-126">Spécification d'options de traitement</span><span class="sxs-lookup"><span data-stu-id="530cc-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="530cc-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="530cc-127">See Also</span></span>  
 <span data-ttu-id="530cc-128">[Exécution de l’Assistant Déploiement de Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="530cc-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="530cc-129">Description du script de déploiement Analysis Services</span><span class="sxs-lookup"><span data-stu-id="530cc-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
