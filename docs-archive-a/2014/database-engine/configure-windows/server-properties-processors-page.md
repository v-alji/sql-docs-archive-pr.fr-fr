---
title: Propriétés du serveur (page Processeurs) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610841"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="ffdf4-102">Propriétés du serveur (page Processeurs)</span><span class="sxs-lookup"><span data-stu-id="ffdf4-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="ffdf4-103">Utilisez cette page pour afficher ou modifier les options de votre processeur.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="ffdf4-104">Les paramètres d'affinité du processeur ne sont activés que si plusieurs processeurs sont installés.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ffdf4-105">Options</span><span class="sxs-lookup"><span data-stu-id="ffdf4-105">Options</span></span>  
 <span data-ttu-id="ffdf4-106">**Affinité du processeur**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="ffdf4-107">Affecte des processeurs à des threads spécifiques afin d'éliminer les recharges de processeurs et de réduire la migration des threads entre les processeurs.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="ffdf4-108">Pour plus d’informations, consultez [affinity mask (option de configuration de serveur)](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffdf4-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="ffdf4-109">**Affinité d'E/S**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="ffdf4-110">Lie les E/S disque [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à un sous-ensemble spécifié de processeurs.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="ffdf4-111">Pour plus d’informations, consultez [affinity Input-Output mask (option de configuration de serveur)](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffdf4-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="ffdf4-112">**Définir automatiquement le masque d'affinité du processeur pour tous les processeurs**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="ffdf4-113">Autorise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à définir l'affinité du processeur.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="ffdf4-114">**Définir automatiquement le masque d'affinité d'E/S pour tous les processeurs**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="ffdf4-115">Autorise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à définir l'affinité d'E/S.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="ffdf4-116">**Nombre maximal de threads de travail**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="ffdf4-117">0 autorise [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à définir dynamiquement le nombre de threads de travail.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="ffdf4-118">Ce paramètre convient à la plupart des systèmes.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-118">This setting is best for most systems.</span></span> <span data-ttu-id="ffdf4-119">Toutefois, selon votre configuration système, l'attribution d'une valeur spécifique à cette option peut permettre d'accroître les performances.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="ffdf4-120">Pour plus d’informations, consultez [Configurer l’option de configuration du serveur max worker threads](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffdf4-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="ffdf4-121">**Renforcer la priorité SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="ffdf4-122">Indique si l’exécution de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit avoir une priorité de planification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows supérieure à celle d’autres processus du même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="ffdf4-123">Pour plus d’informations, consultez [Configurer l’option de configuration du serveur priority boost](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffdf4-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="ffdf4-124">**Utiliser les fibres Windows (regroupement léger)**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="ffdf4-125">Utilise les fibres Windows plutôt que des threads pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffdf4-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="ffdf4-126">Notez que cette option n’est disponible que dans Windows 2003 Server Edition.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="ffdf4-127">Pour plus d’informations, consultez [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffdf4-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="ffdf4-128">**Valeurs configurées**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-128">**Configured Values**</span></span>  
 <span data-ttu-id="ffdf4-129">Affiche les valeurs configurées pour les options de ce volet.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="ffdf4-130">Si vous modifiez ces valeurs, cliquez sur **Valeurs en cours d’exécution** pour vérifier si les modifications ont été prises en compte.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="ffdf4-131">Si ce n'est pas le cas, l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être d'abord redémarrée.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="ffdf4-132">**Valeurs en cours d’exécution**</span><span class="sxs-lookup"><span data-stu-id="ffdf4-132">**Running Values**</span></span>  
 <span data-ttu-id="ffdf4-133">Affiche les valeurs en cours d'exécution pour les options de ce volet.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="ffdf4-134">Ces valeurs sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ffdf4-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdf4-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffdf4-135">See Also</span></span>  
 [<span data-ttu-id="ffdf4-136">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ffdf4-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
