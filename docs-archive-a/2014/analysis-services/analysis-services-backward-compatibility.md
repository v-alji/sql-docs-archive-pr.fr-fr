---
title: Compatibilité descendante Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: 618b6c3a-e20d-47a9-b2c6-6d848dfba05a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a5296bfbd2bae746eb9936d416fd696de16cb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602665"
---
# <a name="analysis-services-backward-compatibility"></a><span data-ttu-id="4d1e2-102">Compatibilité descendante Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d1e2-102">Analysis Services Backward Compatibility</span></span>
  <span data-ttu-id="4d1e2-103">Les rubriques de cette section décrivent les changements de comportement entre les versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d1e2-103">The topics in this section describe the changes in behavior between versions of  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d1e2-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4d1e2-104">In This Section</span></span>  
  
|<span data-ttu-id="4d1e2-105">Rubriques</span><span class="sxs-lookup"><span data-stu-id="4d1e2-105">Topics</span></span>|<span data-ttu-id="4d1e2-106">Description</span><span class="sxs-lookup"><span data-stu-id="4d1e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d1e2-107">Fonctionnalités Analysis Services déconseillées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4d1e2-107">Deprecated Analysis Services Features in SQL Server 2014</span></span>](deprecated-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="4d1e2-108">Décrit les fonctionnalités qui ont été conservées dans la version actuelle pour des raisons de compatibilité descendante, mais qui seront supprimées dans une prochaine version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d1e2-108">Describes features that have been retained in the current version to maintain backward compatibility,  but which will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="4d1e2-109">Fonctionnalités Analysis Services abandonnées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4d1e2-109">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)|<span data-ttu-id="4d1e2-110">Décrit les fonctionnalités qui existaient dans les versions antérieures de  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , mais qui ont été depuis supprimées des versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4d1e2-110">Describes features that existed in earlier versions of  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] but that have since been removed in later versions.</span></span>|  
|[<span data-ttu-id="4d1e2-111">Modifications avec rupture dans les fonctionnalités Analysis Services de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4d1e2-111">Breaking Changes to Analysis Services Features in SQL Server 2014</span></span>](breaking-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="4d1e2-112">Décrit les modifications de code introduites dans cette version de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] susceptibles d’interrompre un modèle, une application personnalisée ou un script créé dans une version précédente du logiciel.</span><span class="sxs-lookup"><span data-stu-id="4d1e2-112">Describes code changes introduced in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that could potentially break a model or custom applications or script created in previous versions of the software .</span></span>|  
|[<span data-ttu-id="4d1e2-113">Modifications de comportement des fonctionnalités Analysis Services dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4d1e2-113">Behavior Changes to Analysis Services Features in SQL Server 2014</span></span>](behavior-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="4d1e2-114">Décrit les fonctionnalités existantes qui présentent des comportements différents dans cette version d’ [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d1e2-114">Describes existing features that have different behaviors in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4d1e2-115">Voici quelques exemples d’opérations courantes : remplacer une valeur par défaut par une nouvelle valeur ou une valeur différente, interdire une opération ou une configuration précédemment autorisée, ou encore forcer la révision ou le remplacement manuel d’une configuration ou d’un paramètre perdu pendant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4d1e2-115">Common examples include changing a default to a new or different value, disallowing a previously allowable operation or configuration, or a introducing a requirement to manually revise or replace a setting or configuration that is lost during upgrade.</span></span><br /> <span data-ttu-id="4d1e2-116">.</span><span class="sxs-lookup"><span data-stu-id="4d1e2-116">.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d1e2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d1e2-117">See Also</span></span>  
 <span data-ttu-id="4d1e2-118">[Nouveautés de Analysis Services et Business Intelligence](what-s-new-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4d1e2-118">[What's New in Analysis Services and Business Intelligence](what-s-new-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="4d1e2-119">Mettre à niveau Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d1e2-119">Upgrade Analysis Services</span></span>](../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
