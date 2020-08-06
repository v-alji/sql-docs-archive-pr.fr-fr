---
title: MSSQLSERVER_617 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702911"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="624a3-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="624a3-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="624a3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="624a3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="624a3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="624a3-104">Product Name</span></span>|<span data-ttu-id="624a3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="624a3-105">SQL Server</span></span>|  
|<span data-ttu-id="624a3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="624a3-106">Event ID</span></span>|<span data-ttu-id="624a3-107">617</span><span class="sxs-lookup"><span data-stu-id="624a3-107">617</span></span>|  
|<span data-ttu-id="624a3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="624a3-108">Event Source</span></span>|<span data-ttu-id="624a3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="624a3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="624a3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="624a3-110">Component</span></span>|<span data-ttu-id="624a3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="624a3-111">SQLEngine</span></span>|  
|<span data-ttu-id="624a3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="624a3-112">Symbolic Name</span></span>|<span data-ttu-id="624a3-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="624a3-113">NODESHASH</span></span>|  
|<span data-ttu-id="624a3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="624a3-114">Message Text</span></span>|<span data-ttu-id="624a3-115">Le descripteur de l'ID d'objet %ld dans l'ID de base de données %d n'a pas été trouvé dans la table de hachage lors de la tentative de déhachage.</span><span class="sxs-lookup"><span data-stu-id="624a3-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="624a3-116">Une entrée est manquante dans une table de travail.</span><span class="sxs-lookup"><span data-stu-id="624a3-116">A work table is missing an entry.</span></span> <span data-ttu-id="624a3-117">Réexécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="624a3-117">Rerun the query.</span></span> <span data-ttu-id="624a3-118">Si un curseur est concerné, fermez et rouvrez le curseur.</span><span class="sxs-lookup"><span data-stu-id="624a3-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="624a3-119">Explication</span><span class="sxs-lookup"><span data-stu-id="624a3-119">Explanation</span></span>  
 <span data-ttu-id="624a3-120">SQL Server ne peut pas localiser la table de travail pour une entrée spécifique.</span><span class="sxs-lookup"><span data-stu-id="624a3-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="624a3-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="624a3-121">User Action</span></span>  
  
1.  <span data-ttu-id="624a3-122">Si un curseur est impliqué, fermez et rouvrez celui-ci.</span><span class="sxs-lookup"><span data-stu-id="624a3-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="624a3-123">Réexécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="624a3-123">Run the query again.</span></span>  
  
  
