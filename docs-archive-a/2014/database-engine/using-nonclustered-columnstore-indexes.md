---
title: Utilisation d’index ColumnStore non cluster | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700193"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="59de2-102">Utilisation d'index columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="59de2-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="59de2-103">Décrit les tâches clés pour l'utilisation d'un index columnstore non cluster sur une table [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59de2-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="59de2-104">Pour une présentation des index columnstore, consultez [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="59de2-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="59de2-105">Pour plus d'informations sur les index columnstore cluster, consultez [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="59de2-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="59de2-106">Contenu</span><span class="sxs-lookup"><span data-stu-id="59de2-106">Contents</span></span>

-   [<span data-ttu-id="59de2-107">Créer un index columnstore non cluster</span><span class="sxs-lookup"><span data-stu-id="59de2-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="59de2-108">Modifier les données dans un index ColumnStore non cluster</span><span class="sxs-lookup"><span data-stu-id="59de2-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="59de2-109">Créer un index ColumnStore non cluster</span><span class="sxs-lookup"><span data-stu-id="59de2-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="59de2-110">Pour charger des données dans un index ColumnStore non cluster, chargez d’abord les données dans une table rowstore traditionnelle stockée en tant que segment de mémoire ou index cluster, puis utilisez [Create COLUMNSTORE index &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) pour créer un index ColumnStore.</span><span class="sxs-lookup"><span data-stu-id="59de2-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="59de2-111">![Chargement de données dans un index columnstore](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Chargement de données dans un index columnstore")</span><span class="sxs-lookup"><span data-stu-id="59de2-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="59de2-112">Modifier les données dans un index ColumnStore non cluster</span><span class="sxs-lookup"><span data-stu-id="59de2-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="59de2-113">Une fois que vous avez créé un index columnstore non cluster sur une table, vous ne pouvez pas modifier directement les données dans cette table.</span><span class="sxs-lookup"><span data-stu-id="59de2-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="59de2-114">Une requête avec INSERT, UPDATE, DELETE ou MERGE échouera et renverra un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="59de2-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="59de2-115">Pour ajouter ou modifier les données de la table, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="59de2-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="59de2-116">Désactivez l’index ColumnStore.</span><span class="sxs-lookup"><span data-stu-id="59de2-116">Disable the columnstore index.</span></span> <span data-ttu-id="59de2-117">Vous pourrez ensuite mettre à jour les données de la table.</span><span class="sxs-lookup"><span data-stu-id="59de2-117">You can then update the data in the table.</span></span> <span data-ttu-id="59de2-118">Si vous désactivez l'index columnstore, vous pouvez le reconstruire lorsque vous avez fini de mettre à jour les données.</span><span class="sxs-lookup"><span data-stu-id="59de2-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="59de2-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="59de2-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="59de2-120">Supprimez l’index ColumnStore, mettez à jour la table, puis recréez l’index ColumnStore avec CREATe COLUMNSTORE INDEX.</span><span class="sxs-lookup"><span data-stu-id="59de2-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="59de2-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="59de2-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="59de2-122">Chargez les données dans une table intermédiaire qui n'a pas d'index columnstore.</span><span class="sxs-lookup"><span data-stu-id="59de2-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="59de2-123">Créez un index columnstore sur la table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="59de2-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="59de2-124">Basculez la table intermédiaire dans une partition vide de la table principale.</span><span class="sxs-lookup"><span data-stu-id="59de2-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="59de2-125">Basculez une partition de la table avec l'index columnstore dans une table intermédiaire vide.</span><span class="sxs-lookup"><span data-stu-id="59de2-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="59de2-126">S'il existe un index columnstore sur la table intermédiaire, désactivez-le.</span><span class="sxs-lookup"><span data-stu-id="59de2-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="59de2-127">Effectuez toutes les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="59de2-127">Perform any updates.</span></span> <span data-ttu-id="59de2-128">Créez (ou reconstruisez) l'index columnstore.</span><span class="sxs-lookup"><span data-stu-id="59de2-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="59de2-129">Rebasculez la table intermédiaire dans la partition (maintenant vide) de la table principale.</span><span class="sxs-lookup"><span data-stu-id="59de2-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




