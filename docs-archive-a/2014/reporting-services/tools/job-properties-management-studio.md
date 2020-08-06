---
title: Propriétés du travail (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700709"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="29842-102">Propriétés du travail (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29842-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="29842-103">Utilisez la page **Propriétés du travail** pour afficher des informations sur un rapport ou abonnement en cours avant de l’annuler.</span><span class="sxs-lookup"><span data-stu-id="29842-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="29842-104">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, puis ouvrez le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="29842-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="29842-105">Cliquez avec le bouton droit sur un travail en cours d’exécution, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="29842-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29842-106">Cette fonctionnalité n'est pas prise en charge dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="29842-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="29842-107">La page n'apparaît pas lorsque vous exécutez [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29842-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="29842-108">Tâches</span><span class="sxs-lookup"><span data-stu-id="29842-108">Tasks</span></span>  
 <span data-ttu-id="29842-109">Avant de pouvoir consulter des informations sur un travail, actualisez la page pour récupérer des informations sur les travaux qui sont actuellement en cours d'exécution sur le serveur de rapports :</span><span class="sxs-lookup"><span data-stu-id="29842-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="29842-110">Ouvrez le dossier du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="29842-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="29842-111">Cliquez avec le bouton droit sur **Travaux**, puis cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="29842-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="29842-112">Si un travail est répertorié, cliquez dessus avec le bouton droit, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="29842-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29842-113">Options</span><span class="sxs-lookup"><span data-stu-id="29842-113">Options</span></span>  
 <span data-ttu-id="29842-114">**ID de travail**</span><span class="sxs-lookup"><span data-stu-id="29842-114">**Job ID**</span></span>  
 <span data-ttu-id="29842-115">GUID attribué à un travail pendant son traitement.</span><span class="sxs-lookup"><span data-stu-id="29842-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="29842-116">La valeur est générée de façon aléatoire chaque fois qu'un rapport ou abonnement est exécuté.</span><span class="sxs-lookup"><span data-stu-id="29842-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="29842-117">**État du travail**</span><span class="sxs-lookup"><span data-stu-id="29842-117">**Job Status**</span></span>  
 <span data-ttu-id="29842-118">Les valeurs valides sont **Nouveau** et **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="29842-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="29842-119">La valeur de l'état est toujours **Nouveau** lorsque le travail commence.</span><span class="sxs-lookup"><span data-stu-id="29842-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="29842-120">Après 60 secondes, la valeur de l'état devient **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="29842-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="29842-121">Vous devez actualiser la page pour voir la modification.</span><span class="sxs-lookup"><span data-stu-id="29842-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="29842-122">**Type de tâche**</span><span class="sxs-lookup"><span data-stu-id="29842-122">**Job Type**</span></span>  
 <span data-ttu-id="29842-123">Les valeurs valides sont **Utilisateur** et **Système**.</span><span class="sxs-lookup"><span data-stu-id="29842-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="29842-124">Un travail utilisateur est un travail qui est initié par un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="29842-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="29842-125">Il peut s'agir de l'exécution d'un rapport sur demande, de la création manuelle d'un instantané d'historique de rapport ou de la création manuelle d'un instantané d'exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="29842-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="29842-126">Un abonnement standard en cours est également un travail utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29842-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="29842-127">Un travail système est un travail lancé par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="29842-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="29842-128">Les travaux système incluent le traitement des rapports déclenché par une planification.</span><span class="sxs-lookup"><span data-stu-id="29842-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="29842-129">**Action du travail**</span><span class="sxs-lookup"><span data-stu-id="29842-129">**Job Action**</span></span>  
 <span data-ttu-id="29842-130">Pour les rapports, cette colonne affiche les processus d'exécution de rapport en cours.</span><span class="sxs-lookup"><span data-stu-id="29842-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="29842-131">Cette valeur est toujours **Rendu**.</span><span class="sxs-lookup"><span data-stu-id="29842-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="29842-132">**Description du travail**</span><span class="sxs-lookup"><span data-stu-id="29842-132">**Job Description**</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="29842-133">ne fournit pas de descriptions de travail par défaut.</span><span class="sxs-lookup"><span data-stu-id="29842-133">does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="29842-134">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="29842-134">**Server Name**</span></span>  
 <span data-ttu-id="29842-135">Affiche le nom du serveur de rapports qui traite le travail.</span><span class="sxs-lookup"><span data-stu-id="29842-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="29842-136">Si vous avez configuré un déploiement avec montée en puissance parallèle, cette valeur affichera le serveur qui traite le travail.</span><span class="sxs-lookup"><span data-stu-id="29842-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="29842-137">**Nom du rapport**</span><span class="sxs-lookup"><span data-stu-id="29842-137">**Report Name**</span></span>  
 <span data-ttu-id="29842-138">Affiche le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="29842-138">Shows the name of the report.</span></span> <span data-ttu-id="29842-139">Les abonnements sont identifiés par leur description.</span><span class="sxs-lookup"><span data-stu-id="29842-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="29842-140">**Chemin d'accès au rapport**</span><span class="sxs-lookup"><span data-stu-id="29842-140">**Report Path**</span></span>  
 <span data-ttu-id="29842-141">Affiche le chemin d'accès au rapport dans l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="29842-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="29842-142">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="29842-142">**Start Time**</span></span>  
 <span data-ttu-id="29842-143">Indique à quel moment le processus a démarré.</span><span class="sxs-lookup"><span data-stu-id="29842-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="29842-144">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="29842-144">**User Name**</span></span>  
 <span data-ttu-id="29842-145">Pour les processus lancés par un utilisateur, cette colonne affiche le nom de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29842-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="29842-146">Pour les travaux système, il s'agit du nom du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="29842-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29842-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29842-147">See Also</span></span>  
 <span data-ttu-id="29842-148">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="29842-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="29842-149">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="29842-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="29842-150">Gérer un processus en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="29842-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
