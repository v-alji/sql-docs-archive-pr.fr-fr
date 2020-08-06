---
title: La base de données du serveur de rapports n’est pas configurée (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600491"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="4c7bd-102">La base de données du serveur de rapports n'est pas configurée (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="4c7bd-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="4c7bd-103">La mise à niveau est bloquée en raison d'une configuration incomplète du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="4c7bd-104">La base de données du serveur de rapports n'est pas configurée.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="4c7bd-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode natif &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="4c7bd-106">Composant</span><span class="sxs-lookup"><span data-stu-id="4c7bd-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4c7bd-107">Description</span><span class="sxs-lookup"><span data-stu-id="4c7bd-107">Description</span></span>  
 <span data-ttu-id="4c7bd-108">Le programme d'installation peut uniquement mettre à niveau une instance du serveur de rapports entièrement configurée.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="4c7bd-109">Pour continuer, vous devez soit configurer la base de données du serveur de rapports, soit utiliser le **panneau de configuration** Microsoft Windows pour supprimer la fonctionnalité de serveur de rapports de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="4c7bd-110">Après avoir supprimé [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez mettre à niveau d'autres composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c7bd-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4c7bd-111">Action corrective</span><span class="sxs-lookup"><span data-stu-id="4c7bd-111">Corrective Action</span></span>  
 <span data-ttu-id="4c7bd-112">Si vous n'avez pas configuré la base de données du serveur de rapports, celui-ci n'est pas opérationnel et doit être supprimé avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="4c7bd-113">Pour plus d’informations sur la désinstallation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , consultez [désinstaller Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="4c7bd-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="4c7bd-114">La rubrique explique comment désinstaller une version spécifique, les procédures des versions antérieures étant similaires.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7bd-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c7bd-115">See Also</span></span>  
 [<span data-ttu-id="4c7bd-116">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="4c7bd-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
