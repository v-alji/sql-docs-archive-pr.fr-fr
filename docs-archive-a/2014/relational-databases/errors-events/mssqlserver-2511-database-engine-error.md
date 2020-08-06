---
title: MSSQLSERVER_2511 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699636"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="402a9-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="402a9-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="402a9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="402a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="402a9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="402a9-104">Product Name</span></span>|<span data-ttu-id="402a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="402a9-105">SQL Server</span></span>|  
|<span data-ttu-id="402a9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="402a9-106">Event ID</span></span>|<span data-ttu-id="402a9-107">2511</span><span class="sxs-lookup"><span data-stu-id="402a9-107">2511</span></span>|  
|<span data-ttu-id="402a9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="402a9-108">Event Source</span></span>|<span data-ttu-id="402a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="402a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="402a9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="402a9-110">Component</span></span>|<span data-ttu-id="402a9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="402a9-111">SQLEngine</span></span>|  
|<span data-ttu-id="402a9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="402a9-112">Symbolic Name</span></span>|<span data-ttu-id="402a9-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="402a9-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="402a9-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="402a9-114">Message Text</span></span>|<span data-ttu-id="402a9-115">Erreur de table, ID d’objet %d, ID d’index %d, ID de partition %I64d, ID d’unité d’allocation %I64d (type %.\*ls).</span><span class="sxs-lookup"><span data-stu-id="402a9-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="402a9-116">Les clés sont désordonnées sur la page %S_PGID, slots %d et %d.</span><span class="sxs-lookup"><span data-stu-id="402a9-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="402a9-117">Explication</span><span class="sxs-lookup"><span data-stu-id="402a9-117">Explanation</span></span>  
 <span data-ttu-id="402a9-118">Des clés désordonnées ont été détectées dans l'index spécifié.</span><span class="sxs-lookup"><span data-stu-id="402a9-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="402a9-119">La page qui contient ces clés peut être endommagée.</span><span class="sxs-lookup"><span data-stu-id="402a9-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="402a9-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="402a9-120">User Action</span></span>  
 <span data-ttu-id="402a9-121">Reconstruisez l'index spécifié en utilisant l'instruction ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="402a9-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
