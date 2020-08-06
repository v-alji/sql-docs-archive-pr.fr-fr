---
title: Nouvelle planification partagée (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newschedule.f1
ms.assetid: b2c69586-d98e-4933-827d-f5e6c15c5203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6afd406730f815d3ab61e59cdebd21d564daa74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603246"
---
# <a name="new-shared-schedule-management-studio"></a><span data-ttu-id="4bac4-102">Nouvelle planification partagée (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4bac4-102">New Shared Schedule (Management Studio)</span></span>
  <span data-ttu-id="4bac4-103">Utilisez cette page pour créer une planification partagée pour exécuter les rapports publiés et les abonnements.</span><span class="sxs-lookup"><span data-stu-id="4bac4-103">Use this page to create a shared schedule to run published reports and subscriptions.</span></span> <span data-ttu-id="4bac4-104">Les planifications partagées peuvent être utilisées à la place des planifications spécifiques des rapports ou spécifiques des abonnements.</span><span class="sxs-lookup"><span data-stu-id="4bac4-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="4bac4-105">Des informations de planification centralisées et la capacité de suspendre et de reprendre les opérations planifiées sont deux fonctionnalités clés qui distinguent les planifications partagées des planifications spécifiques aux éléments.</span><span class="sxs-lookup"><span data-stu-id="4bac4-105">Centralized schedule information and the ability to pause and resume scheduled operations are two key features that distinguish shared schedules from item-specific schedules.</span></span>  
  
 <span data-ttu-id="4bac4-106">Toutes les combinaisons de fréquence ne peuvent pas être prises en charge dans une seule planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-106">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="4bac4-107">Par exemple, si vous souhaitez exécuter un rapport à 12:00</span><span class="sxs-lookup"><span data-stu-id="4bac4-107">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="4bac4-108">et 16:00</span><span class="sxs-lookup"><span data-stu-id="4bac4-108">and 4:00 P.M.</span></span> <span data-ttu-id="4bac4-109">ous les vendredis, vous devez créer deux planifications quotidiennes qui spécifient le vendredi comme jour d'exécution mais avec une heure de début de 12:00 pour l'une</span><span class="sxs-lookup"><span data-stu-id="4bac4-109">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="4bac4-110">et une heure de début de 16:00 pour la seconde.</span><span class="sxs-lookup"><span data-stu-id="4bac4-110">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="4bac4-111">Le traitement de la planification est basé sur l'heure locale du serveur de rapports qui héberge et traite la planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-111">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="4bac4-112">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, cliquez avec le bouton droit sur **Planification partagée**et sélectionnez **Nouvelle planification**.</span><span class="sxs-lookup"><span data-stu-id="4bac4-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Shared Schedule**, and select **New Schedule**.</span></span> <span data-ttu-id="4bac4-113">Pour enregistrer la planification, le service Agent SQL Server doit être en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="4bac4-113">To save the schedule, SQL Server Agent service must be running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bac4-114">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bac4-114">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bac4-115">Pour obtenir la liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Fonctionnalités prises en charge par les éditions de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span><span class="sxs-lookup"><span data-stu-id="4bac4-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4bac4-116">Options</span><span class="sxs-lookup"><span data-stu-id="4bac4-116">Options</span></span>  
 <span data-ttu-id="4bac4-117">**Nom**</span><span class="sxs-lookup"><span data-stu-id="4bac4-117">**Name**</span></span>  
 <span data-ttu-id="4bac4-118">Tapez le nom de la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="4bac4-118">Type a name for the shared schedule.</span></span> <span data-ttu-id="4bac4-119">Ce nom apparaît dans les listes déroulantes lorsque les utilisateurs sélectionnent une planification partagée pour les rapports et les abonnements.</span><span class="sxs-lookup"><span data-stu-id="4bac4-119">This name appears in drop-down lists when users select a shared schedule for reports and subscriptions.</span></span> <span data-ttu-id="4bac4-120">Veillez à fournir un nom descriptif qui s'ajuste facilement dans une liste et qui distingue aisément une planification partagée d'une autre.</span><span class="sxs-lookup"><span data-stu-id="4bac4-120">Be sure to provide a descriptive name that fits easily within a list and that easily distinguishes one shared schedule from another.</span></span> <span data-ttu-id="4bac4-121">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="4bac4-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="4bac4-122">Il peut également comporter des espaces et quelques symboles.</span><span class="sxs-lookup"><span data-stu-id="4bac4-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="4bac4-123">N'utilisez pas les caractères suivants dans le nom :</span><span class="sxs-lookup"><span data-stu-id="4bac4-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="4bac4-124">; ?</span><span class="sxs-lookup"><span data-stu-id="4bac4-124">; ?</span></span> <span data-ttu-id="4bac4-125">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="4bac4-125">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="4bac4-126">" /</span><span class="sxs-lookup"><span data-stu-id="4bac4-126">" /</span></span>  
  
 <span data-ttu-id="4bac4-127">**Commencer l'exécution de cette planification le**</span><span class="sxs-lookup"><span data-stu-id="4bac4-127">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="4bac4-128">Spécifiez la date de début de cette planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-128">Specify a start date for this schedule.</span></span>  
  
 <span data-ttu-id="4bac4-129">**Arrêter cette planification le**</span><span class="sxs-lookup"><span data-stu-id="4bac4-129">**Stop this schedule on**</span></span>  
 <span data-ttu-id="4bac4-130">Spécifiez la date d'expiration de cette planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-130">Specify an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="4bac4-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="4bac4-131">**Type**</span></span>  
 <span data-ttu-id="4bac4-132">Spécifie si la périodicité est basée essentiellement sur les heures, jours, semaines ou mois.</span><span class="sxs-lookup"><span data-stu-id="4bac4-132">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, or months.</span></span>  
  
 <span data-ttu-id="4bac4-133">**Heure (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="4bac4-133">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="4bac4-134">Sélectionnez les options d'exécution d'une opération planifiée par intervalles d'une heure (par exemple, pour exécuter un rapport toutes les 6 heures).</span><span class="sxs-lookup"><span data-stu-id="4bac4-134">Select options to run a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="4bac4-135">Vous pouvez préciser l'intervalle en heures et en minutes.</span><span class="sxs-lookup"><span data-stu-id="4bac4-135">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="4bac4-136">**Jour (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="4bac4-136">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="4bac4-137">Sélectionnez les options d'exécution d'une opération planifiée par intervalles d'un jour (par exemple, pour exécuter un rapport tous les 2 jours).</span><span class="sxs-lookup"><span data-stu-id="4bac4-137">Select options to run a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="4bac4-138">Vous pouvez spécifier l'intervalle en jours et à l'heure à laquelle vous voulez exécuter la planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-138">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="4bac4-139">**Semaine (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="4bac4-139">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="4bac4-140">Sélectionnez les options d'exécution d'une opération planifiée par intervalles d'une semaine ou lorsque la périodicité à répéter est en semaines (par exemple, pour exécuter un rapport une semaine sur deux).</span><span class="sxs-lookup"><span data-stu-id="4bac4-140">Select options to run a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="4bac4-141">Vous pouvez spécifier une planification hebdomadaire au jour et à l'heure où vous voulez l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="4bac4-141">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="4bac4-142">**Mois (Modèle de récurrence)**</span><span class="sxs-lookup"><span data-stu-id="4bac4-142">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="4bac4-143">Sélectionnez les options d'exécution d'une opération planifiée par intervalles d'un mois ou lorsque la périodicité à répéter est en mois.</span><span class="sxs-lookup"><span data-stu-id="4bac4-143">Select options to run a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="4bac4-144">Vous pouvez spécifier une planification mensuelle au jour et à l'heure où vous voulez l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="4bac4-144">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="4bac4-145">Vous pouvez ignorer certains mois dans la planification.</span><span class="sxs-lookup"><span data-stu-id="4bac4-145">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="4bac4-146">**Une fois**</span><span class="sxs-lookup"><span data-stu-id="4bac4-146">**Once**</span></span>  
 <span data-ttu-id="4bac4-147">Sélectionnez cette option pour créer une planification exécutée une seule fois, à une date et une heure spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4bac4-147">Select this option to create a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bac4-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bac4-148">See Also</span></span>  
 <span data-ttu-id="4bac4-149">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4bac4-149">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="4bac4-150">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4bac4-150">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="4bac4-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="4bac4-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="4bac4-152">[Planifications](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="4bac4-152">[Schedules](../subscriptions/schedules.md) </span></span>  
 [<span data-ttu-id="4bac4-153">Aide du serveur de rapports dans Management Studio via la touche F1</span><span class="sxs-lookup"><span data-stu-id="4bac4-153">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
