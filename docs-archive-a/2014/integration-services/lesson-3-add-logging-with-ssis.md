---
title: 'Leçon 3 : ajout de la journalisation | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604629"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="75070-102">Leçon 3 : Ajout du mode d’écriture dans un journal</span><span class="sxs-lookup"><span data-stu-id="75070-102">Lesson 3: Adding Logging</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="75070-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] inclut des fonctions d'écriture dans un journal pour dépanner et contrôler l'exécution du package, lesquelles fournissent une trace des tâches et des événements de conteneur.</span><span class="sxs-lookup"><span data-stu-id="75070-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="75070-104">Les fonctions d'écriture dans un journal sont d'une utilisation souple et peuvent être activées au niveau du package ou de tâches et de conteneurs spécifiques au sein du package.</span><span class="sxs-lookup"><span data-stu-id="75070-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="75070-105">Vous pouvez sélectionner les événements à enregistrer et créer plusieurs journaux pour un seul package.</span><span class="sxs-lookup"><span data-stu-id="75070-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="75070-106">La fonction d'écriture dans un journal est fournie par un module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="75070-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="75070-107">Chaque module fournisseur d'informations peut écrire les informations de journalisation dans différents formats et types de destination.</span><span class="sxs-lookup"><span data-stu-id="75070-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="75070-108">fournit les modules fournisseurs d'informations suivants :</span><span class="sxs-lookup"><span data-stu-id="75070-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="75070-109">Fichier texte</span><span class="sxs-lookup"><span data-stu-id="75070-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="75070-110">Journal des événements Windows</span><span class="sxs-lookup"><span data-stu-id="75070-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="75070-111">Fichier XML</span><span class="sxs-lookup"><span data-stu-id="75070-111">XML file</span></span>  
  
 <span data-ttu-id="75070-112">Au cours de cette leçon, vous allez créer une copie du package que vous avez créé à la [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="75070-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="75070-113">Vous allez utiliser ce nouveau package et ajouter et configurer le mode d'écriture dans un journal pour contrôler des événements particuliers au cours de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="75070-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="75070-114">Si vous n'avez effectué aucune des leçons précédentes, vous pouvez également copier le package final de la leçon 2 inclus dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="75070-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="75070-115">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="75070-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="75070-116">Pour plus d’informations sur l’installation et le déploiement de **AdventureWorksDW2012**, [Reporting Services des exemples de produits sur GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="75070-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="75070-117">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="75070-117">Lesson Tasks</span></span>  
 <span data-ttu-id="75070-118">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="75070-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="75070-119">Étape 1 : Copie du package de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="75070-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="75070-120">Étape 2 : Activation et configuration du mode d’écriture dans un journal</span><span class="sxs-lookup"><span data-stu-id="75070-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="75070-121">Étape 3 : Test du package du tutoriel de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="75070-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="75070-122">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="75070-122">Start the Lesson</span></span>  
 [<span data-ttu-id="75070-123">Étape 1 : Copie du package de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="75070-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
