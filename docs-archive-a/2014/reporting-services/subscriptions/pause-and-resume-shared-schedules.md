---
title: Suspendre et reprendre des planifications partagées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610417"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="ed276-102">Pause and Resume Shared Schedules</span><span class="sxs-lookup"><span data-stu-id="ed276-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="ed276-103">Vous pouvez suspendre et reprendre une planification partagée en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="ed276-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="ed276-104">Le fait de suspendre une planification partagée fournit un moyen de geler temporairement une planification qui est utilisée pour déclencher un traitement de rapport et des abonnements.</span><span class="sxs-lookup"><span data-stu-id="ed276-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="ed276-105">Seules les planifications partagées peuvent être suspendues et reprises.</span><span class="sxs-lookup"><span data-stu-id="ed276-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="ed276-106">Vous ne pouvez pas suspendre des planifications spécifiques aux rapports.</span><span class="sxs-lookup"><span data-stu-id="ed276-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="ed276-107">Vous ne pouvez pas suspendre et reprendre un traitement de rapport en cours.</span><span class="sxs-lookup"><span data-stu-id="ed276-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="ed276-108">Vous ne pouvez suspendre et reprendre que les planifications faisant partie de la file d'attente des planifications du service Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed276-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="ed276-109">Un travail en cours ne fait pas partie du champ d'intervention du moteur de planification.</span><span class="sxs-lookup"><span data-stu-id="ed276-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="ed276-110">Pour plus d’informations, consultez [Gérer un processus en cours d’exécution](manage-a-running-process.md).</span><span class="sxs-lookup"><span data-stu-id="ed276-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="ed276-111">Pendant qu'une planification partagée est suspendue, toutes les opérations censées s'exécuter sont temporairement autorisées à ne pas avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="ed276-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="ed276-112">Lorsque vous reprenez une planification partagée, le traitement du rapport et de la planification se produit à l'heure planifiée suivante, en fonction de l'heure locale du serveur.</span><span class="sxs-lookup"><span data-stu-id="ed276-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="ed276-113">Le serveur de rapports en mode natif ou les applications de service SharePoint n'effectuent pas les opérations planifiées qui étaient censées s'exécuter si la planification n'avait pas été suspendue.</span><span class="sxs-lookup"><span data-stu-id="ed276-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="ed276-114">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="ed276-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="ed276-115">Suspendre et reprendre des planifications partagées (mode natif)</span><span class="sxs-lookup"><span data-stu-id="ed276-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="ed276-116">Suspendre et reprendre des planifications partagées (mode SharePoint)</span><span class="sxs-lookup"><span data-stu-id="ed276-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="ed276-117">Suspendre et reprendre des planifications partagées (mode natif)</span><span class="sxs-lookup"><span data-stu-id="ed276-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="ed276-118">Pour suspendre et reprendre une planification partagée, utilisez la page Planifications du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="ed276-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="ed276-119">Vous ne pouvez pas utiliser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ; ce dernier n'a pas les options nécessaires pour vous permettre de suspendre et de reprendre des planifications.</span><span class="sxs-lookup"><span data-stu-id="ed276-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="ed276-120">Pour plus d’informations, consultez [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="ed276-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="ed276-121">Pour suspendre ou reprendre une planification partagée</span><span class="sxs-lookup"><span data-stu-id="ed276-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="ed276-122">Dans le Gestionnaire de rapports, cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="ed276-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="ed276-123">Cliquez sur **Planifications**.</span><span class="sxs-lookup"><span data-stu-id="ed276-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="ed276-124">Sélectionnez la planification, puis cliquez sur **Suspendre** ou **Reprendre** dans le Ruban.</span><span class="sxs-lookup"><span data-stu-id="ed276-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="ed276-125">Si une planification est actuellement suspendue, la colonne **État** contient **Suspendu**.</span><span class="sxs-lookup"><span data-stu-id="ed276-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="ed276-126">Suspendre et reprendre des planifications partagées (mode SharePoint)</span><span class="sxs-lookup"><span data-stu-id="ed276-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="ed276-127">Pour suspendre et reprendre une planification partagée, utilisez la page Paramètres du site ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed276-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="ed276-128">Les planifications sont gérées en fonction de chaque site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed276-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="ed276-129">Pour suspendre ou reprendre une planification partagée</span><span class="sxs-lookup"><span data-stu-id="ed276-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="ed276-130">Cliquez sur **Actions du site**.</span><span class="sxs-lookup"><span data-stu-id="ed276-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="ed276-131">Cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="ed276-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="ed276-132">Dans la section Reporting Services, cliquez sur **Gérer les planifications partagées**.</span><span class="sxs-lookup"><span data-stu-id="ed276-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="ed276-133">Sélectionnez la planification, puis cliquez sur **Suspendre les planifications sélectionnées** ou sur **Exécuter les planifications sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="ed276-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="ed276-134">Si une planification est actuellement suspendue, la colonne **État** contient **Suspendu**.</span><span class="sxs-lookup"><span data-stu-id="ed276-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed276-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed276-135">See Also</span></span>  
 <span data-ttu-id="ed276-136">[Planifications](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="ed276-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="ed276-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="ed276-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="ed276-138">[Modifier les fuseaux horaires et les paramètres d’horloge sur un serveur de rapports](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed276-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="ed276-139">Gérer un processus en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="ed276-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
