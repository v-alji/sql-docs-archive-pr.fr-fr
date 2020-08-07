---
title: Copier les éléments de projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], copying
- packages [Integration Services], copying
- copying data source views
- copying data sources
- copying packages
- data source views [Integration Services], copying
ms.assetid: 1606c54d-20f9-49f3-a4ef-caad83a772aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3456209c467c3b8474e130181d02304911098d2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610790"
---
# <a name="copy-project-items"></a><span data-ttu-id="d02f0-102">Copier des éléments de projet</span><span class="sxs-lookup"><span data-stu-id="d02f0-102">Copy Project Items</span></span>
  <span data-ttu-id="d02f0-103">Cette rubrique explique comment copier des objets dans un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou entre des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02f0-103">This topic describes how to copy objects within an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="d02f0-104">Vous pouvez également copier des objets entre les autres types de projets [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] et [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02f0-104">You can also copy objects between the other types of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] projects, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d02f0-105">Pour pouvoir effectuer une copie entre des projets, il faut qu'ils appartiennent à la même solution [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02f0-105">To copy between projects, the project must be part of the same [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solution.</span></span> <span data-ttu-id="d02f0-106">Pour plus d’informations, consultez [Projets Integration Services &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="d02f0-106">For more information, see [Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md).</span></span>  
  
### <a name="to-copy-project-level-items"></a><span data-ttu-id="d02f0-107">Pour copier des éléments de niveau projet</span><span class="sxs-lookup"><span data-stu-id="d02f0-107">To copy project level items</span></span>  
  
1.  <span data-ttu-id="d02f0-108">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou la solution [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] avec lequel vous voulez travailler.</span><span class="sxs-lookup"><span data-stu-id="d02f0-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or solution that you want to work with.</span></span>  
  
2.  <span data-ttu-id="d02f0-109">Développez le projet et le dossier de l'élément à partir desquels effectuer la copie.</span><span class="sxs-lookup"><span data-stu-id="d02f0-109">Expand the project and item folder to copy from.</span></span>  
  
3.  <span data-ttu-id="d02f0-110">Cliquez avec le bouton droit sur l’élément, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="d02f0-110">Right-click the item and click **Copy**.</span></span>  
  
4.  <span data-ttu-id="d02f0-111">Cliquez avec le bouton droit sur le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vers lequel effectuer la copie, puis cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="d02f0-111">Right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to copy to and click **Paste**.</span></span>  
  
     <span data-ttu-id="d02f0-112">Les éléments sont automatiquement copiés dans le dossier approprié.</span><span class="sxs-lookup"><span data-stu-id="d02f0-112">The items are automatically copied to the correct folder.</span></span> <span data-ttu-id="d02f0-113">Si vous copiez dans le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] des éléments qui ne sont pas des packages, ces éléments sont copiés dans le dossier **Divers**.</span><span class="sxs-lookup"><span data-stu-id="d02f0-113">If you copy items to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that are not packages, the items are copied to the **Miscellaneous** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02f0-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d02f0-114">See Also</span></span>  
 <span data-ttu-id="d02f0-115">[Integration Services &#40;des packages de&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d02f0-115">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="d02f0-116">Copier des objets de packages</span><span class="sxs-lookup"><span data-stu-id="d02f0-116">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
  
