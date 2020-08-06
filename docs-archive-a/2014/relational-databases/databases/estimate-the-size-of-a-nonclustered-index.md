---
title: Estimer la taille d’un index non-cluster | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705160"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="a798d-102">Estimer la taille d'un index non-cluster</span><span class="sxs-lookup"><span data-stu-id="a798d-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="a798d-103">Utilisez la procédure suivante pour estimer la quantité d'espace nécessaire au stockage d'un index non cluster :</span><span class="sxs-lookup"><span data-stu-id="a798d-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="a798d-104">Calculez les variables à utiliser dans les étapes 2 et 3.</span><span class="sxs-lookup"><span data-stu-id="a798d-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="a798d-105">Calculez l'espace utilisé pour stocker les informations d'index au niveau feuille de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="a798d-106">Calculez l'espace utilisé pour stocker les informations d'index aux niveaux non-feuille de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="a798d-107">Faites la somme des valeurs calculées.</span><span class="sxs-lookup"><span data-stu-id="a798d-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="a798d-108">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="a798d-108">Step 1.</span></span> <span data-ttu-id="a798d-109">Calculer les variables à utiliser dans les étapes 2 et 3</span><span class="sxs-lookup"><span data-stu-id="a798d-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="a798d-110">Vous pouvez utiliser la procédure suivante afin de calculer les variables utilisées pour estimer la quantité d'espace nécessaire au stockage des niveaux supérieurs de l'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="a798d-111">Déterminez le nombre de lignes que contiendra la table :</span><span class="sxs-lookup"><span data-stu-id="a798d-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="a798d-112">***Num_Rows***  = nombre de lignes de la table</span><span class="sxs-lookup"><span data-stu-id="a798d-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="a798d-113">Spécifiez le nombre de colonnes de longueur fixe et de longueur variable de la clé d'index et calculez l'espace nécessaire à leur stockage :</span><span class="sxs-lookup"><span data-stu-id="a798d-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="a798d-114">Les colonnes clés d'un index peuvent inclure des colonnes de longueur fixe et variable.</span><span class="sxs-lookup"><span data-stu-id="a798d-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="a798d-115">Pour estimer la taille de la ligne d'index du niveau intérieur, calculez l'espace occupé par chacun de ces groupes de colonnes dans la ligne d'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="a798d-116">La taille d'une colonne dépend du type des données et de la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a798d-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="a798d-117">***Num_Key_Cols***  = nombre total de colonnes clés (de longueur fixe et variable)</span><span class="sxs-lookup"><span data-stu-id="a798d-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="a798d-118">***Fixed_Key_Size***  = taille totale en octets de toutes les colonnes clés de longueur fixe</span><span class="sxs-lookup"><span data-stu-id="a798d-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="a798d-119">***Num_Variable_Key_Cols***  = nombre de colonnes clés de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a798d-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="a798d-120">***Max_Var_Key_Size***  = taille maximale en octets de toutes les colonnes clés de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a798d-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="a798d-121">Tenez compte du localisateur de ligne de données nécessaire si l'index n'est pas unique :</span><span class="sxs-lookup"><span data-stu-id="a798d-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="a798d-122">Si l'index non-cluster n'est pas unique, le localisateur de ligne de données est associé à la clé d'index non-cluster pour produire une valeur de clé unique pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="a798d-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="a798d-123">Si l'index non-cluster est au-dessus d'un segment, le localisateur de ligne de données est le RID de ce segment.</span><span class="sxs-lookup"><span data-stu-id="a798d-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="a798d-124">Sa taille est de 8 octets.</span><span class="sxs-lookup"><span data-stu-id="a798d-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="a798d-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="a798d-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="a798d-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="a798d-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="a798d-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="a798d-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="a798d-128">Si l'index non cluster est au-dessus d'un index cluster, le localisateur de lignes de données est la clé de clustering.</span><span class="sxs-lookup"><span data-stu-id="a798d-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="a798d-129">Les colonnes qui doivent être associées à la clé d'index non cluster sont les colonnes de la clé de clustering qui ne sont pas déjà présentes dans l'ensemble des colonnes clés de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="a798d-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + nombre de colonnes clés de clustering non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 1 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="a798d-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + taille totale en octets des colonnes clés de clustering de longueur fixe non présentes dans l’ensemble de colonnes clés de l’index non cluster</span><span class="sxs-lookup"><span data-stu-id="a798d-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="a798d-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + nombre de colonnes clés de clustering de longueur variable non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 1 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="a798d-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + taille maximale en octets des colonnes clés de clustering de longueur variable non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 4 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="a798d-134">Une partie de la ligne, nommée null bitmap, peut être réservée à la gestion de l'acceptation de valeurs NULL dans les colonnes.</span><span class="sxs-lookup"><span data-stu-id="a798d-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="a798d-135">Calculez sa taille :</span><span class="sxs-lookup"><span data-stu-id="a798d-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="a798d-136">En présence de colonnes autorisant des valeurs Null dans la clé d'index, notamment toutes les colonnes clés de clustering nécessaires comme décrit dans l'étape 1.3, une partie de la ligne d'index est réservée à la bitmap Null.</span><span class="sxs-lookup"><span data-stu-id="a798d-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="a798d-137">***Index_Null_Bitmap***  = 2 + ((nombre de colonnes dans la ligne d’index + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="a798d-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="a798d-138">Seule la partie entière de l'expression précédente doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="a798d-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="a798d-139">Omettez le reste.</span><span class="sxs-lookup"><span data-stu-id="a798d-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="a798d-140">En l’absence de toute colonne clé autorisant les valeurs Null, attribuez la valeur 0 à ***Index_Null_Bitmap*** .</span><span class="sxs-lookup"><span data-stu-id="a798d-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="a798d-141">Calculez la taille des données de longueur variable :</span><span class="sxs-lookup"><span data-stu-id="a798d-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="a798d-142">En présence de colonnes de longueur variable dans la clé d'index, notamment les colonnes clés d'index cluster nécessaires, déterminez l'espace utilisé pour le stockage des colonnes dans la ligne d'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="a798d-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="a798d-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="a798d-144">Les octets ajoutés à ***Max_Var_Key_Size*** servent à assurer le suivi de chaque colonne variable. Cette formule suppose que toutes les colonnes de longueur variable sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="a798d-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="a798d-145">Si vous pensez qu’un pourcentage inférieur de l’espace de stockage des colonnes de longueur variable sera utilisé, vous pouvez ajuster la valeur de ***Max_Var_Key_Size*** en fonction de ce pourcentage pour obtenir une estimation plus précise de la taille globale de la table.</span><span class="sxs-lookup"><span data-stu-id="a798d-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="a798d-146">En l’absence de toute colonne de longueur variable, attribuez la valeur 0 à ***Variable_Key_Size*** .</span><span class="sxs-lookup"><span data-stu-id="a798d-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="a798d-147">Calculez la taille de la ligne d'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="a798d-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (représentant la surcharge de l’en-tête de la ligne d’index) + 6 (représentant le pointeur de l’ID de la page enfant)</span><span class="sxs-lookup"><span data-stu-id="a798d-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="a798d-149">Calculez le nombre de lignes d'index par page (8 096 octets libres par page) :</span><span class="sxs-lookup"><span data-stu-id="a798d-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="a798d-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="a798d-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="a798d-151">Comme les lignes d'index ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes d'index par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="a798d-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="a798d-152">Le chiffre 2 de la formule concerne l'entrée de la ligne du tableau d'emplacement de la page.</span><span class="sxs-lookup"><span data-stu-id="a798d-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="a798d-153">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="a798d-153">Step 2.</span></span> <span data-ttu-id="a798d-154">Calculer l'espace utilisé pour le stockage des informations d'index au niveau feuille</span><span class="sxs-lookup"><span data-stu-id="a798d-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="a798d-155">Vous pouvez utiliser la procédure suivante pour estimer la quantité d'espace nécessaire au stockage du niveau feuille de l'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="a798d-156">Vous aurez besoin des valeurs conservées dans l'étape 1 pour effectuer cette étape-ci.</span><span class="sxs-lookup"><span data-stu-id="a798d-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="a798d-157">Spécifiez le nombre de colonnes de longueur fixe et de longueur variable au niveau feuille et calculez l'espace nécessaire à leur stockage :</span><span class="sxs-lookup"><span data-stu-id="a798d-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a798d-158">Vous pouvez étendre un index non cluster en incluant les colonnes sans clé en plus des colonnes de clés d'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="a798d-159">Ces colonnes supplémentaires sont stockées uniquement au niveau feuille de l'index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="a798d-160">Pour plus d’informations, consultez [Créer des index avec colonnes incluses](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a798d-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a798d-161">Vous pouvez combiner des colonnes `varchar`, `nvarchar`, `varbinary` ou `sql_variant` qui provoquent le dépassement de la largeur totale de la table définie au-delà de 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="a798d-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="a798d-162">La longueur de chacune de ces colonnes doit toujours être inférieure à la limite de 8 000 octets pour une colonne `varchar`, `varbinary` ou `sql_variant` et de 4 000 octets pour les colonnes `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="a798d-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="a798d-163">Toutefois, l'association de leurs largeurs peut dépasser la limite de 8 060 octets dans une table.</span><span class="sxs-lookup"><span data-stu-id="a798d-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="a798d-164">Ceci s'applique également aux lignes de feuille d'index non-cluster possédant des colonnes incluses.</span><span class="sxs-lookup"><span data-stu-id="a798d-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="a798d-165">Si l'index non-cluster ne possède aucune colonne incluse, utilisez les valeurs de l'étape 1, y compris les éventuelles modifications déterminées dans l'étape 1.3 :</span><span class="sxs-lookup"><span data-stu-id="a798d-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="a798d-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="a798d-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="a798d-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="a798d-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="a798d-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="a798d-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="a798d-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="a798d-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="a798d-170">Si l'index non-cluster ne possède aucune colonne incluse, ajoutez les valeurs appropriées aux valeurs de l'étape 1, y compris les éventuelles modifications de l'étape 1.3.</span><span class="sxs-lookup"><span data-stu-id="a798d-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="a798d-171">La taille d'une colonne dépend du type des données et de la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a798d-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="a798d-172">Pour plus d’informations, consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a798d-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="a798d-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + nombre de colonnes incluses</span><span class="sxs-lookup"><span data-stu-id="a798d-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="a798d-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + taille totale en octets des colonnes incluses de longueur fixe</span><span class="sxs-lookup"><span data-stu-id="a798d-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="a798d-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + nombre de colonnes incluses de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a798d-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="a798d-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + taille maximale en octets des colonnes incluses de longueur variable</span><span class="sxs-lookup"><span data-stu-id="a798d-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="a798d-177">Tenez compte du localisateur de ligne de données :</span><span class="sxs-lookup"><span data-stu-id="a798d-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="a798d-178">Si l'index non-cluster n'est pas unique, la surcharge du localisateur de ligne de données a déjà été prise en compte dans l'étape 1.3 et aucune modification supplémentaire n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a798d-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="a798d-179">Passez à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="a798d-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="a798d-180">Si l'index non-cluster est unique, le localisateur de ligne des données doit être pris en compte dans toutes les lignes au niveau feuille.</span><span class="sxs-lookup"><span data-stu-id="a798d-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="a798d-181">Si l'index non-cluster est au-dessus d'un segment, le localisateur de ligne de données est le RID du segment (taille 8 octets).</span><span class="sxs-lookup"><span data-stu-id="a798d-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="a798d-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="a798d-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="a798d-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="a798d-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="a798d-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="a798d-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="a798d-185">Si l'index non cluster est au-dessus d'un index cluster, le localisateur de lignes de données est la clé de clustering.</span><span class="sxs-lookup"><span data-stu-id="a798d-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="a798d-186">Les colonnes qui doivent être associées à la clé d'index non cluster sont les colonnes de la clé de clustering qui ne sont pas déjà présentes dans l'ensemble des colonnes clés de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="a798d-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + nombre de colonnes clés de clustering non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 1 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="a798d-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + nombre de colonnes clés de clustering de longueur fixe non présentes dans l’ensemble de colonnes clés de l’index non cluster</span><span class="sxs-lookup"><span data-stu-id="a798d-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="a798d-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + nombre de colonnes clés de clustering de longueur variable non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 1 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="a798d-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + taille en octets des colonnes clés de clustering de longueur variable non présentes dans l’ensemble de colonnes clés de l’index non cluster (+ 4 si l’index cluster n’est pas unique)</span><span class="sxs-lookup"><span data-stu-id="a798d-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="a798d-191">Calculez la taille de null bitmap :</span><span class="sxs-lookup"><span data-stu-id="a798d-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="a798d-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="a798d-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="a798d-193">Seule la partie entière de l'expression précédente doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="a798d-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="a798d-194">Omettez le reste.</span><span class="sxs-lookup"><span data-stu-id="a798d-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="a798d-195">Calculez la taille des données de longueur variable :</span><span class="sxs-lookup"><span data-stu-id="a798d-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="a798d-196">En présence de colonnes de longueur variable dans la clé d'index, notamment les colonnes clés de cluster nécessaires comme décrit précédemment dans l'étape 2.2, déterminez l'espace utilisé pour le stockage des colonnes dans la ligne d'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="a798d-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="a798d-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="a798d-198">Les octets ajoutés à ***Max_Var_Key_Size*** servent à assurer le suivi de chaque colonne variable. Cette formule suppose que toutes les colonnes de longueur variable sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="a798d-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="a798d-199">Si vous estimez qu’un pourcentage inférieur de l’espace de stockage des colonnes de longueur variable sera utilisé, vous pouvez multiplier la valeur ***Max_Var_Leaf_Size*** par ce pourcentage pour obtenir une estimation plus précise de la taille globale de la table.</span><span class="sxs-lookup"><span data-stu-id="a798d-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="a798d-200">En l’absence de colonnes de longueur variable, attribuez à ***Variable_Leaf_Size*** la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="a798d-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="a798d-201">Calculez la taille de la ligne d'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="a798d-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (pour la surcharge d’en-tête de ligne d’une ligne d’index) + 6 (pour le pointeur d’ID de page enfant)</span><span class="sxs-lookup"><span data-stu-id="a798d-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="a798d-203">Calculez le nombre de lignes d'index par page (8 096 octets libres par page) :</span><span class="sxs-lookup"><span data-stu-id="a798d-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="a798d-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="a798d-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="a798d-205">Comme les lignes d'index ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes d'index par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="a798d-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="a798d-206">Le chiffre 2 de la formule concerne l'entrée de la ligne du tableau d'emplacement de la page.</span><span class="sxs-lookup"><span data-stu-id="a798d-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="a798d-207">Calculez le nombre de lignes libres réservées par page en fonction du taux de remplissage [Fill_Factor](../indexes/specify-fill-factor-for-an-index.md) spécifié :</span><span class="sxs-lookup"><span data-stu-id="a798d-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="a798d-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="a798d-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="a798d-209">Le facteur de remplissage utilisé dans le calcul est un nombre et non un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="a798d-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="a798d-210">Comme les lignes ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="a798d-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="a798d-211">Au fur et à mesure que le facteur de remplissage s'accroît, davantage de données seront stockées sur chaque page et il y aura moins de pages.</span><span class="sxs-lookup"><span data-stu-id="a798d-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="a798d-212">Le chiffre 2 de la formule concerne l'entrée de la ligne du tableau d'emplacement de la page.</span><span class="sxs-lookup"><span data-stu-id="a798d-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="a798d-213">Calculez ensuite le nombre de pages de données requises pour le stockage de toutes les lignes :</span><span class="sxs-lookup"><span data-stu-id="a798d-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="a798d-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="a798d-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="a798d-215">Le nombre de pages de données estimé doit être arrondi à la page entière la plus proche.</span><span class="sxs-lookup"><span data-stu-id="a798d-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="a798d-216">Calculez la taille de l'index (8 192 octets par page) :</span><span class="sxs-lookup"><span data-stu-id="a798d-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="a798d-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="a798d-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="a798d-218">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="a798d-218">Step 3.</span></span> <span data-ttu-id="a798d-219">Calculer l'espace utilisé pour le stockage des informations d'index aux niveaux non-feuille</span><span class="sxs-lookup"><span data-stu-id="a798d-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="a798d-220">Utilisez la procédure suivante pour estimer la quantité d'espace nécessaire au stockage des niveaux intermédiaires et racine de l'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="a798d-221">Vous aurez besoin des valeurs conservées aux étapes 2 et 3 pour effectuer cette étape-ci.</span><span class="sxs-lookup"><span data-stu-id="a798d-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="a798d-222">Calculez le nombre de niveaux non-feuille contenus dans l'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="a798d-223">***Niveaux non-feuille*** = 1 + Index_Rows_Per_Page de journal (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="a798d-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="a798d-224">Arrondissez cette valeur au nombre entier supérieur le plus proche.</span><span class="sxs-lookup"><span data-stu-id="a798d-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="a798d-225">Cette valeur n'inclut pas le niveau feuille de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="a798d-226">Calculez le nombre de pages non-feuille contenues dans l'index :</span><span class="sxs-lookup"><span data-stu-id="a798d-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="a798d-227">***Num_Index_Pages*** = ∑ level (***Num_Leaf_Pages/***<sup>niveau</sup>Index_Rows_Per_Page) où 1 <***= Level <=*** levels</span><span class="sxs-lookup"><span data-stu-id="a798d-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="a798d-228">Arrondissez chaque élément de la somme au nombre entier supérieur le plus proche.</span><span class="sxs-lookup"><span data-stu-id="a798d-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="a798d-229">À titre d’exemple simple, imaginez un index où ***Num_Leaf_Pages*** = 1000 et ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="a798d-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="a798d-230">Le premier niveau d'index au-dessus du niveau feuille stocke 1 000 lignes d'index, ce qui représente une ligne d'index par page feuille et 25 lignes d'index par page.</span><span class="sxs-lookup"><span data-stu-id="a798d-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="a798d-231">Par conséquent, il faut 40 pages pour stocker ces 1 000 lignes d'index.</span><span class="sxs-lookup"><span data-stu-id="a798d-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="a798d-232">Le niveau suivant de l'index doit stocker 40 lignes.</span><span class="sxs-lookup"><span data-stu-id="a798d-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="a798d-233">Cela requiert donc 2 pages.</span><span class="sxs-lookup"><span data-stu-id="a798d-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="a798d-234">Le niveau final de l'index doit stocker 2 lignes.</span><span class="sxs-lookup"><span data-stu-id="a798d-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="a798d-235">Cela requiert donc 1 page.</span><span class="sxs-lookup"><span data-stu-id="a798d-235">This means that it requires 1 page.</span></span> <span data-ttu-id="a798d-236">Il en résulte 43 pages d'index non-feuille.</span><span class="sxs-lookup"><span data-stu-id="a798d-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="a798d-237">Lorsque ces nombres sont utilisés dans les formules précédentes, le résultat est le suivant :</span><span class="sxs-lookup"><span data-stu-id="a798d-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="a798d-238">***Non leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="a798d-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="a798d-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, ce qui correspond au nombre de pages décrit dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="a798d-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="a798d-240">Calculez la taille de l'index (8 192 octets par page) :</span><span class="sxs-lookup"><span data-stu-id="a798d-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="a798d-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="a798d-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="a798d-242">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="a798d-242">Step 4.</span></span> <span data-ttu-id="a798d-243">Faire la somme des valeurs calculées</span><span class="sxs-lookup"><span data-stu-id="a798d-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="a798d-244">Faites la somme des valeurs obtenues à partir des deux étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="a798d-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="a798d-245">Taille de l’index non cluster (octets) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="a798d-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="a798d-246">Ce calcul ne tient pas compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a798d-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="a798d-247">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="a798d-247">Partitioning</span></span>  
  
     <span data-ttu-id="a798d-248">L'espace réservé pour le partitionnement est minime, mais complexe à calculer.</span><span class="sxs-lookup"><span data-stu-id="a798d-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="a798d-249">Il n'est pas nécessaire de l'inclure.</span><span class="sxs-lookup"><span data-stu-id="a798d-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="a798d-250">Pages d'allocation</span><span class="sxs-lookup"><span data-stu-id="a798d-250">Allocation pages</span></span>  
  
     <span data-ttu-id="a798d-251">Au moins une page IAM est utilisée pour assurer le suivi des pages allouées à un segment de mémoire, mais l'espace réservé est minime. De plus, il n'existe aucun algorithme capable de calculer de manière déterministe et exacte le nombre de pages IAM qui seront utilisées.</span><span class="sxs-lookup"><span data-stu-id="a798d-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="a798d-252">Valeurs LOB</span><span class="sxs-lookup"><span data-stu-id="a798d-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="a798d-253">L'algorithme permettant de déterminer avec exactitude la quantité d'espace qui sera utilisée pour stocker les valeurs des types de données LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` et `image` est complexe.</span><span class="sxs-lookup"><span data-stu-id="a798d-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="a798d-254">Il suffit d’ajouter simplement la taille moyenne des valeurs LOB attendues, de la multiplier par ***Num_Rows***et d’ajouter ce produit à la taille totale de l’index non cluster.</span><span class="sxs-lookup"><span data-stu-id="a798d-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="a798d-255">Compression</span><span class="sxs-lookup"><span data-stu-id="a798d-255">Compression</span></span>  
  
     <span data-ttu-id="a798d-256">Vous ne pouvez pas précalculer la taille d'un index compressé.</span><span class="sxs-lookup"><span data-stu-id="a798d-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="a798d-257">Colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="a798d-257">Sparse columns</span></span>  
  
     <span data-ttu-id="a798d-258">Pour plus d'informations sur l'espace nécessaire pour les colonnes éparses, consultez [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a798d-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a798d-259">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a798d-259">See Also</span></span>  
 <span data-ttu-id="a798d-260">[Description des index cluster et non-cluster](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="a798d-261">[Créez des index non-cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="a798d-262">[Créer des index cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="a798d-263">[Estimer la taille d'une table](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="a798d-264">[Estimer la taille d’un index cluster](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="a798d-265">[Estimer la taille d’un segment de mémoire](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="a798d-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="a798d-266">Estimer la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="a798d-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
