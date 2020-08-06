---
title: MSSQLSERVER_2546 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696872"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="96c6e-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="96c6e-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="96c6e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="96c6e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96c6e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="96c6e-104">Product Name</span></span>|<span data-ttu-id="96c6e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="96c6e-105">SQL Server</span></span>|  
|<span data-ttu-id="96c6e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="96c6e-106">Event ID</span></span>|<span data-ttu-id="96c6e-107">2546</span><span class="sxs-lookup"><span data-stu-id="96c6e-107">2546</span></span>|  
|<span data-ttu-id="96c6e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="96c6e-108">Event Source</span></span>|<span data-ttu-id="96c6e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="96c6e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="96c6e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="96c6e-110">Component</span></span>|<span data-ttu-id="96c6e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="96c6e-111">SQLEngine</span></span>|  
|<span data-ttu-id="96c6e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="96c6e-112">Symbolic Name</span></span>|<span data-ttu-id="96c6e-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="96c6e-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="96c6e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="96c6e-114">Message Text</span></span>|<span data-ttu-id="96c6e-115">L'index 'INDEX_NAME' de la table 'OBJECT_NAME' est marqué comme étant désactivé.</span><span class="sxs-lookup"><span data-stu-id="96c6e-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="96c6e-116">Reconstruisez l'index pour qu'il soit en ligne.</span><span class="sxs-lookup"><span data-stu-id="96c6e-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96c6e-117">Explication</span><span class="sxs-lookup"><span data-stu-id="96c6e-117">Explanation</span></span>  
 <span data-ttu-id="96c6e-118">L'index spécifié est marqué comme étant hors connexion ou il est désactivé.</span><span class="sxs-lookup"><span data-stu-id="96c6e-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="96c6e-119">Cet index ne peut donc pas être vérifié.</span><span class="sxs-lookup"><span data-stu-id="96c6e-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96c6e-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="96c6e-120">User Action</span></span>  
 <span data-ttu-id="96c6e-121">Reconstruisez l'index en utilisant ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="96c6e-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c6e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96c6e-122">See Also</span></span>  
 <span data-ttu-id="96c6e-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96c6e-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="96c6e-124">Réorganiser et reconstruire des index</span><span class="sxs-lookup"><span data-stu-id="96c6e-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
