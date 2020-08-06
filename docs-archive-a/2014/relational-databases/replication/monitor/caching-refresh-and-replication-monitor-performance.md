---
title: Mise en cache, actualisation et performances du moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603388"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="63a86-102">Mise en cache, actualisation et performances du moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="63a86-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="63a86-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Le moniteur de réplication est conçu pour surveiller efficacement un grand nombre d’ordinateurs dans un système de production.</span><span class="sxs-lookup"><span data-stu-id="63a86-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="63a86-104">Les requêtes utilisées par le moniteur de réplication pour effectuer des calculs et collecter des données sont mises en cache et actualisées de façon périodique.</span><span class="sxs-lookup"><span data-stu-id="63a86-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="63a86-105">La mise en cache réduit le nombre de requêtes et de calculs requis lorsque vous affichez différentes pages du moniteur de réplication et permet d'adapter l'analyse à de nombreux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="63a86-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="63a86-106">L'actualisation du cache est gérée par un travail de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent, l' **Actualisateur d'analyse de réplication pour la distribution**.</span><span class="sxs-lookup"><span data-stu-id="63a86-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="63a86-107">Le travail s'exécute en permanence mais la planification de l'actualisation du cache prévoit l'attente d'un certain délai après l'actualisation précédente :</span><span class="sxs-lookup"><span data-stu-id="63a86-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="63a86-108">En cas de modifications de l'historique de l'Agent depuis la dernière création du cache, le délai d'attente est la période la plus courte entre 4 secondes et le temps nécessaire à la création du cache précédent.</span><span class="sxs-lookup"><span data-stu-id="63a86-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="63a86-109">En l'absence de modifications de l'historique de l'Agent depuis la dernière création du cache (d'autres modifications sont possibles), le délai d'attente est la période la plus longue entre 30 secondes et le temps nécessaire à la création du cache précédent.</span><span class="sxs-lookup"><span data-stu-id="63a86-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="63a86-110">Actualisation de l'interface utilisateur du moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="63a86-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="63a86-111">L'interface utilisateur du moniteur de réplication peut être actualisée de plusieurs façons :</span><span class="sxs-lookup"><span data-stu-id="63a86-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="63a86-112">La fenêtre principale du moniteur de réplication (y compris tous les onglets) est automatiquement actualisée toutes les cinq secondes.</span><span class="sxs-lookup"><span data-stu-id="63a86-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="63a86-113">Les actualisations automatiques ne forcent pas une actualisation du cache ; l'interface utilisateur affiche la version la plus récente des données du cache.</span><span class="sxs-lookup"><span data-stu-id="63a86-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="63a86-114">Vous pouvez personnaliser la fréquence d'actualisation utilisée pour toutes les fenêtres associées à un serveur de publication en modifiant les paramètres de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="63a86-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="63a86-115">Vous pouvez aussi désactiver les actualisations automatiques d'un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="63a86-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="63a86-116">Par défaut, les fenêtres de détails lancées à partir du moniteur de réplication ne sont pas automatiquement actualisées, à l'exception des fenêtres liées aux abonnements de fusion qui font l'objet d'une synchronisation.</span><span class="sxs-lookup"><span data-stu-id="63a86-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="63a86-117">Si vous spécifiez que les fenêtres de détails doivent être automatiquement actualisées, elles le sont à la même fréquence que celle planifiée pour la fenêtre principale du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="63a86-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="63a86-118">Toutes les fenêtres peuvent être actualisées manuellement en appuyant sur la touche F5 ou en cliquant avec le bouton droit dans l'arborescence du moniteur de réplication et en cliquant sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="63a86-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="63a86-119">Les actualisations manuelles forcent celle du cache.</span><span class="sxs-lookup"><span data-stu-id="63a86-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="63a86-120">Pour plus d’informations, consultez [Actualiser des données dans le moniteur de réplication](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="63a86-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="63a86-121">Considérations relatives aux performances</span><span class="sxs-lookup"><span data-stu-id="63a86-121">Performance Considerations</span></span>  
 <span data-ttu-id="63a86-122">Même si le moniteur de réplication est conçu pour s'exécuter efficacement, prenez en compte les points suivants :</span><span class="sxs-lookup"><span data-stu-id="63a86-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="63a86-123">Si vous possédez un grand nombre de publications ou d'abonnements, envisagez de définir une planification d'actualisation automatique moins fréquente pour l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63a86-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="63a86-124">Évitez d'exécuter simultanément plusieurs instances du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="63a86-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="63a86-125">Évitez d'inscrire un grand nombre de serveurs de distribution et de configurer le moniteur de réplication pour qu'il se connecte automatiquement à tous.</span><span class="sxs-lookup"><span data-stu-id="63a86-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a86-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63a86-126">See Also</span></span>  
 <span data-ttu-id="63a86-127">[Exécuter des travaux de maintenance de réplication &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="63a86-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="63a86-128">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="63a86-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
