---
title: 'Leçon 2 : ajout de boucles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602887"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="9d5f9-102">Leçon 2 : Ajout d’un bouclage</span><span class="sxs-lookup"><span data-stu-id="9d5f9-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="9d5f9-103">Dans la [leçon 1 : création du projet et du package de base](lesson-1-create-a-project-and-basic-package-with-ssis.md), vous avez créé un package qui a extrait des données d’une source de fichier plat unique, transformé les données à l’aide de transformations de recherche, puis chargé les données dans la table de faits **FactCurrency** de l’exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="9d5f9-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="9d5f9-104">Toutefois, il est rare qu'un processus d'extraction, de transformation et de chargement (ETL, extract, transform, and load) utilise un seul fichier plat.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="9d5f9-105">Un processus ETL classique extrait généralement les données de plusieurs sources de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="9d5f9-106">L'extraction des données à partir de plusieurs sources nécessite un flux de contrôle répétitif.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="9d5f9-107">L’une des fonctionnalités les plus attendues de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] est la possibilité d’ajouter facilement une itération ou un bouclage aux packages.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="9d5f9-108">fournit deux types de conteneurs pour effectuer des boucles dans des packages : le conteneur de boucles Foreach et le conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="9d5f9-109">Le conteneur de boucles Foreach utilise un énumérateur pour effectuer le bouclage, tandis que le conteneur de boucles For utilise généralement une expression variable.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="9d5f9-110">Cette leçon est basée sur le conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="9d5f9-111">Le conteneur de boucles Foreach permet à un package de répéter le flux de contrôle pour chaque membre d'un énumérateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="9d5f9-112">Avec le conteneur de boucles Foreach, vous pouvez énumérer :</span><span class="sxs-lookup"><span data-stu-id="9d5f9-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="9d5f9-113">Lignes du recordset ADO</span><span class="sxs-lookup"><span data-stu-id="9d5f9-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="9d5f9-114">Informations du schéma ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9d5f9-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="9d5f9-115">des structures de fichiers et de répertoires ;</span><span class="sxs-lookup"><span data-stu-id="9d5f9-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="9d5f9-116">des variables système, package et utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="9d5f9-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="9d5f9-117">Objets énumérables contenus dans une variable</span><span class="sxs-lookup"><span data-stu-id="9d5f9-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="9d5f9-118">Éléments d'une collection</span><span class="sxs-lookup"><span data-stu-id="9d5f9-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="9d5f9-119">Nœuds dans une expression de langage XML Path (XPath)</span><span class="sxs-lookup"><span data-stu-id="9d5f9-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="9d5f9-120">Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="9d5f9-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="9d5f9-121">Au cours de cette leçon, vous allez modifier le package ETL simple que vous avez créé au cours de la leçon 1 pour tirer parti du conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="9d5f9-122">Vous allez également définir des variables de package définies par l'utilisateur pour faire en sorte que le package du didacticiel effectue une itération sur tous les fichiers plats du dossier.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="9d5f9-123">Si vous n'avez pas effectué la leçon précédente, vous pouvez également copier le package final de la leçon 1 inclus dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="9d5f9-124">Au cours de cette leçon, vous n'allez pas modifier le flux de données mais uniquement le flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="9d5f9-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9d5f9-125">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="9d5f9-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="9d5f9-126">Pour plus d'informations sur l'installation et le déploiement d' **AdventureWorksDW2012**, consultez [Reporting Services Product Samples sur CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="9d5f9-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9d5f9-127">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="9d5f9-127">Lesson Tasks</span></span>  
 <span data-ttu-id="9d5f9-128">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d5f9-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="9d5f9-129">Étape 1 : Copie du package de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="9d5f9-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="9d5f9-130">Étape 2 : Ajout et configuration du conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="9d5f9-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="9d5f9-131">Étape 3 : Modification du Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="9d5f9-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="9d5f9-132">Étape 4 : Test du package du tutoriel de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="9d5f9-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="9d5f9-133">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="9d5f9-133">Start the Lesson</span></span>  
 [<span data-ttu-id="9d5f9-134">Étape 1 : Copie du package de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="9d5f9-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d5f9-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d5f9-135">See Also</span></span>  
 [<span data-ttu-id="9d5f9-136">Conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="9d5f9-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
