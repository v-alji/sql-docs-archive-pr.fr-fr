---
title: L’envoi de journaux ne s’exécutera pas après la mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server]
ms.assetid: 6727cb7d-ac01-4972-a730-dbb7cdc29705
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2af60743cb2cbf9bf455397fe052c4e81f5a06d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614357"
---
# <a name="log-shipping-will-not-run-after-upgrading"></a><span data-ttu-id="b7e9a-102">La copie des journaux de transaction ne s'exécutera pas après la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="b7e9a-102">Log shipping will not run after upgrading</span></span>
  <span data-ttu-id="b7e9a-103">Le Conseiller de mise à niveau a détecté que vous utilisez l'envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="b7e9a-103">Upgrade Advisor has detected that you are using log shipping.</span></span> <span data-ttu-id="b7e9a-104">La fonctionnalité d'envoi de journaux de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] n'est pas compatible avec celle de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] et ne peut pas être mise à niveau directement.</span><span class="sxs-lookup"><span data-stu-id="b7e9a-104">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] log shipping is incompatible with log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and cannot be upgraded directly.</span></span> <span data-ttu-id="b7e9a-105">Après avoir effectué la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigurez l'envoi de journaux à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="b7e9a-105">After upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e9a-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7e9a-106">See Also</span></span>  
 <span data-ttu-id="b7e9a-107">[SQL Server Agent catégorie de travaux d’envoi de journaux provoque l’échec de la mise à niveau](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="b7e9a-107">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 <span data-ttu-id="b7e9a-108">[La mise à niveau va remplacer le SQL Server Agent compte proxy de l’utilisateur par le UpgradedProxyAccount temporaire](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="b7e9a-108">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 <span data-ttu-id="b7e9a-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b7e9a-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b7e9a-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="b7e9a-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
