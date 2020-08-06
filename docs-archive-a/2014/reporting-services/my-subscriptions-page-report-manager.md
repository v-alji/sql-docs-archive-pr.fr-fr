---
title: Page mes abonnements (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 491a85a3-f323-4155-a0a8-de2779899995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 891796ec491b157f3c9bb5b4adfd15daedbc7c88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707255"
---
# <a name="my-subscriptions-page-report-manager"></a><span data-ttu-id="0d598-102">Page Mes abonnements (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="0d598-102">My Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="0d598-103">La page Mes abonnements vous permet d'afficher tous vos abonnements à un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="0d598-103">Use the My Subscriptions page to view all of your subscriptions in one place.</span></span> <span data-ttu-id="0d598-104">À partir de cette page, vous pouvez accéder à vos propres abonnements et les modifier ou les supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d598-104">From this page, you can access and modify or delete any subscription that you own.</span></span> <span data-ttu-id="0d598-105">Vous ne possédez que les abonnements que vous créez.</span><span class="sxs-lookup"><span data-stu-id="0d598-105">You own only the subscriptions that you create.</span></span> <span data-ttu-id="0d598-106">En revanche, vous ne pouvez pas accéder aux abonnements des autres utilisateurs ou à ceux que vous utilisez mais dont vous n'êtes pas propriétaire (par exemple, si votre nom a été ajouté à un abonnement existant défini par un autre utilisateur).</span><span class="sxs-lookup"><span data-stu-id="0d598-106">You cannot access those of other users, nor can you access subscriptions that you use but do not own (for example, if your name has been added to an existing subscription defined by another user).</span></span> <span data-ttu-id="0d598-107">Vous ne pouvez pas créer d'abonnements à partir de cette page.</span><span class="sxs-lookup"><span data-stu-id="0d598-107">You cannot create subscriptions from this page.</span></span> <span data-ttu-id="0d598-108">Pour plus d’informations sur la création d’abonnements, consultez la [page nouvel abonnement ou modifier l’abonnement &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="0d598-108">For more information about creating subscriptions, see the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="0d598-109">Par défaut, les abonnements sont triés par ordre alphabétique (par nom de rapport).</span><span class="sxs-lookup"><span data-stu-id="0d598-109">By default, subscriptions are sorted in alphabetical order by report name.</span></span> <span data-ttu-id="0d598-110">Cliquez sur un autre en-tête de colonne pour modifier l'ordre de tri des abonnements.</span><span class="sxs-lookup"><span data-stu-id="0d598-110">Click a different column heading to change how subscriptions are sorted.</span></span> <span data-ttu-id="0d598-111">Si vous ne possédez pas d'abonnements ou si vous n'êtes pas autorisé à créer ou gérer des abonnements, aucun abonnement n'apparaît dans la page.</span><span class="sxs-lookup"><span data-stu-id="0d598-111">If you have no subscriptions or if permission to create or manage subscriptions is disabled, no subscriptions appear on the page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d598-112">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d598-112">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d598-113">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="0d598-113">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="0d598-114">Navigation</span><span class="sxs-lookup"><span data-stu-id="0d598-114">Navigation</span></span>  
 <span data-ttu-id="0d598-115">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d598-115">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-my-subscriptions-page"></a><span data-ttu-id="0d598-116">Pour ouvrir la page Mes abonnements</span><span class="sxs-lookup"><span data-stu-id="0d598-116">To open the My Subscriptions page</span></span>  
  
1.  <span data-ttu-id="0d598-117">Ouvrez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="0d598-117">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="0d598-118">En haut de la page, dans l'angle droit, cliquez sur Mes abonnements.</span><span class="sxs-lookup"><span data-stu-id="0d598-118">At the top of the page, in the right-hand corner, click My Subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d598-119">Mes abonnements est toujours disponible, même si vous n'êtes pas autorisé à créer des abonnements.</span><span class="sxs-lookup"><span data-stu-id="0d598-119">My Subscriptions is always available, even if you lack permission to create subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d598-120">Options</span><span class="sxs-lookup"><span data-stu-id="0d598-120">Options</span></span>  
 <span data-ttu-id="0d598-121">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="0d598-121">**Delete**</span></span>  
 <span data-ttu-id="0d598-122">Activez la case à cocher en regard de chaque abonnement à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0d598-122">Select the check box next to each subscription that you want to delete and click **Delete**.</span></span>  
  
 <span data-ttu-id="0d598-123">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="0d598-123">**Edit**</span></span>  
 <span data-ttu-id="0d598-124">Cliquez pour afficher ou modifier la description.</span><span class="sxs-lookup"><span data-stu-id="0d598-124">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="0d598-125">**Report**</span><span class="sxs-lookup"><span data-stu-id="0d598-125">**Report**</span></span>  
 <span data-ttu-id="0d598-126">Affiche le rapport défini dans l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-126">Shows the report that is specified in the subscription.</span></span> <span data-ttu-id="0d598-127">Cliquez sur le nom du rapport pour afficher ce dernier.</span><span class="sxs-lookup"><span data-stu-id="0d598-127">Click the report name to view the report.</span></span>  
  
 <span data-ttu-id="0d598-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="0d598-128">**Description**</span></span>  
 <span data-ttu-id="0d598-129">Affiche une description de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-129">Shows a description of the subscription.</span></span> <span data-ttu-id="0d598-130">Cliquez sur la description pour afficher ou modifier les informations sur l'abonnement du rapport.</span><span class="sxs-lookup"><span data-stu-id="0d598-130">Click the description to view or edit the subscription information for the report.</span></span>  
  
 <span data-ttu-id="0d598-131">**Folder**</span><span class="sxs-lookup"><span data-stu-id="0d598-131">**Folder**</span></span>  
 <span data-ttu-id="0d598-132">Affiche le dossier qui contient le rapport défini dans l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-132">Shows the folder that contains the report that is specified in the subscription.</span></span> <span data-ttu-id="0d598-133">Cliquez sur le nom du dossier pour afficher le contenu de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="0d598-133">Click the folder name to view the contents of the folder.</span></span>  
  
 <span data-ttu-id="0d598-134">**Déclencheur**</span><span class="sxs-lookup"><span data-stu-id="0d598-134">**Trigger**</span></span>  
 <span data-ttu-id="0d598-135">Identifie les critères qui entraînent l'exécution de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-135">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="0d598-136">Un déclencheur **TimedSubscription** est basé sur une planification qui définit à quel moment l'abonnement s'exécute.</span><span class="sxs-lookup"><span data-stu-id="0d598-136">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="0d598-137">Un déclencheur **SnapshotUpdated** est basé sur une mise à jour d'un instantané de rapport.</span><span class="sxs-lookup"><span data-stu-id="0d598-137">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="0d598-138">**Dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="0d598-138">**Last Run**</span></span>  
 <span data-ttu-id="0d598-139">Indique à quel moment a eu lieu le dernier traitement de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-139">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="0d598-140">**État**</span><span class="sxs-lookup"><span data-stu-id="0d598-140">**Status**</span></span>  
 <span data-ttu-id="0d598-141">Indique l'état de l'abonnement</span><span class="sxs-lookup"><span data-stu-id="0d598-141">Shows the status of the subscription.</span></span> <span data-ttu-id="0d598-142">En règle générale, l'état est « Nouveau » ou correspond à la date et à l'heure de la dernière exécution de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d598-142">Usually, the status value is either "New" or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="0d598-143">La valeur d'état « Données incorrectes » se présente lorsque l'abonnement comporte un pointeur vers des valeurs chiffrées qui ne sont plus valides, c'est-à-dire vers les informations d'identification utilisées pour exécuter le rapport).</span><span class="sxs-lookup"><span data-stu-id="0d598-143">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="0d598-144">Les valeurs chiffrées existantes deviennent inutilisables lorsque les clés symétriques utilisées pour chiffrer et déchiffrer les données sont recréées sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0d598-144">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="0d598-145">Il n'est pas possible de traiter un abonnement s'il a été désactivé.</span><span class="sxs-lookup"><span data-stu-id="0d598-145">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="0d598-146">Pour mettre à jour l'abonnement et le rendre opérationnel, ouvrez-le, puis enregistrez-le.</span><span class="sxs-lookup"><span data-stu-id="0d598-146">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d598-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d598-147">See Also</span></span>  
 <span data-ttu-id="0d598-148">[Abonnements et remise &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="0d598-148">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="0d598-149">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="0d598-149">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
