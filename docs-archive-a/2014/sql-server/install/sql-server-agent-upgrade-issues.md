---
title: Problèmes de mise à niveau de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server Agent
- SQL Server Agent, upgrades
ms.assetid: 77e303ff-febd-4103-ae5d-6e5b85bc8009
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ac234a757510af5ebfac261ea6d3e7e57d2f426f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700620"
---
# <a name="sql-server-agent-upgrade-issues"></a><span data-ttu-id="f532c-102">Problèmes de mise à niveau de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="f532c-102">SQL Server Agent Upgrade Issues</span></span>
  <span data-ttu-id="f532c-103">Les rubriques suivantes décrivent les problèmes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent qui peuvent affecter une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="f532c-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent issues that might affect an upgrade.</span></span> <span data-ttu-id="f532c-104">Elles présentent des mesures que vous pouvez prendre pour réduire les effets de ces modifications sur votre environnement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f532c-104">The topics describe actions that you can take to help reduce the effect of these changes on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f532c-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f532c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="f532c-106">Les plans de maintenance de la base de données sont obsolètes</span><span class="sxs-lookup"><span data-stu-id="f532c-106">Database maintenance plans superseded</span></span>](../../../2014/sql-server/install/database-maintenance-plans-superseded.md)  
  
-   [<span data-ttu-id="f532c-107">Seuls les utilisateurs sysadmin peuvent écrire des fichiers journaux des étapes de travail dans le système de fichiers</span><span class="sxs-lookup"><span data-stu-id="f532c-107">Only sysadmin users can write job step log files to the file system</span></span>](../../../2014/sql-server/install/only-sysadmin-users-can-write-job-step-log-files-to-the-file-system.md)  
  
-   [<span data-ttu-id="f532c-108">Utiliser de nouvelles procédures stockées à la place de la procédure stockée étendue xp_sqlagent_proxy_account</span><span class="sxs-lookup"><span data-stu-id="f532c-108">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>](../../../2014/sql-server/install/replace-xp-sqlagent-proxy-account-extended-sp-with-new-stored-procedures.md)  
  
-   [<span data-ttu-id="f532c-109">La catégorie affectée à l'opération de copie des journaux de transaction de l'Agent SQL Server provoque l'échec de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f532c-109">SQL Server Agent log shipping job category causes upgrade to fail</span></span>](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md)  
  
-   [<span data-ttu-id="f532c-110">Le service SQL Server Agent ne peut pas utiliser l'authentification SQL Server</span><span class="sxs-lookup"><span data-stu-id="f532c-110">SQL Server Agent Service cannot use SQL Server Authentication</span></span>](../../../2014/sql-server/install/sql-server-agent-service-cannot-use-sql-server-authentication.md)  
  
-   [<span data-ttu-id="f532c-111">Mettre à jour la syntaxe des jetons dans les étapes de travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="f532c-111">Update token syntax in SQL Server Agent job steps</span></span>](../../../2014/sql-server/install/update-token-syntax-in-sql-server-agent-job-steps.md)  
  
-   [<span data-ttu-id="f532c-112">Mettre à niveau tous les serveurs cibles avant de mettre à niveau le serveur maître</span><span class="sxs-lookup"><span data-stu-id="f532c-112">Upgrade all target servers before upgrading the master server</span></span>](../../../2014/sql-server/install/upgrade-all-target-servers-before-upgrading-the-master-server.md)  
  
-   [<span data-ttu-id="f532c-113">La mise à niveau entraînera la modification du compte proxy utilisateur de l'Agent SQL Server en UpgradedProxyAccount temporaire</span><span class="sxs-lookup"><span data-stu-id="f532c-113">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md)  
  
## <a name="see-also"></a><span data-ttu-id="f532c-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f532c-114">See Also</span></span>  
 <span data-ttu-id="f532c-115">[Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="f532c-115">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="f532c-116">Résolution de problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f532c-116">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
