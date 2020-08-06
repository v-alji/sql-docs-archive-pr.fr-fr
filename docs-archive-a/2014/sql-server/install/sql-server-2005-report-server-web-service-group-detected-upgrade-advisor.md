---
title: SQL Server groupe de services Web du serveur de rapports 2005 détecté (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deployment [Reporting Services]
ms.assetid: 699d24eb-7756-4b41-9294-ef1a94b2f267
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 70be2b9c4e7abd55daaa752830a73cbe6e222659
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710155"
---
# <a name="sql-server-2005-report-server-web-service-group-detected-upgrade-advisor"></a><span data-ttu-id="80d74-102">Le groupe de service Web du serveur de rapports SQL Server 2005 a été détecté (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="80d74-102">SQL Server 2005 Report Server Web Service group detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="80d74-103">Le conseiller de mise à niveau a détecté que l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance est associée à un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] groupe de service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="80d74-103">Upgrade Advisor detected that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is associated with a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span>  
  
||  
|-|  
|<span data-ttu-id="80d74-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="80d74-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="80d74-105">Composant</span><span class="sxs-lookup"><span data-stu-id="80d74-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="80d74-106">Description</span><span class="sxs-lookup"><span data-stu-id="80d74-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="80d74-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]n’utilise pas la [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Groupe de service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="80d74-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not use the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="80d74-108">Lorsque vous effectuez une mise à niveau de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], ce groupe de service est supprimé et les listes de contrôle d'accès personnalisées pour ce groupe ou les utilisateurs qui appartiennent au groupe ne sont pas conservés pendant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="80d74-108">When you upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this service group is deleted and custom Access Control Lists (ACLs) for this group or users who belong to the group are not retained during the upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="80d74-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="80d74-109">Corrective Action</span></span>  
 <span data-ttu-id="80d74-110">Avant de procéder à la mise à niveau, sauvegardez toutes les listes de contrôle d'accès personnalisées ou tous les utilisateurs qui appartiennent au groupe de service Web Report Server [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80d74-110">Before you upgrade, back up any custom ACLs or users who belong to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="80d74-111">Pour ce faire, vous pouvez utiliser l’outil en ligne de commande **Icacls.exe** dans [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 (ou version ultérieure) ou l’outil de ligne de commande Cacls.exe dans les systèmes d’exploitation Windows antérieurs à [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span><span class="sxs-lookup"><span data-stu-id="80d74-111">To do this, you can use the **Icacls.exe** command-line tool in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 and later or the Cacls.exe command-line tool in Windows operating systems prior to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span></span> <span data-ttu-id="80d74-112">Pour plus d'informations sur la syntaxe utilisée dans ces outils, consultez la documentation produit de Windows.</span><span class="sxs-lookup"><span data-stu-id="80d74-112">For more information about the syntax for these tools, see the Windows product documentation.</span></span> <span data-ttu-id="80d74-113">Une fois l'installation terminée, appliquez les listes de contrôle d'accès personnalisées ou les utilisateurs au groupe Windows Report Server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour votre instance du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="80d74-113">After setup successfully completes, apply the custom ACLs or users to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group for your report server instance.</span></span> <span data-ttu-id="80d74-114">Le [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] groupe Windows du serveur de rapports prend la forme SQLServerReportServerUser $ \<*computer_name*> $ \<*instance_name*> .</span><span class="sxs-lookup"><span data-stu-id="80d74-114">The [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group takes the form of SQLServerReportServerUser$\<*computer_name*>$\<*instance_name*>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d74-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80d74-115">See Also</span></span>  
 [<span data-ttu-id="80d74-116">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="80d74-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
