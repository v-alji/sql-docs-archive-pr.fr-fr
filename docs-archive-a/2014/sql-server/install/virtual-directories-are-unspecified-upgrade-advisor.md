---
title: Les répertoires virtuels ne sont pas spécifiés (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604858"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="cbbc8-102">Les répertoires virtuels ne sont pas spécifiés (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="cbbc8-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="cbbc8-103">Le Conseiller de mise à niveau n'a pas détecté de paramètres de répertoire virtuel pour le service Web Report Server ou le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="cbbc8-104">Une fois la mise à niveau terminée, vous devez configurer des réservations d'URL pour le serveur de rapports à l'aide du Gestionnaire de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbbc8-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="cbbc8-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="cbbc8-106">Composant</span><span class="sxs-lookup"><span data-stu-id="cbbc8-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cbbc8-107">Description</span><span class="sxs-lookup"><span data-stu-id="cbbc8-107">Description</span></span>  
 <span data-ttu-id="cbbc8-108">Lors de la mise à niveau d'une installation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de nouvelles URL sont réservées pour le service Web Report Server et le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="cbbc8-109">Le Conseiller de mise à niveau n'a détecté aucun répertoire virtuel pour le serveur de rapports ou le Gestionnaire de rapports dans l'instance à mettre à niveau ; par conséquent, le processus de mise à niveau ne dispose pas d'informations suffisantes pour créer des réservations d'URL pour le serveur de rapports mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="cbbc8-110">La mise à niveau peut continuer, mais le répertoire virtuel du serveur de rapports ou du Gestionnaire de rapports ne sera pas défini après l'installation mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cbbc8-111">Action corrective</span><span class="sxs-lookup"><span data-stu-id="cbbc8-111">Corrective Action</span></span>  
 <span data-ttu-id="cbbc8-112">Une fois la mise à niveau terminée, utilisez le Gestionnaire de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour définir les URL pour le serveur de rapports et le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="cbbc8-113">Utilisez le gestionnaire des services Internet pour supprimer tous les répertoires virtuels dont vous n’avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="cbbc8-114">Pour plus d’informations, consultez [configurer une URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbc8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbbc8-115">See Also</span></span>  
 [<span data-ttu-id="cbbc8-116">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="cbbc8-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
