---
title: 'Tâche 8 : création d’une règle de domaine composite | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612642"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="c7e28-102">Tâche 8 : Création d’une règle de domaine composite</span><span class="sxs-lookup"><span data-stu-id="c7e28-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="c7e28-103">Dans cette tâche, vous allez créer une règle pour le domaine composite **validation d’adresse** .</span><span class="sxs-lookup"><span data-stu-id="c7e28-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="c7e28-104">Vous définissez une règle inter-domaines : si la **ville** est **Los Angeles**, l' **État** doit être **ca** , où **ville** et **État** sont deux domaines.</span><span class="sxs-lookup"><span data-stu-id="c7e28-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="c7e28-105">Dans le volet droit, basculez vers l’onglet **règles du CD** .</span><span class="sxs-lookup"><span data-stu-id="c7e28-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="c7e28-106">Cliquez sur **Ajouter une nouvelle règle de domaine** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="c7e28-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="c7e28-107">Tapez **règle d’état de ville** pour **nom** , puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="c7e28-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="c7e28-108">Dans le volet **créer une règle** , sélectionnez **City** dans la liste des domaines, puis sélectionnez la **valeur condition est égale à** et tapez **Los Angeles** comme valeur.</span><span class="sxs-lookup"><span data-stu-id="c7e28-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="c7e28-109">Dans le volet **Then** , sélectionnez **State** dans la liste de domaines, puis sélectionnez la **valeur est égale à**, tapez **ca** pour la valeur et appuyez sur **Tab**.</span><span class="sxs-lookup"><span data-stu-id="c7e28-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="c7e28-110">![Règle du domaine composite](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Règle du domaine composite")</span><span class="sxs-lookup"><span data-stu-id="c7e28-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="c7e28-111">Cliquez sur le bouton **Fermer** en bas de la page pour basculer vers la page principale du client DQS.</span><span class="sxs-lookup"><span data-stu-id="c7e28-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="c7e28-112">Vous allez publier la base de connaissances dans la leçon suivante.</span><span class="sxs-lookup"><span data-stu-id="c7e28-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="c7e28-113">Notez que la base de connaissances est à l'état verrouillé (icône de verrou).</span><span class="sxs-lookup"><span data-stu-id="c7e28-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c7e28-114">étape suivante</span><span class="sxs-lookup"><span data-stu-id="c7e28-114">Next Step</span></span>  
 [<span data-ttu-id="c7e28-115">Tâche 9 : Configuration d’un service de données de référence</span><span class="sxs-lookup"><span data-stu-id="c7e28-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
