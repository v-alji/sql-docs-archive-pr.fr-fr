---
title: Méthodes de planification | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601878"
---
# <a name="scheduling-methods"></a><span data-ttu-id="8b065-102">Méthodes de planification</span><span class="sxs-lookup"><span data-stu-id="8b065-102">Scheduling Methods</span></span>
  <span data-ttu-id="8b065-103">Vous pouvez utiliser ces méthodes pour créer et gérer des planifications partagées pour l'exécution et la remise de rapports, et pour mettre en cache des plans d'actualisation utilisés par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8b065-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="8b065-104">Méthode</span><span class="sxs-lookup"><span data-stu-id="8b065-104">Method</span></span>|<span data-ttu-id="8b065-105">Action</span><span class="sxs-lookup"><span data-stu-id="8b065-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="8b065-106">Crée un plan d'actualisation du cache pour un élément.</span><span class="sxs-lookup"><span data-stu-id="8b065-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="8b065-107">Crée une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="8b065-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="8b065-108">Supprime un plan d'actualisation du cache.</span><span class="sxs-lookup"><span data-stu-id="8b065-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="8b065-109">Supprime une planification partagée en fonction de son ID.</span><span class="sxs-lookup"><span data-stu-id="8b065-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="8b065-110">Retourne les propriétés du plan d'actualisation du cache spécifié.</span><span class="sxs-lookup"><span data-stu-id="8b065-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="8b065-111">Retourne les valeurs des propriétés d'une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="8b065-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="8b065-112">Retourne une liste des plans d'actualisation du cache associés à un élément de catalogue.</span><span class="sxs-lookup"><span data-stu-id="8b065-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="8b065-113">Retourne une liste des éléments associés à une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="8b065-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="8b065-114">Retourne une liste de toutes les planifications partagées du serveur de rapports ou du site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b065-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="8b065-115">Retourne une liste d'états de planification pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8b065-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="8b065-116">Suspend l'exécution d'une planification donnée.</span><span class="sxs-lookup"><span data-stu-id="8b065-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="8b065-117">Reprend une planification partagée qui a été suspendue.</span><span class="sxs-lookup"><span data-stu-id="8b065-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="8b065-118">Définit les propriétés d'un plan d'actualisation du cache.</span><span class="sxs-lookup"><span data-stu-id="8b065-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="8b065-119">Définit la valeur des propriétés d'une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="8b065-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b065-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b065-120">See Also</span></span>  
 <span data-ttu-id="8b065-121">[Création d’applications à l’aide du service web et du .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="8b065-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="8b065-122">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="8b065-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="8b065-123">[Méthodes du service web Report Server](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="8b065-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="8b065-124">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8b065-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
