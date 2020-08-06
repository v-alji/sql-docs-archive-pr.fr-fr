---
title: Spécification des options de traitement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696243"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="43d68-102">Spécification d'options de traitement</span><span class="sxs-lookup"><span data-stu-id="43d68-102">Specifying Processing Options</span></span>
  <span data-ttu-id="43d68-103">L' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant Déploiement de lit les options de traitement à partir du \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="43d68-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="43d68-104">crée ce fichier lorsque vous générez le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="43d68-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="43d68-105">utilise les options de traitement spécifiées dans la page **déploiement** de la *\<project name>* boîte de dialogue pages de **Propriétés** de pour créer le \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="43d68-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="43d68-106">Examen des options de traitement pour le déploiement</span><span class="sxs-lookup"><span data-stu-id="43d68-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="43d68-107">Les paramètres de configuration stockés dans le \<*project name*> fichier. deploymentoptions sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="43d68-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="43d68-108">**Méthode de traitement** Ce paramètre contrôle si les objets déployés sont traités après le déploiement et le type de traitement à effectuer.</span><span class="sxs-lookup"><span data-stu-id="43d68-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="43d68-109">Trois options de traitement sont possibles :</span><span class="sxs-lookup"><span data-stu-id="43d68-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="43d68-110">Traitement par défaut (option par défaut)</span><span class="sxs-lookup"><span data-stu-id="43d68-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="43d68-111">Traitement complet</span><span class="sxs-lookup"><span data-stu-id="43d68-111">Full processing</span></span>  
  
    -   <span data-ttu-id="43d68-112">None</span><span class="sxs-lookup"><span data-stu-id="43d68-112">None</span></span>  
  
-   <span data-ttu-id="43d68-113">**Options de table d'écriture différée** Si l'écriture différée est activée dans le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , ce paramètre définit les modalités de l'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="43d68-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="43d68-114">Trois options de table d'écriture différée sont possibles :</span><span class="sxs-lookup"><span data-stu-id="43d68-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="43d68-115">Par défaut, s'il existe une table d'écriture différée, elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="43d68-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="43d68-116">S'il n'existe pas de table d'écriture différée, une nouvelle table d'écriture différée est créée.</span><span class="sxs-lookup"><span data-stu-id="43d68-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="43d68-117">S'il existe déjà une table d'écriture différée, le déploiement échoue.</span><span class="sxs-lookup"><span data-stu-id="43d68-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="43d68-118">S'il n'existe pas de table d'écriture différée, une nouvelle table d'écriture différée est créée.</span><span class="sxs-lookup"><span data-stu-id="43d68-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="43d68-119">Une nouvelle table d'écriture différée est créée dans tous les cas, même s'il en existe déjà une.</span><span class="sxs-lookup"><span data-stu-id="43d68-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="43d68-120">Avec cette option, l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supprime toute table existante et la remplace par une nouvelle table d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="43d68-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="43d68-121">**Déploiement transactionnel** Ce paramètre contrôle si le déploiement de modifications de métadonnées et de commandes de processus s'effectue en une seule transaction ou en transactions distinctes.</span><span class="sxs-lookup"><span data-stu-id="43d68-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="43d68-122">Si cette option a la valeur `True` (valeur par défaut), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] déploie toutes les modifications de métadonnées et toutes les commandes de processus en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="43d68-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="43d68-123">Si cette option a la valeur `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] déploie les modifications de métadonnées en une seule transaction et déploie chaque commande de processus dans sa propre transaction.</span><span class="sxs-lookup"><span data-stu-id="43d68-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="43d68-124">Modification des options de traitement pour le déploiement</span><span class="sxs-lookup"><span data-stu-id="43d68-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="43d68-125">Toutefois, vous devrez peut-être déployer le [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet en utilisant des options de traitement différentes de celles stockées dans le \<*project name*> fichier. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="43d68-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="43d68-126">Par exemple, vous pouvez souhaiter que tous les objets soient traités entièrement ou traités en utilisant l'option de traitement par défaut, ou encore qu'aucun traitement n'ait lieu.</span><span class="sxs-lookup"><span data-stu-id="43d68-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="43d68-127">Si les cubes ou les dimensions sont activés en écriture, vous pouvez spécifier si une nouvelle table d'écriture différée ou une table existante doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="43d68-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="43d68-128">Pour modifier les options de traitement utilisées durant le déploiement, vous pouvez soit modifier et régénérer le projet, soit modifier les options de traitement dans le fichier d'entrée en utilisant l'une des méthodes décrites dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="43d68-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="43d68-129">Pour modifier des options de traitement après la génération des fichiers d'entrée</span><span class="sxs-lookup"><span data-stu-id="43d68-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="43d68-130">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode interactif.</span><span class="sxs-lookup"><span data-stu-id="43d68-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="43d68-131">Sur la page **Options de traitement** , spécifiez les options de traitement du projet à déployer.</span><span class="sxs-lookup"><span data-stu-id="43d68-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="43d68-132">-ou-</span><span class="sxs-lookup"><span data-stu-id="43d68-132">-or-</span></span>  
  
-   <span data-ttu-id="43d68-133">Exécutez l'Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'invite de commandes en mode fichier de réponses.</span><span class="sxs-lookup"><span data-stu-id="43d68-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="43d68-134">Pour plus d'informations sur le mode fichier de réponses, consultez [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="43d68-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="43d68-135">-ou-</span><span class="sxs-lookup"><span data-stu-id="43d68-135">-or-</span></span>  
  
-   <span data-ttu-id="43d68-136">Modifiez le \<*project name*> fichier. deploymentoptions à l’aide de n’importe quel éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="43d68-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d68-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43d68-137">See Also</span></span>  
 <span data-ttu-id="43d68-138">[Spécification de la cible d’installation](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="43d68-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="43d68-139">[Spécification des options de déploiement de partitions et de rôles](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="43d68-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="43d68-140">Spécification de paramètres de configuration pour le déploiement de solutions</span><span class="sxs-lookup"><span data-stu-id="43d68-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
