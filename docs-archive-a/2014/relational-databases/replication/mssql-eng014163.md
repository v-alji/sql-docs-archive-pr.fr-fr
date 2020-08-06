---
title: MSSQL_ENG014163 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014163 error
ms.assetid: b53dd463-ba36-421e-9745-67c7387e68dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b407d64b56d8d829d691b54917baae5bf3adbccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603943"
---
# <a name="mssql_eng014163"></a><span data-ttu-id="bc974-102">MSSQL_ENG014163</span><span class="sxs-lookup"><span data-stu-id="bc974-102">MSSQL_ENG014163</span></span>
    
## <a name="message-details"></a><span data-ttu-id="bc974-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="bc974-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc974-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bc974-104">Product Name</span></span>|<span data-ttu-id="bc974-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc974-105">SQL Server</span></span>|  
|<span data-ttu-id="bc974-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bc974-106">Event ID</span></span>|<span data-ttu-id="bc974-107">14163</span><span class="sxs-lookup"><span data-stu-id="bc974-107">14163</span></span>|  
|<span data-ttu-id="bc974-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bc974-108">Event Source</span></span>|<span data-ttu-id="bc974-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bc974-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bc974-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bc974-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="bc974-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bc974-111">Symbolic Name</span></span>||  
|<span data-ttu-id="bc974-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bc974-112">Message Text</span></span>|<span data-ttu-id="bc974-113">Le seuil [%s:%s] de la publication [%s] a été défini.</span><span class="sxs-lookup"><span data-stu-id="bc974-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="bc974-114">Assurez-vous que l'Agent de fusion s'exécute et peut respecter les conditions de latence.</span><span class="sxs-lookup"><span data-stu-id="bc974-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc974-115">Explication</span><span class="sxs-lookup"><span data-stu-id="bc974-115">Explanation</span></span>  
 <span data-ttu-id="bc974-116">La réplication vous permet d'activer des avertissements pour plusieurs situations.</span><span class="sxs-lookup"><span data-stu-id="bc974-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="bc974-117">Vous pouvez, entre autres, signaler le dépassement d'une durée spécifiée pour la synchronisation des modifications entre un serveur de publication de fusion et un Abonné.</span><span class="sxs-lookup"><span data-stu-id="bc974-117">This includes exceeding a specified length of time for synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="bc974-118">Vous pouvez spécifier des seuils différents pour les connexions LAN et pour les connexions d'accès à distance.</span><span class="sxs-lookup"><span data-stu-id="bc974-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="bc974-119">Lorsque vous activez un avertissement à l'aide du moniteur de réplication ou de la procédure stockée [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), vous spécifiez un seuil qui détermine à quel moment l'avertissement sera déclenché.</span><span class="sxs-lookup"><span data-stu-id="bc974-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="bc974-120">Quand ce seuil est atteint ou dépassé, un avertissement s'affiche dans le moniteur de réplication et un événement est enregistré dans le journal des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="bc974-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="bc974-121">Le franchissement d'un seuil peut également déclencher une alerte de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc974-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="bc974-122">Pour plus d’informations, consultez [Définir des seuils et des avertissements dans le moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md) et [Surveiller la réplication par programme](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="bc974-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc974-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bc974-123">User Action</span></span>  
 <span data-ttu-id="bc974-124">Si un abonnement dépasse un seuil de durée, vous devez déterminer si le système a un problème de performance ou si le seuil doit être modifié.</span><span class="sxs-lookup"><span data-stu-id="bc974-124">If a subscription exceeds a duration threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="bc974-125">Une fois la réplication configurée, élaborez un référentiel de performances qui vous permettra d'évaluer les performances de la réplication avec une charge de travail standard pour vos applications et votre topologie.</span><span class="sxs-lookup"><span data-stu-id="bc974-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="bc974-126">Intégrez la durée de synchronisation à ce référentiel afin de pouvoir définir une valeur appropriée pour le seuil.</span><span class="sxs-lookup"><span data-stu-id="bc974-126">Include duration of synchronization in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="bc974-127">Si la valeur du seuil est appropriée, mais qu'elle continue à être franchie, vous devez déterminer où se trouve le goulet d'étranglement dans le système.</span><span class="sxs-lookup"><span data-stu-id="bc974-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="bc974-128">Pour plus d’informations sur le contrôle des performances de réplication et la résolution des éventuels problèmes, consultez [Analyser les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="bc974-128">For more information about how to monitor and troubleshoot replication performance, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc974-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc974-129">See Also</span></span>  
 [<span data-ttu-id="bc974-130">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="bc974-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
