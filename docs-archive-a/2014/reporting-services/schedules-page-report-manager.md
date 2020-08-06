---
title: Page Planifications (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ef19d96e-9f00-4434-950e-152dda9c1ced
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e31bc25473aad23ecd2654f74ee3e837e65b65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603829"
---
# <a name="schedules-page-report-manager"></a><span data-ttu-id="4ce81-102">Page Planifications (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="4ce81-102">Schedules Page (Report Manager)</span></span>
  <span data-ttu-id="4ce81-103">La page Planifications vous permet de créer, modifier, supprimer, suspendre ou reprendre des planifications partagées.</span><span class="sxs-lookup"><span data-stu-id="4ce81-103">Use the Schedules page to create, modify, delete, pause, or resume shared schedules.</span></span> <span data-ttu-id="4ce81-104">Une planification partagée est une planification nommée que vous créez et gérez séparément à partir des rapports, des abonnements et des autres processus qui utilisent des informations de planification.</span><span class="sxs-lookup"><span data-stu-id="4ce81-104">A shared schedule is a named schedule that you can create and manage separately from reports, subscriptions, and other processes that consume schedule information.</span></span> <span data-ttu-id="4ce81-105">Les utilisateurs peuvent sélectionner les planifications partagées que vous leur fournissez.</span><span class="sxs-lookup"><span data-stu-id="4ce81-105">Users can select shared schedules that you provide.</span></span>  
  
 <span data-ttu-id="4ce81-106">Pour supprimer, suspendre ou reprendre une planification partagée, activez la case à cocher en regard de la planification partagée que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="4ce81-106">To delete, pause, or resume a shared schedule, select the check box next to the shared schedule that you want to modify.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ce81-107">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ce81-107">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ce81-108">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="4ce81-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="4ce81-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="4ce81-109">Navigation</span></span>  
 <span data-ttu-id="4ce81-110">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4ce81-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-schedules-page"></a><span data-ttu-id="4ce81-111">Pour ouvrir la page Planifications</span><span class="sxs-lookup"><span data-stu-id="4ce81-111">To open the Schedules page</span></span>  
  
1.  <span data-ttu-id="4ce81-112">Ouvrez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="4ce81-112">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="4ce81-113">En haut de la page, dans l'angle droit, cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="4ce81-113">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="4ce81-114">La page des propriétés générales du site s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4ce81-114">This opens the General Properties page of the site.</span></span>  
  
3.  <span data-ttu-id="4ce81-115">Sélectionnez l'onglet **Planifications** .</span><span class="sxs-lookup"><span data-stu-id="4ce81-115">Select the **Schedules** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4ce81-116">Options</span><span class="sxs-lookup"><span data-stu-id="4ce81-116">Options</span></span>  
 <span data-ttu-id="4ce81-117">**Nouvelle planification**</span><span class="sxs-lookup"><span data-stu-id="4ce81-117">**New Schedule**</span></span>  
 <span data-ttu-id="4ce81-118">Cliquez pour ouvrir la page Planification qui permet de spécifier les informations de fréquence.</span><span class="sxs-lookup"><span data-stu-id="4ce81-118">Click to open the Scheduling page, which is used to specify frequency information.</span></span>  
  
 <span data-ttu-id="4ce81-119">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="4ce81-119">**Delete**</span></span>  
 <span data-ttu-id="4ce81-120">Cliquez pour supprimer une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="4ce81-120">Click to remove a shared schedule.</span></span>  
  
 <span data-ttu-id="4ce81-121">**Pause**</span><span class="sxs-lookup"><span data-stu-id="4ce81-121">**Pause**</span></span>  
 <span data-ttu-id="4ce81-122">Cliquez pour arrêter l'exécution d'une planification partagée de façon temporaire.</span><span class="sxs-lookup"><span data-stu-id="4ce81-122">Click to stop a shared schedule from running temporarily.</span></span> <span data-ttu-id="4ce81-123">La suspension d'une planification empêche l'exécution des abonnements et des autres processus planifiés.</span><span class="sxs-lookup"><span data-stu-id="4ce81-123">Pausing a schedule prevents subscriptions and other scheduled processes from running.</span></span>  
  
 <span data-ttu-id="4ce81-124">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="4ce81-124">**Resume**</span></span>  
 <span data-ttu-id="4ce81-125">Cliquez pour reprendre une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="4ce81-125">Click to reinstate a shared schedule.</span></span> <span data-ttu-id="4ce81-126">Les processus dont l'exécution était planifiée pendant la suspension de la planification ne sont pas exécutés.</span><span class="sxs-lookup"><span data-stu-id="4ce81-126">Lapsed processes that were scheduled to run while the schedule was paused are not made up.</span></span>  
  
 <span data-ttu-id="4ce81-127">**Planification**</span><span class="sxs-lookup"><span data-stu-id="4ce81-127">**Schedule**</span></span>  
 <span data-ttu-id="4ce81-128">Affiche les planifications partagées actuellement définies.</span><span class="sxs-lookup"><span data-stu-id="4ce81-128">Shows the shared schedules that are currently defined.</span></span> <span data-ttu-id="4ce81-129">Cliquez sur une planification partagée pour afficher ou modifier les informations de fréquence.</span><span class="sxs-lookup"><span data-stu-id="4ce81-129">Click a shared schedule to view or edit frequency information.</span></span>  
  
 <span data-ttu-id="4ce81-130">**Creator**</span><span class="sxs-lookup"><span data-stu-id="4ce81-130">**Creator**</span></span>  
 <span data-ttu-id="4ce81-131">Affiche le nom de l'utilisateur qui a créé la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="4ce81-131">Shows the name of the user who created the shared schedule.</span></span>  
  
 <span data-ttu-id="4ce81-132">**Dernière exécution, Prochaine exécution**</span><span class="sxs-lookup"><span data-stu-id="4ce81-132">**Last Run, Next Run**</span></span>  
 <span data-ttu-id="4ce81-133">Indique la dernière et la prochaine exécution de la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="4ce81-133">Shows when the shared schedule was last run and when it will run next.</span></span>  
  
 <span data-ttu-id="4ce81-134">**État**</span><span class="sxs-lookup"><span data-stu-id="4ce81-134">**Status**</span></span>  
 <span data-ttu-id="4ce81-135">Indique si une planification partagée est suspendue ou active.</span><span class="sxs-lookup"><span data-stu-id="4ce81-135">Shows whether a shared schedule is paused or active.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce81-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ce81-136">See Also</span></span>  
 <span data-ttu-id="4ce81-137">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="4ce81-137">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="4ce81-138">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="4ce81-138">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
