---
title: Déployer un package de déploiement de modèle à l’aide de l’Assistant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705212"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="0efca-102">Déployer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="0efca-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="0efca-103">Utilisez l'Assistant Déploiement de modèle [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour déployer les packages qui contiennent uniquement des objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="0efca-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="0efca-104">Si vous avez besoin de déployer un package avec des données, consultez [Déployer un package de déploiement de modèle à l’aide de MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="0efca-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0efca-105">Les packages peuvent être déployés uniquement dans l'édition de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans laquelle ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="0efca-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="0efca-106">Cela signifie que les packages créés dans [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ne peuvent pas être déployés sur [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0efca-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0efca-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0efca-107">Prerequisites</span></span>  
 <span data-ttu-id="0efca-108">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0efca-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0efca-109">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** dans l'environnement [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] cible.</span><span class="sxs-lookup"><span data-stu-id="0efca-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="0efca-110">Un package de déploiement de modèle doit exister.</span><span class="sxs-lookup"><span data-stu-id="0efca-110">A model deployment package must exist.</span></span> <span data-ttu-id="0efca-111">Pour plus d’informations, consultez [Créer un package de déploiement de modèle à l’aide de l’Assistant](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0efca-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="0efca-112">Vous devez être administrateur dans l'environnement où vous déployez le modèle.</span><span class="sxs-lookup"><span data-stu-id="0efca-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="0efca-113">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0efca-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="0efca-114">Pour déployer un package de déploiement de modèle d'objets de modèle uniquement</span><span class="sxs-lookup"><span data-stu-id="0efca-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="0efca-115">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="0efca-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0efca-116">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Système** , puis cliquez sur **Déploiement**.</span><span class="sxs-lookup"><span data-stu-id="0efca-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="0efca-117">Dans l' **Assistant Déploiement de modèle**, cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="0efca-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="0efca-118">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="0efca-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="0efca-119">Recherchez votre package de déploiement (fichier .pkg), puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="0efca-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="0efca-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0efca-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="0efca-121">Une fois le package chargé, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0efca-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="0efca-122">Si le modèle existe déjà, vous pouvez le mettre à jour en sélectionnant **Mettre à jour le modèle existant**.</span><span class="sxs-lookup"><span data-stu-id="0efca-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="0efca-123">Pour créer un modèle, sélectionnez **Créer un modèle** , cliquez sur **Suivant** , puis tapez un nom pour le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="0efca-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="0efca-124">Cliquez sur **Terminer** pour quitter l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="0efca-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="0efca-125">**Remarques :**</span><span class="sxs-lookup"><span data-stu-id="0efca-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="0efca-126">Si une vue d’abonnement dans le package a le même nom qu’une vue d’abonnement dans un modèle existant, la vue est créée en tant que *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="0efca-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="0efca-127">Si ce nom existe déjà, la vue d'abonnement n'est pas créée.</span><span class="sxs-lookup"><span data-stu-id="0efca-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="0efca-128">Le processus de déploiement comporte quatre étapes :</span><span class="sxs-lookup"><span data-stu-id="0efca-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="0efca-129">Les objets de modèle sont créés.</span><span class="sxs-lookup"><span data-stu-id="0efca-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="0efca-130">Les vues d'abonnement sont créées.</span><span class="sxs-lookup"><span data-stu-id="0efca-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="0efca-131">Les règles d'entreprise sont créées.</span><span class="sxs-lookup"><span data-stu-id="0efca-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="0efca-132">Les données de référence sont remplies.</span><span class="sxs-lookup"><span data-stu-id="0efca-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="0efca-133">Lorsque vous créez un modèle nouveau ou cloné, si le processus échoue au cours d'une étape, le modèle est supprimé.</span><span class="sxs-lookup"><span data-stu-id="0efca-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="0efca-134">Lorsque vous mettez à jour un modèle, si le processus échoue au cours des trois premières étapes, il s'arrête ; toutefois, les modifications qui sont déjà effectuées ne sont pas annulées.</span><span class="sxs-lookup"><span data-stu-id="0efca-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="0efca-135">Si le processus échoue à l'étape 4, les membres qui peuvent être mis à jour sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="0efca-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0efca-136">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0efca-136">Next Steps</span></span>  
 <span data-ttu-id="0efca-137">Les métadonnées définies par l'utilisateur, les attributs de fichier et les autorisations d'accès ne sont pas inclus dans les packages de déploiement de modèle.</span><span class="sxs-lookup"><span data-stu-id="0efca-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="0efca-138">Après avoir déployé un modèle, vous devez les mettre à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="0efca-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="0efca-139">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="0efca-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="0efca-140">Ajouter des métadonnées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0efca-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="0efca-141">Affecter des autorisations d’objet de modèle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0efca-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="0efca-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0efca-142">See Also</span></span>  
 [<span data-ttu-id="0efca-143">Déploiement de modèles &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0efca-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
