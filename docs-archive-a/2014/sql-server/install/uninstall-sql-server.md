---
title: Désinstaller SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e6255f8e-a25e-4b3d-9310-c5da2f9c9333
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e72f153c28a1ccd827150eb3dddc0b52321518a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604880"
---
# <a name="uninstall-sql-server-2014"></a><span data-ttu-id="398b0-102">Désinstaller SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="398b0-102">Uninstall SQL Server 2014</span></span>
  <span data-ttu-id="398b0-103">Suivez les rubriques ci-dessous pour désinstaller une instance existante de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] complètement, et préparer le système afin de pouvoir réinstaller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="398b0-103">Follow the topics below to uninstall an existing instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] completely, and prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="398b0-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="398b0-104">In This Section</span></span>  
 [<span data-ttu-id="398b0-105">Désinstaller une instance existante de SQL Server &#40;programme d’installation&#41;</span><span class="sxs-lookup"><span data-stu-id="398b0-105">Uninstall an Existing Instance of SQL Server &#40;Setup&#41;</span></span>](uninstall-an-existing-instance-of-sql-server-setup.md)  
 <span data-ttu-id="398b0-106">Cet rubrique explique comment désinstaller manuellement une instance autonome de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="398b0-106">This topic describes how to manually uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="398b0-107">Désinstaller PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="398b0-107">Uninstall PowerPivot for SharePoint</span></span>](uninstall-power-pivot-for-sharepoint.md)  
 <span data-ttu-id="398b0-108">Cette rubrique explique comment désinstaller manuellement PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="398b0-108">This topic describes how to manually uninstall PowerPivot for SharePoint.</span></span>  
  
 [<span data-ttu-id="398b0-109">Désinstaller Reporting Services</span><span class="sxs-lookup"><span data-stu-id="398b0-109">Uninstall Reporting Services</span></span>](uninstall-reporting-services.md)  
 <span data-ttu-id="398b0-110">Cette rubrique décrit comment désinstaller les serveurs [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour les serveurs en mode SharePoint et en mode natif.</span><span class="sxs-lookup"><span data-stu-id="398b0-110">This topic describes how to uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servers for both SharePoint mode and Native mode servers.</span></span>  
  
 [<span data-ttu-id="398b0-111">Désinstaller et supprimer Master Data Services</span><span class="sxs-lookup"><span data-stu-id="398b0-111">Uninstall and Remove Master Data Services</span></span>](uninstall-and-remove-master-data-services.md)  
 <span data-ttu-id="398b0-112">Cette rubrique décrit le processus de désinstallation et de suppression de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="398b0-112">This topic describes the process of uninstalling and removing [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from the local computer.</span></span>  
  
 [<span data-ttu-id="398b0-113">Supprimer des objets Data Quality Server</span><span class="sxs-lookup"><span data-stu-id="398b0-113">Remove Data Quality Server Objects</span></span>](remove-data-quality-server-objects.md)  
 <span data-ttu-id="398b0-114">Cette rubrique décrit comment supprimer manuellement les objets du [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] après la désinstallation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou uniquement le composant [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] dans [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="398b0-114">This topic describes how to manually remove the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] objects after uninstalling either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or just the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] component in [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="398b0-115">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="398b0-115">Related Sections</span></span>  
  
-   [<span data-ttu-id="398b0-116">Supprimer une instance de cluster de basculement SQL Server &#40;programme d’installation&#41;</span><span class="sxs-lookup"><span data-stu-id="398b0-116">Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;</span></span>](../failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md)  
  
-   [<span data-ttu-id="398b0-117">Ajouter ou supprimer des nœuds dans un cluster de basculement SQL Server &#40;programme d’installation&#41;</span><span class="sxs-lookup"><span data-stu-id="398b0-117">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
-   [<span data-ttu-id="398b0-118">Ignorer une installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="398b0-118">Drop a SQL Server 2014 Installation</span></span>](../../database-engine/install-windows/repair-a-failed-sql-server-installation.md)  
  
## <a name="see-also"></a><span data-ttu-id="398b0-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="398b0-119">See Also</span></span>  
 <span data-ttu-id="398b0-120">[Planification d'une installation SQL Server](planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="398b0-120">[Planning a SQL Server Installation](planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="398b0-121">[Installer SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="398b0-121">[Install SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span></span>  
 [<span data-ttu-id="398b0-122">Mettre à niveau vers SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="398b0-122">Upgrade to SQL Server 2014</span></span>](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
