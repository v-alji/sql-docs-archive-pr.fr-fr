---
title: 'Étape 1 : Copie du package de la leçon 4 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614169"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="b2a9c-102">Étape 1 : Copie du package de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="b2a9c-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="b2a9c-103">Dans cette tâche, vous créez une copie du package Lesson 4.dtsx que vous avez créé à la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="b2a9c-104">Vous pouvez également ajouter au projet le package final de la leçon 4 inclus avec le didacticiel, puis le copier.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="b2a9c-105">Vous allez utiliser cette nouvelle copie tout au long de la leçon 5.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="b2a9c-106">Pour copier le package de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="b2a9c-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="b2a9c-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools n’est pas déjà ouvert, dans le menu **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server 2012**et cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="b2a9c-108">Dans le menu **Fichier** , cliquez sur **Ouvrir**, cliquez sur **Projet/Solution**, sélectionnez **Didacticiel SSIS** , cliquez sur **Ouvrir**, puis double-cliquez sur **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="b2a9c-109">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Lesson 4.dtsx**et choisissez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="b2a9c-110">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **coller**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="b2a9c-111">Par défaut, le package copié est nommé Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="b2a9c-112">Dans l’Explorateur de solutions, double-cliquez sur **Lesson 5.dtsx** pour ouvrir le package.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="b2a9c-113">Cliquez avec le bouton droit n’importe où dans l’arrière-plan de l’onglet **Flow Control** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="b2a9c-114">Dans le Fenêtre Propriétés, mettez à jour la `Name` propriété avec la valeur `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="b2a9c-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="b2a9c-115">Cliquez sur la zone de la propriété **ID** , cliquez sur la flèche déroulante, puis sur **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="b2a9c-116">Pour ajouter le package final de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="b2a9c-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="b2a9c-117">Ouvrez [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools et ouvrez le projet Didacticiel SSIS.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="b2a9c-118">Dans Explorateur de solutions, cliquez avec le bouton droit sur **packages SSIS**, puis cliquez sur **Ajouter un package existant**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="b2a9c-119">Dans la boîte de dialogue **Ajouter une copie des packages existants** , dans **Emplacement du package**, sélectionnez **Système de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="b2a9c-120">Cliquez sur le bouton Parcourir **(...)** , accédez à la **leçon 4. dtsx** sur votre ordinateur, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="b2a9c-121">Pour télécharger tous les packages de leçons de ce didacticiel, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="b2a9c-122">Accédez à [Exemples de produits Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="b2a9c-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="b2a9c-123">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="b2a9c-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="b2a9c-124">Cliquez sur le fichier SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="b2a9c-125">Copiez et collez le package de la leçon 4 comme décrit dans les étapes 3 à 8 de la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="b2a9c-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b2a9c-126">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b2a9c-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b2a9c-127">Étape 2 : Activation et configuration des configurations de package</span><span class="sxs-lookup"><span data-stu-id="b2a9c-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
