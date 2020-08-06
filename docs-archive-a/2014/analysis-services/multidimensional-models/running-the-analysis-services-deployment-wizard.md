---
title: Exécution de l’Assistant Déploiement de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services Deployment Wizard, running
ms.assetid: 3a38d489-4625-4878-bd18-c6f903be33df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6207e3e7981f52ca158f50515166d237e0524ea7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710904"
---
# <a name="running-the-analysis-services-deployment-wizard"></a><span data-ttu-id="885d2-102">Exécution de l'Assistant Déploiement d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="885d2-102">Running the Analysis Services Deployment Wizard</span></span>
  <span data-ttu-id="885d2-103">Lorsque vous utilisez l' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant déploiement pour déployer un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet, vous pouvez exécuter l’Assistant des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="885d2-103">When you use the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard to deploy a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can run the wizard in the following ways:</span></span>  
  
-   <span data-ttu-id="885d2-104">**Interactivement** Lorsque vous exécutez l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de manière interactive, il génère un script de déploiement XML basé sur les fichiers d'entrée, modifié de manière interactive par l'entrée utilisateur.</span><span class="sxs-lookup"><span data-stu-id="885d2-104">**Interactively** When run interactively, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard generates an XML deployment script based on the input files, as modified interactively by user input.</span></span> <span data-ttu-id="885d2-105">L'Assistant applique les modifications utilisateur uniquement au script de déploiement.</span><span class="sxs-lookup"><span data-stu-id="885d2-105">The wizard applies any user modifications only to the deployment script.</span></span> <span data-ttu-id="885d2-106">Il ne modifie pas les fichiers d'entrée.</span><span class="sxs-lookup"><span data-stu-id="885d2-106">The wizard does not modify the input files.</span></span> <span data-ttu-id="885d2-107">Pour plus d’informations sur les fichiers d’entrée, voir [Précisions sur les fichiers d’entrée utilisés pour créer le script de déploiement](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="885d2-107">For more information about the input files, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
-   <span data-ttu-id="885d2-108">**À partir de l’invite de commandes** Lorsqu’il est exécuté à partir de l’invite de commandes, l' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant Déploiement génère un script de déploiement XML for Analysis (XMLA) basé sur les commutateurs que vous utilisez pour exécuter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="885d2-108">**From the command prompt** When run at the command prompt, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard generates an XML for Analysis (XMLA) deployment script based upon the switches that you use to run the wizard.</span></span> <span data-ttu-id="885d2-109">L'Assistant peut effectuer les opérations suivantes : vous demander une entrée utilisateur et modifier les fichiers d'entrée en fonction de cette entrée, exécuter un déploiement automatisé en mode silencieux en utilisant les fichiers d'entrée tels quels, ou créer un script de déploiement que vous pouvez utiliser ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="885d2-109">The wizard may any one of the following: prompt you for user input and modify input files based on that input; run a silent, unattended deployment using the input files as is; or create a deployment script that you can use later.</span></span>  
  
## <a name="running-the-analysis-services-deployment-wizard-interactively"></a><span data-ttu-id="885d2-110">Exécution de l'Assistant Déploiement d'Analysis Services de manière interactive</span><span class="sxs-lookup"><span data-stu-id="885d2-110">Running the Analysis Services Deployment Wizard Interactively</span></span>  
 <span data-ttu-id="885d2-111">Lorsque vous exécutez l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de manière interactive, il lit les valeurs des fichiers d'entrée et affiche ces informations.</span><span class="sxs-lookup"><span data-stu-id="885d2-111">When you run interactively, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the values from the input files and presents this information to you.</span></span> <span data-ttu-id="885d2-112">Vous pouvez modifier ces valeurs d’entrée, telles que la destination de déploiement, les paramètres de configuration, les options de déploiement et les mots de passe de chaîne de connexion, ou les conserver en l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="885d2-112">You can modify these input values-such as deployment destination, configuration settings, deployment options, and connection string passwords-or leave them as is.</span></span> <span data-ttu-id="885d2-113">Si vous changez les valeurs d'entrée, l'Assistant utilise ces modifications lors de la génération du script de déploiement XMLA.</span><span class="sxs-lookup"><span data-stu-id="885d2-113">If you change any input values, the wizard uses these changes when generating the XMLA deployment script.</span></span> <span data-ttu-id="885d2-114">Toutefois, il ne modifie pas les valeurs du fichier d'entrée.</span><span class="sxs-lookup"><span data-stu-id="885d2-114">However, the wizard does not make any changes to the values in the input file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="885d2-115">Pour que l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] modifie les valeurs d'entrée, exécutez-le à partir de l'invite de commandes et configurez-le pour fonctionner en mode de fichier de réponses.</span><span class="sxs-lookup"><span data-stu-id="885d2-115">If you want to have the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard modify the input values, run the wizard at the command prompt and set the wizard to run in answer file mode.</span></span>  
  
 <span data-ttu-id="885d2-116">Après avoir vérifié les valeurs d'entrée et effectué les modifications appropriées, l'Assistant génère le script de déploiement XMLA.</span><span class="sxs-lookup"><span data-stu-id="885d2-116">After you review the input values and make any wanted changes, the wizard generates the XMLA deployment script.</span></span> <span data-ttu-id="885d2-117">Vous pouvez exécuter ce script de déploiement immédiatement sur le serveur de destination ou l'enregistrer en vue d'une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="885d2-117">You can run this deployment script immediately on the destination server or save the script for later use.</span></span>  
  
