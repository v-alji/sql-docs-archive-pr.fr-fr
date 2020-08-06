---
title: 'Tâche 9 : création d’une hiérarchie dérivée à l’aide de la Data Manager Master | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710039"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="20dcb-102">Tâche 9 : Création d’une hiérarchie dérivée à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="20dcb-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="20dcb-103">Dans cette tâche, vous allez créer une hiérarchie dérivée à l'aide de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="20dcb-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="20dcb-104">Cette hiérarchie dérivée est dérivée des relations d’attributs basés sur un domaine entre les entités **fournisseur** et **État** .</span><span class="sxs-lookup"><span data-stu-id="20dcb-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="20dcb-105">Basculez vers la page principale du **Data Manager maître** en cliquant sur **SQL Server Master Data Services 2012** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="20dcb-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="20dcb-106">Cliquez sur **administration de système** dans la section **tâches administratives** .</span><span class="sxs-lookup"><span data-stu-id="20dcb-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="20dcb-107">Pointez la souris sur **gérer** dans la barre de menus, puis cliquez sur **hiérarchies dérivées**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="20dcb-108">![Menu Gérer - Hiérarchies dérivées sélectionnées](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Menu Gérer - Hiérarchies dérivées sélectionnées")</span><span class="sxs-lookup"><span data-stu-id="20dcb-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="20dcb-109">Cliquez sur le bouton **Ajouter une hiérarchie dérivée (+)** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="20dcb-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="20dcb-110">![Bouton Ajouter une hiérarchie dérivée](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Bouton Ajouter une hiérarchie dérivée")</span><span class="sxs-lookup"><span data-stu-id="20dcb-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="20dcb-111">Tapez **SuppliersInState** pour le **nom de la hiérarchie dérivée**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="20dcb-112">Cliquez sur le bouton **Enregistrer** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="20dcb-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="20dcb-113">![Bouton Enregistrer une hiérarchie dérivée](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Bouton Enregistrer une hiérarchie dérivée")</span><span class="sxs-lookup"><span data-stu-id="20dcb-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="20dcb-114">Faites glisser **fournisseur** des **niveaux disponibles : SuppliersInState** à **niveaux actuels : SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="20dcb-115">![Entités et hiérarchies disponibles au niveau actuel](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Entités et hiérarchies disponibles au niveau actuel")</span><span class="sxs-lookup"><span data-stu-id="20dcb-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="20dcb-116">Faites glisser **État** de **niveaux disponibles : SuppliersInState** à **niveaux actuels : SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="20dcb-117">L’écran doit avoir les **niveaux actuels** , comme indiqué dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="20dcb-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="20dcb-118">![Niveaux actuels et aperçu de hiérarchie dérivée](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Niveaux actuels et aperçu de hiérarchie dérivée")</span><span class="sxs-lookup"><span data-stu-id="20dcb-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="20dcb-119">Dans la fenêtre d' **Aperçu** , développez **NY {New York}** et vous devriez voir un fournisseur dans cet État, comme indiqué dans l’image précédente.</span><span class="sxs-lookup"><span data-stu-id="20dcb-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="20dcb-120">Basculez vers la page principale du **Data Manager maître** en cliquant sur **SQL Server Master Data Services 2012** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="20dcb-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="20dcb-121">Cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="20dcb-122">Pointez la souris sur **hiérarchies** , puis cliquez sur **dérivé : SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="20dcb-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="20dcb-123">![Hiérarchies - Menu Derived:SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hiérarchies - Menu Derived:SuppliersInState")</span><span class="sxs-lookup"><span data-stu-id="20dcb-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="20dcb-124">Cliquez sur n’importe quel nœud d' **État** dans l' **arborescence** pour afficher les fournisseurs dans cet État dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="20dcb-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="20dcb-125">![Hiérarchie dérivée dans l'Explorateur](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Hiérarchie dérivée dans l'Explorateur")</span><span class="sxs-lookup"><span data-stu-id="20dcb-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="20dcb-126">étape suivante</span><span class="sxs-lookup"><span data-stu-id="20dcb-126">Next Step</span></span>  
 [<span data-ttu-id="20dcb-127">Leçon 5 : Automatisation du nettoyage et de la mise en correspondance avec SSIS</span><span class="sxs-lookup"><span data-stu-id="20dcb-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
