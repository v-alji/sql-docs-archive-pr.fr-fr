---
title: Installer ADOMD.NET sur des serveurs Web frontaux exécutant l’administration centrale | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601282"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="95fe9-102">Installer ADOMD.NET sur des serveurs Web frontaux exécutant l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="95fe9-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="95fe9-103">Si vous installez PowerPivot pour SharePoint dans une batterie de serveurs qui a la topologie de l'Administration centrale, sans Excel Services ou PowerPivot pour SharePoint, téléchargez et installez la bibliothèque cliente Microsoft ADOMD.NET si vous voulez disposer d'un accès total aux rapports intégrés dans le tableau de bord de gestion PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="95fe9-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="95fe9-104">Certains rapports du tableau de bord utilisent ADOMD.NET pour accéder aux données internes qui fournissent les données de création de rapports sur le traitement des requêtes PowerPivot et l'intégrité des serveurs de la batterie.</span><span class="sxs-lookup"><span data-stu-id="95fe9-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="95fe9-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="95fe9-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="95fe9-106">Pour SharePoint 2013, le fournisseur est inclus dans le Feature Pack SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95fe9-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="95fe9-107">Pour plus d’informations sur le téléchargement de spPowerPivot.msi, consultez [Microsoft SQL Server Feature Pack 2014](https://www.microsoft.com/download/details.aspx?id=35577)</span><span class="sxs-lookup"><span data-stu-id="95fe9-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="95fe9-108">Télécharger et installer la bibliothèque cliente</span><span class="sxs-lookup"><span data-stu-id="95fe9-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="95fe9-109">Sur la [page SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/?LinkID=296473), recherchez Microsoft ADOMD.net.</span><span class="sxs-lookup"><span data-stu-id="95fe9-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="95fe9-110">Téléchargez le package x64 du programme d'installation `SQL_AS_ADOMD.msi`.</span><span class="sxs-lookup"><span data-stu-id="95fe9-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="95fe9-111">Exécutez le fichier .msi pour installer la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="95fe9-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="95fe9-112">Réinitialisez IIS une fois l'installation finie.</span><span class="sxs-lookup"><span data-stu-id="95fe9-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="95fe9-113">Ouvrez une invite de commandes d’administration et tapez **IISReset**.</span><span class="sxs-lookup"><span data-stu-id="95fe9-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="95fe9-114">Vérifier l'installation</span><span class="sxs-lookup"><span data-stu-id="95fe9-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="95fe9-115">Accédez à Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="95fe9-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="95fe9-116">Cliquez avec le bouton droit sur Microsoft. AnalysisServices. AdomdClient, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="95fe9-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="95fe9-117">Cliquez sur **Version**.</span><span class="sxs-lookup"><span data-stu-id="95fe9-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="95fe9-118">Vérifiez que la version comprend 12,00.\<build number></span><span class="sxs-lookup"><span data-stu-id="95fe9-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="95fe9-119">et que la description est Microsoft. AnalysisService. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="95fe9-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fe9-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95fe9-120">See Also</span></span>  
 [<span data-ttu-id="95fe9-121">Tableau de bord de gestion PowerPivot et données d’utilisation</span><span class="sxs-lookup"><span data-stu-id="95fe9-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
