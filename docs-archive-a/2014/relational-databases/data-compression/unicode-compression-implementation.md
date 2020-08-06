---
title: Implémentation de la compression Unicode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612946"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="3fef7-102">Implémentation de la compression Unicode</span><span class="sxs-lookup"><span data-stu-id="3fef7-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3fef7-103">utilise une implémentation de l’algorithme SCSU (Standard Compression Scheme for Unicode) pour compresser les valeurs Unicode stockées dans des objets à compression de ligne ou de page.</span><span class="sxs-lookup"><span data-stu-id="3fef7-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="3fef7-104">Pour ces objets compressés, la compression Unicode est automatique pour les colonnes `nchar(n)` et `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="3fef7-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="3fef7-105">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] stocke les données Unicode comme 2 octets, indépendamment des paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="3fef7-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="3fef7-106">Ceci porte le nom d'encodage UCS-2.</span><span class="sxs-lookup"><span data-stu-id="3fef7-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="3fef7-107">Pour certains paramètres régionaux, l'implémentation de la compression SCSU dans SQL Server peut économiser jusqu'à 50 pour cent d'espace de stockage.</span><span class="sxs-lookup"><span data-stu-id="3fef7-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="3fef7-108">Types de données pris en charge</span><span class="sxs-lookup"><span data-stu-id="3fef7-108">Supported Data Types</span></span>  
 <span data-ttu-id="3fef7-109">La compression Unicode prend en charge les types de données de longueur fixe `nchar(n)` et `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="3fef7-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="3fef7-110">Les valeurs de données stockées hors ligne ou dans des colonnes `nvarchar(max)` ne sont pas compressées.</span><span class="sxs-lookup"><span data-stu-id="3fef7-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fef7-111">La compression Unicode n'est pas prise en charge pour les données d'`nvarchar(max)`, même si celles-ci sont stockées dans des lignes.</span><span class="sxs-lookup"><span data-stu-id="3fef7-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="3fef7-112">Toutefois, ce type de données peut tirer parti de la compression de page.</span><span class="sxs-lookup"><span data-stu-id="3fef7-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="3fef7-113">Mise à niveau à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fef7-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="3fef7-114">Quand une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est mise à niveau vers [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], les modifications liées à la compression Unicode ne sont apportées à aucun objet de base de données, compressé ou non compressé.</span><span class="sxs-lookup"><span data-stu-id="3fef7-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="3fef7-115">Une fois la base de données mise à niveau, les objets sont affectés comme suit :</span><span class="sxs-lookup"><span data-stu-id="3fef7-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="3fef7-116">Si l'objet n'est pas compressé, aucune modification n'est apportée et l'objet continue de fonctionner comme précédemment.</span><span class="sxs-lookup"><span data-stu-id="3fef7-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="3fef7-117">Les objets à compression de page ou de ligne continuent de fonctionner comme précédemment.</span><span class="sxs-lookup"><span data-stu-id="3fef7-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="3fef7-118">Les données non compressés restent sous forme non compressée jusqu'à ce que leur valeur soit mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3fef7-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="3fef7-119">Les nouvelles lignes insérées dans une table à compression de page ou de ligne sont compressées à l'aide de la compression Unicode.</span><span class="sxs-lookup"><span data-stu-id="3fef7-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3fef7-120">Pour tirer pleinement parti des avantages de la compression Unicode, l'objet doit être reconstruit avec compression de ligne ou de page.</span><span class="sxs-lookup"><span data-stu-id="3fef7-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="3fef7-121">Impact de la compression Unicode sur le stockage des données</span><span class="sxs-lookup"><span data-stu-id="3fef7-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="3fef7-122">Lorsqu'un index est créé ou reconstruit ou lorsqu'une valeur est modifiée dans une table compressée avec la compression de page ou de ligne, l'index ou la valeur affecté est stockée sous forme compressée uniquement si sa taille compressée est inférieure à sa taille actuelle.</span><span class="sxs-lookup"><span data-stu-id="3fef7-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="3fef7-123">Cela empêche que la taille des lignes dans une table ou un index n'augmente à cause de la compression Unicode.</span><span class="sxs-lookup"><span data-stu-id="3fef7-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="3fef7-124">L'espace de stockage économisé par la compression dépend des caractéristiques des données compressées et des paramètres régionaux des données.</span><span class="sxs-lookup"><span data-stu-id="3fef7-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="3fef7-125">Le tableau suivant répertorie les économies d'espace qui peuvent être accomplies pour plusieurs paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="3fef7-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="3fef7-126">Paramètres régionaux</span><span class="sxs-lookup"><span data-stu-id="3fef7-126">Locale</span></span>|<span data-ttu-id="3fef7-127">Pourcentage de compression</span><span class="sxs-lookup"><span data-stu-id="3fef7-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="3fef7-128">Anglais</span><span class="sxs-lookup"><span data-stu-id="3fef7-128">English</span></span>|<span data-ttu-id="3fef7-129">50</span><span class="sxs-lookup"><span data-stu-id="3fef7-129">50%</span></span>|  
|<span data-ttu-id="3fef7-130">Allemand</span><span class="sxs-lookup"><span data-stu-id="3fef7-130">German</span></span>|<span data-ttu-id="3fef7-131">50</span><span class="sxs-lookup"><span data-stu-id="3fef7-131">50%</span></span>|  
|<span data-ttu-id="3fef7-132">Hindi</span><span class="sxs-lookup"><span data-stu-id="3fef7-132">Hindi</span></span>|<span data-ttu-id="3fef7-133">50</span><span class="sxs-lookup"><span data-stu-id="3fef7-133">50%</span></span>|  
|<span data-ttu-id="3fef7-134">Turc</span><span class="sxs-lookup"><span data-stu-id="3fef7-134">Turkish</span></span>|<span data-ttu-id="3fef7-135">48 %</span><span class="sxs-lookup"><span data-stu-id="3fef7-135">48%</span></span>|  
|<span data-ttu-id="3fef7-136">Vietnamien</span><span class="sxs-lookup"><span data-stu-id="3fef7-136">Vietnamese</span></span>|<span data-ttu-id="3fef7-137">39</span><span class="sxs-lookup"><span data-stu-id="3fef7-137">39%</span></span>|  
|<span data-ttu-id="3fef7-138">Japonais</span><span class="sxs-lookup"><span data-stu-id="3fef7-138">Japanese</span></span>|<span data-ttu-id="3fef7-139">15 %</span><span class="sxs-lookup"><span data-stu-id="3fef7-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fef7-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fef7-140">See Also</span></span>  
 <span data-ttu-id="3fef7-141">[Compression de données](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="3fef7-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="3fef7-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3fef7-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="3fef7-143">[Implémentation de la compression de page](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="3fef7-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="3fef7-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fef7-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
