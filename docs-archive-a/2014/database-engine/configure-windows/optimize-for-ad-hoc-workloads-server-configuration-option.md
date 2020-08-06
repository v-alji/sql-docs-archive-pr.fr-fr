---
title: optimize for ad hoc workloads (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697163"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="3c0ce-102">optimize for ad hoc workloads (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="3c0ce-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="3c0ce-103">L'option **optimize for ad hoc workloads** permet d'améliorer l'efficacité du cache du plan pour les charges de travail qui contiennent de nombreux lots ad hoc à usage unique.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="3c0ce-104">Lorsque cette option a la valeur 1, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] stocke un petit stub du plan compilé dans le cache du plan lorsqu'un lot est compilé pour la première fois, au lieu du plan compilé complet.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="3c0ce-105">La mémoire est ainsi moins sollicitée car le cache du plan n'est pas saturé de plans compilés qui ne sont pas réutilisés.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="3c0ce-106">Le stub du plan compilé permet au [!INCLUDE[ssDE](../../includes/ssde-md.md)] de reconnaître que ce lot ad hoc a déjà été compilé mais qu'il n'a stocké qu'un stub du plan compilé. Par conséquent, lorsque le lot est à nouveau appelé (compilé ou exécuté), le [!INCLUDE[ssDE](../../includes/ssde-md.md)] compile le lot, supprime le stub du plan compilé du cache du plan et ajoute le plan compilé complet au cache du plan.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="3c0ce-107">Attribuer la valeur 1 à l'option **Optimiser pour les charges de travail ad hoc** affecte uniquement les nouveaux plans ; les plans qui se trouvent déjà dans le cache du plan ne sont pas concernés.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="3c0ce-108">Le stub du plan compilé est l'un des types d'objets cache contenus dans l'affichage catalogue sys.dm_exec_cached_plans.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="3c0ce-109">Il possède un handle SQL et un handle de plan qui sont uniques.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="3c0ce-110">Aucun plan d'exécution n'est associé au stub du plan compilé et interroger le handle du plan ne retourne pas de plan d'exécution de requêtes XML.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="3c0ce-111">L'indicateur de trace 8 032 rétablit les paramètres de limitation du cache au paramètre RTM [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] qui permet en général aux caches d'être plus volumineux.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="3c0ce-112">Utilisez ce paramètre quand les entrées du cache fréquemment utilisées ne tiennent pas dans le cache et que l’ *option de configuration de serveur Optimiser pour les charges de travail ad hoc* ne permet pas de résoudre le problème avec le cache du plan.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3c0ce-113">L'indicateur de trace 8 032 peut altérer les performances si des caches volumineux diminuent la mémoire disponible pour les autres consommateurs, tels que le pool de mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="3c0ce-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0ce-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c0ce-114">See Also</span></span>  
 <span data-ttu-id="3c0ce-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c0ce-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="3c0ce-116">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0ce-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
