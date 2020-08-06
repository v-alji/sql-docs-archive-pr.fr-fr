---
title: Microsoft SQL Server Reporting Services service partagé SharePoint est installé côte à côte (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6ae1017e-129b-4702-9ea7-00ac9b024062
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8a26fedd892dfb26dea4616efd46d3b3748b508
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612072"
---
# <a name="microsoft-sql-server-reporting-services-sharepoint-shared-service-is-installed-side-by-side-upgrade-advisor"></a><span data-ttu-id="5f942-102">Le service partagé SharePoint Microsoft SQL Server Reporting Services est installé côte à côte (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="5f942-102">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side (Upgrade Advisor)</span></span>
  <span data-ttu-id="5f942-103">Le conseiller de mise à niveau a détecté que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] le service partagé SharePoint est installé côte à côte avec une version précédente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f942-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="5f942-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f942-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="5f942-105">Composant</span><span class="sxs-lookup"><span data-stu-id="5f942-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="5f942-106">Description</span><span class="sxs-lookup"><span data-stu-id="5f942-106">Description</span></span>  
 <span data-ttu-id="5f942-107">Le conseiller de mise à niveau a détecté [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que le service partagé SharePoint est installé côte à côte avec une version précédente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] qui n’est pas basée sur l’architecture de service partagé SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f942-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is not based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="5f942-108">Parce que des technologies [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint anciennes et nouvelles sont installées côte à côte sur l'ordinateur, la mise à niveau est bloquée.</span><span class="sxs-lookup"><span data-stu-id="5f942-108">Because the computer has both older and newer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint related technologies installed side by side, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="5f942-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="5f942-109">Corrective Action</span></span>  
 <span data-ttu-id="5f942-110">Pour continuer la mise à niveau, vous devez désinstaller une des installations existantes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f942-110">To continue with upgrade, you must uninstall one of the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installations.</span></span> <span data-ttu-id="5f942-111">Après avoir supprimé une des installations de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], relancez le Conseiller de mise à niveau pour confirmer qu'il n'y a pas d'autre problèmes de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5f942-111">After removing one of the installations of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
  
