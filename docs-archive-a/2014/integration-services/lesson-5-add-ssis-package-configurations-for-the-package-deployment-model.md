---
title: 'Leçon 5 : ajout de configurations de package pour le modèle de déploiement de package | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696984"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="628cb-102">Leçon 5 : Ajout de configurations de package pour le modèle de déploiement de package</span><span class="sxs-lookup"><span data-stu-id="628cb-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="628cb-103">Les configurations de package permettent de définir, en dehors de l'environnement de développement, des propriétés et des variables appliquées au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="628cb-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="628cb-104">Les configurations permettent de développer des packages souples et faciles à déployer et à distribuer.</span><span class="sxs-lookup"><span data-stu-id="628cb-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="628cb-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offre les types de configuration suivants :</span><span class="sxs-lookup"><span data-stu-id="628cb-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="628cb-106">Fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="628cb-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="628cb-107">Variable d’environnement</span><span class="sxs-lookup"><span data-stu-id="628cb-107">Environment variable</span></span>  
  
-   <span data-ttu-id="628cb-108">Entrée de Registre</span><span class="sxs-lookup"><span data-stu-id="628cb-108">Registry entry</span></span>  
  
-   <span data-ttu-id="628cb-109">Variable de package parent</span><span class="sxs-lookup"><span data-stu-id="628cb-109">Parent package variable</span></span>  
  
-   <span data-ttu-id="628cb-110">Table [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="628cb-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>  
  
 <span data-ttu-id="628cb-111">Dans cette leçon, vous allez modifier le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] simple que vous avez créé dans [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) pour utiliser le modèle de déploiement de package et tirer parti des configurations de package.</span><span class="sxs-lookup"><span data-stu-id="628cb-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="628cb-112">Vous pouvez également copier le package final de la leçon 4 inclus dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="628cb-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="628cb-113">À l'aide de l'Assistant Configuration de package, vous allez créer une configuration XML qui met à jour la propriété `Directory` du conteneur de boucles Foreach en utilisant une variable de niveau package mappée à la propriété Directory.</span><span class="sxs-lookup"><span data-stu-id="628cb-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="628cb-114">Une fois que vous avez créé le fichier de configuration, vous allez modifier la valeur de la variable en dehors de l'environnement de développement et faire pointer la propriété modifiée vers un nouveau dossier de données exemple.</span><span class="sxs-lookup"><span data-stu-id="628cb-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="628cb-115">Lorsque vous réexécutez le package, le fichier de configuration remplit la valeur de la variable, et la variable à son tour met à jour la `Directory` propriété.</span><span class="sxs-lookup"><span data-stu-id="628cb-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="628cb-116">Ainsi, le package parcourra les fichiers du nouveau dossier de données et non les fichiers du dossier d'origine qui a été codé de manière irréversible dans le package.</span><span class="sxs-lookup"><span data-stu-id="628cb-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="628cb-117">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="628cb-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="628cb-118">Pour plus d'informations sur l'installation et le déploiement d' **AdventureWorksDW2012**, consultez [Reporting Services Product Samples sur CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="628cb-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="628cb-119">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="628cb-119">Lesson Tasks</span></span>  
 <span data-ttu-id="628cb-120">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="628cb-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="628cb-121">Étape 1 : Copie du package de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="628cb-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="628cb-122">Étape 2 : Activation et configuration des configurations de package</span><span class="sxs-lookup"><span data-stu-id="628cb-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="628cb-123">Étape 3 : Modification de la valeur de configuration de la propriété Directory</span><span class="sxs-lookup"><span data-stu-id="628cb-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="628cb-124">Étape 4 : Test du package du tutoriel de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="628cb-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="628cb-125">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="628cb-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="628cb-126">Étape 1 : Copie du package de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="628cb-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
