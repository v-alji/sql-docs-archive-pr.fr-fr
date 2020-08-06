---
title: Propriétés de la mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710843"
---
# <a name="memory-properties"></a><span data-ttu-id="9a4e5-102">Propriétés de mémoire</span><span class="sxs-lookup"><span data-stu-id="9a4e5-102">Memory Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="9a4e5-103">prend en charge les propriétés de mémoire du serveur répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-103">supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="9a4e5-104">Pour obtenir des conseils sur la définition de ces propriétés, consultez le [guide des opérations de SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="9a4e5-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="9a4e5-105">Les valeurs comprises entre 1 et 100 représentent des pourcentages de **mémoire physique totale** ou d' **espace d'adressage virtuel**, la valeur la plus petite étant retenue.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="9a4e5-106">Les valeurs supérieures à 100 représentent les limites de mémoire en octets.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="9a4e5-107">**S’applique à :** Mode serveur multidimensionnel et tabulaire, sauf indication contraire.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9a4e5-108">Propriétés</span><span class="sxs-lookup"><span data-stu-id="9a4e5-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="9a4e5-109">Une propriété de nombre signé 64 bits à virgule flottante double précision qui définit le point auquel le serveur manque de mémoire, exprimée en pourcentage de mémoire physique totale.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="9a4e5-110">Lorsque cette limite est atteinte, l'instance commence lentement à nettoyer la mémoire des caches en fermant les sessions expirées et en déchargeant les calculs non utilisés.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="9a4e5-111">Le serveur ne libère pas la mémoire en dessous de cette limite.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="9a4e5-112">La valeur par défaut est 65, ce qui indique que la limite de mémoire inférieure correspond à 65 % de la mémoire physique ou de l'espace d'adressage virtuel, la valeur inférieure étant applicable.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="9a4e5-113">Définit un seuil qui, une fois atteint, a pour effet d'indiquer au serveur de désallouer la mémoire de façon intensive.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="9a4e5-114">La valeur par défaut est 80 % de la mémoire physique ou de l'espace d'adressage virtuel, la valeur inférieure étant applicable.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="9a4e5-115">Notez que `TotalMemoryLimit` doit toujours être inférieur à `HardMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="9a4e5-116">Spécifie un seuil de mémoire après lequel l'instance ferme de façon intensive les sessions utilisateur actives pour réduire l'utilisation de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="9a4e5-117">Toutes les sessions fermées vont générer une erreur relative à l'annulation par sollicitation de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="9a4e5-118">La valeur par défaut, zéro (0), signifie que `HardMemoryLimit` aura une valeur intermédiaire entre `TotalMemoryLimit` et la mémoire physique totale du système ; si la mémoire physique du système est supérieure à l'espace d'adressage virtuel du processus, l'espace d'adressage virtuel sera utilisé à la place pour calculer `HardMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="9a4e5-119">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="9a4e5-120">Spécifie le comportement de pagination lorsque le serveur est à court de mémoire.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="9a4e5-121">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a4e5-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="9a4e5-122">Zéro (**0**) désactive la pagination.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="9a4e5-123">Si la mémoire est insuffisante, le traitement échoue avec une erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="9a4e5-124">Si vous désactivez la pagination, vous devez accorder des privilèges Windows au compte de service.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="9a4e5-125">Pour obtenir des instructions, consultez [Configurer les comptes de service &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a4e5-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="9a4e5-126">**1** est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-126">**1** is the default.</span></span> <span data-ttu-id="9a4e5-127">Cette propriété active la pagination sur le disque à l'aide du fichier de pagination du système d'exploitation (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="9a4e5-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="9a4e5-128">Lorsque `VertiPaqPagingPolicy` est défini sur 1, le traitement est moins susceptible d'échouer à cause des contraintes de mémoire, car le serveur tente de paginer sur le disque à l'aide de la méthode spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="9a4e5-129">La définition de la propriété `VertiPaqPagingPolicy` ne garantit pas que les erreurs de mémoire ne se produiront pas.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="9a4e5-130">Les erreurs de mémoire insuffisante peuvent toujours se produire dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a4e5-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="9a4e5-131">Il n'y a pas assez de mémoire pour tous les dictionnaires.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="9a4e5-132">Au cours du traitement, Analysis Services verrouille les dictionnaires pour chaque colonne dans la mémoire, et l'ensemble de ces éléments ne peut pas dépasser la valeur spécifiée pour `VertiPaqMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="9a4e5-133">L'espace d'adressage virtuel est insuffisant pour le processus.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="9a4e5-134">Pour résoudre les erreurs persistantes de mémoire insuffisante, vous pouvez reconcevoir le modèle pour réduire la quantité de données à traiter, ou bien ajouter plus de mémoire physique à l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="9a4e5-135">S'applique au mode serveur tabulaire uniquement.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="9a4e5-136">Si la pagination sur le disque est autorisée, cette propriété indique le niveau de la consommation de mémoire (en pourcentage de la mémoire totale) auquel la pagination démarre.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="9a4e5-137">La valeur par défaut est 60.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-137">The default is 60.</span></span> <span data-ttu-id="9a4e5-138">Si la consommation de mémoire est inférieure à 60 %, le serveur ne paginera pas sur le disque.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="9a4e5-139">Cette propriété dépend de `VertiPaqPagingPolicyProperty`, qui doit avoir la valeur 1 pour autoriser la pagination.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="9a4e5-140">S'applique au mode serveur tabulaire uniquement.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="9a4e5-141">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="9a4e5-142">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="9a4e5-143">S'applique au mode serveur multidimensionnel uniquement.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="9a4e5-144">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="9a4e5-145">S'applique au mode serveur multidimensionnel uniquement.</span><span class="sxs-lookup"><span data-stu-id="9a4e5-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="9a4e5-146">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="9a4e5-147">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="9a4e5-148">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="9a4e5-149">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="9a4e5-150">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="9a4e5-151">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="9a4e5-152">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a4e5-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a4e5-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a4e5-153">See Also</span></span>  
 <span data-ttu-id="9a4e5-154">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a4e5-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="9a4e5-155">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9a4e5-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
