---
title: Les composants de compatibilité descendante IIS n’ont pas été détectés (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IIS [Reporting Services]
ms.assetid: e794185a-0a77-480a-9aea-d09f8760a6b8
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a5aad54a01b3840e121c6a63de0ea26f35921fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613781"
---
# <a name="iis-backward-compatibility-components-were-not-detected-upgrade-advisor"></a><span data-ttu-id="a8466-102">Les composants de compatibilité descendante IIS n'ont pas été détectés (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="a8466-102">IIS backward compatibility components were not detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="a8466-103">Le Conseiller de mise à niveau n'a pas détecté les composants et paramètres IIS qui fournissent des informations utilisées par le programme d'installation pour créer les nouvelles URL de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8466-103">Upgrade Advisor did not detect IIS components and settings that provide information used by Setup to create new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLS.</span></span>  
  
||  
|-|  
|<span data-ttu-id="a8466-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="a8466-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="a8466-105">Composant</span><span class="sxs-lookup"><span data-stu-id="a8466-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a8466-106">Description</span><span class="sxs-lookup"><span data-stu-id="a8466-106">Description</span></span>  
 <span data-ttu-id="a8466-107">IIS inclut des composants qui fournissent des informations sur les répertoires virtuels du serveur de rapports et du Gestionnaire de rapports, et ces composants ne sont pas installés sur l'ordinateur serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a8466-107">IIS includes components that provide information about the report server and Report Manager virtual directories, and those components are not installed on the report server computer.</span></span> <span data-ttu-id="a8466-108">La mise à niveau peut continuer, mais les URL du serveur de rapports et du Gestionnaire de rapports ne seront pas recréées par la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a8466-108">Upgrade can continue, but URLs for the report server or Report Manager will not be recreated by upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a8466-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a8466-109">Corrective Action</span></span>  
 <span data-ttu-id="a8466-110">Une fois la mise à niveau terminée, utilisez l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour définir les URL pour le serveur de rapports ou le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="a8466-110">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set the URLs for report server or Report Manager.</span></span> <span data-ttu-id="a8466-111">Utilisez le Gestionnaire des services IIS pour supprimer les répertoires virtuels dont vous n'avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="a8466-111">Use IIS Manager to remove the virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="a8466-112">Pour plus d’informations, consultez [configurer une URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="a8466-112">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8466-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8466-113">See Also</span></span>  
 [<span data-ttu-id="a8466-114">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="a8466-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
