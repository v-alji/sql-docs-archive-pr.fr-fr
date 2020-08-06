---
title: MSSQLSERVER_17084 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612885"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="8a042-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="8a042-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="8a042-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8a042-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a042-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8a042-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8a042-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8a042-105">Event ID</span></span>|<span data-ttu-id="8a042-106">17084</span><span class="sxs-lookup"><span data-stu-id="8a042-106">17084</span></span>|  
|<span data-ttu-id="8a042-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8a042-107">Event Source</span></span>|<span data-ttu-id="8a042-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8a042-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8a042-109">Composant</span><span class="sxs-lookup"><span data-stu-id="8a042-109">Component</span></span>|<span data-ttu-id="8a042-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8a042-110">SQLEngine</span></span>|  
|<span data-ttu-id="8a042-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8a042-111">Symbolic Name</span></span>|<span data-ttu-id="8a042-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="8a042-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="8a042-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8a042-113">Message Text</span></span>|<span data-ttu-id="8a042-114">La clause WITH de l'instruction BEGIN ATOMIC doit spécifier une valeur pour l'option « %ls ».</span><span class="sxs-lookup"><span data-stu-id="8a042-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8a042-115">Explication</span><span class="sxs-lookup"><span data-stu-id="8a042-115">Explanation</span></span>  
 <span data-ttu-id="8a042-116">La clause WITH de l'instruction BEGIN ATOMIC n'a pas spécifié de valeur pour une option.</span><span class="sxs-lookup"><span data-stu-id="8a042-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a042-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8a042-117">User Action</span></span>  
 <span data-ttu-id="8a042-118">Les blocs `ATOMIC` requièrent des valeurs pour les options `WITH``TRANSACTION ISOLATION LEVEL` et `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="8a042-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="8a042-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8a042-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="8a042-120">Pour plus d’informations, consultez [OLTP en mémoire &#40;optimisation en mémoire&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="8a042-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a042-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a042-121">See Also</span></span>  
 [<span data-ttu-id="8a042-122">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="8a042-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
