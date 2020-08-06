---
title: 'Étape 1 : Copie du package de la leçon 2 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bd91402-4e37-41de-ab78-8ca5a1948a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39bfc965febc401bd66b1077388021b8ccf52aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700014"
---
# <a name="step-1-copying-the-lesson-2-package"></a><span data-ttu-id="9858f-102">Étape 1 : Copie du package de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="9858f-102">Step 1: Copying the Lesson 2 Package</span></span>
  <span data-ttu-id="9858f-103">Dans cette tâche, vous allez créer une copie du package Lesson 2.dtsx que vous avez créé à la leçon 2.</span><span class="sxs-lookup"><span data-stu-id="9858f-103">In this task, you will create a copy of the Lesson 2.dtsx package that you created in Lesson 2.</span></span> <span data-ttu-id="9858f-104">Vous pouvez également ajouter au projet le package final de la leçon 2 fourni avec le didacticiel, puis le copier à la place.</span><span class="sxs-lookup"><span data-stu-id="9858f-104">Alternatively, you can add the completed lesson 2 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="9858f-105">Vous utiliserez cette nouvelle copie tout au long de la leçon 3.</span><span class="sxs-lookup"><span data-stu-id="9858f-105">You will use this new copy throughout the rest of Lesson 3.</span></span>  
  
### <a name="to-create-the-lesson-3-package"></a><span data-ttu-id="9858f-106">Pour créer le package de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="9858f-106">To create the Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="9858f-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools n’est pas déjà ouvert, dans le menu **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server 2012**et cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="9858f-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="9858f-108">Dans le menu **Fichier** , cliquez sur **Ouvrir**, cliquez sur **Projet/Solution**, sélectionnez **Didacticiel SSIS** , cliquez sur **Ouvrir**, puis double-cliquez sur **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="9858f-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="9858f-109">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Lesson 2.dtsx**et choisissez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="9858f-109">In Solution Explorer, right-click **Lesson 2.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="9858f-110">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **coller**.</span><span class="sxs-lookup"><span data-stu-id="9858f-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="9858f-111">Par défaut, le package copié est nommé Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="9858f-111">By default, the copied package is named Lesson 3.dtsx.</span></span>  
  
5.  <span data-ttu-id="9858f-112">Dans Explorateur de solutions, double-cliquez sur la **leçon 3. dtsx** pour ouvrir le package.</span><span class="sxs-lookup"><span data-stu-id="9858f-112">In Solution Explorer, double-click **Lesson 3.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="9858f-113">Cliquez avec le bouton droit dans l’arrière-plan de l’onglet **Flux de contrôle** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9858f-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="9858f-114">Dans le Fenêtre Propriétés, mettez à jour la `Name` propriété avec la valeur `Lesson 3` .</span><span class="sxs-lookup"><span data-stu-id="9858f-114">In the Properties window, update the `Name` property to `Lesson 3`.</span></span>  
  
8.  <span data-ttu-id="9858f-115">Cliquez sur la zone de la propriété **ID** , puis dans la liste, cliquez sur **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="9858f-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson2-package"></a><span data-ttu-id="9858f-116">Pour ajouter le package final de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="9858f-116">To add the completed Lesson2 package</span></span>  
  
1.  <span data-ttu-id="9858f-117">Ouvrez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , puis le projet SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="9858f-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="9858f-118">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **Ajouter un package existant**.</span><span class="sxs-lookup"><span data-stu-id="9858f-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="9858f-119">Dans la boîte de dialogue **Ajouter une copie des packages existants** , dans **Emplacement du package**, sélectionnez **Système de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="9858f-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="9858f-120">Cliquez sur le bouton de navigation **(...)** , accédez à **Lesson 2.dtsx** sur votre ordinateur, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="9858f-120">Click the browse **(...)** button, navigate to **Lesson 2.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9858f-121">Pour télécharger tous les packages de leçons de ce didacticiel, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9858f-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="9858f-122">Accédez à [Exemples de produits Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="9858f-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="9858f-123">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="9858f-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="9858f-124">Cliquez sur le fichier SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="9858f-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="9858f-125">Copiez et collez le package de la leçon 3 selon les étapes 3 à 8 décrites dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="9858f-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9858f-126">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="9858f-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9858f-127">Étape 2 : Activation et configuration du mode d’écriture dans un journal</span><span class="sxs-lookup"><span data-stu-id="9858f-127">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
  
