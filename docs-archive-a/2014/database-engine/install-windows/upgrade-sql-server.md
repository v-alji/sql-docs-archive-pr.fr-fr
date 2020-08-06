---
title: Mise à niveau vers SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
ms.assetid: 5064e35b-b70d-4a0b-a9e9-fff04162f9d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 857bbd6d7269b7675653b11a9d7c0acd07927f62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698519"
---
# <a name="upgrade-to-sql-server-2014"></a><span data-ttu-id="e3636-102">Mettre à niveau vers SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e3636-102">Upgrade to SQL Server 2014</span></span>
  <span data-ttu-id="e3636-103">Vous pouvez mettre à niveau les instances de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3636-103">You can upgrade instances of, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e3636-104">Avant d'exécuter le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour effectuer une mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], consultez le [Guide technique de la mise à niveau vers SQL Server 2014](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (téléchargement PDF), consultez les rubriques sur la mise à niveau de cette section et lisez les [Notes de mise à jour de SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="e3636-104">Before running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], check out the [SQL Server 2014 Upgrade Technical Guide](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF download), review the topics about the upgrade process in this section, and read the [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3636-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e3636-105">In This Section</span></span>  
 <span data-ttu-id="e3636-106">Cette section contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e3636-106">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="e3636-107">Mises à niveau de la version et de l’édition prises en charge</span><span class="sxs-lookup"><span data-stu-id="e3636-107">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="e3636-108">Utiliser le Conseiller de mise à niveau pour la préparation des mises à niveau</span><span class="sxs-lookup"><span data-stu-id="e3636-108">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="e3636-109">Utiliser Distributed Replay Utility pour préparer des mises à niveau</span><span class="sxs-lookup"><span data-stu-id="e3636-109">Use the Distributed Replay Utility to Prepare for Upgrades</span></span>](../../sql-server/install/use-the-distributed-replay-utility-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="e3636-110">Mettre à niveau Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e3636-110">Upgrade Analysis Services</span></span>](upgrade-analysis-services.md)  
  
-   [<span data-ttu-id="e3636-111">Mettre à niveau le moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="e3636-111">Upgrade Database Engine</span></span>](upgrade-database-engine.md)  
  
-   [<span data-ttu-id="e3636-112">Mettre à niveau Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="e3636-112">Upgrade Data Quality Services</span></span>](upgrade-data-quality-services.md)  
  
-   [<span data-ttu-id="e3636-113">Mettre à niveau Integration Services</span><span class="sxs-lookup"><span data-stu-id="e3636-113">Upgrade Integration Services</span></span>](../../integration-services/install-windows/upgrade-integration-services.md)  
  
-   [<span data-ttu-id="e3636-114">Mettre à niveau Master Data Services</span><span class="sxs-lookup"><span data-stu-id="e3636-114">Upgrade Master Data Services</span></span>](upgrade-master-data-services.md)  
  
-   [<span data-ttu-id="e3636-115">Mettre à niveau PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e3636-115">Upgrade PowerPivot for SharePoint</span></span>](upgrade-power-pivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="e3636-116">Mettre à niveau des bases de données répliquées</span><span class="sxs-lookup"><span data-stu-id="e3636-116">Upgrade Replicated Databases</span></span>](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
-   [<span data-ttu-id="e3636-117">Mettre à niveau et migrer Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e3636-117">Upgrade and Migrate Reporting Services</span></span>](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)  
  
-   [<span data-ttu-id="e3636-118">Mettre à niveau les outils d’administration SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3636-118">Upgrade SQL Server Management Tools</span></span>](upgrade-sql-server-management-tools.md)  
  
-   [<span data-ttu-id="e3636-119">Rubriques de procédures relatives à la mise en niveau</span><span class="sxs-lookup"><span data-stu-id="e3636-119">Upgrade How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3636-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e3636-120">See Also</span></span>  
 <span data-ttu-id="e3636-121">[Mettre à niveau le moteur de base de données](upgrade-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-121">[Upgrade Database Engine](upgrade-database-engine.md) </span></span>  
 <span data-ttu-id="e3636-122">[Mettre à niveau Analysis Services](upgrade-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-122">[Upgrade Analysis Services](upgrade-analysis-services.md) </span></span>  
 <span data-ttu-id="e3636-123">[Mettre à niveau et migrer Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-123">[Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span></span>  
 <span data-ttu-id="e3636-124">[Mettre à niveau Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-124">[Upgrade Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span></span>  
 <span data-ttu-id="e3636-125">[Mettre à niveau des bases de données répliquées](../../database-engine/install-windows/upgrade-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-125">[Upgrade Replicated Databases](../../database-engine/install-windows/upgrade-replicated-databases.md) </span></span>  
 <span data-ttu-id="e3636-126">[Mettre à niveau Master Data Services](upgrade-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e3636-126">[Upgrade Master Data Services](upgrade-master-data-services.md) </span></span>  
 <span data-ttu-id="e3636-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span><span class="sxs-lookup"><span data-stu-id="e3636-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span></span>  
 <span data-ttu-id="e3636-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span><span class="sxs-lookup"><span data-stu-id="e3636-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span></span>  
 [<span data-ttu-id="e3636-129">Compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="e3636-129">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
