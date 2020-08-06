---
title: Impossible de mettre à niveau les connexions SQL Server dormantes 6,5 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604929"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="e6caf-102">Les connexions SQL Server 6.5 dormantes ne peuvent pas être mises à niveau</span><span class="sxs-lookup"><span data-stu-id="e6caf-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="e6caf-103">Le Conseiller de mise à niveau a détecté un nom de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dont le mot de passe ne peut pas être directement mis à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6caf-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="e6caf-104">Pour activer cette connexion, vous devez redéfinir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e6caf-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="e6caf-105">Vous pouvez redéfinir le mot de passe en utilisant ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="e6caf-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="e6caf-106">Le nouveau mot de passe sera validé par rapport à la stratégie de complexité des mots de passe de votre système, sauf si la vérification de la stratégie est désactivée.</span><span class="sxs-lookup"><span data-stu-id="e6caf-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="e6caf-107">Nous vous recommandons d'utiliser des mots de passe complexes et de ne pas désactiver la vérification de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e6caf-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="e6caf-108">L'option MUST_CHANGE oblige l'utilisateur à choisir un nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e6caf-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="e6caf-109">Cette étape est recommandée, mais elle n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e6caf-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="e6caf-110">Vous pouvez identifier les connexions dormantes à l'aide de la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="e6caf-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6caf-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6caf-111">See Also</span></span>  
 <span data-ttu-id="e6caf-112">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e6caf-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e6caf-113">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="e6caf-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
