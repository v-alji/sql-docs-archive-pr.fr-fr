---
title: MSSQLSERVER_41307 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41307 (Database Engine error)
ms.assetid: 56f56410-b07d-4379-b01c-702c95761070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 98407a65d5529fd73bccc638df11167131bd9f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702932"
---
# <a name="mssqlserver_41307"></a><span data-ttu-id="76e80-102">MSSQLSERVER_41307</span><span class="sxs-lookup"><span data-stu-id="76e80-102">MSSQLSERVER_41307</span></span>
    
## <a name="details"></a><span data-ttu-id="76e80-103">Détails</span><span class="sxs-lookup"><span data-stu-id="76e80-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76e80-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="76e80-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="76e80-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="76e80-105">Event ID</span></span>|<span data-ttu-id="76e80-106">41307</span><span class="sxs-lookup"><span data-stu-id="76e80-106">41307</span></span>|  
|<span data-ttu-id="76e80-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="76e80-107">Event Source</span></span>|<span data-ttu-id="76e80-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="76e80-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="76e80-109">Composant</span><span class="sxs-lookup"><span data-stu-id="76e80-109">Component</span></span>|<span data-ttu-id="76e80-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="76e80-110">SQLEngine</span></span>|  
|<span data-ttu-id="76e80-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="76e80-111">Symbolic Name</span></span>|<span data-ttu-id="76e80-112">HK_HEKATON_ROW_LIMIT</span><span class="sxs-lookup"><span data-stu-id="76e80-112">HK_HEKATON_ROW_LIMIT</span></span>|  
|<span data-ttu-id="76e80-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="76e80-113">Message Text</span></span>|<span data-ttu-id="76e80-114">La limite de taille de ligne de *nombre* octets pour les tables optimisées en mémoire a été atteinte.</span><span class="sxs-lookup"><span data-stu-id="76e80-114">The row size limit of *number* bytes for memory optimized tables has been exceeded.</span></span> <span data-ttu-id="76e80-115">Veuillez simplifier la définition de la table.</span><span class="sxs-lookup"><span data-stu-id="76e80-115">Please simplify the table definition.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76e80-116">Explication</span><span class="sxs-lookup"><span data-stu-id="76e80-116">Explanation</span></span>  
 <span data-ttu-id="76e80-117">La limite de taille ligne pour les tables optimisées en mémoire est de 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="76e80-117">The row size limit for memory optimized tables is 8,060 bytes.</span></span> <span data-ttu-id="76e80-118">Pour plus d’informations, consultez [Taille de la table et des lignes dans les tables optimisées en mémoire](../in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="76e80-118">For more information, see [Table and Row Size in Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md).</span></span> <span data-ttu-id="76e80-119">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="76e80-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e80-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76e80-120">See Also</span></span>  
 [<span data-ttu-id="76e80-121">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="76e80-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
