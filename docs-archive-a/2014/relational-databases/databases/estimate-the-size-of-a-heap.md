---
title: Estimer la taille d’un segment de mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614620"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="a5e62-102">Estimer la taille d’un segment de mémoire</span><span class="sxs-lookup"><span data-stu-id="a5e62-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="a5e62-103">La procédure suivante vous permet d'obtenir une estimation de la quantité d'espace nécessaire au stockage de données dans un segment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="a5e62-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="a5e62-104">Déterminez le nombre de lignes que contiendra la table :</span><span class="sxs-lookup"><span data-stu-id="a5e62-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="a5e62-105">***Num_Rows***  = nombre de lignes de la table</span><span class="sxs-lookup"><span data-stu-id="a5e62-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="a5e62-106">Spécifiez le nombre de colonnes de longueur fixe et variable et calculez l'espace nécessaire à leur stockage :</span><span class="sxs-lookup"><span data-stu-id="a5e62-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="a5e62-107">Calculez l'espace que chacun de ces groupes de colonnes occupe dans la ligne de données.</span><span class="sxs-lookup"><span data-stu-id="a5e62-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="a5e62-108">La taille d'une colonne dépend du type des données et de la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a5e62-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="a5e62-109">***Num_Cols***  = nombre total de colonnes (de longueur fixe et variable)</span><span class="sxs-lookup"><span data-stu-id="a5e62-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="a5e62-110">***Fixed_Data_Size***  = taille totale en octets de toutes les colonnes de longueur fixe</span><span class="sxs-lookup"><span data-stu-id="a5e62-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="a5e62-111">***Num_Variable_Cols***  = nombre de colonnes de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a5e62-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="a5e62-112">***Max_Var_Size*** = taille maximale en octets de toutes les colonnes de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a5e62-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="a5e62-113">Une partie de la ligne, connue sous le nom de bitmap NULL, est réservée pour gérer la possibilité de valeur NULL de la colonne.</span><span class="sxs-lookup"><span data-stu-id="a5e62-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="a5e62-114">Calculez sa taille :</span><span class="sxs-lookup"><span data-stu-id="a5e62-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="a5e62-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="a5e62-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="a5e62-116">Seule la partie entière de l'expression doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="a5e62-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="a5e62-117">Omettez le reste.</span><span class="sxs-lookup"><span data-stu-id="a5e62-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="a5e62-118">Calculez la taille des données de longueur variable :</span><span class="sxs-lookup"><span data-stu-id="a5e62-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="a5e62-119">En présence de colonnes de longueur variable dans la table, déterminez l'espace utilisé pour stocker les colonnes dans la ligne au moyen de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="a5e62-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="a5e62-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="a5e62-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="a5e62-121">Les octets ajoutés à ***Max_Var_Size*** servent à assurer le suivi de chaque colonne de longueur variable.</span><span class="sxs-lookup"><span data-stu-id="a5e62-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="a5e62-122">Il est supposé, lorsque vous utilisez cette formule, que toutes les colonnes de longueur variable sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="a5e62-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="a5e62-123">Si vous pensez qu’un pourcentage inférieur de l’espace de stockage des colonnes de longueur variable sera utilisé, vous pouvez ajuster la valeur de ***Max_Var_Size*** en fonction de ce pourcentage pour obtenir une estimation plus précise de la taille globale de la table.</span><span class="sxs-lookup"><span data-stu-id="a5e62-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5e62-124">Vous pouvez combiner des colonnes `varchar`, `nvarchar`, `varbinary` ou `sql_variant` qui provoquent le dépassement de la largeur totale de la table définie au-delà de 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="a5e62-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="a5e62-125">La longueur de chacune de ces colonnes doit toujours être comprise dans la limite de 8 000 octets pour une `varchar` `nvarchar,``varbinary` colonne, ou `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="a5e62-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="a5e62-126">Toutefois, l'association de leurs largeurs peut dépasser la limite de 8 060 octets dans une table.</span><span class="sxs-lookup"><span data-stu-id="a5e62-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="a5e62-127">En l’absence de toute colonne de longueur variable, attribuez la valeur 0 à ***Variable_Data_Size*** .</span><span class="sxs-lookup"><span data-stu-id="a5e62-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="a5e62-128">Calculez la taille totale de la ligne :</span><span class="sxs-lookup"><span data-stu-id="a5e62-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="a5e62-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="a5e62-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="a5e62-130">La valeur 4 dans la formule correspond à l'espace réservé à l'en-tête de la ligne de données.</span><span class="sxs-lookup"><span data-stu-id="a5e62-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="a5e62-131">Calculez le nombre de lignes par page (8 096 octets disponibles par page) :</span><span class="sxs-lookup"><span data-stu-id="a5e62-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="a5e62-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="a5e62-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="a5e62-133">Comme les lignes ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="a5e62-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="a5e62-134">La valeur 2 dans la formule correspond à l'entrée de la ligne dans le tableau d'emplacements de la page.</span><span class="sxs-lookup"><span data-stu-id="a5e62-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="a5e62-135">Calculez ensuite le nombre de pages de données requises pour le stockage de toutes les lignes :</span><span class="sxs-lookup"><span data-stu-id="a5e62-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="a5e62-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="a5e62-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="a5e62-137">Le nombre de pages de données estimé doit être arrondi à la page entière la plus proche.</span><span class="sxs-lookup"><span data-stu-id="a5e62-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="a5e62-138">Calculez la quantité d'espace nécessaire pour le stockage des données dans le segment de mémoire (8 192 octets par page) :</span><span class="sxs-lookup"><span data-stu-id="a5e62-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="a5e62-139">Taille du segment de mémoire (octets) = 8192 x ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="a5e62-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="a5e62-140">Ce calcul ne tient pas compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a5e62-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="a5e62-141">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="a5e62-141">Partitioning</span></span>  
  
     <span data-ttu-id="a5e62-142">L'espace réservé pour le partitionnement est minime, mais complexe à calculer.</span><span class="sxs-lookup"><span data-stu-id="a5e62-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="a5e62-143">Il n'est pas nécessaire de l'inclure.</span><span class="sxs-lookup"><span data-stu-id="a5e62-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="a5e62-144">Pages d'allocation</span><span class="sxs-lookup"><span data-stu-id="a5e62-144">Allocation pages</span></span>  
  
     <span data-ttu-id="a5e62-145">Au moins une page IAM est utilisée pour assurer le suivi des pages allouées à un segment de mémoire, mais l'espace réservé est minime. De plus, il n'existe aucun algorithme capable de calculer de manière déterministe et exacte le nombre de pages IAM qui seront utilisées.</span><span class="sxs-lookup"><span data-stu-id="a5e62-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="a5e62-146">Valeurs LOB</span><span class="sxs-lookup"><span data-stu-id="a5e62-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="a5e62-147">L’algorithme permettant de déterminer avec précision la quantité d’espace qui sera utilisée pour stocker les types de données LOB,,,, `varchar(max)` `varbinary(max)` `nvarchar(max)` `text` **ntextxml**et les `image` valeurs est complexe.</span><span class="sxs-lookup"><span data-stu-id="a5e62-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="a5e62-148">Vous pouvez simplement ajouter la taille moyenne des valeurs LOB attendues à la taille totale du segment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="a5e62-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="a5e62-149">Compression</span><span class="sxs-lookup"><span data-stu-id="a5e62-149">Compression</span></span>  
  
     <span data-ttu-id="a5e62-150">Vous ne pouvez pas précalculer la taille d'un segment de mémoire compressé.</span><span class="sxs-lookup"><span data-stu-id="a5e62-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="a5e62-151">Colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="a5e62-151">Sparse columns</span></span>  
  
     <span data-ttu-id="a5e62-152">Pour plus d'informations sur l'espace nécessaire pour les colonnes éparses, consultez [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a5e62-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e62-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5e62-153">See Also</span></span>  
 <span data-ttu-id="a5e62-154">[Segments &#40;tables sans index cluster&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="a5e62-155">[Description des index cluster et non-cluster](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="a5e62-156">[Créer des index cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="a5e62-157">[Créez des index non-cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="a5e62-158">[Estimer la taille d'une table](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="a5e62-159">[Estimer la taille d’un index cluster](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="a5e62-160">[Estimer la taille d'un index non-cluster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="a5e62-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="a5e62-161">Estimer la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="a5e62-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
