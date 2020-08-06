---
title: MSSQLSERVER_32042 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604524"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="d41a7-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="d41a7-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="d41a7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d41a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d41a7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d41a7-104">Product Name</span></span>|<span data-ttu-id="d41a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d41a7-105">SQL Server</span></span>|  
|<span data-ttu-id="d41a7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d41a7-106">Event ID</span></span>|<span data-ttu-id="d41a7-107">32042</span><span class="sxs-lookup"><span data-stu-id="d41a7-107">32042</span></span>|  
|<span data-ttu-id="d41a7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d41a7-108">Event Source</span></span>|<span data-ttu-id="d41a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d41a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d41a7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d41a7-110">Component</span></span>|<span data-ttu-id="d41a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d41a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="d41a7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d41a7-112">Symbolic Name</span></span>|<span data-ttu-id="d41a7-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="d41a7-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="d41a7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d41a7-114">Message Text</span></span>|<span data-ttu-id="d41a7-115">L'alerte relative au journal non envoyé s'est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="d41a7-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="d41a7-116">La valeur actuelle de '%d' dépasse le seuil '%d'.</span><span class="sxs-lookup"><span data-stu-id="d41a7-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d41a7-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d41a7-117">Explanation</span></span>  
 <span data-ttu-id="d41a7-118">Cet événement de mise en miroir de bases de données est émis sur l'instance du serveur principal pour indiquer que la quantité de journal non envoyé a atteint la valeur de seuil définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d41a7-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="d41a7-119">En règle générale, cet événement se produit car les performances du système ont changé.</span><span class="sxs-lookup"><span data-stu-id="d41a7-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="d41a7-120">Soit la bande passante entre les deux systèmes a diminué, soit la charge a augmenté.</span><span class="sxs-lookup"><span data-stu-id="d41a7-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="d41a7-121">La quantité de journal non envoyé est une mesure de performance qui peut vous aider à évaluer le risque de perte de données exprimé en kilo-octets (Ko) de journal non envoyé.</span><span class="sxs-lookup"><span data-stu-id="d41a7-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="d41a7-122">Cette mesure s’avère particulièrement appropriée pour les sessions en mode hautes performances.</span><span class="sxs-lookup"><span data-stu-id="d41a7-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="d41a7-123">Toutefois, elle est également adaptée aux sessions en mode haute sécurité lorsque la mise en miroir est interrompue ou suspendue suite à une déconnexion des serveurs partenaires.</span><span class="sxs-lookup"><span data-stu-id="d41a7-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d41a7-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d41a7-124">User Action</span></span>  
 <span data-ttu-id="d41a7-125">Vérifiez les charges incombant aux instances du serveur principal et du serveur miroir et à leur connexion réseau pour déterminer la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="d41a7-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41a7-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d41a7-126">See Also</span></span>  
 <span data-ttu-id="d41a7-127">[Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d41a7-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="d41a7-128">Utiliser des seuils d’avertissement et d’alertes sur des métriques de performances de mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d41a7-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
