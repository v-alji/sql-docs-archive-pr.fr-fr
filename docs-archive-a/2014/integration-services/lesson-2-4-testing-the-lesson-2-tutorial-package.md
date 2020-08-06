---
title: 'Étape 4 : Test du package du didacticiel de la leçon 2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601559"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="6c607-102">Étape 4 : Test du package du tutoriel de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="6c607-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="6c607-103">Une fois le conteneur de boucles Foreach et le gestionnaire de connexions de fichiers plats configurés, le package Lesson 2 peut parcourir l'ensemble des 14 fichiers plats dans le dossier Sample Data.</span><span class="sxs-lookup"><span data-stu-id="6c607-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="6c607-104">À chaque fois qu'un nom de fichier correspondant au nom de fichier spécifié est trouvé, le conteneur de boucles Foreach remplace la variable définie par l'utilisateur par ce nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="6c607-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="6c607-105">Cette variable met à jour à son tour la propriété ConnectionString du Gestionnaire de connexions de fichiers plats, et une connexion au nouveau fichier plat est établie.</span><span class="sxs-lookup"><span data-stu-id="6c607-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="6c607-106">Le conteneur de boucles Foreach exécute alors la tâche de flux de données inchangée sur les données du nouveau fichier plat avant de se connecter au fichier suivant dans le dossier.</span><span class="sxs-lookup"><span data-stu-id="6c607-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="6c607-107">Suivez la procédure ci-dessous pour tester la nouvelle fonctionnalité de bouclage que vous avez ajoutée à votre package.</span><span class="sxs-lookup"><span data-stu-id="6c607-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c607-108">Si vous avez exécuté le package de la leçon 1, vous devez supprimer les enregistrements de dbo.FactCurrency dans AdventureWorksDW2012 avant d'exécuter le package de cette leçon, sans quoi il échouera avec une erreur indiquant une violation de contrainte de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="6c607-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="6c607-109">Vous obtiendrez les mêmes erreurs si vous exécutez le package en sélectionnant Déboguer/Démarrer le débogage (ou en appuyant sur F5), car la leçon 1 et la leçon 2 s'exécuteront en même temps.</span><span class="sxs-lookup"><span data-stu-id="6c607-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="6c607-110">La leçon 2 essaiera d'insérer des enregistrements déjà insérés dans la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="6c607-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="6c607-111">Vérification de la disposition du package</span><span class="sxs-lookup"><span data-stu-id="6c607-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="6c607-112">Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 2 contiennent les objets affichés dans les diagrammes suivants.</span><span class="sxs-lookup"><span data-stu-id="6c607-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="6c607-113">Le flux de données doit être identique au flux de données de la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="6c607-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="6c607-114">**Flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="6c607-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="6c607-115">![Flux de contrôle dans le package](../../2014/tutorials/media/task4lesson2control.gif "Flux de contrôle dans le package")</span><span class="sxs-lookup"><span data-stu-id="6c607-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="6c607-116">**Flux de données**</span><span class="sxs-lookup"><span data-stu-id="6c607-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="6c607-117">![Flux de données dans le package](../../2014/tutorials/media/task9lesson1data.gif "Flux de données dans le package")</span><span class="sxs-lookup"><span data-stu-id="6c607-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="6c607-118">Pour tester le package du didacticiel de la leçon 2</span><span class="sxs-lookup"><span data-stu-id="6c607-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="6c607-119">Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur **Lesson 2.dtsx** , puis cliquez sur **Exécuter le package**.</span><span class="sxs-lookup"><span data-stu-id="6c607-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="6c607-120">Le package est exécuté.</span><span class="sxs-lookup"><span data-stu-id="6c607-120">The package will run.</span></span> <span data-ttu-id="6c607-121">Vous pouvez vérifier l’état de chaque boucle dans la fenêtre sortie ou en cliquant sur l’onglet **progression** . Par exemple, vous pouvez voir que 1097 lignes ont été ajoutées à la table de destination à partir du fichier Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="6c607-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="6c607-122">Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="6c607-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6c607-123">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="6c607-123">Next Lesson</span></span>  
 [<span data-ttu-id="6c607-124">Leçon 5 : Ajout de configurations de package pour le modèle de déploiement de package</span><span class="sxs-lookup"><span data-stu-id="6c607-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c607-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c607-125">See Also</span></span>  
 [<span data-ttu-id="6c607-126">Exécution de projets et de packages</span><span class="sxs-lookup"><span data-stu-id="6c607-126">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
