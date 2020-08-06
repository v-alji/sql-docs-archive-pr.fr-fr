---
title: Modifications du comportement des indicateurs de trace | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604964"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="44f35-102">Modifications du comportement des indicateurs de trace</span><span class="sxs-lookup"><span data-stu-id="44f35-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="44f35-103">Les indicateurs de trace globaux définis par une session prennent effet dans d'autres sessions immédiatement.</span><span class="sxs-lookup"><span data-stu-id="44f35-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="44f35-104">Certains indicateurs de trace de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] n'existent plus dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44f35-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="44f35-105">Composant</span><span class="sxs-lookup"><span data-stu-id="44f35-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="44f35-106">Description</span><span class="sxs-lookup"><span data-stu-id="44f35-106">Description</span></span>  
 <span data-ttu-id="44f35-107">Nous vous conseillons de désactiver tous les indicateurs de trace avant d'effectuer la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="44f35-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="44f35-108">Les indicateurs de trace qui modifient la disponibilité de la base de données ou les modes de récupération peuvent empêcher le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] de mettre à niveau votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44f35-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="44f35-109">Vous pouvez activer les indicateurs de trace après avoir vérifié que les indicateurs de trace sont requis et encore valides dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44f35-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="44f35-110">Si vous devez réactiver des indicateurs de trace, vous devez effectuer des tests supplémentaires sur votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44f35-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="44f35-111">prend en charge les indicateurs de trace globaux et de niveau session.</span><span class="sxs-lookup"><span data-stu-id="44f35-111">supports global and session level trace flags.</span></span> <span data-ttu-id="44f35-112">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], les indicateurs de trace peuvent être spécifiés comme locaux ou globaux à l'aide d'un argument supplémentaire (-1) dans la commande DBCC TRACEON.</span><span class="sxs-lookup"><span data-stu-id="44f35-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="44f35-113">Si cet argument n'est pas spécifié, les indicateurs sont locaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="44f35-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="44f35-114">En outre, dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , un indicateur de trace défini dans la session a ne prend pas automatiquement effet dans une session B existante. Au lieu de cela, cet indicateur de trace prend effet uniquement après la première fois qu’un indicateur de trace est défini dans la session B. Ce comportement n’est pas déterministe dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] et est déterministe dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et les versions ultérieures, où les indicateurs de trace globaux définis dans la session A sont définis immédiatement dans d’autres sessions simultanées.</span><span class="sxs-lookup"><span data-stu-id="44f35-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f35-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44f35-115">See Also</span></span>  
 <span data-ttu-id="44f35-116">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="44f35-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="44f35-117">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="44f35-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
