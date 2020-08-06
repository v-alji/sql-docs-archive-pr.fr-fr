---
title: Installation de PowerPivot pour SharePoint 2010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612670"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="f5c61-102">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="f5c61-102">PowerPivot for SharePoint 2010 Installation</span></span>
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] <span data-ttu-id="f5c61-103">est une collection de composants serveur qui fournissent le traitement des requêtes et le contrôle de gestion pour les classeurs [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que vous publiez sur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f5c61-103">is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="f5c61-104">Les services incluent le moteur Analysis Services et le service système [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5c61-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5c61-105">Pour plus d'informations sur [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] et l'installation avec SharePoint Server 2013, consultez :</span><span class="sxs-lookup"><span data-stu-id="f5c61-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="f5c61-106">La section « SQL Server 2012 SP1 » de la rubrique [vue d’ensemble de l’installation de SQL Server maintenance](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="f5c61-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="f5c61-107">Analysis Services fournit le traitement côté serveur pour les classeurs Excel qui contiennent des données [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5c61-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="f5c61-108">Le service système[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] fonctionne avec Analysis Services, et ajoute l'intégration SharePoint, l'équilibrage de charge et la gestion des connexions.</span><span class="sxs-lookup"><span data-stu-id="f5c61-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="f5c61-109">étend Excel Services en associant sa capacité de traitement de données à grande échelle aux services de rendu de données fournis par Excel.</span><span class="sxs-lookup"><span data-stu-id="f5c61-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="f5c61-110">Pour installer [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], utilisez le support d'installation de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5c61-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="f5c61-111">Pour obtenir des instructions sur les scénarios de déploiement avancés, consultez [liste de vérification du déploiement : Reporting Services, Power View et PowerPivot pour SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) et liste de vérification du [déploiement : montée en puissance parallèle en ajoutant des serveurs PowerPivot à une batterie de serveurs SharePoint 2010](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="f5c61-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5c61-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f5c61-112">In This Section</span></span>  
 [<span data-ttu-id="f5c61-113">Installer PowerPivot pour SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="f5c61-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="f5c61-114">Installer le fournisseur OLE DB Analysis Services sur les serveurs SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c61-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="f5c61-115">Installer ADOMD.NET sur des serveurs Web frontaux exécutant l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="f5c61-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="f5c61-116">Installation d'ADO.NET Data Services pour prendre en charge les exportations de flux de données des listes SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c61-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="f5c61-117">Installer PowerPivot à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="f5c61-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="f5c61-118">Désinstaller PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c61-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="f5c61-119">Réparer PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="f5c61-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="f5c61-120">Configuration initiale &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="f5c61-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5c61-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5c61-121">See Also</span></span>  
 [<span data-ttu-id="f5c61-122">Administration et configuration d’un serveur PowerPivot dans l’Administration centrale</span><span class="sxs-lookup"><span data-stu-id="f5c61-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