#### <a name="to-run-the-analysis-services-deployment-wizard-interactively"></a><span data-ttu-id="885d2-118">Pour exécuter l'Assistant Déploiement d'Analysis Services de manière interactive</span><span class="sxs-lookup"><span data-stu-id="885d2-118">To run the Analysis Services Deployment Wizard interactively</span></span>  
  
-   <span data-ttu-id="885d2-119">Dans le menu **Démarrer**, pointez successivement sur **Tous les programmes**, **Microsoft SQL Server**et **Analysis Services**, puis cliquez sur **Assistant Déploiement**.</span><span class="sxs-lookup"><span data-stu-id="885d2-119">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Analysis Services**, and then click **Deployment Wizard**.</span></span>  
  
     <span data-ttu-id="885d2-120">-ou-</span><span class="sxs-lookup"><span data-stu-id="885d2-120">-or-</span></span>  
  
-   <span data-ttu-id="885d2-121">Dans le dossier **projets** du [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet, double-cliquez sur le *\<project name>* fichier. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="885d2-121">In the **Projects** folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, double-click the *\<project name>*.asdatabase file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="885d2-122">Si vous ne trouvez pas le *\<project name>* fichier. asdatabase, essayez d’utiliser la recherche et spécifiez \*. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="885d2-122">If you cannot find the *\<project name>*.asdatabase file, try using Search and specify \*.asdatabase.</span></span>  
  
## <a name="running-the-analysis-services-deployment-wizard-at-the-command-prompt"></a><span data-ttu-id="885d2-123">Exécution de l'Assistant Déploiement d'Analysis Services à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="885d2-123">Running the Analysis Services Deployment Wizard at the Command Prompt</span></span>  
 <span data-ttu-id="885d2-124">Vous pouvez également exécuter l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="885d2-124">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard can also be run at the command prompt.</span></span> <span data-ttu-id="885d2-125">Lorsque vous exécutez l'Assistant à l'invite de commandes, vous fournissez le chemin d'accès complet au fichier .asdatabase et exécutez l'Assistant en l'un des modes suivants :</span><span class="sxs-lookup"><span data-stu-id="885d2-125">When you run the wizard at the command prompt, you provide the full path to the .asdatabase file and  run the wizard in one of the following modes:</span></span>  
  
 <span data-ttu-id="885d2-126">**Mode de fichier de réponses**</span><span class="sxs-lookup"><span data-stu-id="885d2-126">**Answer file mode**</span></span>  
 <span data-ttu-id="885d2-127">Dans ce mode, l’Assistant permet de modifier de manière interactive les fichiers d’entrée générés à l’origine lors de la création du projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="885d2-127">In answer file mode, the wizard lets you interactively modify the input files that were originally generated when the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project was built in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="885d2-128">L'Assistant enregistre les fichiers d'entrée modifiés avant de générer le script de déploiement XMLA.</span><span class="sxs-lookup"><span data-stu-id="885d2-128">The wizard saves these modified input files before generating the XMLA deployment script.</span></span> <span data-ttu-id="885d2-129">Les fichiers d'entrée deviennent le nouveau point de départ de la prochaine exécution de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="885d2-129">The modified input files become the new starting point the next time that the wizard is run.</span></span>  
  
 <span data-ttu-id="885d2-130">Pour exécuter l’Assistant en mode fichier de réponses, utilisez le commutateur **/a** .</span><span class="sxs-lookup"><span data-stu-id="885d2-130">To run the wizard in answer file mode, use the **/a** switch.</span></span>  
  
 <span data-ttu-id="885d2-131">**Mode silencieux**</span><span class="sxs-lookup"><span data-stu-id="885d2-131">**Silent mode**</span></span>  
 <span data-ttu-id="885d2-132">En mode silencieux, l'Assistant exécute un déploiement automatisé en fonction des informations qui se trouvent dans les fichiers d'entrée.</span><span class="sxs-lookup"><span data-stu-id="885d2-132">In silent mode, the wizard runs a silent, unattended deployment based on the information resident in the input files.</span></span>  
  
 <span data-ttu-id="885d2-133">Pour exécuter l’Assistant en mode silencieux, utilisez le commutateur **/s** .</span><span class="sxs-lookup"><span data-stu-id="885d2-133">To run the wizard in silent mode, use the **/s** switch.</span></span> <span data-ttu-id="885d2-134">Lorsque vous exécutez l'Assistant en mode silencieux, les messages sont affichés sur la console ou enregistrés dans un fichier journal (s'il en existe un).</span><span class="sxs-lookup"><span data-stu-id="885d2-134">When you run the wizard in silent mode, messages are output to the console or to a log file if one is provided.</span></span>  
  
 <span data-ttu-id="885d2-135">**Mode de sortie**</span><span class="sxs-lookup"><span data-stu-id="885d2-135">**Output mode**</span></span>  
 <span data-ttu-id="885d2-136">En mode de sortie, l'Assistant génère un script de déploiement XMLA pour l'exécuter plus tard en fonction des fichiers d'entrée.</span><span class="sxs-lookup"><span data-stu-id="885d2-136">In output mode, the wizard generates an XMLA deployment script for later execution based on the input files.</span></span>  
  
 <span data-ttu-id="885d2-137">Pour exécuter l’Assistant en mode de sortie, utilisez le commutateur **/o** et fournissez un nom de fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="885d2-137">To run the wizard in output mode, use the **/o** switch and provide an output file name.</span></span>  
  
 <span data-ttu-id="885d2-138">Pour plus d’informations sur les commutateurs de ligne de commande, voir [Déployer des solutions de modèle avec l’utilitaire de déploiement](deploy-model-solutions-with-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="885d2-138">For more information about these command line switches, see [Deploy Model Solutions with the Deployment Utility](deploy-model-solutions-with-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="885d2-139">La procédure suivante explique comment exécuter l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="885d2-139">The following procedure describes how to run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt.</span></span>  
  
#### <a name="to-run-the-analysis-services-deployment-wizard-at-the-command-prompt"></a><span data-ttu-id="885d2-140">Pour exécuter l'Assistant Déploiement d'Analysis Services à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="885d2-140">To run the Analysis Services Deployment Wizard at the command prompt</span></span>  
  
1.  <span data-ttu-id="885d2-141">Ouvrez une invite de commandes et accédez au dossier C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="885d2-141">Open a command prompt and navigate to the C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE folder.</span></span>  
  
2.  <span data-ttu-id="885d2-142">Tapez **Microsoft.AnalysisServices.Deployment.exe** , suivi des commutateurs qui correspondent au mode dans lequel vous souhaitez exécuter l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="885d2-142">Type **Microsoft.AnalysisServices.Deployment.exe** followed by the switches that correspond to the mode in which you want to run the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885d2-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="885d2-143">See Also</span></span>  
 <span data-ttu-id="885d2-144">[Compréhension du script de déploiement Analysis Services](understanding-the-analysis-services-deployment-script.md) </span><span class="sxs-lookup"><span data-stu-id="885d2-144">[Understanding the Analysis Services Deployment Script](understanding-the-analysis-services-deployment-script.md) </span></span>  
 [<span data-ttu-id="885d2-145">Deploy Model Solutions Using the Deployment Wizard</span><span class="sxs-lookup"><span data-stu-id="885d2-145">Deploy Model Solutions Using the Deployment Wizard</span></span>](deploy-model-solutions-using-the-deployment-wizard.md)  
  
  