---
title: Modifier un package de déploiement de modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615169"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="8b87a-102">Modifier un package de déploiement de modèle</span><span class="sxs-lookup"><span data-stu-id="8b87a-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="8b87a-103">Cette rubrique explique comment déployer les pièces sélectionnées d'un modèle dans MDS, plutôt qu'un modèle entier.</span><span class="sxs-lookup"><span data-stu-id="8b87a-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="8b87a-104">Pour ce faire, vous modifiez un package de modèle MDS à l'aide de l'Éditeur de package de modèle.</span><span class="sxs-lookup"><span data-stu-id="8b87a-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="8b87a-105">L'assistant Éditeur de package de modèle vous permet de sélectionner les entités spécifiques, hiérarchies dérivées, vues d'abonnement et règles d'entreprise d'un modèle que vous souhaitez inclure dans un package MDS, puis déployer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="8b87a-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="8b87a-106">Vous pouvez ignorer les parties du modèle que vous ne souhaitez pas déployer.</span><span class="sxs-lookup"><span data-stu-id="8b87a-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="8b87a-107">Lorsque vous sélectionnez une entité, tous les objets dépendants de cette entité sont également automatiquement sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8b87a-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="8b87a-108">Vous utilisez l'Éditeur de package de modèle pour sélectionner des parties d'un modèle dans un fichier de package créé par l'outil MDSModelDeploy (qui crée un fichier de package incluant des objets et données) ou l'assistant Déploiement de modèle (qui crée un fichier comprenant uniquement la structure de modèle).</span><span class="sxs-lookup"><span data-stu-id="8b87a-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="8b87a-109">Après modification du modèle dans le package, vous utilisez l'outil MDSModelDeploy pour déployer les objets et données, ou l'assistant Déploiement de modèle pour déployer uniquement la structure du modèle.</span><span class="sxs-lookup"><span data-stu-id="8b87a-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b87a-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="8b87a-110">Prerequisites</span></span>  
 <span data-ttu-id="8b87a-111">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="8b87a-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8b87a-112">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="8b87a-112">You must be a model administrator.</span></span> <span data-ttu-id="8b87a-113">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8b87a-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8b87a-114">Pour que vous puissiez le modifier, un package de modèle doit exister.</span><span class="sxs-lookup"><span data-stu-id="8b87a-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="8b87a-115">Pour plus d’informations, consultez [Déploiement de modèles &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) et [Créer un package de déploiement de modèle à l’aide de l’Assistant](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) ou [Créer un package de déploiement de modèle à l’aide de MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="8b87a-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="8b87a-116">Pour modifier un package de déploiement de modèle</span><span class="sxs-lookup"><span data-stu-id="8b87a-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="8b87a-117">Dans l'Explorateur Windows sur le serveur MDS, accédez à *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="8b87a-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="8b87a-118">Exécutez ModelPackageEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="8b87a-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="8b87a-119">Dans l'assistant Éditeur de package de modèle, cliquez sur **Parcourir**, accédez au dossier contenant vos packages, sélectionnez un package, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="8b87a-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="8b87a-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8b87a-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="8b87a-121">Sélectionnez les entités, hiérarchies dérivées, vues d'abonnements ou règles d'entreprise à déployer.</span><span class="sxs-lookup"><span data-stu-id="8b87a-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="8b87a-122">Désélectionnez celles que vous ne souhaitez pas déployer.</span><span class="sxs-lookup"><span data-stu-id="8b87a-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="8b87a-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8b87a-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="8b87a-124">Vérifiez la liste des sélections à déployer.</span><span class="sxs-lookup"><span data-stu-id="8b87a-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="8b87a-125">Pour effectuer une modification, cliquez sur **Précédent** et répétez l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="8b87a-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="8b87a-126">Cliquez sur **Parcourir**, accédez au dossier dans lequel vous souhaitez enregistrer le package partiel, puis entrez le nom de fichier du package partiel (avec l’extension .pkg).</span><span class="sxs-lookup"><span data-stu-id="8b87a-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="8b87a-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8b87a-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="8b87a-128">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8b87a-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8b87a-129">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="8b87a-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="8b87a-130">Déployer un package de déploiement de modèle à l'aide de l'Assistant</span><span class="sxs-lookup"><span data-stu-id="8b87a-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="8b87a-131">Déployer un package de déploiement de modèle à l'aide de MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="8b87a-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
