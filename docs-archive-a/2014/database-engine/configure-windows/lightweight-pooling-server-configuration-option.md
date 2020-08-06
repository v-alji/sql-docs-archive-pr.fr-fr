---
title: lightweight pooling (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610855"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="b8720-102">lightweight pooling (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="b8720-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="b8720-103">Utilisez l’option **lightweight pooling** pour fournir un moyen de réduire la charge système associée aux basculements excessifs de contexte rencontrés parfois en environnement de multitraitement symétrique.</span><span class="sxs-lookup"><span data-stu-id="b8720-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="b8720-104">En cas de basculements de contexte excessifs, le regroupement léger peut offrir une meilleure capacité de traitement en effectuant le basculement de contexte en ligne, ce qui permet de réduire les permutations circulaires utilisateur/noyau.</span><span class="sxs-lookup"><span data-stu-id="b8720-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="b8720-105">Le mode fibre est prévu pour certaines situations dans lesquelles le basculement de contexte des travailleurs UMS constitue le goulot d'étranglement critique en ce qui concerne les performances.</span><span class="sxs-lookup"><span data-stu-id="b8720-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="b8720-106">Ces situations étant rares, le mode fibre améliore rarement les performance ou l'évolutivité sur un système ordinaire.</span><span class="sxs-lookup"><span data-stu-id="b8720-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="b8720-107">L’amélioration du basculement de contexte dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] a également réduit la nécessité du mode fibre.</span><span class="sxs-lookup"><span data-stu-id="b8720-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="b8720-108">Il n'est pas recommandé d'utiliser la planification du mode fibre pour les opérations courantes.</span><span class="sxs-lookup"><span data-stu-id="b8720-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="b8720-109">Ceci pour deux raisons : cela peut réduire les performances en inhibant les avantages ordinaires du basculement de contexte et certains composants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui utilisent des objets TLS (Thread Stockage Local) ou possédés par des threads, tels que des mutexes (un type d'objet de noyau Win32), ne peuvent pas fonctionner correctement en mode fibre.</span><span class="sxs-lookup"><span data-stu-id="b8720-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="b8720-110">Quand l’option**lightweight pooling** a la valeur 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bascule en planification de mode fibre.</span><span class="sxs-lookup"><span data-stu-id="b8720-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="b8720-111">La valeur par défaut de cette option est 0.</span><span class="sxs-lookup"><span data-stu-id="b8720-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="b8720-112">L’option **lightweight pooling** est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="b8720-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="b8720-113">Si vous utilisez la procédure stockée système **sp_configure** pour changer sa valeur, vous ne pouvez modifier l’option **lightweight pooling** que si la valeur 1 a été attribuée à l’option **Afficher les options avancées**.</span><span class="sxs-lookup"><span data-stu-id="b8720-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="b8720-114">Le paramétrage prend effet une fois le serveur redémarré.</span><span class="sxs-lookup"><span data-stu-id="b8720-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8720-115">Le regroupement léger n’est pas pris en charge pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 ni [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span><span class="sxs-lookup"><span data-stu-id="b8720-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="b8720-116">fournit une prise en charge complète du regroupement léger.</span><span class="sxs-lookup"><span data-stu-id="b8720-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8720-117">L'exécution du CLR (Common Language Runtime) n'est pas prise en charge sous l'option lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="b8720-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="b8720-118">Désactivez l'une des deux options suivantes : « clr enabled » ou « lightweight pooling ».</span><span class="sxs-lookup"><span data-stu-id="b8720-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="b8720-119">Les fonctionnalités qui reposent sur le CLR et qui ne fonctionnent pas correctement en mode fibre incluent le type de données de hiérarchie, la réplication et la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="b8720-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8720-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8720-120">See Also</span></span>  
 <span data-ttu-id="b8720-121">[clr enabled (option de configuration de serveur)](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="b8720-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="b8720-122">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8720-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b8720-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b8720-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="b8720-124">clr enabled (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="b8720-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
