---
title: Tâches au niveau système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707015"
---
# <a name="system-level-tasks"></a><span data-ttu-id="f5451-102">Tâches au niveau système</span><span class="sxs-lookup"><span data-stu-id="f5451-102">System-Level Tasks</span></span>
  <span data-ttu-id="f5451-103">Une tâche de niveau système est une collection d'autorisations liées à des opérations qui s'appliquent au site du serveur de rapports dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="f5451-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f5451-104">inclut aussi des tâches au niveau élément qui s’appliquent à des éléments spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f5451-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="f5451-105">Pour plus d’informations, consultez [Tâches au niveau élément](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f5451-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="f5451-106">Pour plus d'informations sur les tâches et les autorisations en général, consultez [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f5451-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5451-107">Si vous travaillez avec ces tâches par programmation, vous devez utiliser des méthodes qui prennent en charge les tâches au niveau système.</span><span class="sxs-lookup"><span data-stu-id="f5451-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="f5451-108">Pour plus d’informations, consultez <xref:ReportService2010.ReportingService2010.ListTasks%2A> et <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5451-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="f5451-109">Autorisations dans les tâches de niveau système</span><span class="sxs-lookup"><span data-stu-id="f5451-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="f5451-110">Le tableau suivant identifie la collection d'autorisations pour chaque tâche système.</span><span class="sxs-lookup"><span data-stu-id="f5451-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="f5451-111">Les autorisations sont répertoriées à titre d'informations uniquement, afin de fournir une description plus exacte de la fonctionnalité disponible via chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="f5451-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="f5451-112">Tâche</span><span class="sxs-lookup"><span data-stu-id="f5451-112">Task</span></span>|<span data-ttu-id="f5451-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f5451-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f5451-114">Exécuter les définitions de rapport</span><span class="sxs-lookup"><span data-stu-id="f5451-114">Execute report definitions</span></span>|<span data-ttu-id="f5451-115">Exécuter les définitions de rapport (l'autorisation et la tâche portent le même nom)</span><span class="sxs-lookup"><span data-stu-id="f5451-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="f5451-116">Générer des événements</span><span class="sxs-lookup"><span data-stu-id="f5451-116">Generate events</span></span>|<span data-ttu-id="f5451-117">Générer des événements</span><span class="sxs-lookup"><span data-stu-id="f5451-117">Generate Events</span></span>|  
|<span data-ttu-id="f5451-118">Gestion des travaux</span><span class="sxs-lookup"><span data-stu-id="f5451-118">Manage jobs</span></span>|<span data-ttu-id="f5451-119">Lire les propriétés système</span><span class="sxs-lookup"><span data-stu-id="f5451-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="f5451-120">Mettre à jour les propriétés système</span><span class="sxs-lookup"><span data-stu-id="f5451-120">Update System Properties</span></span>|  
|<span data-ttu-id="f5451-121">Gérer les propriétés du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f5451-121">Manage report server properties</span></span>|<span data-ttu-id="f5451-122">Lire les propriétés système</span><span class="sxs-lookup"><span data-stu-id="f5451-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="f5451-123">Mettre à jour les propriétés système</span><span class="sxs-lookup"><span data-stu-id="f5451-123">Update System Properties</span></span>|  
|<span data-ttu-id="f5451-124">Gérer les rôles</span><span class="sxs-lookup"><span data-stu-id="f5451-124">Manage roles</span></span>|<span data-ttu-id="f5451-125">Créer les rôles</span><span class="sxs-lookup"><span data-stu-id="f5451-125">Create Roles</span></span><br /><br /> <span data-ttu-id="f5451-126">Supprimer les rôles</span><span class="sxs-lookup"><span data-stu-id="f5451-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="f5451-127">Lire les propriétés des rôles</span><span class="sxs-lookup"><span data-stu-id="f5451-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="f5451-128">Mettre à jour les propriétés des rôles</span><span class="sxs-lookup"><span data-stu-id="f5451-128">Update Role Properties</span></span>|  
|<span data-ttu-id="f5451-129">Gérer les planifications partagées</span><span class="sxs-lookup"><span data-stu-id="f5451-129">Manage shared schedules</span></span>|<span data-ttu-id="f5451-130">Créer les planifications</span><span class="sxs-lookup"><span data-stu-id="f5451-130">Create Schedules</span></span>|  
|<span data-ttu-id="f5451-131">Gérer la sécurité du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f5451-131">Manage report server security</span></span>|<span data-ttu-id="f5451-132">Lire les stratégies de sécurité du système</span><span class="sxs-lookup"><span data-stu-id="f5451-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="f5451-133">Mettre à jour les stratégies de sécurité du système</span><span class="sxs-lookup"><span data-stu-id="f5451-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="f5451-134">Afficher les propriétés du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f5451-134">View report server properties</span></span>|<span data-ttu-id="f5451-135">Lire les propriétés système</span><span class="sxs-lookup"><span data-stu-id="f5451-135">Read System Properties</span></span>|  
|<span data-ttu-id="f5451-136">Afficher les planifications partagées</span><span class="sxs-lookup"><span data-stu-id="f5451-136">View shared schedules</span></span>|<span data-ttu-id="f5451-137">Lire les planifications</span><span class="sxs-lookup"><span data-stu-id="f5451-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5451-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5451-138">See Also</span></span>  
 [<span data-ttu-id="f5451-139">Octroi d'autorisations sur un serveur de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="f5451-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
