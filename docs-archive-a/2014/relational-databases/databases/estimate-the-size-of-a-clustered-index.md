---
title: Estimer la taille d’un index cluster | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709551"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="8cdb4-102">Estimer la taille d’un index cluster</span><span class="sxs-lookup"><span data-stu-id="8cdb4-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="8cdb4-103">Vous pouvez estimer la quantité d'espace nécessaire au stockage des données d'un index cluster en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="8cdb4-104">Calculez l'espace utilisé pour le stockage des données au niveau feuille de l'index cluster.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="8cdb4-105">Calculez l'espace utilisé pour le stockage des informations relatives à l'index cluster.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="8cdb4-106">Faites la somme des valeurs calculées.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="8cdb4-107">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-107">Step 1.</span></span> <span data-ttu-id="8cdb4-108">Calculer l'espace utilisé pour le stockage des données au niveau feuille</span><span class="sxs-lookup"><span data-stu-id="8cdb4-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="8cdb4-109">Déterminez le nombre de lignes que contiendra la table :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="8cdb4-110">***Num_Rows***  = nombre de lignes de la table</span><span class="sxs-lookup"><span data-stu-id="8cdb4-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="8cdb4-111">Spécifiez le nombre de colonnes de longueur fixe et variable et calculez l'espace nécessaire à leur stockage :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="8cdb4-112">Calculez l'espace que chacun de ces groupes de colonnes occupe dans la ligne de données.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="8cdb4-113">La taille d'une colonne dépend du type des données et de la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="8cdb4-114">***Num_Cols***  = nombre total de colonnes (de longueur fixe et variable)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="8cdb4-115">***Fixed_Data_Size***  = taille totale en octets de toutes les colonnes de longueur fixe</span><span class="sxs-lookup"><span data-stu-id="8cdb4-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="8cdb4-116">***Num_Variable_Cols***  = nombre de colonnes de longueur variable</span><span class="sxs-lookup"><span data-stu-id="8cdb4-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="8cdb4-117">***Max_Var_Size***  = taille maximale en octets de toutes les colonnes de longueur variable</span><span class="sxs-lookup"><span data-stu-id="8cdb4-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="8cdb4-118">S'il s'agit d'un index cluster non unique, définissez la colonne *uniqueifier* :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="8cdb4-119">Cette colonne est une colonne de longueur variable qui accepte les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="8cdb4-120">Elle présentera une valeur non NULL et une taille de 4 octets dans les lignes qui contiennent des valeurs de clés non uniques.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="8cdb4-121">Cette valeur fait partie de la clé d'index et est nécessaire pour garantir que chaque ligne contient une valeur de clé unique.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="8cdb4-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="8cdb4-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="8cdb4-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="8cdb4-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="8cdb4-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="8cdb4-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="8cdb4-125">Ces modifications supposent que toutes ces valeurs ne seront pas uniques.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="8cdb4-126">Une partie de la ligne, connue sous le nom de bitmap NULL, est réservée pour gérer la possibilité de valeur NULL de la colonne.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="8cdb4-127">Calculez sa taille :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="8cdb4-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="8cdb4-129">Seule la partie entière de l'expression précédente doit être utilisée ; omettez le reste.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="8cdb4-130">Calculez la taille des données de longueur variable :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="8cdb4-131">En présence de colonnes de longueur variable dans la table, déterminez l'espace utilisé pour stocker les colonnes dans la ligne au moyen de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="8cdb4-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="8cdb4-133">Les octets ajoutés à ***Max_Var_Size*** servent à assurer le suivi de chaque colonne variable.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="8cdb4-134">Il est supposé, lorsque vous utilisez cette formule, que toutes les colonnes de longueur variable sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="8cdb4-135">Si vous pensez qu’un pourcentage inférieur de l’espace de stockage des colonnes de longueur variable sera utilisé, vous pouvez ajuster la valeur de ***Max_Var_Size*** en fonction de ce pourcentage pour obtenir une estimation plus précise de la taille globale de la table.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8cdb4-136">Vous pouvez combiner des colonnes `varchar`, `nvarchar`, `varbinary` ou `sql_variant` qui provoquent le dépassement de la largeur totale de la table définie au-delà de 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="8cdb4-137">La longueur de chacune de ces colonnes doit toujours être inférieure à la limite de 8 000 octets pour une colonne `varchar`, `varbinary` ou `sql_variant` et de 4 000 octets pour les colonnes `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="8cdb4-138">Toutefois, l'association de leurs largeurs peut dépasser la limite de 8 060 octets dans une table.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="8cdb4-139">En l’absence de toute colonne de longueur variable, attribuez la valeur 0 à ***Variable_Data_Size*** .</span><span class="sxs-lookup"><span data-stu-id="8cdb4-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="8cdb4-140">Calculez la taille totale de la ligne :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="8cdb4-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="8cdb4-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="8cdb4-142">La valeur 4 correspond à l'espace réservé à l'en-tête d'une ligne de données.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="8cdb4-143">Calculez le nombre de lignes par page (8 096 octets disponibles par page) :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="8cdb4-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="8cdb4-145">Comme les lignes ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="8cdb4-146">La valeur 2 dans la formule correspond à l'entrée de la ligne dans le tableau d'emplacements de la page.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="8cdb4-147">Calculez le nombre de lignes libres réservées par page en fonction du taux de remplissage [Fill_Factor](../indexes/specify-fill-factor-for-an-index.md) spécifié :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="8cdb4-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="8cdb4-149">Le facteur de remplissage utilisé dans le calcul est un nombre et non un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="8cdb4-150">Comme les lignes ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="8cdb4-151">Au fur et à mesure que le facteur de remplissage s'accroît, davantage de données seront stockées sur chaque page et il y aura moins de pages.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="8cdb4-152">La valeur 2 dans la formule correspond à l'entrée de la ligne dans le tableau d'emplacements de la page.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="8cdb4-153">Calculez ensuite le nombre de pages de données requises pour le stockage de toutes les lignes :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="8cdb4-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="8cdb4-155">Le nombre de pages de données estimé doit être arrondi à la page entière la plus proche.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="8cdb4-156">Calculez la quantité d'espace nécessaire pour le stockage des données au niveau feuille (au total, 8 192 octets par page) :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="8cdb4-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="8cdb4-158">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-158">Step 2.</span></span> <span data-ttu-id="8cdb4-159">Calculer l'espace utilisé pour le stockage des informations d'index</span><span class="sxs-lookup"><span data-stu-id="8cdb4-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="8cdb4-160">Vous pouvez estimer la quantité d'espace nécessaire au stockage des niveaux supérieurs de l'index en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="8cdb4-161">Spécifiez le nombre de colonnes de longueur fixe et de longueur variable de la clé d'index et calculez l'espace nécessaire à leur stockage :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="8cdb4-162">Les colonnes clés d'un index peuvent inclure des colonnes de longueur fixe et variable.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="8cdb4-163">Pour estimer la taille de la ligne d'index du niveau intérieur, calculez l'espace occupé par chacun de ces groupes de colonnes dans la ligne d'index.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="8cdb4-164">La taille d'une colonne dépend du type des données et de la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="8cdb4-165">***Num_Key_Cols***  = nombre total de colonnes clés (de longueur fixe et variable)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="8cdb4-166">***Fixed_Key_Size***  = taille totale en octets de toutes les colonnes clés de longueur fixe</span><span class="sxs-lookup"><span data-stu-id="8cdb4-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="8cdb4-167">***Num_Variable_Key_Cols***  = nombre de colonnes clés de longueur variable</span><span class="sxs-lookup"><span data-stu-id="8cdb4-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="8cdb4-168">***Max_Var_Key_Size***  = taille maximale en octets de toutes les colonnes clés de longueur variable</span><span class="sxs-lookup"><span data-stu-id="8cdb4-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="8cdb4-169">Définissez les colonnes uniqueifier nécessaires s'il s'agit d'un index non unique :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="8cdb4-170">Cette colonne est une colonne de longueur variable qui accepte les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="8cdb4-171">Elle présentera une valeur non NULL et une taille de 4 octets dans les lignes qui contiennent des valeurs de clés d'index non uniques.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="8cdb4-172">Cette valeur fait partie de la clé d'index et est nécessaire pour garantir que chaque ligne contient une valeur de clé unique.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="8cdb4-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="8cdb4-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="8cdb4-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="8cdb4-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="8cdb4-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="8cdb4-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="8cdb4-176">Ces modifications supposent que toutes ces valeurs ne seront pas uniques.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="8cdb4-177">Calculez la taille de null bitmap :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="8cdb4-178">En présence de colonnes autorisant des valeurs Null dans la clé d'index, une partie de la ligne d'index est réservée à la bitmap Null.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="8cdb4-179">Calculez sa taille :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="8cdb4-180">***Index_Null_Bitmap***  = 2 + ((nombre de colonnes dans la ligne d’index + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="8cdb4-181">Seule la partie entière de l'expression précédente doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="8cdb4-182">Omettez le reste.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="8cdb4-183">En l’absence de toute colonne clé autorisant les valeurs Null, attribuez la valeur 0 à ***Index_Null_Bitmap*** .</span><span class="sxs-lookup"><span data-stu-id="8cdb4-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="8cdb4-184">Calculez la taille des données de longueur variable :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="8cdb4-185">En présence de colonnes de longueur variable, déterminez l'espace utilisé pour le stockage des colonnes dans la ligne d'index au moyen de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="8cdb4-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="8cdb4-187">Les octets ajoutés à ***Max_Var_Key_Size*** servent à assurer le suivi de chaque colonne de longueur variable.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="8cdb4-188">Il est supposé, lorsque vous utilisez cette formule, que toutes les colonnes de longueur variable sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="8cdb4-189">Si vous pensez qu’un pourcentage inférieur de l’espace de stockage des colonnes de longueur variable sera utilisé, vous pouvez ajuster la valeur de ***Max_Var_Key_Size*** en fonction de ce pourcentage pour obtenir une estimation plus précise de la taille globale de la table.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="8cdb4-190">En l’absence de toute colonne de longueur variable, attribuez la valeur 0 à ***Variable_Key_Size*** .</span><span class="sxs-lookup"><span data-stu-id="8cdb4-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="8cdb4-191">Calculez la taille de la ligne d'index :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="8cdb4-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (représentant la surcharge de l’en-tête de la ligne d’index) + 6 (représentant le pointeur de l’ID de la page enfant)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="8cdb4-193">Calculez le nombre de lignes d'index par page (8 096 octets libres par page) :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="8cdb4-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="8cdb4-195">Comme les lignes d'index ne peuvent pas être fractionnées sur plusieurs pages de données, arrondissez le nombre de lignes d'index par page à la ligne entière inférieure.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="8cdb4-196">Le chiffre 2 de la formule concerne l'entrée de la ligne du tableau d'emplacement de la page.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="8cdb4-197">Calculez le nombre de niveaux contenus dans l'index :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="8cdb4-198">***Non leaf_Levels*** = 1 + Index_Rows_Per_Page de journal (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="8cdb4-199">Arrondissez cette valeur au nombre entier supérieur le plus proche.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="8cdb4-200">Cette valeur n'inclut pas le niveau feuille de l'index cluster.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="8cdb4-201">Calculez le nombre de pages non-feuille contenues dans l'index :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="8cdb4-202">***Num_Index_Pages =*** ∑ level ***(Num_Leaf_Pages/(***<sup>niveau</sup>Index_Rows_Per_Page ***))***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="8cdb4-203">où 1 <= Level <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="8cdb4-204">Arrondissez chaque élément de la somme au nombre entier supérieur le plus proche.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="8cdb4-205">À titre d’exemple simple, imaginez un index où ***Num_Leaf_Pages*** = 1000 et ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="8cdb4-206">Le premier niveau d'index au-dessus du niveau feuille stocke 1 000 lignes d'index, ce qui représente une ligne d'index par page feuille et 25 lignes d'index par page.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="8cdb4-207">Par conséquent, il faut 40 pages pour stocker ces 1 000 lignes d'index.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="8cdb4-208">Le niveau suivant de l'index doit stocker 40 lignes.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="8cdb4-209">Cela requiert donc 2 pages.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-209">This means it requires 2 pages.</span></span> <span data-ttu-id="8cdb4-210">Le niveau final de l'index doit stocker 2 lignes.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="8cdb4-211">Cela requiert donc 1 page.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-211">This means it requires 1 page.</span></span> <span data-ttu-id="8cdb4-212">Il en résulte 43 pages d'index non-feuille.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="8cdb4-213">Lorsque ces nombres sont utilisés dans les formules précédentes, le résultat est le suivant :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="8cdb4-214">***Non leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="8cdb4-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="8cdb4-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, ce qui correspond au nombre de pages décrit dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="8cdb4-216">Calculez la taille de l'index (8 192 octets par page) :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="8cdb4-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="8cdb4-218">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-218">Step 3.</span></span> <span data-ttu-id="8cdb4-219">Faire la somme des valeurs calculées</span><span class="sxs-lookup"><span data-stu-id="8cdb4-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="8cdb4-220">Faites la somme des valeurs obtenues à partir des deux étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="8cdb4-221">Taille de l’index cluster (octets) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="8cdb4-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="8cdb4-222">Ce calcul ne tient pas compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8cdb4-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="8cdb4-223">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="8cdb4-223">Partitioning</span></span>  
  
     <span data-ttu-id="8cdb4-224">L'espace réservé pour le partitionnement est minime, mais complexe à calculer.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="8cdb4-225">Il n'est pas nécessaire de l'inclure.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="8cdb4-226">Pages d'allocation</span><span class="sxs-lookup"><span data-stu-id="8cdb4-226">Allocation pages</span></span>  
  
     <span data-ttu-id="8cdb4-227">Au moins une page IAM est utilisée pour assurer le suivi des pages allouées à un segment de mémoire, mais l'espace réservé est minime. De plus, il n'existe aucun algorithme capable de calculer de manière déterministe et exacte le nombre de pages IAM qui seront utilisées.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="8cdb4-228">Valeurs LOB</span><span class="sxs-lookup"><span data-stu-id="8cdb4-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="8cdb4-229">L'algorithme permettant de déterminer avec exactitude la quantité d'espace qui sera utilisée pour stocker les valeurs des types de données LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` et `image` est complexe.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="8cdb4-230">Il suffit simplement de faire la somme de la taille moyenne des valeurs LOB attendues, de la multiplier par ***Num_Rows***, puis d’ajouter le résultat à la taille totale de l’index cluster.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="8cdb4-231">Compression</span><span class="sxs-lookup"><span data-stu-id="8cdb4-231">Compression</span></span>  
  
     <span data-ttu-id="8cdb4-232">Vous ne pouvez pas précalculer la taille d'un index compressé.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="8cdb4-233">Colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="8cdb4-233">Sparse columns</span></span>  
  
     <span data-ttu-id="8cdb4-234">Pour plus d'informations sur l'espace nécessaire pour les colonnes éparses, consultez [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8cdb4-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdb4-235">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8cdb4-235">See Also</span></span>  
 <span data-ttu-id="8cdb4-236">[Description des index cluster et non-cluster](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="8cdb4-237">[Estimer la taille d'une table](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="8cdb4-238">[Créer des index cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="8cdb4-239">[Créez des index non-cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="8cdb4-240">[Estimer la taille d'un index non-cluster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="8cdb4-241">[Estimer la taille d’un segment de mémoire](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="8cdb4-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="8cdb4-242">Estimer la taille d'une base de données</span><span class="sxs-lookup"><span data-stu-id="8cdb4-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
