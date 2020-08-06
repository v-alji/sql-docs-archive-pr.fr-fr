---
title: Performances, instantanés, mise en cache (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700805"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="d51b6-102">Performances, instantanés, mise en cache (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="d51b6-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="d51b6-103">Les performances du serveur de rapports sont affectées par une combinaison de facteurs qui incluent le matériel, le nombre d'utilisateurs simultanés qui accèdent aux rapports, la quantité de données d'un rapport et le format de sortie.</span><span class="sxs-lookup"><span data-stu-id="d51b6-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="d51b6-104">Pour déterminer quels sont les facteurs de performances spécifiques à votre installation et quelles sont les solutions qui produiront les résultats escomptés, vous devez obtenir des données de référence et effectuer des tests.</span><span class="sxs-lookup"><span data-stu-id="d51b6-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="d51b6-105">Pour plus d'informations sur les outils et instructions disponibles, consultez les publications suivantes sur MSDN : [Optimisation des performances de Reporting Services](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) et [Utilisation de Visual Studio 2005 pour effectuer un test de charge sur un serveur de rapports SQL Server 2005 Reporting Services](https://go.microsoft.com/fwlink/?LinkID=77519)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="d51b6-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="d51b6-106">Les principes généraux à prendre en considération sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d51b6-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="d51b6-107">Le traitement et le rendu des rapports sont des opérations qui nécessitent beaucoup de mémoire.</span><span class="sxs-lookup"><span data-stu-id="d51b6-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="d51b6-108">Si possible, choisissez un ordinateur disposant d'une grande quantité de mémoire.</span><span class="sxs-lookup"><span data-stu-id="d51b6-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="d51b6-109">L'hébergement du serveur de rapports et de la base de données du serveur de rapports sur des ordinateurs distincts a tendance à offrir de meilleures performances qu'un hébergement sur un seul ordinateur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="d51b6-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="d51b6-110">Si le traitement de l'ensemble des rapports est lent, songez à effectuer un déploiement avec montée en puissance parallèle, où plusieurs instances de serveur de rapports prennent en charge une base de données du serveur de rapports unique.</span><span class="sxs-lookup"><span data-stu-id="d51b6-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="d51b6-111">Pour obtenir les meilleurs résultats, utilisez un logiciel d'équilibrage de charge afin de répartir les requêtes de manière uniforme dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d51b6-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="d51b6-112">Si le traitement d'un rapport unique est lent, ajustez les requêtes de dataset du rapport si le rapport doit s'exécuter à la demande.</span><span class="sxs-lookup"><span data-stu-id="d51b6-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="d51b6-113">Vous pouvez également envisager d'utiliser des datasets partagés que vous pouvez mettre en cache, de mettre en cache le rapport ou d'exécuter le rapport comme un instantané.</span><span class="sxs-lookup"><span data-stu-id="d51b6-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="d51b6-114">Si le traitement de l'ensemble des rapports est lent dans un format spécifique (lors du rendu au format PDF, par exemple), songez à utiliser la remise par partage de fichiers, à ajouter davantage de mémoire ou à choisir un autre format.</span><span class="sxs-lookup"><span data-stu-id="d51b6-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="d51b6-115">Pour déterminer le temps de traitement d'un rapport et pour connaître d'autres mesures relatives à l'utilisation, consultez le journal des exécutions du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d51b6-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="d51b6-116">Pour plus d’informations, consultez [Journal d’exécution du serveur de rapports et vue ExecutionLog3](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="d51b6-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="d51b6-117">Pour plus d’informations sur la façon d’atténuer les problèmes de performances en réglant les paramètres de configuration liés à la gestion de mémoire, consultez [Configurer la mémoire disponible pour les applications du serveur de rapports](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="d51b6-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d51b6-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d51b6-118">In This Section</span></span>  
 [<span data-ttu-id="d51b6-119">Contrôle des performances d'un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="d51b6-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="d51b6-120">Décrit les objets de performances dont vous pouvez vous servir pour assurer le suivi de la charge de traitement sur votre serveur.</span><span class="sxs-lookup"><span data-stu-id="d51b6-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="d51b6-121">Définir les propriétés de traitement d'un rapport</span><span class="sxs-lookup"><span data-stu-id="d51b6-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="d51b6-122">Décrit les différentes configurations d'un rapport pour qu'il s'exécute à la demande, à partir de la mémoire cache ou suivant une planification en tant qu'instantané de rapport.</span><span class="sxs-lookup"><span data-stu-id="d51b6-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="d51b6-123">Configurer la mémoire disponible pour les applications du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="d51b6-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="d51b6-124">Décrit comment remplacer le comportement par défaut de gestion de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="d51b6-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="d51b6-125">Mise en cache de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d51b6-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="d51b6-126">Décrit le comportement de mise en cache d'un rapport sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d51b6-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="d51b6-127">Mettre en cache les datasets partagés &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d51b6-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="d51b6-128">Décrit le comportement de mise en cache d'un dataset partagé sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d51b6-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="d51b6-129">Traiter les rapports volumineux</span><span class="sxs-lookup"><span data-stu-id="d51b6-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="d51b6-130">Délivre des recommandations sur la façon de configurer et de distribuer un rapport de taille volumineuse.</span><span class="sxs-lookup"><span data-stu-id="d51b6-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="d51b6-131">Définition des valeurs de délai d’attente pour le traitement d’un rapport et d’un dataset partagé &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d51b6-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="d51b6-132">Explique comment définir des délais d'attente pour le traitement des requêtes et des rapports.</span><span class="sxs-lookup"><span data-stu-id="d51b6-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51b6-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d51b6-133">See Also</span></span>  
 <span data-ttu-id="d51b6-134">[Gérer un processus en cours d'exécution](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="d51b6-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="d51b6-135">Vérification de l'exécution d'un rapport</span><span class="sxs-lookup"><span data-stu-id="d51b6-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
