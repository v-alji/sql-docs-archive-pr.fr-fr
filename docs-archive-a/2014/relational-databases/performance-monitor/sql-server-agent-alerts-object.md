---
title: SQL Server Agent, objet Alerts | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602800"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="36401-102">SQL Server Agent, objet Alerts</span><span class="sxs-lookup"><span data-stu-id="36401-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="36401-103">L'objet de performance **Alerts** de l'Agent SQL Server contient des compteurs de performance qui donnent des informations sur les alertes de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36401-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="36401-104">Le tableau ci-dessous répertorie les compteurs inclus dans cet objet.</span><span class="sxs-lookup"><span data-stu-id="36401-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="36401-105">Le tableau suivant contient les compteurs **SQLAgent:Alerts** .</span><span class="sxs-lookup"><span data-stu-id="36401-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="36401-106">Nom</span><span class="sxs-lookup"><span data-stu-id="36401-106">Name</span></span>|<span data-ttu-id="36401-107">Description</span><span class="sxs-lookup"><span data-stu-id="36401-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="36401-108">**Alertes activées**</span><span class="sxs-lookup"><span data-stu-id="36401-108">**Activated alerts**</span></span>|<span data-ttu-id="36401-109">Ce compteur donne le nombre total d'alertes que l'Agent SQL Server a activées depuis son dernier redémarrage.</span><span class="sxs-lookup"><span data-stu-id="36401-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="36401-110">**Alertes activées/minute**</span><span class="sxs-lookup"><span data-stu-id="36401-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="36401-111">Ce compteur donne le nombre d'alertes que l'Agent SQL Server a activées au cours de la dernière minute.</span><span class="sxs-lookup"><span data-stu-id="36401-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="36401-112">Pour utiliser cet objet de l’Agent SQL Server, les utilisateurs doivent être membres du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="36401-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36401-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36401-113">See Also</span></span>  
 <span data-ttu-id="36401-114">[Alerts](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="36401-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="36401-115">[Utiliser des objets de performance](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="36401-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="36401-116">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="36401-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
