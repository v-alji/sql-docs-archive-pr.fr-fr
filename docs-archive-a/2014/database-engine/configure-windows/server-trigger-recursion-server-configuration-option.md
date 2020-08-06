---
title: server trigger recursion (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- recursive triggers [SQL Server]
- triggers [SQL Server], recursive
- server trigger recursion option
ms.assetid: da4c25f5-d04c-4951-a3db-409e71a1b468
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 23a4997bd1a6f8b2c04af34d5cdc3229575901a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707851"
---
# <a name="server-trigger-recursion-server-configuration-option"></a><span data-ttu-id="65cc0-102">server trigger recursion (Option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="65cc0-102">server trigger recursion Server Configuration Option</span></span>
  <span data-ttu-id="65cc0-103">Utilisez l’option **server trigger recursion** pour permettre ou non l’exécution de manière récursive des déclencheurs au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="65cc0-103">Use the **server trigger recursion** option to specify whether to allow server-level triggers to fire recursively.</span></span> <span data-ttu-id="65cc0-104">Lorsque cette option a la valeur 1 (ON), les déclencheurs au niveau du serveur peuvent être exécutés de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="65cc0-104">When this option is set to 1 (ON), server-level triggers will be allowed to fire recursively.</span></span> <span data-ttu-id="65cc0-105">Lorsqu'elle a la valeur 0 (OFF), les déclencheurs ne peuvent pas être exécutés de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="65cc0-105">When set to 0 (OFF), server-level triggers cannot be fired recursively.</span></span> <span data-ttu-id="65cc0-106">Seule la récursivité directe est désactivée lorsque l'option server trigger recursion a la valeur 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="65cc0-106">Only direct recursion is prevented when the server trigger recursion option is set to 0 (OFF).</span></span> <span data-ttu-id="65cc0-107">(Pour désactiver la récursivité indirecte, affectez à l’option **nested triggers** la valeur 0.) La valeur par défaut de cette option est 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="65cc0-107">(To disable indirect recursion, set the **nested triggers** option to 0.) The default value for this option is 1 (ON).</span></span> <span data-ttu-id="65cc0-108">Le paramètre prend effet immédiatement (sans redémarrage du serveur).</span><span class="sxs-lookup"><span data-stu-id="65cc0-108">The setting takes effect immediately (without a server restart).</span></span>  
  
 <span data-ttu-id="65cc0-109">Pour plus d’informations, consultez [Créer des déclencheurs imbriqués](../../relational-databases/triggers/create-nested-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="65cc0-109">For more information, see [Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cc0-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65cc0-110">See Also</span></span>  
 <span data-ttu-id="65cc0-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65cc0-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="65cc0-112">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="65cc0-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="65cc0-113">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65cc0-113">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
