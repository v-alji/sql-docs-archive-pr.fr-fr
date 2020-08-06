---
title: 'Étape 1 : Copie du package de la leçon 3 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0d053786-5203-43f3-a613-27a8dd2bc44a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fde3bd907e8a55b1ac9a164b2960268189b19392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604627"
---
# <a name="step-1-copying-the-lesson-3-package"></a><span data-ttu-id="c6ecf-102">Étape 1 : Copie du package de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="c6ecf-102">Step 1: Copying the Lesson 3 Package</span></span>
  <span data-ttu-id="c6ecf-103">Dans cette tâche, vous allez créer une copie du package Lesson 3.dtsx que vous avez créé à la leçon 3.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-103">In this task, you will create a copy of the Lesson 3.dtsx package that you created in Lesson 3.</span></span> <span data-ttu-id="c6ecf-104">Si vous n'avez pas terminé la leçon 3, vous pouvez également ajouter au projet le package final de la leçon 3 inclus avec le didacticiel, puis le copier pour l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-104">Alternatively, if you did not complete lesson 3, you can add the completed lesson 3 package that is included with the tutorial to the project, and then make a copy of it to work with.</span></span> <span data-ttu-id="c6ecf-105">Vous allez utiliser cette nouvelle copie tout au long de la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-105">You will use this new copy throughout the rest of Lesson 4.</span></span>  
  
### <a name="to-create-the-lesson-4-package"></a><span data-ttu-id="c6ecf-106">Pour créer le package de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="c6ecf-106">To create the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="c6ecf-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools n’est pas déjà ouvert, dans le menu **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server**et cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="c6ecf-108">Dans le menu **Fichier** , cliquez sur **Ouvrir**, cliquez sur **Projet/Solution**, sélectionnez **Didacticiel SSIS** , cliquez sur **Ouvrir**, puis double-cliquez sur **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="c6ecf-109">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Lesson 3.dtsx**et choisissez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-109">In Solution Explorer, right-click **Lesson 3.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="c6ecf-110">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **coller**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="c6ecf-111">Par défaut, le package copié est nommé Lesson 4.dtsx.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-111">By default, the copied package is named Lesson 4.dtsx.</span></span>  
  
5.  <span data-ttu-id="c6ecf-112">Dans Explorateur de solutions, double-cliquez sur **leçon 4. dtsx** pour ouvrir le package.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-112">In Solution Explorer, double-click **Lesson 4.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="c6ecf-113">Cliquez avec le bouton droit dans l’arrière-plan de l’onglet **Flux de contrôle** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="c6ecf-114">Dans le Fenêtre Propriétés, mettez à jour la `Name` propriété avec la valeur `Lesson 4` .</span><span class="sxs-lookup"><span data-stu-id="c6ecf-114">In the Properties window, update the `Name` property to `Lesson 4`.</span></span>  
  
8.  <span data-ttu-id="c6ecf-115">Cliquez sur la zone de la propriété **ID** , puis dans la liste, cliquez sur **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-3-package"></a><span data-ttu-id="c6ecf-116">Pour ajouter le package final de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="c6ecf-116">To add the completed Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="c6ecf-117">Ouvrez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , puis le projet SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="c6ecf-118">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **Ajouter un package existant**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="c6ecf-119">Dans la boîte de dialogue **Ajouter une copie des packages existants** , dans **Emplacement du package**, sélectionnez **Système de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="c6ecf-120">Cliquez sur le bouton de navigation **(...)**, accédez à Lesson 3.dtsx sur votre ordinateur, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-120">Click the browse **(...)** button, navigate to Lesson 3.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="c6ecf-121">Pour télécharger tous les packages de leçons de ce didacticiel, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="c6ecf-122">Accédez à [Exemples de produits Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="c6ecf-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="c6ecf-123">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="c6ecf-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="c6ecf-124">Cliquez sur le fichier SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="c6ecf-125">Copiez et collez le package de la leçon 3 selon les étapes 3 à 8 décrites dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="c6ecf-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c6ecf-126">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="c6ecf-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c6ecf-127">Étape 2 : Création d’un fichier corrompu</span><span class="sxs-lookup"><span data-stu-id="c6ecf-127">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
  
