---
title: Résolution des problèmes de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614344"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="ebb0f-102">Résolution de problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ebb0f-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="ebb0f-103">Les rubriques dans cette section décrivent les problèmes de mise à niveau qui peuvent être détectés ainsi que ceux qui ne peuvent pas être détectés mais sont susceptibles d'affecter la mise à niveau ou les fonctionnalités après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="ebb0f-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="ebb0f-104">Les problèmes sont organisés par composant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebb0f-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebb0f-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ebb0f-105">In This Section</span></span>  
  
-   [<span data-ttu-id="ebb0f-106">Informations les plus récentes concernant les problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ebb0f-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="ebb0f-107">Problèmes de mise à niveau du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="ebb0f-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="ebb0f-108">Problèmes de mise à niveau de la fonction de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="ebb0f-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="ebb0f-109">Problèmes de mise à niveau de la réplication</span><span class="sxs-lookup"><span data-stu-id="ebb0f-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="ebb0f-110">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="ebb0f-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="ebb0f-111">Problèmes de mise à niveau de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebb0f-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="ebb0f-112">Problèmes qui empêchent la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ebb0f-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="ebb0f-113">Quelques configurations ou paramètres d'une version précédente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent vous empêcher d'effectuer une mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebb0f-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ebb0f-114">Si le programme d’installation détecte ces problèmes lors de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’installation de, le programme d’installation arrête le processus de mise à niveau et demande que vous exécutiez le conseiller de mise à niveau et corrige les éventuels problèmes de blocage.</span><span class="sxs-lookup"><span data-stu-id="ebb0f-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="ebb0f-115">Si les tâches suivantes sont répertoriées dans le rapport de mise à niveau du [!INCLUDE[ssDE](../../includes/ssde-md.md)], vous devez effectuer les actions requises avant de procéder à la mise niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ebb0f-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="ebb0f-116">Détacher l'ID de base de données 32767</span><span class="sxs-lookup"><span data-stu-id="ebb0f-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="ebb0f-117">Renommer les accès correspondant aux noms de rôles serveur fixes</span><span class="sxs-lookup"><span data-stu-id="ebb0f-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="ebb0f-118">Renommer l'utilisateur système</span><span class="sxs-lookup"><span data-stu-id="ebb0f-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="ebb0f-119">Utiliser sp_rename pour renommer le nom d'index en double</span><span class="sxs-lookup"><span data-stu-id="ebb0f-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="ebb0f-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebb0f-120">See Also</span></span>  
 [<span data-ttu-id="ebb0f-121">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="ebb0f-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
