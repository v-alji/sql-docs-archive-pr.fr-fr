---
title: MSSQLSERVER_41342 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611828"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="c18f5-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="c18f5-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="c18f5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="c18f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c18f5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="c18f5-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="c18f5-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="c18f5-105">Event ID</span></span>|<span data-ttu-id="c18f5-106">41342</span><span class="sxs-lookup"><span data-stu-id="c18f5-106">41342</span></span>|  
|<span data-ttu-id="c18f5-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="c18f5-107">Event Source</span></span>|<span data-ttu-id="c18f5-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c18f5-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c18f5-109">Composant</span><span class="sxs-lookup"><span data-stu-id="c18f5-109">Component</span></span>|<span data-ttu-id="c18f5-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c18f5-110">SQLEngine</span></span>|  
|<span data-ttu-id="c18f5-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="c18f5-111">Symbolic Name</span></span>|<span data-ttu-id="c18f5-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="c18f5-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="c18f5-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="c18f5-113">Message Text</span></span>|<span data-ttu-id="c18f5-114">Le modèle du processeur sur le système ne prend pas en charge la création de *construct*.</span><span class="sxs-lookup"><span data-stu-id="c18f5-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="c18f5-115">En règle générale, cette erreur se produit avec les processeurs plus anciens.</span><span class="sxs-lookup"><span data-stu-id="c18f5-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="c18f5-116">Pour plus d'informations sur les modèles pris en charge, consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c18f5-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c18f5-117">Explication</span><span class="sxs-lookup"><span data-stu-id="c18f5-117">Explanation</span></span>  
 <span data-ttu-id="c18f5-118">Les tables optimisées en mémoire requièrent un modèle de processeur qui prend en charge les opérations de comparaison et d'échange atomiques sur les valeurs 128 bits, qui nécessitent l'instruction d'assemblage CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="c18f5-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="c18f5-119">Certains modèles de processeur AMD plus anciens ne prennent pas en charge l'instruction CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="c18f5-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="c18f5-120">En outre, certains environnements de virtualisation n'autorisent pas cette instruction par défaut.</span><span class="sxs-lookup"><span data-stu-id="c18f5-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c18f5-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c18f5-121">User Action</span></span>  
 <span data-ttu-id="c18f5-122">Mettez à niveau votre processeur.</span><span class="sxs-lookup"><span data-stu-id="c18f5-122">Upgrade your processor.</span></span> <span data-ttu-id="c18f5-123">Si votre processeur prend en charge l'instruction et que vous exécutez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un ordinateur virtuel, modifiez la configuration afin de prendre en charge l'instruction CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="c18f5-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18f5-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c18f5-124">See Also</span></span>  
 [<span data-ttu-id="c18f5-125">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="c18f5-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
