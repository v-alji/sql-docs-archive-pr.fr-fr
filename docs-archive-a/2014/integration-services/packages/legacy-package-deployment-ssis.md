---
title: Déploiement de packages (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, deploying
- deploying packages [Integration Services]
- SQL Server Integration Services packages, deploying
- deploying packages [Integration Services], about deploying packages
- packages [Integration Services], deploying
- SSIS packages, deploying
ms.assetid: 0f5fc7be-e37e-4ecd-ba99-697c8ae3436f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 32627eddf5e7a696decd549e9b87ebb5c3b9d031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611152"
---
# <a name="package-deployment-ssis"></a><span data-ttu-id="ed249-102">Déploiement de packages (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ed249-102">Package Deployment (SSIS)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ed249-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] comprend des outils et des assistants qui facilitent le déploiement de packages de l’ordinateur de développement au serveur de production ou à d’autres ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="ed249-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes tools and wizards that make it simple to deploy packages from the development computer to the production server or to other computers.</span></span>  
  
 <span data-ttu-id="ed249-104">Ce processus de déploiement de package se déroule en quatre étapes :</span><span class="sxs-lookup"><span data-stu-id="ed249-104">There are four steps in the package deployment process:</span></span>  
  
1.  <span data-ttu-id="ed249-105">La première étape est facultative et implique la création de configurations de package qui mettent à jour les propriétés des éléments de package au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="ed249-105">The first optional step is optional and involves creating package configurations that update properties of package elements at run time.</span></span> <span data-ttu-id="ed249-106">Les configurations sont automatiquement incluses lorsque vous déployez les packages.</span><span class="sxs-lookup"><span data-stu-id="ed249-106">The configurations are automatically included when you deploy the packages.</span></span>  
  
2.  <span data-ttu-id="ed249-107">La deuxième étape consiste à générer le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] afin de créer un utilitaire de déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="ed249-107">The second step is to build the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to create a package deployment utility.</span></span> <span data-ttu-id="ed249-108">L'utilitaire de déploiement du projet contient les packages à déployer.</span><span class="sxs-lookup"><span data-stu-id="ed249-108">The deployment utility for the project contains the packages that you want to deploy</span></span>  
  
3.  <span data-ttu-id="ed249-109">La troisième étape consiste à copier, sur l'ordinateur cible, le dossier de déploiement créé lors de la génération du projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed249-109">The third step is to copy the deployment folder that was created when you built the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to the target computer.</span></span>  
  
4.  <span data-ttu-id="ed249-110">La quatrième étape consiste à exécuter l’Assistant Installation de package sur l’ordinateur cible pour installer les packages sur le système de fichiers ou une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed249-110">The fourth step is to run, on the target computer, the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ed249-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ed249-111">Related Tasks</span></span>  
 <span data-ttu-id="ed249-112">Pour plus d’informations sur la création d’un utilitaire de déploiement, consultez [Créer un utilitaire de déploiement](../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ed249-112">For information about how to create a deployment utility, see [Create a Deployment Utility](../create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="ed249-113">Pour plus d’informations sur le déploiement de packages à l’aide de l’utilitaire de déploiement, consultez [Déployer des packages à l’aide de l’utilitaire de déploiement](../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ed249-113">For information about how to deploy packages using the deployment utility, see [Deploy Packages by Using the Deployment Utility](../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="ed249-114">Pour plus d’informations sur la création de configurations de package, consultez [Créer des configurations de package](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ed249-114">For information about how to create package configurations, see [Create Package Configurations](../create-package-configurations.md).</span></span>  
  
  
