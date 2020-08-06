---
title: 'Leçon 4 : ajout de redirection de workflow d’erreur | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708483"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="56ebb-102">Leçon 4 : Ajout de redirection de flux d’erreurs</span><span class="sxs-lookup"><span data-stu-id="56ebb-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="56ebb-103">Pour gérer les erreurs qui peuvent se produire dans le processus de transformation, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vous donne la possibilité de choisir une base par composant et par colonne pour gérer les données qui ne peuvent pas être transformées.</span><span class="sxs-lookup"><span data-stu-id="56ebb-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="56ebb-104">Vous pouvez choisir d'ignorer une erreur dans certaines colonnes, de rediriger dans sa totalité la ligne qui a échoué ou simplement de faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="56ebb-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="56ebb-105">Par défaut, tous les composants de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sont configurés pour échouer lorsque des erreurs se produisent.</span><span class="sxs-lookup"><span data-stu-id="56ebb-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="56ebb-106">Le fait de faire échouer un composant entraîne l'échec du package et l'arrêt de tous les traitements ultérieurs.</span><span class="sxs-lookup"><span data-stu-id="56ebb-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="56ebb-107">Au lieu de permettre l'arrêt de l'exécution du package à la suite d'échecs, il est recommandé de configurer et de traiter les erreurs de traitement potentielles au moment où elles se produisent dans la transformation.</span><span class="sxs-lookup"><span data-stu-id="56ebb-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="56ebb-108">Si vous pouvez choisir d'ignorer les erreurs pour vous assurer que votre package s'exécute correctement, il est souvent préférable de rediriger la ligne qui a échoué vers un autre chemin de traitement où les données et l'erreur peuvent être rendues persistantes, étudiées et retraitées ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="56ebb-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="56ebb-109">Au cours de cette leçon, vous allez créer une copie du package que vous avez développé dans la [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="56ebb-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="56ebb-110">Avec ce package, vous allez créer une version endommagée de l'un des exemples de fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="56ebb-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="56ebb-111">Ce fichier endommagé entraînera une erreur de traitement lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="56ebb-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="56ebb-112">Pour gérer les données d'erreur, vous allez ajouter et configurer une destination de fichier plat chargée d'écrire dans un fichier toutes les lignes qui ne parviennent pas à détecter une valeur de recherche dans la transformation Lookup Currency Key.</span><span class="sxs-lookup"><span data-stu-id="56ebb-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="56ebb-113">Avant d'écrire les données d'erreur dans le fichier, vous devez inclure un composant Script qui utilise un script pour se procurer des descriptions sur les erreurs.</span><span class="sxs-lookup"><span data-stu-id="56ebb-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="56ebb-114">Vous allez ensuite reconfigurer la transformation Lookup Currency Key pour réacheminer vers la transformation Script toutes les données qui n'ont pas pu être traitées.</span><span class="sxs-lookup"><span data-stu-id="56ebb-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56ebb-115">Pour suivre ce didacticiel, vous devez disposer de l'exemple de base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="56ebb-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="56ebb-116">Pour plus d'informations sur l'installation et le déploiement d' **AdventureWorksDW2012**, consultez [Reporting Services Product Samples sur CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="56ebb-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="56ebb-117">Contenu de la leçon</span><span class="sxs-lookup"><span data-stu-id="56ebb-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="56ebb-118">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="56ebb-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="56ebb-119">Étape 1 : Copie du package de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="56ebb-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="56ebb-120">Étape 2 : Création d’un fichier corrompu</span><span class="sxs-lookup"><span data-stu-id="56ebb-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="56ebb-121">Étape 3 : Ajout de redirection de flux d’erreurs</span><span class="sxs-lookup"><span data-stu-id="56ebb-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="56ebb-122">Étape 4 : Ajout d’une destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="56ebb-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="56ebb-123">Étape 5 : Test du package du tutoriel de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="56ebb-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="56ebb-124">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="56ebb-124">Start the Lesson</span></span>  
 [<span data-ttu-id="56ebb-125">Étape 1 : Copie du package de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="56ebb-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
