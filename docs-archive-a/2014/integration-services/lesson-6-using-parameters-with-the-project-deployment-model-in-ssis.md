---
title: 'Leçon 6 : utilisation des paramètres avec le modèle de déploiement de projet | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602882"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="319e0-102">Leçon 6 : Utilisation des paramètres dans le modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="319e0-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="319e0-103">SQL Server 2012 introduit un nouveau modèle de déploiement qui permet de déployer vos projets sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="319e0-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="319e0-104">Le serveur Integration Services vous permet de gérer et d'exécuter les packages, et de configurer leurs valeurs d'exécution.</span><span class="sxs-lookup"><span data-stu-id="319e0-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="319e0-105">Dans cette leçon, vous allez modifier le package que vous avez créé au cours de la [leçon 5 : ajout de configurations de package pour le modèle de déploiement de package](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) afin d’utiliser le modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="319e0-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="319e0-106">Vous remplacerez la valeur de configuration par un paramètre pour spécifier l'emplacement des exemples de données.</span><span class="sxs-lookup"><span data-stu-id="319e0-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="319e0-107">Vous pouvez également copier le package final de la leçon 5 inclus dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="319e0-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="319e0-108">À l'aide de l'Assistant Configuration de projet Integration Services, vous convertirez le projet en modèle de déploiement de projet, et vous utiliserez un paramètre au lieu d'une valeur de configuration pour définir la propriété Directory.</span><span class="sxs-lookup"><span data-stu-id="319e0-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="319e0-109">Cette leçon couvre partiellement les étapes que vous suivriez pour convertir les packages SSIS existants en nouveau modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="319e0-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="319e0-110">Quand vous réexécutez le package, le service Integration Services utilise le paramètre pour donner sa valeur à la variable, qui à son tour met à jour la propriété Répertoire.</span><span class="sxs-lookup"><span data-stu-id="319e0-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="319e0-111">Ainsi, le package itère dans les fichiers du nouveau dossier de données spécifié par la valeur du paramètre, et non du dossier défini dans le fichier de configuration du package.</span><span class="sxs-lookup"><span data-stu-id="319e0-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="319e0-112">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="319e0-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="319e0-113">Pour plus d’informations sur l’installation et le déploiement de **AdventureWorksDW2012**, consultez [Considérations relatives à l’installation d’exemples de bases de données et d’exemples de code SQL Server](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span><span class="sxs-lookup"><span data-stu-id="319e0-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="319e0-114">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="319e0-114">Lesson Tasks</span></span>  
 <span data-ttu-id="319e0-115">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="319e0-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="319e0-116">Étape 1 : Copie du package de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="319e0-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="319e0-117">Étape 2 : Conversion du projet en modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="319e0-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="319e0-118">Étape 3 : Test du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="319e0-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="319e0-119">Étape 4 : Déploiement du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="319e0-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="319e0-120">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="319e0-120">Start the Lesson</span></span>  
 [<span data-ttu-id="319e0-121">Étape 1 : Copie du package de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="319e0-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
