---
title: 'Étape 1 : Copie du package de la leçon 5 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614737"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="7e215-102">Étape 1 : Copie du package de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="7e215-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="7e215-103">Dans cette tâche, vous allez créer une copie du package Lesson 5.dtsx que vous avez créé à la leçon 5.</span><span class="sxs-lookup"><span data-stu-id="7e215-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="7e215-104">Vous pouvez également ajouter au projet le package final de la leçon 5 inclus avec le didacticiel, puis le copier à la place.</span><span class="sxs-lookup"><span data-stu-id="7e215-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="7e215-105">Vous allez utiliser cette nouvelle copie tout au long de la leçon 6.</span><span class="sxs-lookup"><span data-stu-id="7e215-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="7e215-106">Pour copier le package de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="7e215-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="7e215-107">Si SQL Server Data Tools n'est pas déjà ouvert, dans le menu Démarrer, pointez sur Tous les programmes, puis sur Microsoft SQL Server 2012 et cliquez sur SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="7e215-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="7e215-108">Dans le menu Fichier, cliquez sur Ouvrir, cliquez sur Projet/Solution, sélectionnez Didacticiel SSIS, cliquez sur Ouvrir, puis double-cliquez sur SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="7e215-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="7e215-109">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur Lesson 5.dtsx et choisissez Copier.</span><span class="sxs-lookup"><span data-stu-id="7e215-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="7e215-110">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur Packages SSIS et choisissez Coller.</span><span class="sxs-lookup"><span data-stu-id="7e215-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="7e215-111">Par défaut, le package copié est nommé Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="7e215-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="7e215-112">Dans l'Explorateur de solutions, double-cliquez avec le bouton droit sur Lesson 6.dtsx pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="7e215-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="7e215-113">Cliquez n'importe où dans l'arrière-plan de l'onglet Flux de contrôle, puis cliquez sur Propriétés.</span><span class="sxs-lookup"><span data-stu-id="7e215-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="7e215-114">Dans la fenêtre Propriétés, mettez la propriété Name à jour vers la leçon 6 (Lesson 6).</span><span class="sxs-lookup"><span data-stu-id="7e215-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="7e215-115">Cliquez sur la zone de la propriété ID, puis sur la flèche déroulante et sur \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="7e215-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="7e215-116">Pour ajouter le package final de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="7e215-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="7e215-117">Ouvrez SQL Server Data Tools et ouvrez le projet Didacticiel SSIS.</span><span class="sxs-lookup"><span data-stu-id="7e215-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="7e215-118">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur Packages SSIS, puis cliquez sur Ajouter le package existant.</span><span class="sxs-lookup"><span data-stu-id="7e215-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="7e215-119">Dans la boîte de dialogue Ajouter une copie des packages existants, sous Emplacement du package, sélectionnez Système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7e215-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="7e215-120">Cliquez sur le bouton Parcourir (...), leçon 5. dtsx sur votre ordinateur, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="7e215-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="7e215-121">Pour télécharger tous les packages de leçons de ce didacticiel, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7e215-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="7e215-122">Accédez à [Exemples de produits Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="7e215-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="7e215-123">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="7e215-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="7e215-124">Cliquez sur le fichier SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="7e215-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="7e215-125">Copiez et collez le package de la leçon 5 selon les étapes 3 à 8 décrites dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="7e215-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="7e215-126">Après la copie du package de la leçon 5, si vous avez des packages des leçons précédentes dans votre solution, cliquez avec le bouton droit sur chaque package des leçons 1 à 5 et cliquez sur Exclure du projet.</span><span class="sxs-lookup"><span data-stu-id="7e215-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="7e215-127">Lorsque vous avez terminé, vous devez avoir uniquement la leçon 6.dtsx dans votre solution.</span><span class="sxs-lookup"><span data-stu-id="7e215-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7e215-128">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="7e215-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7e215-129">Étape 2 : Conversion du projet en modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="7e215-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
