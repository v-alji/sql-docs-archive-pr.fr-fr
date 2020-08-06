---
title: Vue d’ensemble du processus de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710135"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="cc9a7-102">Vue d'ensemble du processus de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cc9a7-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="cc9a7-103">Cette rubrique fournit des informations sur les meilleures pratiques concernant le Conseiller de mise à niveau [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] et un résumé du processus recommandé pour effectuer une mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="cc9a7-104">Processus de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cc9a7-104">Upgrade Process</span></span>  
 <span data-ttu-id="cc9a7-105">Les serveurs qui exécutent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] peuvent être mis à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cc9a7-106">Alors que certains composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être mis à niveau sur place, d'autres doivent être migrés et d'autres encore ont été remplacés par de nouveaux composants.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="cc9a7-107">Par exemple, depuis [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) remplace les services DTS (Data Transformation Services) et DTS n'est plus pris en charge dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cc9a7-108">Lorsque vous formulez votre plan de mise à niveau, vous devez peut-être planifier la mise à jour de vos packages DTS actuels en packages [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="cc9a7-109">Le Conseiller de mise à niveau vous permet d'évaluer les installations, les composants et les fichiers connexes actuels de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour identifier les problèmes connus qui pourront éventuellement se manifester pendant ou après la mise à niveau ou la migration vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="cc9a7-110">Quelques-uns de ces problèmes connus bloquent la [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="cc9a7-111">Dans le rapport du Conseiller de mise à niveau, ces problèmes sont identifiés comme des blocages de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="cc9a7-112">Si vous n'avez pas traité les blocages de mise à niveau avant d'exécuter le programme d'installation, le programme d'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] se ferme et vous recommande d'exécuter le Conseiller de mise à niveau pour identifier les problèmes spécifiques qui bloquent la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="cc9a7-113">Avant d'effectuer la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], nous vous recommandons de sauvegarder vos données et paramètres système et de prendre les mesures stratégiques répertoriées dans les instructions opérationnelles définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="cc9a7-114">Exécutez les opérations suivantes pour réaliser la mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="cc9a7-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="cc9a7-115">Consultez [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc9a7-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="cc9a7-116">Sauvegardez les données et les paramètres système.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="cc9a7-117">Exécutez le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="cc9a7-118">Le Conseiller de mise à niveau ne modifie pas vos données ni vos paramètres sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="cc9a7-119">Examinez les problèmes identifiés dans le rapport du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="cc9a7-120">Résolvez tous les problèmes de blocage qui vous empêcheraient d'effectuer la mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc9a7-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="cc9a7-121">Résolvez tous les autres problèmes antérieurs à la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="cc9a7-122">Exécutez le Conseiller de mise à niveau pour vérifier que tous les problèmes connus ont été traités.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="cc9a7-123">Exécutez le programme d'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc9a7-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="cc9a7-124">Résolvez tous les problèmes postérieurs à la mise à niveau et à la migration.</span><span class="sxs-lookup"><span data-stu-id="cc9a7-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9a7-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc9a7-125">See Also</span></span>  
 <span data-ttu-id="cc9a7-126">[Exécution du conseiller de mise à niveau &#40;de l’interface utilisateur&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="cc9a7-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="cc9a7-127">[Utilisation des rapports](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="cc9a7-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="cc9a7-128">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cc9a7-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
