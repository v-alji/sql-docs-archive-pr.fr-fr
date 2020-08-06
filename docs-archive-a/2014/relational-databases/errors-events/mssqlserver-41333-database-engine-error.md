---
title: MSSQLSERVER_41333 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701231"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="a0744-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="a0744-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="a0744-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a0744-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0744-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a0744-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a0744-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a0744-105">Event ID</span></span>|<span data-ttu-id="a0744-106">41333</span><span class="sxs-lookup"><span data-stu-id="a0744-106">41333</span></span>|  
|<span data-ttu-id="a0744-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a0744-107">Event Source</span></span>|<span data-ttu-id="a0744-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a0744-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a0744-109">Composant</span><span class="sxs-lookup"><span data-stu-id="a0744-109">Component</span></span>|<span data-ttu-id="a0744-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a0744-110">SQLEngine</span></span>|  
|<span data-ttu-id="a0744-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a0744-111">Symbolic Name</span></span>|<span data-ttu-id="a0744-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="a0744-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="a0744-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a0744-113">Message Text</span></span>|<span data-ttu-id="a0744-114">Les transactions suivantes doivent accéder à des tables mémoire optimisées et à des procédures stockées compilées en mode natif dans un isolement d’instantané : transactions RepeatableRead, transactions Serializable et transactions qui accèdent aux tables non mémoire optimisées dans l’isolement RepeatableRead ou Serializable.</span><span class="sxs-lookup"><span data-stu-id="a0744-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0744-115">Explication</span><span class="sxs-lookup"><span data-stu-id="a0744-115">Explanation</span></span>  
 <span data-ttu-id="a0744-116">Des restrictions s'appliquent à l'utilisateur pour des niveaux d'isolement plus élevés, entre des transactions sur disque et des transactions XTP.</span><span class="sxs-lookup"><span data-stu-id="a0744-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0744-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a0744-117">User Action</span></span>  
 <span data-ttu-id="a0744-118">Ne tentez pas des opérations de haut niveau d'isolement sur les tables optimisées en mémoire (et les procédures compilées en mode natif) et les tables sur disque.</span><span class="sxs-lookup"><span data-stu-id="a0744-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="a0744-119">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="a0744-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0744-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0744-120">See Also</span></span>  
 [<span data-ttu-id="a0744-121">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="a0744-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
