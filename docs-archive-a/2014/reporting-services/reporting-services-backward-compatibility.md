---
title: Compatibilité descendante Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703812"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="ee638-102">Compatibilité descendante de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ee638-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="ee638-103">Cette section décrit les modifications de comportement entre les versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee638-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="ee638-104">Elle traite des fonctionnalités qui ne sont plus disponibles ou destinées à être supprimées dans les versions futures.</span><span class="sxs-lookup"><span data-stu-id="ee638-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="ee638-105">Elle décrit également les changements importants apportés au produit, connus pour empêcher le bon fonctionnement d’une application personnalisée incluant la fonctionnalité [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee638-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee638-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ee638-106">In This Section</span></span>  
  
|<span data-ttu-id="ee638-107">Rubrique</span><span class="sxs-lookup"><span data-stu-id="ee638-107">Topic</span></span>|<span data-ttu-id="ee638-108">Description</span><span class="sxs-lookup"><span data-stu-id="ee638-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ee638-109">Fonctionnalités supprimées dans SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ee638-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="ee638-110">Décrit les fonctionnalités qui existaient dans les versions antérieures de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , mais ont été supprimées des versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="ee638-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="ee638-111">Fonctions déconseillées dans SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ee638-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="ee638-112">Décrit les fonctionnalités qui existent dans cette version de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour des raisons de compatibilité descendante, mais qui seront supprimées dans une prochaine version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ee638-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="ee638-113">Modifications importantes de SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ee638-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="ee638-114">Décrit les problèmes que vous pouvez rencontrer lors d'une mise à niveau de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee638-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ee638-115">Changements de comportement apportés à SQL Server Reporting Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ee638-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="ee638-116">Décrit les fonctionnalités qui ont changé dans [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee638-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee638-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee638-117">See Also</span></span>  
 <span data-ttu-id="ee638-118">[Compatibilité descendante](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="ee638-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="ee638-119">Compatibilité descendante Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ee638-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
