---
title: Estimer la taille d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604548"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="83fc6-102">Estimer la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="83fc6-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="83fc6-103">Lorsque vous concevez une base de données, il peut être utile d'estimer quelle taille elle aura une fois remplie.</span><span class="sxs-lookup"><span data-stu-id="83fc6-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="83fc6-104">Cette estimation peut vous aider à déterminer la configuration matérielle dont vous aurez besoin pour :</span><span class="sxs-lookup"><span data-stu-id="83fc6-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="83fc6-105">atteindre le niveau de performances requis par vos applications ;</span><span class="sxs-lookup"><span data-stu-id="83fc6-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="83fc6-106">garantir la quantité d'espace disque physique nécessaire pour stocker les données et les index.</span><span class="sxs-lookup"><span data-stu-id="83fc6-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="83fc6-107">L'estimation de la taille de la base de données peut aussi vous aider à déterminer si des améliorations de conception s'imposent.</span><span class="sxs-lookup"><span data-stu-id="83fc6-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="83fc6-108">Par exemple, vous pouvez arriver à la conclusion que la base de données risque d'atteindre une taille trop importante pour que son implémentation s'effectue dans de bonnes conditions dans votre organisation et qu'il faut aller dans le sens d'une plus grande normalisation.</span><span class="sxs-lookup"><span data-stu-id="83fc6-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="83fc6-109">À l'inverse, la taille estimée peut être plus petite que prévu,</span><span class="sxs-lookup"><span data-stu-id="83fc6-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="83fc6-110">ce qui vous donne la possibilité de dénormaliser la base de données pour améliorer les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="83fc6-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="83fc6-111">Pour estimer la taille d'une base de données, faites une estimation pour chaque table, puis additionnez les valeurs trouvées.</span><span class="sxs-lookup"><span data-stu-id="83fc6-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="83fc6-112">La taille d'une table dépend de la présence ou non d'index et, le cas échéant, de leur type.</span><span class="sxs-lookup"><span data-stu-id="83fc6-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83fc6-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="83fc6-113">In This Section</span></span>  
  
|<span data-ttu-id="83fc6-114">Rubrique</span><span class="sxs-lookup"><span data-stu-id="83fc6-114">Topic</span></span>|<span data-ttu-id="83fc6-115">Description</span><span class="sxs-lookup"><span data-stu-id="83fc6-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="83fc6-116">Estimer la taille d’une table</span><span class="sxs-lookup"><span data-stu-id="83fc6-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="83fc6-117">Définit les étapes et les calculs nécessaires pour estimer l'espace requis pour le stockage des données dans une table et les index associés.</span><span class="sxs-lookup"><span data-stu-id="83fc6-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="83fc6-118">Estimer la taille d’un segment de mémoire</span><span class="sxs-lookup"><span data-stu-id="83fc6-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="83fc6-119">Définit les étapes et les calculs nécessaires pour estimer l'espace requis pour le stockage des données dans un segment.</span><span class="sxs-lookup"><span data-stu-id="83fc6-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="83fc6-120">Un segment est une table qui n'a pas d'index cluster.</span><span class="sxs-lookup"><span data-stu-id="83fc6-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="83fc6-121">Estimer la taille d'un index cluster</span><span class="sxs-lookup"><span data-stu-id="83fc6-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="83fc6-122">Définit les étapes et les calculs nécessaires pour estimer l'espace requis pour le stockage des données dans un index cluster.</span><span class="sxs-lookup"><span data-stu-id="83fc6-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="83fc6-123">Estimer la taille d'un index non-cluster</span><span class="sxs-lookup"><span data-stu-id="83fc6-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="83fc6-124">Définit les étapes et les calculs nécessaires pour estimer l'espace requis pour le stockage des données dans un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="83fc6-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
