---
title: Segments (tables sans index cluster) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- heaps
ms.assetid: df5c4dfb-d372-4d0f-859a-a2d2533ee0d7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a39bac2e0352f2adc7749e980d5cc91044f8ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614058"
---
# <a name="heaps-tables-without-clustered-indexes"></a><span data-ttu-id="17a60-102">Segments (tables sans index cluster)</span><span class="sxs-lookup"><span data-stu-id="17a60-102">Heaps (Tables without Clustered Indexes)</span></span>
  <span data-ttu-id="17a60-103">Un segment est une table sans index cluster.</span><span class="sxs-lookup"><span data-stu-id="17a60-103">A heap is a table without a clustered index.</span></span> <span data-ttu-id="17a60-104">Un ou plusieurs index non cluster peuvent être créés sur des tables stockées comme segment.</span><span class="sxs-lookup"><span data-stu-id="17a60-104">One or more nonclustered indexes can be created on tables stored as a heap.</span></span> <span data-ttu-id="17a60-105">Les données sont stockées dans le segment sans spécifier d'ordre.</span><span class="sxs-lookup"><span data-stu-id="17a60-105">Data is stored in the heap without specifying an order.</span></span> <span data-ttu-id="17a60-106">Généralement, les données sont stockées initialement dans l'ordre dans lequel les lignes sont insérées dans la table, mais le [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut déplacer des données dans le segment pour stocker les lignes efficacement ; l'ordre des données ne peut donc pas être prédit.</span><span class="sxs-lookup"><span data-stu-id="17a60-106">Usually data is initially stored in the order in which is the rows are inserted into the table, but the [!INCLUDE[ssDE](../../includes/ssde-md.md)] can move data around in the heap to store the rows efficiently; so the data order cannot be predicted.</span></span> <span data-ttu-id="17a60-107">Pour garantir l'ordre des lignes retournées à partir d'un segment, vous devez utiliser la clause `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="17a60-107">To guarantee the order of rows returned from a heap, you must use the `ORDER BY` clause.</span></span> <span data-ttu-id="17a60-108">Pour spécifier l'ordre de stockage des lignes, créez un index cluster sur la table, de sorte que la table ne soit pas un segment.</span><span class="sxs-lookup"><span data-stu-id="17a60-108">To specify the order for storage of the rows, create a clustered index on the table, so that the table is not a heap.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17a60-109">Il existe parfois de bonnes raisons de conserver une table comme segment plutôt que de créer un index cluster, mais l'utilisation de segments est effectivement une compétence avancée.</span><span class="sxs-lookup"><span data-stu-id="17a60-109">There are sometimes good reasons to leave a table as a heap instead of creating a clustered index, but using heaps effectively is an advanced skill.</span></span> <span data-ttu-id="17a60-110">La plupart des tables doivent avoir un index cluster soigneusement choisi, à moins qu'il n'existe une bonne raison de conserver la table comme segment.</span><span class="sxs-lookup"><span data-stu-id="17a60-110">Most tables should have a carefully chosen clustered index unless a good reason exists for leaving the table as a heap.</span></span>  
  
## <a name="when-to-use-a-heap"></a><span data-ttu-id="17a60-111">À quel moment utiliser un segment</span><span class="sxs-lookup"><span data-stu-id="17a60-111">When to Use a Heap</span></span>  
 <span data-ttu-id="17a60-112">Si une table est un segment et ne possède pas d'index non cluster, la table entière doit être examinée (analyse de table) pour rechercher une ligne quelconque.</span><span class="sxs-lookup"><span data-stu-id="17a60-112">If a table is a heap and does not have any nonclustered indexes, then the entire table must be examined (a table scan) to find any row.</span></span> <span data-ttu-id="17a60-113">Cela peut être acceptable lorsque la table est minuscule, par exemple s'il s'agit d'une liste des 12 bureaux régionaux d'une société.</span><span class="sxs-lookup"><span data-stu-id="17a60-113">This can be acceptable when the table is tiny, such as a list of the 12 regional offices of a company.</span></span>  
  
 <span data-ttu-id="17a60-114">Lorsqu'une table est stockée en tant que segment, les différentes lignes sont identifiées par référence à un identificateur de ligne (RID) composé d'un numéro de fichier, d'un numéro de page de données et de l'emplacement sur la page.</span><span class="sxs-lookup"><span data-stu-id="17a60-114">When a table is stored as a heap, individual rows are identified by reference to a row identifier (RID) consisting of the file number, data page number, and slot on the page.</span></span> <span data-ttu-id="17a60-115">L'ID de ligne est une structure petite et efficace.</span><span class="sxs-lookup"><span data-stu-id="17a60-115">The row id is a small and efficient structure.</span></span> <span data-ttu-id="17a60-116">Parfois, les architectes de données utilisent des segments lorsque l'accès aux données s'effectue toujours par le biais d'index non cluster et que le RID est plus petit que la clé d'index cluster.</span><span class="sxs-lookup"><span data-stu-id="17a60-116">Sometimes data architects use heaps when data is always accessed through nonclustered indexes and the RID is smaller than a clustered index key.</span></span>  
  
## <a name="when-not-to-use-a-heap"></a><span data-ttu-id="17a60-117">À quel moment ne pas utiliser un segment</span><span class="sxs-lookup"><span data-stu-id="17a60-117">When Not to Use a Heap</span></span>  
 <span data-ttu-id="17a60-118">N'utilisez pas de segment lorsque les données sont souvent retournées dans un ordre trié.</span><span class="sxs-lookup"><span data-stu-id="17a60-118">Do not use a heap when the data is frequently returned in a sorted order.</span></span> <span data-ttu-id="17a60-119">Un index cluster sur la colonne de tri peut éviter l'opération de tri.</span><span class="sxs-lookup"><span data-stu-id="17a60-119">A clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="17a60-120">N'utilisez pas de segment lorsque les données sont souvent regroupées.</span><span class="sxs-lookup"><span data-stu-id="17a60-120">Do not use a heap when the data is frequently grouped together.</span></span> <span data-ttu-id="17a60-121">Les données doivent être triées avant d'être regroupées et un index cluster sur la colonne de tri peut éviter l'opération de tri.</span><span class="sxs-lookup"><span data-stu-id="17a60-121">Data must be sorted before it is grouped, and a clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="17a60-122">N'utilisez pas de segment lorsque des plages de données sont souvent interrogées pour la table.</span><span class="sxs-lookup"><span data-stu-id="17a60-122">Do not use a heap when ranges of data are frequently queried from the table.</span></span>  <span data-ttu-id="17a60-123">Un index cluster sur la colonne de plages évitera de devoir trier le segment entier.</span><span class="sxs-lookup"><span data-stu-id="17a60-123">A clustered index on the range column will avoid sorting the entire heap.</span></span>  
  
 <span data-ttu-id="17a60-124">N'utilisez pas de segment lorsqu'il n'y a pas d'index non cluster et que la table est grande.</span><span class="sxs-lookup"><span data-stu-id="17a60-124">Do not use a heap when there are no nonclustered indexes and the table is large.</span></span> <span data-ttu-id="17a60-125">Dans un segment, toutes les lignes du segment doivent être lues pour trouver n'importe une ligne quelconque.</span><span class="sxs-lookup"><span data-stu-id="17a60-125">In a heap, all rows of the heap must be read to find any row.</span></span>  
  
## <a name="managing-heaps"></a><span data-ttu-id="17a60-126">Gestion des segments</span><span class="sxs-lookup"><span data-stu-id="17a60-126">Managing Heaps</span></span>  
 <span data-ttu-id="17a60-127">Pour créer un segment, créez une table sans index cluster.</span><span class="sxs-lookup"><span data-stu-id="17a60-127">To create a heap, create a table without a clustered index.</span></span> <span data-ttu-id="17a60-128">Si la table possède déjà un index cluster, supprimez-le afin de reconvertir la table en segment.</span><span class="sxs-lookup"><span data-stu-id="17a60-128">If a table already has a clustered index, drop the clustered index to return the table to a heap.</span></span>  
  
 <span data-ttu-id="17a60-129">Pour supprimer un segment, créez un index cluster sur le segment.</span><span class="sxs-lookup"><span data-stu-id="17a60-129">To remove a heap, create a clustered index on the heap.</span></span>  
  
 <span data-ttu-id="17a60-130">Pour reconstruire un segment afin de récupérer de l'espace perdu, créez un index cluster sur le segment, puis supprimez l'index cluster.</span><span class="sxs-lookup"><span data-stu-id="17a60-130">To rebuild a heap to reclaim wasted space, create a clustered index on the heap, and then drop that clustered index.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="17a60-131">La création ou suppression d'index cluster nécessite de réécrire la table entière.</span><span class="sxs-lookup"><span data-stu-id="17a60-131">Creating or dropping clustered indexes requires rewriting the entire table.</span></span> <span data-ttu-id="17a60-132">Si la table a des index non cluster, tous les index non cluster doivent être recréés à chaque fois que l'index cluster est modifié.</span><span class="sxs-lookup"><span data-stu-id="17a60-132">If the table has nonclustered indexes, all the nonclustered indexes must all be recreated whenever the clustered index is changed.</span></span> <span data-ttu-id="17a60-133">Par conséquent, le passage d’un segment à une structure d’index cluster (ou inversement) peut prendre beaucoup de temps et nécessiter de l’espace disque pour réorganiser les données dans tempdb.</span><span class="sxs-lookup"><span data-stu-id="17a60-133">Therefore, changing from a heap to a clustered index structure or back can take a lot of time and require disk space for reordering data in tempdb.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="17a60-134">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="17a60-134">Related Content</span></span>  
 [<span data-ttu-id="17a60-135">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a60-135">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="17a60-136">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17a60-136">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="17a60-137">Description des index cluster et non cluster</span><span class="sxs-lookup"><span data-stu-id="17a60-137">Clustered and Nonclustered Indexes Described</span></span>](clustered-and-nonclustered-indexes-described.md)  
  
  
