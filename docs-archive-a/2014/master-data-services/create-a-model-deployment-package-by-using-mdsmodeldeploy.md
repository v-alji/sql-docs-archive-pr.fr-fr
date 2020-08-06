---
title: Créer un package de déploiement de modèle à l’aide de MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614706"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="fdfe6-102">Créer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="fdfe6-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="fdfe6-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], utilisez l’outil MDSModelDeploy pour créer un package.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="fdfe6-104">Selon les commandes spécifiées, le package peut contenir :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="fdfe6-105">Des objets de modèle uniquement.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="fdfe6-106">Des objets de modèle et des données.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="fdfe6-107">Si vous souhaitez déployer un package qui contient uniquement des objets de modèle, vous pouvez utiliser l'Assistant Déploiement de modèle dans l'application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] à la place.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="fdfe6-108">Pour plus d’informations, consultez [Créer un package de déploiement de modèle à l’aide de l’Assistant](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe6-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="fdfe6-109">Cette version de l’outil MDSModelDeploy ne peut pas utiliser plus de gigaoctets (Go) de mémoire.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="fdfe6-110">Lorsque vous créez ou déployez des modèles volumineux à l’aide d' **objets de modèle et** de l’option de données, vous pouvez constater des erreurs de type « mémoire insuffisante » ou « flux trop long ».</span><span class="sxs-lookup"><span data-stu-id="fdfe6-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="fdfe6-111">Pour résoudre ce problème, utilisez la mise en lots de MDS pour déployer les données. ou effectuez une mise à niveau vers MDS 2016 ou une version ultérieure, qui comprend la version mise à jour de l’outil MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="fdfe6-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fdfe6-112">Prerequisites</span></span>  
 <span data-ttu-id="fdfe6-113">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="fdfe6-114">Les autorisations de base nécessaires pour exécuter l'outil MDSModelDeploy sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="fdfe6-115">La même autorisation Windows que le gestionnaire de configuration MDS (administrateur Windows)</span><span class="sxs-lookup"><span data-stu-id="fdfe6-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="fdfe6-116">Autorisation DBA sur la base de données MDS.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="fdfe6-117">Les autorisations nécessaires pour créer le package à l'aide de l'outil MDSModelDeploy sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="fdfe6-118">Autorisation d'administrateur de modèle MDS sur le modèle de données.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="fdfe6-119">Autorisation de fonction Gestion de l'intégration MDS.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="fdfe6-120">Les autorisations nécessaires pour déployer le package à l'aide de l'outil MDSModelDeploy sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="fdfe6-121">Autorisation de fonction Explorateur MDS</span><span class="sxs-lookup"><span data-stu-id="fdfe6-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="fdfe6-122">Autorisation de fonction Gestion de l'intégration MDS</span><span class="sxs-lookup"><span data-stu-id="fdfe6-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="fdfe6-123">Autorisation de fonction Administration de système MDS.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="fdfe6-124">Les autorisations nécessaires pour répertorier les modèles à l'aide de l'outil MDSModelDeploy sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="fdfe6-125">Autorisation de fonction Explorateur MDS</span><span class="sxs-lookup"><span data-stu-id="fdfe6-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="fdfe6-126">Autorisation d'administrateur de modèle MDS sur le modèle de données pour voir le modèle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="fdfe6-127">Un modèle doit exister pour que vous puissiez créer un package.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="fdfe6-128">Pour plus d’informations, consultez [Créer un modèle &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe6-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="fdfe6-129">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe6-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="fdfe6-130">Pour créer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="fdfe6-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="fdfe6-131">Ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="fdfe6-132">Accédez à l'emplacement de MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="fdfe6-133">Si MDS a été installé à l’emplacement par défaut, le fichier se trouve dans *lecteur*: \Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="fdfe6-134">Si MDS n'a pas été installé dans l'emplacement par défaut, recherchez MDSModelDeploy.exe sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="fdfe6-135">facultatif.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-135">Optional.</span></span> <span data-ttu-id="fdfe6-136">Consultez les options et l'aide.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="fdfe6-137">Pour afficher toutes les options disponibles, tapez `MDSModelDeploy` et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="fdfe6-138">Pour afficher l’aide pour une option, tapez la commande suivante, où *OptionName* est le nom de l’option : `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="fdfe6-139">facultatif.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-139">Optional.</span></span> <span data-ttu-id="fdfe6-140">Si vous possédez plusieurs applications Web, déterminez le nom du service que vous allez déployer en entrant cette commande et en appuyant sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="fdfe6-141">Une liste de valeurs est retournée, par exemple `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="fdfe6-142">La première valeur de cette liste (dans ce cas, `MDS1`) est nécessaire pour déployer le modèle.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="fdfe6-143">Pour créer un package qui contient des objets de modèle et des données, tapez la commande suivante, où *ModelName*, *VersionName*, *ServiceName*et *PackageName* sont respectivement les noms du modèle, la version, le service et le fichier de sortie .pkg :</span><span class="sxs-lookup"><span data-stu-id="fdfe6-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="fdfe6-144">Si vous ne souhaitez pas inclure de données, n’utilisez pas les commutateurs `-version` et `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="fdfe6-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="fdfe6-145">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-145">Press Enter.</span></span> <span data-ttu-id="fdfe6-146">Quand le package est créé, un message indiquant que l’opération de MDSModelDeploy est terminée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fdfe6-147">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fdfe6-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="fdfe6-148">Déployer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="fdfe6-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="fdfe6-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdfe6-149">See Also</span></span>  
 <span data-ttu-id="fdfe6-150">[Options de déploiement de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fdfe6-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="fdfe6-151">Déploiement de modèles &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fdfe6-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
