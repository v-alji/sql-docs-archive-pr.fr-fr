---
title: Page mise en cache, datasets partagés (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605260"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="3a748-102">Page Mise en cache, datasets partagés (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="3a748-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="3a748-103">Utilisez la page de propriétés de mise en cache pour définir les options de mise en cache d'un dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="3a748-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a748-104">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a748-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3a748-105">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3a748-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="3a748-106">Navigation</span><span class="sxs-lookup"><span data-stu-id="3a748-106">Navigation</span></span>  
 <span data-ttu-id="3a748-107">Utilisez la procédure suivante pour accéder à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3a748-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="3a748-108">Pour ouvrir la page des propriétés de mise en cache d'un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="3a748-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="3a748-109">Ouvrez le Gestionnaire de rapports et recherchez le rapport pour lequel vous souhaitez configurer les propriétés de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="3a748-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="3a748-110">Pointez sur le dataset partagé, puis cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="3a748-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="3a748-111">Dans la liste déroulante, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="3a748-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="3a748-112">La page de propriétés générales du rapport s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="3a748-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="3a748-113">Cliquez sur l'onglet **Mise en cache** .</span><span class="sxs-lookup"><span data-stu-id="3a748-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a748-114">Options</span><span class="sxs-lookup"><span data-stu-id="3a748-114">Options</span></span>  
 <span data-ttu-id="3a748-115">**Mettre en cache le dataset partagé**</span><span class="sxs-lookup"><span data-stu-id="3a748-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="3a748-116">Place une copie temporaire des données dans un cache lorsqu'un utilisateur ouvre pour la première fois un rapport qui utilise ce dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="3a748-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="3a748-117">Les utilisateurs suivants qui exécutent le rapport dans la période de mise en cache reçoivent la copie mise en cache des données.</span><span class="sxs-lookup"><span data-stu-id="3a748-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="3a748-118">La mise en cache améliore habituellement les performances, car les données sont retournées à partir du cache ; la requête de dataset n'est pas réexécutée.</span><span class="sxs-lookup"><span data-stu-id="3a748-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="3a748-119">**Faire expirer le cache après ce nombre de minutes**</span><span class="sxs-lookup"><span data-stu-id="3a748-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="3a748-120">Spécifie la durée, en minutes, pendant laquelle la copie mise en cache des données est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="3a748-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="3a748-121">Dès qu'une copie temporaire expire, les données ne sont plus retournées à partir du cache.</span><span class="sxs-lookup"><span data-stu-id="3a748-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="3a748-122">Lors de l'ouverture suivante d'un rapport utilisant ce dataset partagé par un utilisateur, la requête de dataset s'exécute et le serveur de rapports réinsère une copie des données actualisées dans le cache.</span><span class="sxs-lookup"><span data-stu-id="3a748-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="3a748-123">**Faire expirer le cache selon la planification suivante**</span><span class="sxs-lookup"><span data-stu-id="3a748-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="3a748-124">Planifie l'heure à laquelle les données mises en cache ne sont plus valides et sont supprimées du cache.</span><span class="sxs-lookup"><span data-stu-id="3a748-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="3a748-125">Il peut s'agir d'une planification partagée ou d'une planification s'appliquant exclusivement au dataset partagé actuel.</span><span class="sxs-lookup"><span data-stu-id="3a748-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="3a748-126">**Planification spécifique aux datasets**</span><span class="sxs-lookup"><span data-stu-id="3a748-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="3a748-127">Spécifie une planification qui est utilisée uniquement par ce dataset.</span><span class="sxs-lookup"><span data-stu-id="3a748-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="3a748-128">**Planification partagée**</span><span class="sxs-lookup"><span data-stu-id="3a748-128">**Shared schedule**</span></span>  
 <span data-ttu-id="3a748-129">Spécifie une planification qui est partagée par des rapports, des abonnements et d'autres datasets partagés.</span><span class="sxs-lookup"><span data-stu-id="3a748-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="3a748-130">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="3a748-130">**Apply**</span></span>  
 <span data-ttu-id="3a748-131">Enregistrez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="3a748-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a748-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a748-132">See Also</span></span>  
 <span data-ttu-id="3a748-133">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3a748-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="3a748-134">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3a748-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="3a748-135">[Mettre en cache les datasets partagés &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3a748-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="3a748-136">Planifications</span><span class="sxs-lookup"><span data-stu-id="3a748-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
