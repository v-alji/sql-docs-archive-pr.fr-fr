---
title: Propriétés de planification (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603816"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="eb474-102">Propriétés de planification (page Général)</span><span class="sxs-lookup"><span data-stu-id="eb474-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="eb474-103">Utilisez cette page pour afficher ou modifier une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="eb474-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="eb474-104">Les planifications partagées peuvent être utilisées à la place des planifications spécifiques des rapports ou spécifiques des abonnements.</span><span class="sxs-lookup"><span data-stu-id="eb474-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="eb474-105">Les modifications apportées à la planification sont appliquées après l'avoir enregistrée.</span><span class="sxs-lookup"><span data-stu-id="eb474-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="eb474-106">La modification d'une planification n'a aucun effet sur les travaux qui sont actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="eb474-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="eb474-107">Si vous modifiez une planification pendant qu'elle est utilisée, tous les rapports et abonnements en cours de traitement déclenchés par cette planification pourront être menés à bien.</span><span class="sxs-lookup"><span data-stu-id="eb474-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="eb474-108">Toutes les combinaisons de fréquence ne peuvent pas être prises en charge dans une seule planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="eb474-109">Par exemple, si vous souhaitez exécuter un rapport à 12:00</span><span class="sxs-lookup"><span data-stu-id="eb474-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="eb474-110">et 16:00</span><span class="sxs-lookup"><span data-stu-id="eb474-110">and 4:00 P.M.</span></span> <span data-ttu-id="eb474-111">ous les vendredis, vous devez créer deux planifications quotidiennes qui spécifient le vendredi comme jour d'exécution mais avec une heure de début de 12:00 pour l'une</span><span class="sxs-lookup"><span data-stu-id="eb474-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="eb474-112">et une heure de début de 16:00 pour la seconde.</span><span class="sxs-lookup"><span data-stu-id="eb474-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="eb474-113">Le traitement de la planification est basé sur l'heure locale du serveur de rapports qui héberge et traite la planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="eb474-114">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, ouvrez le dossier **Planifications partagées** , cliquez avec le bouton droit sur une planification partagée, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="eb474-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb474-115">Cette fonctionnalité est disponible dans chaque édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et cette page n'apparaît pas lorsque vous exécutez une édition qui n'a pas cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="eb474-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="eb474-116">Pour obtenir la liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [fonctionnalités prises en charge par les éditions de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="eb474-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb474-117">Options</span><span class="sxs-lookup"><span data-stu-id="eb474-117">Options</span></span>  
 <span data-ttu-id="eb474-118">**Nom**</span><span class="sxs-lookup"><span data-stu-id="eb474-118">**Name**</span></span>  
 <span data-ttu-id="eb474-119">Indique le nom de la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="eb474-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="eb474-120">**Commencer l'exécution de cette planification le**</span><span class="sxs-lookup"><span data-stu-id="eb474-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="eb474-121">Spécifie la date de début de cette planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="eb474-122">**Arrêter cette planification le**</span><span class="sxs-lookup"><span data-stu-id="eb474-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="eb474-123">Spécifie la date d'expiration de cette planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="eb474-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="eb474-124">**Type**</span></span>  
 <span data-ttu-id="eb474-125">Spécifie si la périodicité est basée essentiellement sur les heures, jours, semaines, mois, ou si elle n'est définie qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="eb474-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="eb474-126">**Heure (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="eb474-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="eb474-127">Spécifie les options d'exécution d'une opération planifiée par intervalles d'une heure (par exemple, pour exécuter un rapport toutes les 6 heures).</span><span class="sxs-lookup"><span data-stu-id="eb474-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="eb474-128">Vous pouvez préciser l'intervalle en heures et en minutes.</span><span class="sxs-lookup"><span data-stu-id="eb474-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="eb474-129">**Jour (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="eb474-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="eb474-130">Spécifie les options d'exécution d'une opération planifiée par intervalles d'un jour (par exemple, pour exécuter un rapport tous les 2 jours).</span><span class="sxs-lookup"><span data-stu-id="eb474-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="eb474-131">Vous pouvez spécifier l'intervalle en jours et à l'heure à laquelle vous voulez exécuter la planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="eb474-132">**Semaine (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="eb474-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="eb474-133">Spécifie les options d'exécution d'une opération planifiée par intervalles d'une semaine ou lorsque la périodicité à répéter est en semaines (par exemple, pour exécuter un rapport une semaine sur deux).</span><span class="sxs-lookup"><span data-stu-id="eb474-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="eb474-134">Vous pouvez spécifier une planification hebdomadaire au jour et à l'heure où vous voulez l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="eb474-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="eb474-135">**Mois (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="eb474-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="eb474-136">Spécifie les options d'exécution d'une opération planifiée par intervalles d'un mois ou lorsque la périodicité à répéter est en mois.</span><span class="sxs-lookup"><span data-stu-id="eb474-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="eb474-137">Vous pouvez spécifier une planification mensuelle au jour et à l'heure où vous voulez l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="eb474-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="eb474-138">Vous pouvez ignorer certains mois dans la planification.</span><span class="sxs-lookup"><span data-stu-id="eb474-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="eb474-139">**Une fois**</span><span class="sxs-lookup"><span data-stu-id="eb474-139">**Once**</span></span>  
 <span data-ttu-id="eb474-140">Spécifie une planification exécutée une fois seulement, à une date et une heure spécifiques.</span><span class="sxs-lookup"><span data-stu-id="eb474-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb474-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb474-141">See Also</span></span>  
 <span data-ttu-id="eb474-142">[Serveur de rapports dans Management Studio aide (F1)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="eb474-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="eb474-143">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="eb474-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="eb474-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="eb474-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="eb474-145">Planifications</span><span class="sxs-lookup"><span data-stu-id="eb474-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
