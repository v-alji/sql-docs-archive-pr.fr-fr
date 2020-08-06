---
title: affinity64 mask (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- affinity64 mask option
- binding processors [SQL Server]
ms.assetid: 75ed08c7-f85c-4e15-9ee1-e7bc545d3293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2ea6d2e364feaa67d91de0055617aac9dc285ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611304"
---
# <a name="affinity64-mask-server-configuration-option"></a><span data-ttu-id="754df-102">affinity64 mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="754df-102">affinity64 mask Server Configuration Option</span></span>
  <span data-ttu-id="754df-103">L'option affinity64 mask lie des processeurs à des threads spécifiques, à l'image de l'option affinity mask.</span><span class="sxs-lookup"><span data-stu-id="754df-103">The affinity64 mask binds processors to specific threads, similar to the affinity mask option.</span></span> <span data-ttu-id="754df-104">Utilisez l'option affinity mask pour lier les 32 premiers processeurs et l'option affinity64 mask pour lier les processeurs restants de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="754df-104">Use affinity mask to bind the first 32 processors, and use affinity64 mask to bind the remaining processors on the computer.</span></span> <span data-ttu-id="754df-105">Cette option est visible uniquement sur la version 64 bits de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="754df-105">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="754df-106">Utilisez plutôt [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="754df-106">Use [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754df-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="754df-107">See Also</span></span>  
 <span data-ttu-id="754df-108">[affinity mask (option de configuration de serveur)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="754df-108">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="754df-109">[Analyser l’utilisation des ressources &#40;Moniteur système&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="754df-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="754df-110">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="754df-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="754df-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="754df-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="754df-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="754df-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
