---
title: Déployer un package de déploiement de modèle à l’aide de MDSModelDeploy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611836"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="d5fa8-102">Déployer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="d5fa8-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="d5fa8-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], utilisez l'outil MDSModelDeploy pour déployer un package qui contient soit :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="d5fa8-104">Des objets de modèle uniquement.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="d5fa8-105">Des objets de modèle et des données.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="d5fa8-106">Si vous souhaitez déployer un package qui contient uniquement des objets de modèle, vous pouvez utiliser l'Assistant Déploiement de modèle dans l'application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] à la place.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="d5fa8-107">Pour plus d’informations, consultez [Déployer un package de déploiement de modèle à l’aide de l’Assistant](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d5fa8-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5fa8-108">Les packages peuvent être déployés uniquement dans l'édition de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans laquelle ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="d5fa8-109">Cela signifie que les packages créés dans [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ne peuvent pas être déployés sur [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] ou les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5fa8-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d5fa8-110">Prerequisites</span></span>  
 <span data-ttu-id="d5fa8-111">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d5fa8-112">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** dans l'environnement [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] cible.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="d5fa8-113">Un package de déploiement de modèle doit exister.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-113">A model deployment package must exist.</span></span> <span data-ttu-id="d5fa8-114">Pour plus d’informations, consultez  [Créer un package de déploiement de modèle à l'aide de MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="d5fa8-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="d5fa8-115">Vous devez être administrateur dans l'environnement où vous déployez le modèle.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="d5fa8-116">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5fa8-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d5fa8-117">Si vous mettez à jour un modèle avec des données, la version que vous déployez ne peut pas avoir l’état **Verrouillé** ou **Activé**.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="d5fa8-118">Pour déployer un package de déploiement de modèle</span><span class="sxs-lookup"><span data-stu-id="d5fa8-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="d5fa8-119">Déterminez si vous déployez un nouveau modèle, un clone d'un modèle, ou si vous mettez à jour un modèle préalablement cloné.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="d5fa8-120">Pour plus d’informations, consultez [Options de déploiement de modèle &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5fa8-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="d5fa8-121">Ouvrez une invite de commandes et accédez à MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="d5fa8-122">Si MDS est installé à l’emplacement par défaut, l’outil est disponible dans *lecteur*: \Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span><span class="sxs-lookup"><span data-stu-id="d5fa8-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="d5fa8-123">Si MDS n'est pas installé dans l'emplacement par défaut, recherchez MDSModelDeploy.exe sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="d5fa8-124">facultatif.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-124">Optional.</span></span> <span data-ttu-id="d5fa8-125">Consultez les options et l'aide.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="d5fa8-126">Pour afficher toutes les options disponibles, tapez `MDSModelDeploy` et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="d5fa8-127">Pour afficher l’aide pour une option, tapez la commande suivante, où *OptionName* est le nom de l’option : `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="d5fa8-128">facultatif.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-128">Optional.</span></span> <span data-ttu-id="d5fa8-129">Si vous possédez plusieurs applications Web, déterminez le nom du service que vous allez déployer en entrant cette commande et en appuyant sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="d5fa8-130">Une liste de valeurs est retournée, par exemple `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="d5fa8-131">La première valeur de cette liste (dans ce cas, `MDS1`) est nécessaire pour déployer le modèle.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="d5fa8-132">Selon que vous créez un modèle, clonez modèle ou mettez à jour un modèle, à l'invite de commandes, tapez la commande suivante et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="d5fa8-133">Pour créer un modèle :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="d5fa8-134">Pour créer un clone d'un modèle :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="d5fa8-135">Pour mettre à jour un de modèle existant et ses données :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d5fa8-136">Si vous utilisez l'outil MDSModelDeploy pour mettre à jour un modèle existant et ses données et que le package ne contient pas une entité, un attribut ou un membre existant dans le modèle de destination, MDSModelDeploy ne supprime pas cette entité, cet attribut ou ce membre du modèle.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="d5fa8-137">Où *PackageName* est le nom du fichier de package (.pkg), *ModelName* est le nom du nouveau modèle, *VersionName* est le nom de la version et *ServiceName* est le nom du service que vous avez retourné à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="d5fa8-138">Vérifiez que les noms de modèle et de version correspondent aux noms en respectant la casse.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="d5fa8-139">Quand le package est déployé, un message indiquant que l’opération de MDSModelDeploy est terminée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="d5fa8-140">**Remarques :**</span><span class="sxs-lookup"><span data-stu-id="d5fa8-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="d5fa8-141">Si une vue d’abonnement dans le package a le même nom qu’une vue d’abonnement dans un modèle existant, la vue est créée en tant que *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="d5fa8-142">Si ce nom existe déjà, la vue d'abonnement n'est pas créée.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="d5fa8-143">Le processus de déploiement comporte quatre étapes :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="d5fa8-144">Les objets de modèle sont créés.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="d5fa8-145">Les règles d'entreprise sont créées.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="d5fa8-146">Les vues d'abonnement sont créées.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="d5fa8-147">Les données de référence sont remplies.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="d5fa8-148">Lorsque vous créez un modèle nouveau ou cloné, si le processus échoue au cours d'une étape, le modèle est supprimé.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="d5fa8-149">Lorsque vous mettez à jour un modèle, si le processus échoue au cours des trois premières étapes, il s'arrête ; toutefois, les modifications qui sont déjà effectuées ne sont pas annulées.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="d5fa8-150">Si le processus échoue à l'étape 4, les membres qui peuvent être mis à jour sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5fa8-151">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d5fa8-151">Next Steps</span></span>  
 <span data-ttu-id="d5fa8-152">Les métadonnées définies par l'utilisateur, les attributs de fichier et les autorisations d'accès ne sont pas inclus dans les packages de déploiement de modèle.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="d5fa8-153">Après avoir déployé un modèle, vous devez les mettre à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="d5fa8-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="d5fa8-154">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5fa8-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d5fa8-155">Ajouter des métadonnées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5fa8-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="d5fa8-156">Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5fa8-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5fa8-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5fa8-157">See Also</span></span>  
 [<span data-ttu-id="d5fa8-158">Déploiement de modèles &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5fa8-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
