---
title: Chevauchement correct du masque d’affinité et du masque de sortie d’entrée d’affinité | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710583"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="5e105-102">Chevauchement correct du masque d’affinité et du masque de sortie d’entrée d’affinité</span><span class="sxs-lookup"><span data-stu-id="5e105-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="5e105-103">Cette règle vérifie si l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un ou plusieurs processeurs prévus pour être utilisés à la fois avec l'option affinity mask (masque d'affinité) et l'option affinity I/O mask (masque d'affinité d'E/S).</span><span class="sxs-lookup"><span data-stu-id="5e105-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="5e105-104">Sur un ordinateur doté de plusieurs processeurs, les options affinity mask et affinity I/O mask sont utilisées pour désigner quels processeurs sont utilisés par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e105-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5e105-105">L'activation d'un processeur à la fois dans affinity mask et dans affinity I/O mask peut ralentir les performances en forçant l'utilisation excessive du processeur.</span><span class="sxs-lookup"><span data-stu-id="5e105-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="5e105-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="5e105-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="5e105-107">Lorsque vous définissez l'option affinity mask, vous devez également définir l'option affinity I/O mask, et inversement, mais vous ne devez activer chaque processeur que dans l'une de ces options.</span><span class="sxs-lookup"><span data-stu-id="5e105-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="5e105-108">N'activez pas le même processeur à la fois dans l'option affinity mask et dans l'option affinity I/O mask.</span><span class="sxs-lookup"><span data-stu-id="5e105-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="5e105-109">Les bits correspondant à chaque processeur doivent présenter l'un des états suivants :</span><span class="sxs-lookup"><span data-stu-id="5e105-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="5e105-110">0 dans l'option affinity mask et dans l'option affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="5e105-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="5e105-111">0 dans l'option affinity mask et 1 dans l'option affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="5e105-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="5e105-112">1 dans l'option affinity mask et 0 dans l'option affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="5e105-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="5e105-113">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="5e105-113">For More Information</span></span>  
 [<span data-ttu-id="5e105-114">affinity mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="5e105-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="5e105-115">affinity Input-Otput mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="5e105-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="5e105-116">affinity64 mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="5e105-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="5e105-117">affinity64 Input-Output mask (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="5e105-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e105-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e105-118">See Also</span></span>  
 [<span data-ttu-id="5e105-119">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="5e105-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
