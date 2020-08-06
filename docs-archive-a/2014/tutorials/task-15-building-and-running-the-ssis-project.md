---
title: 'Tâche 15 : génération et exécution du projet SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703491"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="8f4c7-102">Tâche 15 : Génération et exécution du projet SSIS</span><span class="sxs-lookup"><span data-stu-id="8f4c7-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="8f4c7-103">Dans cette tâche, vous allez générer et exécuter le projet SSIS.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="8f4c7-104">Si la version 64 bits d’Excel 2010 est installée sur votre ordinateur, vous devez définir la valeur de **Run64BitRuntime** sur **false** pour que la source Excel fonctionne.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="8f4c7-105">Dans la fenêtre **Explorateur de solutions** , cliquez sur **projet** dans le menu, puis sur **Propriétés de CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="8f4c7-106">Dans la boîte de dialogue **Propriétés** , développez **Propriétés de configuration** sur la gauche, puis cliquez sur **débogage**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="8f4c7-107">Affectez à **Run64BitRuntime** la **valeur false**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="8f4c7-108">![Propriétés du projet CleanseAndCurateSuppliers](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "Propriétés du projet CleanseAndCurateSuppliers")</span><span class="sxs-lookup"><span data-stu-id="8f4c7-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="8f4c7-109">Cliquez sur **OK** pour fermer la boîte de dialogue **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="8f4c7-110">Dans la barre de menus, cliquez sur **générer** , puis sur **générer CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="8f4c7-111">Vérifiez l'absence d'erreurs de génération.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="8f4c7-112">Dans la barre de menus, cliquez sur **Déboguer** , puis sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="8f4c7-113">Passez en revue les messages dans la fenêtre de **progression** et vérifiez que le package est exécuté et qu’il s’est terminé avec succès.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="8f4c7-114">![Résultats de la fenêtre En cours](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Résultats de la fenêtre En cours")</span><span class="sxs-lookup"><span data-stu-id="8f4c7-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="8f4c7-115">![État final de la fenêtre En cours](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "État final de la fenêtre En cours")</span><span class="sxs-lookup"><span data-stu-id="8f4c7-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="8f4c7-116">Cliquez sur **Déboguer** dans la barre de menus et cliquez sur **arrêter le débogage** pour arrêter la session de débogage.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="8f4c7-117">Si le package échoue, vous devez activer les visionneuses de données pour voir comment les données circulent entre les composants.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8f4c7-118">étape suivante</span><span class="sxs-lookup"><span data-stu-id="8f4c7-118">Next Step</span></span>  
 [<span data-ttu-id="8f4c7-119">Tâche 16 : Vérification à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="8f4c7-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  
