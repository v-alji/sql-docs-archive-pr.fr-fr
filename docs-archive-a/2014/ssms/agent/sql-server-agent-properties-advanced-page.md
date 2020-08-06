---
title: Propriétés de SQL Server Agent (page Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613268"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="5eb18-102">Propriétés de l'Agent SQL Server (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="5eb18-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="5eb18-103">Utilisez cette page pour afficher et modifier les propriétés avancées du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service agent.</span><span class="sxs-lookup"><span data-stu-id="5eb18-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5eb18-104">Options</span><span class="sxs-lookup"><span data-stu-id="5eb18-104">Options</span></span>  
 <span data-ttu-id="5eb18-105">**Transfert d'événements SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5eb18-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="5eb18-106">Les options de cette catégorie permettent d'activer et de configurer le transfert d'événements.</span><span class="sxs-lookup"><span data-stu-id="5eb18-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="5eb18-107">**Transférer les événements sur un autre serveur**</span><span class="sxs-lookup"><span data-stu-id="5eb18-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="5eb18-108">Transfère les événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sur un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="5eb18-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="5eb18-109">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="5eb18-109">**Server**</span></span>  
 <span data-ttu-id="5eb18-110">Sélectionnez le nom du serveur sur lequel vous voulez transférer les événements.</span><span class="sxs-lookup"><span data-stu-id="5eb18-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="5eb18-111">**Événements non gérés**</span><span class="sxs-lookup"><span data-stu-id="5eb18-111">**Unhandled events**</span></span>  
 <span data-ttu-id="5eb18-112">Transfère uniquement les événements non gérés sur le serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="5eb18-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5eb18-113">Agent transfère uniquement les événements auxquels aucune alerte ne répond.</span><span class="sxs-lookup"><span data-stu-id="5eb18-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="5eb18-114">**Tous les événements**</span><span class="sxs-lookup"><span data-stu-id="5eb18-114">**All events**</span></span>  
 <span data-ttu-id="5eb18-115">Transfère tous les événements.</span><span class="sxs-lookup"><span data-stu-id="5eb18-115">Forwards all events.</span></span> <span data-ttu-id="5eb18-116">Si une alerte répond à l'événement dans l'instance locale, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent transfère l'événement et traite l'alerte.</span><span class="sxs-lookup"><span data-stu-id="5eb18-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="5eb18-117">**Si l'événement a une gravité au moins égale à**</span><span class="sxs-lookup"><span data-stu-id="5eb18-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="5eb18-118">Transfère uniquement les événements dont le niveau de gravité est supérieur ou égal au niveau spécifié.</span><span class="sxs-lookup"><span data-stu-id="5eb18-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="5eb18-119">**Condition d'inactivité de l'UC**</span><span class="sxs-lookup"><span data-stu-id="5eb18-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="5eb18-120">Les options de cette catégorie définissent les conditions dans lesquelles [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent exécute les travaux dont l'exécution est planifiée pendant l'inactivité de l'UC.</span><span class="sxs-lookup"><span data-stu-id="5eb18-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="5eb18-121">**Définir la condition d'inactivité de l'UC**</span><span class="sxs-lookup"><span data-stu-id="5eb18-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="5eb18-122">Définit les conditions dans lesquelles [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considère que l'UC est inactive.</span><span class="sxs-lookup"><span data-stu-id="5eb18-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="5eb18-123">**La moyenne d'utilisation de l'UC tombe en dessous de**</span><span class="sxs-lookup"><span data-stu-id="5eb18-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="5eb18-124">Pourcentage d'utilisation de l'UC au-dessous duquel l'UC est considérée comme inactive.</span><span class="sxs-lookup"><span data-stu-id="5eb18-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="5eb18-125">**Et reste sous ce niveau pendant**</span><span class="sxs-lookup"><span data-stu-id="5eb18-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="5eb18-126">Durée pendant laquelle la moyenne d'utilisation de l'UC doit rester au-dessous du niveau spécifié avant que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent démarre l'exécution des travaux planifiés pendant l'inactivité de l'UC.</span><span class="sxs-lookup"><span data-stu-id="5eb18-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb18-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5eb18-127">See Also</span></span>  
 <span data-ttu-id="5eb18-128">[Créer et attacher des planifications à des travaux](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="5eb18-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="5eb18-129">Gérer les événements</span><span class="sxs-lookup"><span data-stu-id="5eb18-129">Manage Events</span></span>](manage-events.md)  
  
  
