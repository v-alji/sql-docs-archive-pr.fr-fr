---
title: 'Étape 5 : Test du package du didacticiel de la leçon 4 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704296"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="73758-102">Étape 5 : Test du package du tutoriel de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="73758-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="73758-103">Au moment de l'exécution, le fichier corrompu, Currency_BAD.txt, ne parvient pas à générer une correspondance avec la transformation de recherche Currency Key.</span><span class="sxs-lookup"><span data-stu-id="73758-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="73758-104">Du fait que la sortie d'erreur de la transformation de recherche Currency Key a été configurée en vue de réacheminer les lignes qui ont échoué vers une nouvelle destination de lignes échouées, le composant n'échoue pas et le package s'exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="73758-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="73758-105">Toutes les lignes qui ont échoué sont enregistrées dans le fichier ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="73758-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="73758-106">Au cours de cette tâche, vous allez tester la configuration de sortie d'erreur révisée en exécutant le package.</span><span class="sxs-lookup"><span data-stu-id="73758-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="73758-107">Une fois le package exécuté, vous visualiserez le contenu du fichier ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="73758-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73758-108">Pour éviter l'accumulation de lignes d'erreur dans le fichier ErrorOutput.txt, vous devez manuellement supprimer le contenu du fichier entre chaque exécution du package.</span><span class="sxs-lookup"><span data-stu-id="73758-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="73758-109">Vérification de la disposition du package</span><span class="sxs-lookup"><span data-stu-id="73758-109">Checking the Package layout</span></span>  
 <span data-ttu-id="73758-110">Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 4 contiennent les objets affichés dans les diagrammes suivants.</span><span class="sxs-lookup"><span data-stu-id="73758-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="73758-111">Le flux de contrôle doit être identique au flux de contrôle des leçons 2 à 4.</span><span class="sxs-lookup"><span data-stu-id="73758-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="73758-112">**Flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="73758-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="73758-113">![Flux de contrôle dans le package](../../2014/tutorials/media/task4lesson2control.gif "Flux de contrôle dans le package")</span><span class="sxs-lookup"><span data-stu-id="73758-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="73758-114">**Flux de données**</span><span class="sxs-lookup"><span data-stu-id="73758-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="73758-115">![Flux de données dans le package](../../2014/tutorials/media/task5lesson5data.gif "Flux de données dans le package")</span><span class="sxs-lookup"><span data-stu-id="73758-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="73758-116">Pour exécuter le package du didacticiel Lesson 4</span><span class="sxs-lookup"><span data-stu-id="73758-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="73758-117">Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="73758-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="73758-118">Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="73758-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="73758-119">Pour vérifier le contenu du fichier ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="73758-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="73758-120">Dans le Bloc-notes ou un autre éditeur de texte, ouvrez le fichier ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="73758-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="73758-121">L'ordre par défaut des colonnes est le suivant : AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="73758-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="73758-122">Notez que toutes les lignes du fichier contiennent la valeur CurrencyID non appariée définie à BAD, la valeur ErrorCode définie à -1071607778, la valeur ErrorColumn définie à 0 et la valeur ErrorDescription dévoilant le message « Aucune correspondance de ligne trouvée au cours de la recherche ».</span><span class="sxs-lookup"><span data-stu-id="73758-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="73758-123">La valeur de ErrorColumn est définie à 0 puisque l'erreur n'est pas liée à une colonne.</span><span class="sxs-lookup"><span data-stu-id="73758-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="73758-124">C'est l'opération de recherche qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="73758-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="73758-125">.</span><span class="sxs-lookup"><span data-stu-id="73758-125">.</span></span>  
  
  
