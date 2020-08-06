---
title: affinity64 Input-Output mask (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- binding processors [SQL Server]
- affinity64 I/O mask option
ms.assetid: d304eae7-5116-40ee-a0fa-0a3c0bc20c01
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19616f5718254bde5601ea1beeec21412ad867de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611306"
---
# <a name="affinity64-input-output-mask-server-configuration-option"></a><span data-ttu-id="098e4-102">affinity64 Input-Output mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="098e4-102">affinity64 Input-Output mask Server Configuration Option</span></span>
  <span data-ttu-id="098e4-103">L’option **affinity64 I/O mask** lie les E/S disque de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à un sous-ensemble spécifié d’unités centrales, de manière comparable à l’option **affinity I/O mask** .</span><span class="sxs-lookup"><span data-stu-id="098e4-103">The **affinity64 I/O mask** binds [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/O to a specified subset of CPUs, similar to the **affinity I/O mask** option.</span></span> <span data-ttu-id="098e4-104">Utilisez l’option **affinity I/O mask** pour lier les 32 premiers processeurs, puis **affinity64 I/O mask** pour lier les processeurs restants de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="098e4-104">Use **affinity I/O mask** to bind the first 32 processors, and use **affinity64 I/O mask** to bind the remaining processors on the computer.</span></span> <span data-ttu-id="098e4-105">Si vous reconfigurez l’option **affinity64 I/O mask**, vous devez redémarrer l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="098e4-105">If you reconfigure the **affinity64 I/O mask**, you must restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="098e4-106">Cette option est visible uniquement sur la version 64 bits de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="098e4-106">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098e4-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="098e4-107">See Also</span></span>  
 <span data-ttu-id="098e4-108">[affinity Input-Otput mask (option de configuration de serveur)](affinity-input-output-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="098e4-108">[affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="098e4-109">[Analyser l’utilisation des ressources &#40;Moniteur système&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="098e4-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="098e4-110">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="098e4-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="098e4-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="098e4-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="098e4-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="098e4-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
