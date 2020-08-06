---
title: MSSQLSERVER_32044 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604523"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="f4849-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="f4849-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="f4849-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f4849-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4849-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f4849-104">Product Name</span></span>|<span data-ttu-id="f4849-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4849-105">SQL Server</span></span>|  
|<span data-ttu-id="f4849-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f4849-106">Event ID</span></span>|<span data-ttu-id="f4849-107">32044</span><span class="sxs-lookup"><span data-stu-id="f4849-107">32044</span></span>|  
|<span data-ttu-id="f4849-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f4849-108">Event Source</span></span>|<span data-ttu-id="f4849-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4849-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4849-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f4849-110">Component</span></span>|<span data-ttu-id="f4849-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f4849-111">SQLEngine</span></span>|  
|<span data-ttu-id="f4849-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f4849-112">Symbolic Name</span></span>|<span data-ttu-id="f4849-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="f4849-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="f4849-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f4849-114">Message Text</span></span>|<span data-ttu-id="f4849-115">L'alerte relative au temps de traitement de validation de miroir s'est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="f4849-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="f4849-116">La valeur actuelle de '%d' dépasse le seuil '%d'.</span><span class="sxs-lookup"><span data-stu-id="f4849-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4849-117">Explication</span><span class="sxs-lookup"><span data-stu-id="f4849-117">Explanation</span></span>  
 <span data-ttu-id="f4849-118">Cet événement de mise en miroir de bases de données est émis sur l'instance du serveur principal pour indiquer que le délai d'attente de la validation d'agrégation a atteint ou dépassé la valeur de seuil définie par l'utilisateur à cause de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="f4849-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="f4849-119">Le délai d'attente correspond au produit du nombre de transactions et de la durée de chaque transaction.</span><span class="sxs-lookup"><span data-stu-id="f4849-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="f4849-120">Par exemple, le délai d’attente est de 1 000 millisecondes dans les deux cas suivants : 1 000 transactions \* 1 milliseconde et 1 transaction \* 1 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="f4849-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="f4849-121">Le délai d'attente de la validation peut augmenter en raison d'une brusque augmentation du nombre de transactions, de retards dans l'envoi du journal ou de retards dans le vidage du journal sur l'instance du serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="f4849-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="f4849-122">La durée du temps de traitement de validation de miroir est une mesure de performance qui peut vous aider à évaluer l'impact actuel du fonctionnement synchrone sur les performances.</span><span class="sxs-lookup"><span data-stu-id="f4849-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="f4849-123">Cette mesure n'est utile qu'en mode haute sécurité.</span><span class="sxs-lookup"><span data-stu-id="f4849-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="f4849-124">Étant donné que le mode haute sécurité est synchrone, l'instance du serveur principal envoie un enregistrement de journal à l'instance du serveur miroir et ne valide la transaction qu'après avoir reçu la confirmation que l'instance du serveur miroir a écrit cet enregistrement sur le disque.</span><span class="sxs-lookup"><span data-stu-id="f4849-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="f4849-125">L'enregistrement de journal reste sur le disque sur l'instance du serveur miroir en attendant d'être restauré dans la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="f4849-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4849-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f4849-126">User Action</span></span>  
 <span data-ttu-id="f4849-127">Vérifiez les charges incombant aux instances du serveur principal et du serveur miroir et à leur connexion réseau pour déterminer la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="f4849-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4849-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4849-128">See Also</span></span>  
 <span data-ttu-id="f4849-129">[Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4849-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="f4849-130">Utiliser des seuils d’avertissement et d’alertes sur des métriques de performances de mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f4849-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
