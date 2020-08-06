---
title: Créer un package de déploiement de modèle à l’aide de l’Assistant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614144"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="65c0f-102">Créer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="65c0f-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="65c0f-103">Utilisez l'Assistant Déploiement de modèle de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour créer un package d'objets de modèle uniquement.</span><span class="sxs-lookup"><span data-stu-id="65c0f-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="65c0f-104">Si vous avez besoin d’inclure des données dans un package, consultez [Créer un package de déploiement de modèle à l’aide de MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="65c0f-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="65c0f-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="65c0f-105">Prerequisites</span></span>  
 <span data-ttu-id="65c0f-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="65c0f-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="65c0f-107">Dans l’application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="65c0f-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="65c0f-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="65c0f-108">You must be a model administrator.</span></span> <span data-ttu-id="65c0f-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="65c0f-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="65c0f-110">Un modèle doit exister pour que vous puissiez créer un package.</span><span class="sxs-lookup"><span data-stu-id="65c0f-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="65c0f-111">Pour plus d’informations, consultez [Créer un modèle &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="65c0f-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="65c0f-112">Pour créer un package de déploiement de modèle</span><span class="sxs-lookup"><span data-stu-id="65c0f-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="65c0f-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="65c0f-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="65c0f-114">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Système** , puis cliquez sur **Déploiement**.</span><span class="sxs-lookup"><span data-stu-id="65c0f-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="65c0f-115">Dans **l’Assistant Déploiement de modèle**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="65c0f-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="65c0f-116">Dans la page **Créer un package** , sélectionnez un modèle dans la liste **Modèle** .</span><span class="sxs-lookup"><span data-stu-id="65c0f-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="65c0f-117">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="65c0f-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="65c0f-118">Cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="65c0f-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="65c0f-119">Enregistrez le fichier .</span><span class="sxs-lookup"><span data-stu-id="65c0f-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="65c0f-120">Cliquez sur **Fermer** pour fermer l’assistant.</span><span class="sxs-lookup"><span data-stu-id="65c0f-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="65c0f-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="65c0f-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="65c0f-122">Déployer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="65c0f-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="65c0f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65c0f-123">See Also</span></span>  
 [<span data-ttu-id="65c0f-124">Déploiement de modèles &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="65c0f-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
