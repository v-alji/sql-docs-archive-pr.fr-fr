---
title: Utilisation du conseiller de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604824"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="8ec27-102">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8ec27-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="8ec27-103">Pour garantir la réussite de la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], le Conseiller de mise à niveau fournit une console centrale pour identifier les problèmes à résoudre dans les installations avant de procéder à la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec27-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="8ec27-104">Le Conseiller de mise à niveau vous permet d'effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ec27-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="8ec27-105">Analyser les composants de la version précédente sur des serveurs locaux ou distants.</span><span class="sxs-lookup"><span data-stu-id="8ec27-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8ec27-106">Vous ne pouvez pas analyser des instances distantes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec27-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8ec27-107">Affichez les résultats de l’analyse.</span><span class="sxs-lookup"><span data-stu-id="8ec27-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="8ec27-108">Le Conseiller de mise à niveau intègre un analyseur et une visionneuse.</span><span class="sxs-lookup"><span data-stu-id="8ec27-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="8ec27-109">L'Assistant Analyse du Conseiller de mise à niveau analyse les composants de votre choix.</span><span class="sxs-lookup"><span data-stu-id="8ec27-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="8ec27-110">L'analyseur génère ensuite des rapports personnalisés concernant les problèmes à traiter avant de procéder à la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec27-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8ec27-111">La visionneuse de rapports du Conseiller de mise à niveau vous permet d'afficher les rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="8ec27-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="8ec27-112">Pour plus d’informations sur la détection de l’analyse du conseiller de mise à niveau, consultez [résolution des problèmes de mise à niveau](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ec27-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="8ec27-113">Les rubriques de cette section fournissent une vue d’ensemble de la fonctionnalité du conseiller de mise à niveau et des informations sur l’utilisation des rapports du conseiller de mise à niveau et du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8ec27-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ec27-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8ec27-114">In This Section</span></span>  
  
|<span data-ttu-id="8ec27-115">Rubrique</span><span class="sxs-lookup"><span data-stu-id="8ec27-115">Topic</span></span>|<span data-ttu-id="8ec27-116">Description</span><span class="sxs-lookup"><span data-stu-id="8ec27-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8ec27-117">Vue d’ensemble du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8ec27-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="8ec27-118">Fournit une vue d'ensemble du processus de mise à niveau, de l'Assistant Analyse du Conseiller de mise à niveau et de la visionneuse de rapports du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8ec27-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="8ec27-119">Rubriques de procédures relatives au Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8ec27-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="8ec27-120">Fournit des instructions pour effectuer les procédures du Conseiller de mise à niveau les plus courantes.</span><span class="sxs-lookup"><span data-stu-id="8ec27-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="8ec27-121">Guide de référence de l'interface utilisateur du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8ec27-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="8ec27-122">Contient des rubriques qui s’affichent si vous appuyez sur la touche F1 ou cliquez sur **aide** dans les pages de l’Assistant analyse du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8ec27-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ec27-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ec27-123">See Also</span></span>  
 <span data-ttu-id="8ec27-124">[Installation du conseiller de mise à niveau](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="8ec27-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="8ec27-125">Résolution de problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8ec27-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
