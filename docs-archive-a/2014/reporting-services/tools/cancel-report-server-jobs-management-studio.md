---
title: Annuler les travaux du serveur de rapports (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706183"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="8b9fe-102">Annuler les travaux du serveur de rapports (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8b9fe-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="8b9fe-103">Utilisez la boîte de dialogue **Annuler les travaux du serveur de rapports** pour afficher ou annuler les rapports en cours.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="8b9fe-104">Cette boîte de dialogue affiche tous les travaux qui sont en cours d'exécution sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="8b9fe-105">Bien que vous ne puissiez pas suspendre ni redémarrer des travaux en cours de traitement, vous pouvez annuler tous les travaux ou des travaux individuels si leur exécution est trop longue.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="8b9fe-106">Vous pouvez annuler des travaux utilisateur et système.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="8b9fe-107">Un travail utilisateur est un travail qui est initié par un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="8b9fe-108">Il peut s'agir de l'exécution d'un rapport à la demande, de la création manuelle d'un instantané d'historique de rapport ou de la création manuelle d'un instantané d'exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="8b9fe-109">Un abonnement standard en cours est également un travail utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="8b9fe-110">Un travail système est un travail lancé par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="8b9fe-111">Les travaux système incluent le traitement planifié des rapports.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="8b9fe-112">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, cliquez avec le bouton droit sur **Travaux**, puis cliquez sur **Annuler tous les travaux**.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="8b9fe-113">Vous pouvez également ouvrir **Travaux**, cliquer avec le bouton droit sur un travail en cours d’exécution sur le serveur de rapports, puis sélectionner **Annuler les travaux**.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="8b9fe-114">Avant d'annuler un travail, vous pouvez consulter ses propriétés pour déterminer à quel moment il a démarré.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="8b9fe-115">Pour plus d’informations, consultez [Propriétés du travail &#40;Management Studio&#41;](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8b9fe-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b9fe-116">Cette fonctionnalité n'est pas prise en charge dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="8b9fe-117">La page n'apparaît pas lorsque vous exécutez [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b9fe-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b9fe-118">Options</span><span class="sxs-lookup"><span data-stu-id="8b9fe-118">Options</span></span>  
 <span data-ttu-id="8b9fe-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-119">**Name**</span></span>  
 <span data-ttu-id="8b9fe-120">Affiche le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-120">Shows the name of the report.</span></span> <span data-ttu-id="8b9fe-121">Les abonnements sont identifiés par leur description.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="8b9fe-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-122">**Type**</span></span>  
 <span data-ttu-id="8b9fe-123">Les valeurs valides sont **Utilisateur** et **Système**.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="8b9fe-124">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-124">**Start Time**</span></span>  
 <span data-ttu-id="8b9fe-125">Indique à quel moment le travail a démarré.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="8b9fe-126">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-126">**User Name**</span></span>  
 <span data-ttu-id="8b9fe-127">Pour les travaux lancés par un utilisateur, cette colonne affiche le nom de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="8b9fe-128">**État**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-128">**Status**</span></span>  
 <span data-ttu-id="8b9fe-129">Indique l'état du travail.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-129">Shows the status of the job.</span></span> <span data-ttu-id="8b9fe-130">Les valeurs valides sont **Nouveau** et **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="8b9fe-131">La valeur de l'état est toujours **Nouveau** lorsque le travail commence.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="8b9fe-132">Après 60 secondes, la valeur de l'état devient **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="8b9fe-133">Vous devez actualiser la page pour voir la modification.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="8b9fe-134">**OK**</span><span class="sxs-lookup"><span data-stu-id="8b9fe-134">**OK**</span></span>  
 <span data-ttu-id="8b9fe-135">Annulez un seul travail ou plusieurs travaux.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="8b9fe-136">Les travaux sont immédiatement annulés et ne peuvent pas être repris.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="8b9fe-137">Si vous annulez un travail par erreur, vous devez demander une nouvelle fois le rapport ou l'abonnement pour démarrer un nouveau travail.</span><span class="sxs-lookup"><span data-stu-id="8b9fe-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9fe-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b9fe-138">See Also</span></span>  
 <span data-ttu-id="8b9fe-139">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="8b9fe-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="8b9fe-140">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8b9fe-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="8b9fe-141">Gérer un processus en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="8b9fe-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
