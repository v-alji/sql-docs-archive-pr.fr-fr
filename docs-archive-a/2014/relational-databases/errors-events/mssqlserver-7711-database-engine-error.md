---
title: MSSQLSERVER_7711 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605467"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="5a502-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="5a502-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="5a502-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5a502-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a502-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5a502-104">Product Name</span></span>|<span data-ttu-id="5a502-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a502-105">SQL Server</span></span>|  
|<span data-ttu-id="5a502-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5a502-106">Event ID</span></span>|<span data-ttu-id="5a502-107">7711</span><span class="sxs-lookup"><span data-stu-id="5a502-107">7711</span></span>|  
|<span data-ttu-id="5a502-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5a502-108">Event Source</span></span>|<span data-ttu-id="5a502-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a502-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a502-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5a502-110">Component</span></span>|<span data-ttu-id="5a502-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a502-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a502-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5a502-112">Symbolic Name</span></span>|<span data-ttu-id="5a502-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="5a502-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="5a502-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5a502-114">Message Text</span></span>|<span data-ttu-id="5a502-115">L’option DATA_COMPRESSION a été spécifiée plusieurs fois pour la table, l’index, ou l’une de leurs partitions.</span><span class="sxs-lookup"><span data-stu-id="5a502-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a502-116">Explication</span><span class="sxs-lookup"><span data-stu-id="5a502-116">Explanation</span></span>  
 <span data-ttu-id="5a502-117">Une erreur s'est produite dans l'option DATA_COMPRESSION dans l'une des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a502-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="5a502-118">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="5a502-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="5a502-119">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="5a502-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="5a502-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="5a502-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="5a502-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="5a502-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="5a502-122">Si la table ou l'index cité est partitionné, l'option DATA_COMPRESSION a été répertoriée plusieurs fois pour au moins l'une des partitions.</span><span class="sxs-lookup"><span data-stu-id="5a502-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="5a502-123">Si la table ou l'index n'est pas partitionné, l'option DATA_COMPRESSION a été citée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="5a502-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a502-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5a502-124">User Action</span></span>  
 <span data-ttu-id="5a502-125">Pour une table partitionnée ou un index, assurez-vous que l'option DATA_COMPRESSION n'est spécifiée qu'une seule fois pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="5a502-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="5a502-126">Pour une table ou un index qui n'est pas partitionné, utilisez l'option DATA_COMPRESSION une seule fois dans l'instruction.</span><span class="sxs-lookup"><span data-stu-id="5a502-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
