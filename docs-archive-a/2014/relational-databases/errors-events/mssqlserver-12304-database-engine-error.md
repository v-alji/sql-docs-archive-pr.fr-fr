---
title: MSSQLSERVER_12304 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12304 (Database Engine error)
ms.assetid: a2c252c2-e815-4ac8-a101-7af5b32e3233
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2347fc46fe5ab83ef2ff46b81500cd737ed02d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611114"
---
# <a name="mssqlserver_12304"></a><span data-ttu-id="2fb52-102">MSSQLSERVER_12304</span><span class="sxs-lookup"><span data-stu-id="2fb52-102">MSSQLSERVER_12304</span></span>
    
## <a name="details"></a><span data-ttu-id="2fb52-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2fb52-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fb52-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2fb52-104">Product Name</span></span>|<span data-ttu-id="2fb52-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fb52-105">SQL Server</span></span>|  
|<span data-ttu-id="2fb52-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2fb52-106">Event ID</span></span>|<span data-ttu-id="2fb52-107">12304</span><span class="sxs-lookup"><span data-stu-id="2fb52-107">12304</span></span>|  
|<span data-ttu-id="2fb52-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2fb52-108">Event Source</span></span>|<span data-ttu-id="2fb52-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2fb52-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2fb52-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2fb52-110">Component</span></span>|<span data-ttu-id="2fb52-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2fb52-111">SQLEngine</span></span>|  
|<span data-ttu-id="2fb52-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2fb52-112">Symbolic Name</span></span>|<span data-ttu-id="2fb52-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span><span class="sxs-lookup"><span data-stu-id="2fb52-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span></span>|  
|<span data-ttu-id="2fb52-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2fb52-114">Message Text</span></span>|<span data-ttu-id="2fb52-115">L'utilisation d'un type de table optimisée en mémoire utilisant la propriété IDENTITY avec l'une de ses colonnes n'est pas prise en charge lors de l'utilisation du type hors du contexte de la procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="2fb52-115">Using a memory optimized table type that uses the IDENTITY property with any of its columns is not supported when using the type outside the context of a natively compiled stored procedure.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="2fb52-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2fb52-116">User Action</span></span>  
 <span data-ttu-id="2fb52-117">N'utilisez pas un type de table optimisée en mémoire qui utilise la propriété d'identité avec l'une de ses colonnes.</span><span class="sxs-lookup"><span data-stu-id="2fb52-117">Do not use a memory-optimized table type that uses the identity property with any of its columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb52-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2fb52-118">See Also</span></span>  
 [<span data-ttu-id="2fb52-119">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="2fb52-119">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
