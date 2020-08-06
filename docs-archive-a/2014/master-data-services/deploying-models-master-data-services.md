---
title: Déploiement de modèles (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615186"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="8805c-102">Déploiement de modèles (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8805c-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="8805c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], un package est un fichier XML qui contient une structure de modèle déployable et, éventuellement, les données du modèle.</span><span class="sxs-lookup"><span data-stu-id="8805c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="8805c-104">Utilisez les packages de modèle pour déplacer des copies de modèles d'un environnement MDS vers un autre, ou pour créer de nouveaux modèles dans votre environnement MDS existant.</span><span class="sxs-lookup"><span data-stu-id="8805c-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8805c-105">Les packages peuvent être déployés uniquement dans l'édition de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans laquelle ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="8805c-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="8805c-106">Cela signifie que les packages créés dans [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ne peuvent pas être déployés sur [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="8805c-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="8805c-107">Outils pour déployer des modèles</span><span class="sxs-lookup"><span data-stu-id="8805c-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="8805c-108">Pour utiliser les packages de modèles, vous pouvez opter pour l'un des trois outils, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8805c-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="8805c-109">**Outil MDSModelDeploy**: pour créer et déployer des objets de modèle et des données, utilisez l'outil MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="8805c-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="8805c-110">Si vous avez sélectionné le chemin d’accès par défaut lors de l’installation de MDS, cet outil se trouve sur *lecteur*: \Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="8805c-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="8805c-111">**Assistant Déploiement de modèle**: pour créer et déployer des packages de la structure de modèle uniquement, utilisez l'Assistant dans l'application Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8805c-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="8805c-112">Vous ne pouvez pas utiliser cet Assistant pour déployer des données.</span><span class="sxs-lookup"><span data-stu-id="8805c-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="8805c-113">**Éditeur de package de modèle**: pour modifier un package de modèle, utilisez l'outil ModelPackageEditor.exe qui lance l'Assistant Éditeur de package de modèle.</span><span class="sxs-lookup"><span data-stu-id="8805c-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="8805c-114">Vous utilisez cet Assistant pour modifier un package créé par l'outil MDSModelDeploy ou l'Assistant Déploiement de modèle.</span><span class="sxs-lookup"><span data-stu-id="8805c-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="8805c-115">Si vous avez sélectionné le chemin d’accès par défaut lors de l’installation de MDS, cet outil se trouve sur *lecteur*: \Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="8805c-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8805c-116">Vous pouvez utiliser MDSDeployModel pour créer un modèle, créer un clone d'un modèle ou mettre à jour un modèle existant et ses données.</span><span class="sxs-lookup"><span data-stu-id="8805c-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="8805c-117">Si vous utilisez l'outil MDSModelDeploy pour mettre à jour un modèle existant et ses données et que le package ne contient pas une entité, un attribut ou un membre existant dans le modèle de destination, MDSModelDeploy ne supprime pas cette entité, cet attribut ou ce membre du modèle.</span><span class="sxs-lookup"><span data-stu-id="8805c-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="8805c-118">Contenu des packages</span><span class="sxs-lookup"><span data-stu-id="8805c-118">What Packages Contain</span></span>  
 <span data-ttu-id="8805c-119">Un package de modèle est un fichier XML enregistré avec l'extension .pkg.</span><span class="sxs-lookup"><span data-stu-id="8805c-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="8805c-120">Lorsque vous créez un package de déploiement, vous pouvez décider s'il convient d'inclure ou non des données.</span><span class="sxs-lookup"><span data-stu-id="8805c-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="8805c-121">Si vous décidez d'inclure des données, vous devez sélectionner une version des données à inclure.</span><span class="sxs-lookup"><span data-stu-id="8805c-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="8805c-122">Tous les objets de modèle sont inclus dans un package.</span><span class="sxs-lookup"><span data-stu-id="8805c-122">All model objects are included in a package.</span></span> <span data-ttu-id="8805c-123">Ces objets sont :</span><span class="sxs-lookup"><span data-stu-id="8805c-123">These objects are:</span></span>  
  
-   <span data-ttu-id="8805c-124">Entités</span><span class="sxs-lookup"><span data-stu-id="8805c-124">Entities</span></span>  
  
-   <span data-ttu-id="8805c-125">Attributs</span><span class="sxs-lookup"><span data-stu-id="8805c-125">Attributes</span></span>  
  
-   <span data-ttu-id="8805c-126">Groupes d’attributs</span><span class="sxs-lookup"><span data-stu-id="8805c-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="8805c-127">Hierarchies</span><span class="sxs-lookup"><span data-stu-id="8805c-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="8805c-128">Collections</span><span class="sxs-lookup"><span data-stu-id="8805c-128">Collections</span></span>  
  
-   <span data-ttu-id="8805c-129">Règles d'entreprise</span><span class="sxs-lookup"><span data-stu-id="8805c-129">Business rules</span></span>  
  
-   <span data-ttu-id="8805c-130">Indicateurs de version</span><span class="sxs-lookup"><span data-stu-id="8805c-130">Version flags</span></span>  
  
-   <span data-ttu-id="8805c-131">Vues d'abonnement</span><span class="sxs-lookup"><span data-stu-id="8805c-131">Subscription views</span></span>  
  
 <span data-ttu-id="8805c-132">Les métadonnées définies par l'utilisateur, les attributs de fichier et les autorisations d'accès ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="8805c-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="8805c-133">Après avoir déployé un modèle, vous devez les mettre à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="8805c-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="8805c-134">Exemples de packages</span><span class="sxs-lookup"><span data-stu-id="8805c-134">Sample Packages</span></span>  
 <span data-ttu-id="8805c-135">Des fichiers d'exemple de package sont inclus lorsque vous installez [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8805c-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="8805c-136">Ils se trouvent dans le répertoire Master Data Services\Samples\Packages où vous avez installé [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8805c-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="8805c-137">Lorsque vous déployez ces exemples de packages à l'aide de l'outil MDSModelDeploy, les exemples de modèles sont créés et remplis avec les données.</span><span class="sxs-lookup"><span data-stu-id="8805c-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8805c-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8805c-138">Related Tasks</span></span>  
  
|<span data-ttu-id="8805c-139">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="8805c-139">Task Description</span></span>|<span data-ttu-id="8805c-140">Rubrique</span><span class="sxs-lookup"><span data-stu-id="8805c-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8805c-141">Créez un nouveau package de déploiement d'objets de modèle et/ou de données à l'aide de l'outil MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="8805c-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="8805c-142">Créer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8805c-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="8805c-143">Créez un nouveau package de déploiement d'objets de modèle uniquement à l'aide de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="8805c-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="8805c-144">Créer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="8805c-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="8805c-145">Déployez un package d'objets de modèle et des données à l'aide de l'outil MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="8805c-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="8805c-146">Déployer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8805c-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="8805c-147">Déployez un package d'objets de modèle uniquement à l'aide de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="8805c-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="8805c-148">Déployer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="8805c-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="8805c-149">Modifiez un package de déploiement de modèle pour déployer les parties sélectionnées d'un modèle, plutôt que le modèle entier.</span><span class="sxs-lookup"><span data-stu-id="8805c-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="8805c-150">Modifier un package de déploiement de modèle</span><span class="sxs-lookup"><span data-stu-id="8805c-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="8805c-151">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="8805c-151">Related Content</span></span>  
  
-   [<span data-ttu-id="8805c-152">Options de déploiement de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8805c-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
