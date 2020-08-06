---
title: MSSQLSERVER_32040 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604525"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="efdce-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="efdce-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="efdce-103">Détails</span><span class="sxs-lookup"><span data-stu-id="efdce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efdce-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="efdce-104">Product Name</span></span>|<span data-ttu-id="efdce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="efdce-105">SQL Server</span></span>|  
|<span data-ttu-id="efdce-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="efdce-106">Event ID</span></span>|<span data-ttu-id="efdce-107">32040</span><span class="sxs-lookup"><span data-stu-id="efdce-107">32040</span></span>|  
|<span data-ttu-id="efdce-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="efdce-108">Event Source</span></span>|<span data-ttu-id="efdce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="efdce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="efdce-110">Composant</span><span class="sxs-lookup"><span data-stu-id="efdce-110">Component</span></span>|<span data-ttu-id="efdce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="efdce-111">SQLEngine</span></span>|  
|<span data-ttu-id="efdce-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="efdce-112">Symbolic Name</span></span>|<span data-ttu-id="efdce-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="efdce-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="efdce-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="efdce-114">Message Text</span></span>|<span data-ttu-id="efdce-115">L'alerte relative à la transaction non envoyée la plus ancienne s'est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="efdce-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="efdce-116">La valeur actuelle de '%d' dépasse le seuil '%d'.</span><span class="sxs-lookup"><span data-stu-id="efdce-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efdce-117">Explication</span><span class="sxs-lookup"><span data-stu-id="efdce-117">Explanation</span></span>  
 <span data-ttu-id="efdce-118">Cet événement de mise en miroir de bases de données est émis sur l'instance du serveur principal pour indiquer que la durée de vie de la plus ancienne transaction non envoyée a atteint la valeur de seuil définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="efdce-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="efdce-119">En règle générale, cet événement se produit car les performances du système ont changé.</span><span class="sxs-lookup"><span data-stu-id="efdce-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="efdce-120">Soit la bande passante entre les deux systèmes a diminué, soit la charge a augmenté.</span><span class="sxs-lookup"><span data-stu-id="efdce-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="efdce-121">La durée de vie de la plus ancienne transaction non envoyée est une mesure de performance qui peut vous aider à évaluer le risque de perte de données exprimé en minutes de transactions non envoyées.</span><span class="sxs-lookup"><span data-stu-id="efdce-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="efdce-122">Cette mesure s'avère particulièrement appropriée pour les sessions en mode hautes performances.</span><span class="sxs-lookup"><span data-stu-id="efdce-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="efdce-123">Toutefois, elle est également adaptée aux sessions en mode haute sécurité lorsque la mise en miroir est interrompue ou suspendue suite à une déconnexion des serveurs partenaires.</span><span class="sxs-lookup"><span data-stu-id="efdce-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efdce-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="efdce-124">User Action</span></span>  
 <span data-ttu-id="efdce-125">Vérifiez les charges incombant aux instances du serveur principal et du serveur miroir et à leur connexion réseau pour déterminer la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="efdce-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdce-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efdce-126">See Also</span></span>  
 <span data-ttu-id="efdce-127">[Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="efdce-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="efdce-128">Utiliser des seuils d’avertissement et d’alertes sur des métriques de performances de mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="efdce-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
