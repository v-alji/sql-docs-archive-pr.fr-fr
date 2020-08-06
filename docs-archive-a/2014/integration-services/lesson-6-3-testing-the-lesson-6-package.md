---
title: 'Étape 3 : Test du package de la leçon 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705283"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="be412-102">Étape 3 : Test du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="be412-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="be412-103">Au moment de l'exécution, votre package obtient la valeur de la propriété Directory à partir du paramètre VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="be412-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="be412-104">Pour vérifier si le package met à jour la propriété Directory avec la nouvelle valeur lors de l'exécution, exécutez tout simplement le package.</span><span class="sxs-lookup"><span data-stu-id="be412-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="be412-105">Étant donné que seuls trois fichiers de données exemple ont été copiés dans le nouveau répertoire, le flux de données ne sera exécuté que trois fois au lieu de parcourir les 14 fichiers du dossier d'origine.</span><span class="sxs-lookup"><span data-stu-id="be412-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="be412-106">Vérification de la disposition du package</span><span class="sxs-lookup"><span data-stu-id="be412-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="be412-107">Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 6 contiennent les objets affichés dans les diagrammes suivants.</span><span class="sxs-lookup"><span data-stu-id="be412-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="be412-108">Le flux de contrôle doit être identique au flux de contrôle de la leçon 5.</span><span class="sxs-lookup"><span data-stu-id="be412-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="be412-109">Le flux de données doit être identique au flux de données de la leçon 5.</span><span class="sxs-lookup"><span data-stu-id="be412-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="be412-110">**Flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="be412-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="be412-111">![Flux de contrôle](../../2014/tutorials/media/task3lesson6control.jpg "Flux de contrôle")</span><span class="sxs-lookup"><span data-stu-id="be412-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="be412-112">**Flux de données**</span><span class="sxs-lookup"><span data-stu-id="be412-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="be412-113">![Flux de données](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span><span class="sxs-lookup"><span data-stu-id="be412-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="be412-114">Pour tester le package du didacticiel de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="be412-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="be412-115">Dans le menu Déboguer, cliquez sur Démarrer le débogage.</span><span class="sxs-lookup"><span data-stu-id="be412-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="be412-116">Une fois l'exécution du package terminée, dans le menu Déboguer, cliquez sur Arrêter le débogage.</span><span class="sxs-lookup"><span data-stu-id="be412-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="be412-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="be412-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="be412-118">Étape 4 : Déploiement du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="be412-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
