---
title: Mettre en cache un dataset partagé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611563"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="c911a-102">Mettre en cache un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="c911a-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="c911a-103">L'un des moyens d'améliorer les performances est de configurer les propriétés de mise en cache d'un dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="c911a-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="c911a-104">Lorsqu'un dataset partagé est mis en cache, une copie des résultats de la requête est enregistrée pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="c911a-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="c911a-105">Le premier utilisateur qui demande un rapport utilisant le dataset partagé doit attendre que les résultats de la requête et l'ensemble du traitement soient terminés avant de consulter ce rapport.</span><span class="sxs-lookup"><span data-stu-id="c911a-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="c911a-106">Les utilisateurs suivants qui demandent le rapport dans la période de mise en cache bénéficient de meilleures performances car la requête et le traitement ont déjà eu lieu.</span><span class="sxs-lookup"><span data-stu-id="c911a-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="c911a-107">Vous pouvez également spécifier un plan d'actualisation du cache pour exécuter la requête et mettre en cache les résultats jusqu'à l'expiration du cache spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c911a-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="c911a-108">Les utilisateurs qui exécutent des rapports basés sur un dataset partagé ou des plans d'actualisation du cache créent le cache de requête et dans les deux cas, le cache est disponible en fonction des options d'expiration du cache.</span><span class="sxs-lookup"><span data-stu-id="c911a-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="c911a-109">Il existe des restrictions concernant les types de datasets partagés que vous pouvez mettre en cache.</span><span class="sxs-lookup"><span data-stu-id="c911a-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="c911a-110">Par exemple, les résultats de la requête ne peuvent pas être mis en cache si les données varient selon l'identité de l'utilisateur, ou si celles-ci sont récupérées à l'aide du jeton de sécurité de l'utilisateur qui demande le rapport.</span><span class="sxs-lookup"><span data-stu-id="c911a-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="c911a-111">Pour plus d’informations, consultez [Mettre en cache les datasets partagés &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) et [Mise en cache des rapports &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c911a-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="c911a-112">Pour planifier l'expiration d'un rapport mis en cache</span><span class="sxs-lookup"><span data-stu-id="c911a-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="c911a-113">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c911a-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c911a-114">Dans le Gestionnaire de rapports, accédez au dataset partagé pour lequel vous souhaitez définir des propriétés de mise en cache, pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="c911a-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c911a-115">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="c911a-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="c911a-116">Dans le cadre de gauche, cliquez sur **Mise en cache**.</span><span class="sxs-lookup"><span data-stu-id="c911a-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c911a-117">Si le message d'erreur **Les informations d'identification utilisées pour exécuter le dataset partagé ne sont pas stockées**apparaît, l'option de mise en cache du dataset partagé est désactivée.</span><span class="sxs-lookup"><span data-stu-id="c911a-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="c911a-118">Vous devez modifier la source de données pour stocker les informations d'identification ou modifier le dataset partagé de sorte qu'il utilise une source de données différente qui stocke les informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="c911a-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="c911a-119">Sélectionnez **Mettre en cache le dataset partagé**.</span><span class="sxs-lookup"><span data-stu-id="c911a-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="c911a-120">Sélectionnez l'option pour faire expirer le cache après 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="c911a-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="c911a-121">Vous pouvez également choisir de faire expirer le cache selon une planification spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c911a-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="c911a-122">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c911a-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c911a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c911a-123">See Also</span></span>  
 [<span data-ttu-id="c911a-124">Gérer des datasets partagés</span><span class="sxs-lookup"><span data-stu-id="c911a-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
