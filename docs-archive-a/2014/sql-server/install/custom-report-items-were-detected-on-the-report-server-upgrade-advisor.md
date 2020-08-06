---
title: Des éléments de rapport personnalisés ont été détectés sur le serveur de rapports (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603219"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="f14be-102">Des éléments de rapport personnalisés ont été détectés sur le serveur de rapports (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="f14be-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="f14be-103">Les éléments de rapport personnalisés qui ont été créés pour les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ne sont pas compatibles avec [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f14be-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f14be-104">La mise à niveau peut continuer, mais les rapports qui utilisent des éléments de rapport personnalisés ne s'exécuteront pas comme prévu.</span><span class="sxs-lookup"><span data-stu-id="f14be-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="f14be-105">Le Conseiller de mise à niveau a détecté des éléments de rapport personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f14be-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="f14be-106">La mise à niveau peut continuer, mais vous devez déplacer manuellement les fichiers des éléments de rapport personnalisés vers le nouveau dossier d'installation une fois la mise à niveau terminée.</span><span class="sxs-lookup"><span data-stu-id="f14be-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="f14be-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode natif &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f14be-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="f14be-108">Composant</span><span class="sxs-lookup"><span data-stu-id="f14be-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f14be-109">Description</span><span class="sxs-lookup"><span data-stu-id="f14be-109">Description</span></span>  
 <span data-ttu-id="f14be-110">Le Conseiller de mise à niveau a détecté des paramètres d'extension [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] personnalisés dans les fichiers de configuration, qui indiquent que votre installation inclut un ou plusieurs assemblys personnalisés pour les rapports.</span><span class="sxs-lookup"><span data-stu-id="f14be-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f14be-111">Action corrective</span><span class="sxs-lookup"><span data-stu-id="f14be-111">Corrective Action</span></span>  
 <span data-ttu-id="f14be-112">Une fois la mise à niveau terminée, déplacez manuellement les fichiers des éléments de rapport personnalisés vers le nouveau dossier d'installation.</span><span class="sxs-lookup"><span data-stu-id="f14be-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14be-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f14be-113">See Also</span></span>  
 [<span data-ttu-id="f14be-114">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="f14be-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
