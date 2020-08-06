---
title: Guide du développeur&#39;s (réplication) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705071"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="9a1ba-102">Guide du développeur&#39;s (réplication)</span><span class="sxs-lookup"><span data-stu-id="9a1ba-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="9a1ba-103">La possibilité de configurer, de gérer et d'analyser par programme une topologie de réplication entraîne la simplification des tâches de réplication répétitives et l'amélioration de l'expérience utilisateur pour vos applications basées sur la réplication.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="9a1ba-104">Grâce à la programmation de la réplication, les utilisateurs finaux peuvent bénéficier de fonctionnalités de réplication personnalisées sans avoir à connaître les procédures stockées de réplication et les fichiers exécutables de l'Agent de réplication. Ils n'ont pas non plus besoin d'utiliser l'interface utilisateur pour la réplication implémentée par [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a1ba-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9a1ba-105">Un accès par programme aux services de réplication peut être utile pour vos applications dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a1ba-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="9a1ba-106">Ajout de fonctionnalités de réplication à une application existante pour utilisateur final, telles que la synchronisation d'un abonnement par extraction de données lorsque l'utilisateur clique sur un bouton.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="9a1ba-107">Création d'une interface utilisateur Web pour administrer la réplication à distance.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="9a1ba-108">Création d'une interface utilisateur personnalisée qui expose uniquement une partie des fonctionnalités d'administration (pour administrer à distance plusieurs topologies de réplication à partir d'un même emplacement) ou qui associe des fonctionnalités d'administration et de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="9a1ba-109">Amélioration d'un outil d'analyse existant en intégrant la possibilité d'analyser l'état d'une publication, d'un abonnement ou au niveau du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="9a1ba-110">Création d'une application personnalisée pour administrer ou synchroniser des abonnements sur un serveur de publication Oracle.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="9a1ba-111">Écriture de règles d'entreprise personnalisées qui sont exécutées lors de la synchronisation d'un abonnement de fusion.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="9a1ba-112">Génération de scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] pouvant être exécutés à plusieurs reprises lors de la configuration de nouveaux abonnés.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9a1ba-113">vous permet non seulement de contrôler par programme les agents de réplication, mais aussi d'administrer et d'analyser par programme une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-113">enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="9a1ba-114">Pour en savoir plus sur la programmation de la réplication, consultez [Concepts de programmation en matière de réplication](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="9a1ba-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a1ba-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9a1ba-115">In This Section</span></span>  
 [<span data-ttu-id="9a1ba-116">Concepts de programmation en matière de réplication</span><span class="sxs-lookup"><span data-stu-id="9a1ba-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="9a1ba-117">Décrit les étapes de planification permettant de développer une application qui utilise la réplication.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="9a1ba-118">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="9a1ba-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="9a1ba-119">Décrit comment les procédures stockées système peuvent être utilisées pour assurer un accès par programme dans une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="9a1ba-120">Concepts liés à Replication Management Objects</span><span class="sxs-lookup"><span data-stu-id="9a1ba-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="9a1ba-121">Explique les concepts relatifs à l'utilisation de Replication Management Objects.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="9a1ba-122">Il s'agit d'un assembly de code managé qui encapsule les fonctionnalités de réplication pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a1ba-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="9a1ba-123">Concepts des exécutables de l'agent de réplication</span><span class="sxs-lookup"><span data-stu-id="9a1ba-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="9a1ba-124">Décrit l'utilisation des fichiers exécutables de l'Agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="9a1ba-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
