---
title: Redéploiement des packages | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- redeploying packages [Integration Services]
- deploying packages [Integration Services], redeploying
ms.assetid: 86806efb-8cf4-4f9d-9824-1152cb4c495c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c5286d406d96f62fc74eb619f7e7a6064fde2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696951"
---
# <a name="redeployment-of-packages"></a><span data-ttu-id="f3147-102">Redéploiement de packages</span><span class="sxs-lookup"><span data-stu-id="f3147-102">Redeployment of Packages</span></span>
  <span data-ttu-id="f3147-103">Après qu'un projet a été déployé, vous pouvez avoir besoin de mettre à jour ou d'étendre les fonctionnalités du package, puis de redéployer le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient les packages mis à jour.</span><span class="sxs-lookup"><span data-stu-id="f3147-103">After a project is deployed, you may need to update or extend package functionality and then redeploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the updated packages.</span></span> <span data-ttu-id="f3147-104">Au cours du processus de redéploiement des packages, vous devez vérifier les propriétés de configuration incluses dans l'utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f3147-104">As part of the process of redeploying packages, you should review the configuration properties that are included in the deployment utility.</span></span> <span data-ttu-id="f3147-105">Par exemple, vous pouvez décider de ne pas autoriser les modifications de configuration après le redéploiement du package.</span><span class="sxs-lookup"><span data-stu-id="f3147-105">For example, you may not want to allow configuration changes after the package is redeployed.</span></span>  
  
## <a name="process-for-redeployment"></a><span data-ttu-id="f3147-106">Processus de redéploiement</span><span class="sxs-lookup"><span data-stu-id="f3147-106">Process for Redeployment</span></span>  
 <span data-ttu-id="f3147-107">Après avoir mis à jour les packages, vous recréez le projet, vous copiez le dossier de déploiement sur l'ordinateur cible et vous réexécutez l'Assistant Installation de package.</span><span class="sxs-lookup"><span data-stu-id="f3147-107">After you finish updating the packages, you rebuild the project, copy the deployment folder to the target computer, and then rerun the Package Installation Wizard.</span></span>  
  
 <span data-ttu-id="f3147-108">Si vous ne mettez à jour que quelques packages dans le projet, vous ne souhaitez pas forcément redéployer le projet tout entier.</span><span class="sxs-lookup"><span data-stu-id="f3147-108">If you update only a few packages in the project, you may not want to redeploy the entire project.</span></span> <span data-ttu-id="f3147-109">Pour ne déployer que quelques packages, vous pouvez créer un nouveau projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , ajouter les packages mis à jour au nouveau projet, puis créer et déployer le projet.</span><span class="sxs-lookup"><span data-stu-id="f3147-109">To deploy only a few packages, you can create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add the updated packages to the new project, and then build and deploy the project.</span></span> <span data-ttu-id="f3147-110">Les configurations de package sont automatiquement copiées avec le package lorsque vous l'ajoutez à un autre projet.</span><span class="sxs-lookup"><span data-stu-id="f3147-110">Package configurations are automatically copied with the package when you add the package to a different project.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f3147-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f3147-111">Related Tasks</span></span>  
 [<span data-ttu-id="f3147-112">Déployer des packages à l’aide de l’utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="f3147-112">Deploy Packages by Using the Deployment Utility</span></span>](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)  
  
  
