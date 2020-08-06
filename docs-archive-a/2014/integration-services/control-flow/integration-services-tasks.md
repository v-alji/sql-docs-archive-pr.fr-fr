---
title: Tâches Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604074"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="053c7-102">Tâches Integration Services</span><span class="sxs-lookup"><span data-stu-id="053c7-102">Integration Services Tasks</span></span>
  <span data-ttu-id="053c7-103">Les tâches sont des éléments de flux de contrôle qui définissent des unités de travail qui sont exécutées dans un flux de contrôle de package.</span><span class="sxs-lookup"><span data-stu-id="053c7-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="053c7-104">Un package [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est composé d’une ou plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="053c7-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="053c7-105">Si le package contient plusieurs tâches, elles sont connectées et organisées dans le flux de contrôle par des contraintes de priorité.</span><span class="sxs-lookup"><span data-stu-id="053c7-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="053c7-106">Vous pouvez également écrire des tâches personnalisées à l'aide d'un langage de programmation qui prend en charge COM, tel que Visual Basic, ou d'un langage de programmation .NET, tel que C#.</span><span class="sxs-lookup"><span data-stu-id="053c7-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="053c7-107">Le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)], outil graphique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permettant de manipuler les packages, met à votre disposition une aire de conception pour la création des flux de contrôle de package, ainsi que des éditeurs personnalisés pour la configuration des tâches.</span><span class="sxs-lookup"><span data-stu-id="053c7-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="053c7-108">Vous pouvez aussi programmer le modèle objet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour créer des packages par programmation.</span><span class="sxs-lookup"><span data-stu-id="053c7-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="053c7-109">Types de tâches</span><span class="sxs-lookup"><span data-stu-id="053c7-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="053c7-110">comprend les types de tâches suivants.</span><span class="sxs-lookup"><span data-stu-id="053c7-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="053c7-111">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="053c7-111">Data Flow Task</span></span>  
 <span data-ttu-id="053c7-112">Tâche qui exécute les flux de données pour extraire les données, pour appliquer les transformations au niveau des colonnes et pour charger des données.</span><span class="sxs-lookup"><span data-stu-id="053c7-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="053c7-113">Tâches de préparation des données</span><span class="sxs-lookup"><span data-stu-id="053c7-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="053c7-114">Ces tâches effectuent les processus suivants : copie de fichiers et de répertoires, téléchargement de fichiers et de données, exécution de méthodes Web, application d'opérations aux documents XML et profilage des données à des fins de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="053c7-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="053c7-115">Tâches de flux de travail</span><span class="sxs-lookup"><span data-stu-id="053c7-115">Workflow Tasks</span></span>  
 <span data-ttu-id="053c7-116">Tâches qui communiquent avec d'autres processus pour exécuter les packages, exécuter les programmes ou les fichiers de commandes, gérer les échanges de messages entre les packages, envoyer des messages électroniques, lire les données WMI (Windows Management Instrumentation) et observer les événements WMI.</span><span class="sxs-lookup"><span data-stu-id="053c7-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="053c7-117">Tâches SQL Server</span><span class="sxs-lookup"><span data-stu-id="053c7-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="053c7-118">Tâches qui accèdent aux objets et aux données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , et qui les copient, les insèrent, les suppriment et les modifient.</span><span class="sxs-lookup"><span data-stu-id="053c7-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="053c7-119">Tâches de script</span><span class="sxs-lookup"><span data-stu-id="053c7-119">Scripting Tasks</span></span>  
 <span data-ttu-id="053c7-120">Tâches qui étendent les fonctionnalités des packages à l'aide de scripts.</span><span class="sxs-lookup"><span data-stu-id="053c7-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="053c7-121">Tâches Analysis Services</span><span class="sxs-lookup"><span data-stu-id="053c7-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="053c7-122">Tâches qui créent, modifient, suppriment et traitent les objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="053c7-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="053c7-123">Tâches de maintenance</span><span class="sxs-lookup"><span data-stu-id="053c7-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="053c7-124">Tâches qui réalisent des fonctions d'administration telles que la sauvegarde et la réduction des bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la reconstruction et la réorganisation des index ou l'exécution des travaux d'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="053c7-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="053c7-125">Tâches personnalisées</span><span class="sxs-lookup"><span data-stu-id="053c7-125">Custom Tasks</span></span>  
 <span data-ttu-id="053c7-126">Vous pouvez aussi écrire des tâches personnalisées à l'aide d'un langage de programmation qui prend en charge COM, tel que Visual Basic, ou d'un langage de programmation .NET, tel que C#.</span><span class="sxs-lookup"><span data-stu-id="053c7-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="053c7-127">Si vous voulez accéder à votre tâche personnalisée dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vous pouvez créer et inscrire une interface utilisateur pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="053c7-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="053c7-128">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="053c7-129">Configuration des tâches</span><span class="sxs-lookup"><span data-stu-id="053c7-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="053c7-130">Un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] peut contenir une seule tâche, par exemple une tâche d'exécution SQL qui supprime des enregistrements dans une table de base de données lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="053c7-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="053c7-131">Les packages contiennent cependant en général plusieurs tâches et chacune d'elles est définie de manière à être exécutée dans le contexte du flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="053c7-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="053c7-132">Les gestionnaires d'événements, qui sont des flux de travail exécutés en réponse aux événements d'exécution, peuvent également avoir des tâches.</span><span class="sxs-lookup"><span data-stu-id="053c7-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="053c7-133">Pour plus d’informations sur l’ajout d’une tâche à un package à l’aide du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="053c7-134">Pour plus d’informations sur l’ajout d'une tâche à un package par programmation, consultez [Ajout de tâches par programme](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="053c7-135">Chaque tâche peut être configurée séparément à l’aide des boîtes de dialogue personnalisées du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou de la fenêtre Propriétés de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="053c7-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="053c7-136">Un package peut contenir plusieurs tâches du même type (par exemple, six tâches d’exécution SQL) et chaque tâche peut être configurée différemment.</span><span class="sxs-lookup"><span data-stu-id="053c7-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="053c7-137">Pour plus d’informations, consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="053c7-138">Connexions et groupes des tâches</span><span class="sxs-lookup"><span data-stu-id="053c7-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="053c7-139">Si la tâche contient plusieurs tâches, elles sont connectées et organisées dans le flux de contrôle par des contraintes de priorité.</span><span class="sxs-lookup"><span data-stu-id="053c7-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="053c7-140">Pour plus d’informations, consultez [Contraintes de précédence](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="053c7-141">Les tâches peuvent être regroupées et exécutées en tant qu'unité de travail unique ou répétées dans une boucle.</span><span class="sxs-lookup"><span data-stu-id="053c7-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="053c7-142">Pour plus d’informations, consultez [Conteneur de boucles Foreach](foreach-loop-container.md), [Conteneur de boucles For](for-loop-container.md)et [Conteneur de séquences](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="053c7-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="053c7-143">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="053c7-143">Related Tasks</span></span>  
 [<span data-ttu-id="053c7-144">Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="053c7-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
