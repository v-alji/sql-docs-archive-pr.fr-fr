---
title: Migrer des scripts vers VSTA | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708060"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="bb7dc-102">Migrer des scripts vers VSTA</span><span class="sxs-lookup"><span data-stu-id="bb7dc-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="bb7dc-103">Lorsque vous mettez à niveau des [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migre les scripts dans des tâches de script ou des composants script vers [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="bb7dc-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="bb7dc-104">VSTA est l'environnement de script que [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilise.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="bb7dc-105">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , l’environnement de script pour [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span><span class="sxs-lookup"><span data-stu-id="bb7dc-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="bb7dc-106">Si les scripts des tâches de script ou des composants Script font référence à des interfaces, il se peut que vous deviez modifier ces références avant de mettre le package à niveau.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="bb7dc-107">Si vous ne le faites pas, la mise à niveau du package ou la validation des scripts échoue, selon la méthode de mise à niveau choisie.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="bb7dc-108">Pour modifier ces références, remplacez les références aux interfaces IDTS*xxx*90 par des références aux interfaces IDTS*xxx*100 correspondantes.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="bb7dc-109">Pour plus d’informations sur la migration des scripts et des packages de mise à niveau, consultez [mettre à niveau des packages Integration Services](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bb7dc-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="bb7dc-110">Présentation des échecs de migration</span><span class="sxs-lookup"><span data-stu-id="bb7dc-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="bb7dc-111">Lorsque vous migrez les scripts, la migration peut échouer pour l'une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb7dc-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="bb7dc-112">Le point d'entrée du script VSA a été renommé.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="bb7dc-113">Le point d'entrée spécifie dans la classe `ScriptMain` du projet VSTA la méthode que le runtime [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise comme point d'entrée du code de tâche de script.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="bb7dc-114">La classe `ScriptMain` est celle que génèrent par défaut les modèles de script.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="bb7dc-115">Le script VSA ne contient aucun point d'entrée ou en contient plusieurs.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="bb7dc-116">Des références d'assemblys n'ont pas pu être ajoutées.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="bb7dc-117">La classe `ScriptMain` a été modifiée pour hériter d'autres classes en plus de la classe de `ScriptObjectModelSSIS`.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="bb7dc-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]ne prend pas en charge l’héritage multiple.</span><span class="sxs-lookup"><span data-stu-id="bb7dc-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="bb7dc-119">Vous ne pouvez pas convertir un script VSA qui utilise [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] dans un script VSTA qui utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb7dc-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="bb7dc-120">Toutefois, vous pouvez créer un nouveau script VSTA qui utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb7dc-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="bb7dc-121">Pour plus d’informations, consultez [Codage et débogage de la tâche de script](../../integration-services/control-flow/script-task.md) et [Codage et débogage du composant Script](../../integration-services/data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="bb7dc-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7dc-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb7dc-122">See Also</span></span>  
 [<span data-ttu-id="bb7dc-123">Extension de packages avec des scripts</span><span class="sxs-lookup"><span data-stu-id="bb7dc-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
