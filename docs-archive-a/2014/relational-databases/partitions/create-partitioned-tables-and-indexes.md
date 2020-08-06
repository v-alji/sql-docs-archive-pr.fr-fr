---
title: Créer des tables et des index partitionnés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603957"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="e5789-102">Créer des tables et des index partitionnés</span><span class="sxs-lookup"><span data-stu-id="e5789-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="e5789-103">Vous pouvez créer une table ou un index partitionné(e) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5789-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e5789-104">Les données contenues dans des tables et des index partitionnés sont divisées horizontalement en unités qui peuvent être réparties sur plusieurs groupes de fichiers d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="e5789-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="e5789-105">Le partitionnement permet de rendre des tables et des index volumineux plus gérables et plus évolutifs.</span><span class="sxs-lookup"><span data-stu-id="e5789-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="e5789-106">La création d'une table ou d'un index partitionné(e) se produit généralement en quatre étapes :</span><span class="sxs-lookup"><span data-stu-id="e5789-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="e5789-107">Créez un ou plusieurs groupes de fichiers et les fichiers correspondants qui contiendront les partitions spécifiées par le schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="e5789-108">Créez une fonction de partition qui mappe les lignes d'une table ou d'un index avec des partitions basées sur les valeurs d'une colonne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5789-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="e5789-109">Créez un schéma de partition qui mappe les partitions d'une table ou d'un index partitionné(e) avec les nouveaux groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="e5789-110">Créez ou modifiez une table ou un index et spécifiez le schéma de partition comme emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="e5789-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="e5789-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e5789-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e5789-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e5789-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e5789-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5789-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e5789-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5789-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e5789-115">**Pour créer une table ou un index partitionné(e), utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e5789-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="e5789-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5789-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e5789-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5789-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5789-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e5789-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e5789-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5789-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e5789-120">L'étendue d'une fonction de partition et d'un schéma est limitée à la base de données dans laquelle ils ont été créés.</span><span class="sxs-lookup"><span data-stu-id="e5789-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="e5789-121">Dans la base de données, les fonctions de partition résident dans un espace de noms indépendant des autres fonctions.</span><span class="sxs-lookup"><span data-stu-id="e5789-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="e5789-122">Si des lignes dans une fonction de partition ont des colonnes de partitionnement avec des valeurs Null, ces lignes sont allouées à la partition la plus à gauche.</span><span class="sxs-lookup"><span data-stu-id="e5789-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="e5789-123">Toutefois, si NULL est spécifié comme valeur limite et que RIGHT est indiqué, la partition la plus à gauche reste vide et les valeurs NULL sont placées dans la deuxième partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e5789-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5789-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e5789-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e5789-125">Permissions</span></span>  
 <span data-ttu-id="e5789-126">La création d'une table partitionnée nécessite une autorisation CREATE TABLE dans la base de données et une autorisation ALTER pour le schéma dans lequel la table est créée.</span><span class="sxs-lookup"><span data-stu-id="e5789-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="e5789-127">La création d'un index partitionné nécessite l'autorisation ALTER sur la table ou la vue dans laquelle l'index est créé.</span><span class="sxs-lookup"><span data-stu-id="e5789-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="e5789-128">La création d'une table ou d'un index partitionné(e) nécessite l'une des autorisations supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5789-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="e5789-129">Autorisation ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="e5789-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="e5789-130">Cette autorisation est attribuée par défaut aux membres du rôle de serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="e5789-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="e5789-131">Autorisation CONTROL ou ALTER sur la base de données dans laquelle la fonction de partition et le schéma de partition sont créés.</span><span class="sxs-lookup"><span data-stu-id="e5789-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="e5789-132">Autorisation CONTROL SERVER ou ALTER ANY DATABASE sur le serveur de la base de données dans laquelle la fonction de partition et le schéma de partition sont créés.</span><span class="sxs-lookup"><span data-stu-id="e5789-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e5789-133">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5789-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e5789-134">Suivez les étapes de cette procédure pour créer un ou plusieurs groupes de fichiers, les fichiers correspondants et une table.</span><span class="sxs-lookup"><span data-stu-id="e5789-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="e5789-135">Vous référencerez ces objets dans la procédure suivante lorsque vous créerez la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e5789-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="e5789-136">Pour créer de nouveaux groupes de fichiers pour une table partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="e5789-137">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la base de données dans laquelle vous souhaitez créer une table partitionnée et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e5789-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e5789-138">Dans la boîte de dialogue **Propriétés de la base de données -** *nom_base_de_données*, sous **Sélectionner une page**, sélectionnez **Groupes de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="e5789-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="e5789-139">Sous **Lignes**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e5789-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="e5789-140">Dans la nouvelle ligne, entrez le nom du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="e5789-141">Vous devez toujours avoir un groupe de fichiers supplémentaire en plus du nombre de groupes de fichiers spécifié pour les valeurs limites lorsque vous créez des partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="e5789-142">Continuez à ajouter des lignes jusqu'à ce que vous ayez créé tous les groupes de fichiers pour la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e5789-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="e5789-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5789-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="e5789-144">Sous **Sélectionner une page**, sélectionnez **Fichiers**.</span><span class="sxs-lookup"><span data-stu-id="e5789-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="e5789-145">Sous **Lignes**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e5789-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="e5789-146">Dans la nouvelle ligne, entrez un nom de fichier et sélectionnez un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="e5789-147">Continuez à ajouter des lignes jusqu'à ce que vous ayez créé au moins un fichier pour chaque groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="e5789-148">Développez le dossier **Tables** et créez une table selon la procédure habituelle.</span><span class="sxs-lookup"><span data-stu-id="e5789-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="e5789-149">Pour plus d’informations, consultez [Créer des tables &#40;moteur de base de données&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="e5789-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="e5789-150">Vous pouvez éventuellement spécifier une table existante dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="e5789-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="e5789-151">Pour créer une table partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="e5789-152">Cliquez avec le bouton droit sur la table à partitionner, pointez sur **Stockage**, puis cliquez sur **Créer une partition...** .</span><span class="sxs-lookup"><span data-stu-id="e5789-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="e5789-153">Dans l' **Assistant Création de partition**, sur la page **Assistant Création de partition** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="e5789-154">Sur la page **Sélectionner une colonne de partitionnement** , dans la grille **Colonnes de partitionnement disponibles** , sélectionnez la colonne sur laquelle vous souhaitez partitionner votre table.</span><span class="sxs-lookup"><span data-stu-id="e5789-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="e5789-155">Seules les colonnes dont le type de données peut être utilisé pour partitionner des données seront affichées dans la grille **Colonnes de partitionnement disponibles** .</span><span class="sxs-lookup"><span data-stu-id="e5789-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="e5789-156">Si vous sélectionnez une colonne calculée comme colonne de partitionnement, celle-ci doit être désignée en tant que colonne persistante.</span><span class="sxs-lookup"><span data-stu-id="e5789-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="e5789-157">Le degré avec lequel vous pouvez regrouper les données de façon logique déterminent les options dont vous disposez pour définir la colonne de partitionnement et la plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="e5789-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="e5789-158">Par exemple, vous pouvez choisir de diviser vos données en regroupements logiques par mois ou trimestres d'une année.</span><span class="sxs-lookup"><span data-stu-id="e5789-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="e5789-159">Les requêtes que vous projetez d'exécuter sur vos données détermineront si ce regroupement logique est adéquat pour gérer vos partitions de table.</span><span class="sxs-lookup"><span data-stu-id="e5789-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="e5789-160">Tous les types de données sont utilisables comme colonnes de partitionnement, à l'exception de `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, des types de données d'alias ou des types de données CLR définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e5789-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="e5789-161">Les options supplémentaires suivantes sont disponibles sur cette page :</span><span class="sxs-lookup"><span data-stu-id="e5789-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="e5789-162">**Colocaliser cette table avec la table partitionnée sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="e5789-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="e5789-163">Permet de sélectionner une table partitionnée qui contient les données connexes à joindre à cette table sur la colonne de partitionnement.</span><span class="sxs-lookup"><span data-stu-id="e5789-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="e5789-164">Les requêtes portant sur des tables présentant des partitions jointes sur les colonnes de partitionnement sont généralement plus efficaces.</span><span class="sxs-lookup"><span data-stu-id="e5789-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="e5789-165">**Aligner les index non uniques et uniques avec une colonne de partition indexée lors du stockage**</span><span class="sxs-lookup"><span data-stu-id="e5789-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="e5789-166">Aligne tous les index de la table qui sont partitionnés avec le même schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="e5789-167">Lorsqu'une table et ses index sont alignés, vous pouvez plus efficacement déplacer des partitions dans et hors de tables partitionnées, car vos données sont partitionnées avec le même algorithme.</span><span class="sxs-lookup"><span data-stu-id="e5789-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="e5789-168">Après avoir sélectionné la colonne de partitionnement et toute autre option, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="e5789-169">Sur la page **Sélectionner une fonction de partition** , sous **Sélectionner une fonction de partition**, cliquez sur **Nouvelle fonction de partition** ou sur **Fonction de partition existante**.</span><span class="sxs-lookup"><span data-stu-id="e5789-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="e5789-170">Si vous choisissez **Nouvelle fonction de partition**, entrez le nom de la fonction.</span><span class="sxs-lookup"><span data-stu-id="e5789-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="e5789-171">Si vous choisissez **Fonction de partition existante**, sélectionnez le nom de la fonction que vous souhaitez utiliser dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e5789-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="e5789-172">L'option **Fonction de partition existante** ne sera pas disponible s'il n'existe aucune autre fonction de partition sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5789-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="e5789-173">Après avoir complété cette page, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="e5789-174">Sur la page **Sélectionner un schéma de partition** , sous **Sélectionner un schéma de partition**, cliquez sur **Nouveau schéma de partition** ou sur **Schéma de partition existant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="e5789-175">Si vous choisissez **Nouveau schéma de partition**, entrez le nom du schéma.</span><span class="sxs-lookup"><span data-stu-id="e5789-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="e5789-176">Si vous choisissez **Schéma de partition existant**, sélectionnez le nom du schéma que vous souhaitez utiliser dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e5789-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="e5789-177">L'option **Schéma de partition existant** ne sera pas disponible s'il n'existe aucun autre schéma de partition sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5789-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="e5789-178">Après avoir complété cette page, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="e5789-179">Sur la page **Associer les partitions** , sous **Plage**, sélectionnez **Limite gauche** ou **Limite droite** pour spécifier s'il faut inclure la valeur limite la plus élevée ou la plus basse dans chaque groupe de fichiers que vous créez.</span><span class="sxs-lookup"><span data-stu-id="e5789-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="e5789-180">Vous devez toujours entrer un groupe de fichiers supplémentaire en plus du nombre de groupes de fichiers spécifié pour les valeurs limites lorsque vous créez des partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="e5789-181">Dans la grille **Sélectionnez les groupes de fichiers et spécifiez les valeurs limites** , sous **Groupe de fichiers**, sélectionnez le groupe de fichiers dans lequel vous souhaitez partitionner vos données.</span><span class="sxs-lookup"><span data-stu-id="e5789-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="e5789-182">Sous **Limite**, entrez la valeur limite pour chaque groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="e5789-183">Si la valeur limite reste vide, la fonction de partition mappe la totalité de la table ou de l'index en une seule partition en utilisant le nom de la fonction de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="e5789-184">Les options supplémentaires suivantes sont disponibles sur cette page :</span><span class="sxs-lookup"><span data-stu-id="e5789-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="e5789-185">**Définir les limites...**</span><span class="sxs-lookup"><span data-stu-id="e5789-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="e5789-186">Ouvre la boîte de dialogue **Définir les valeurs limites** pour sélectionner les valeurs limites et les plages de dates voulues pour vos partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="e5789-187">Cette option est disponible uniquement lorsque vous avez sélectionné une colonne de partitionnement qui contient l'un des types de données suivants : `date`, `datetime`, `smalldatetime`, `datetime2` ou `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="e5789-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="e5789-188">**Estimer le stockage**</span><span class="sxs-lookup"><span data-stu-id="e5789-188">**Estimate storage**</span></span>  
     <span data-ttu-id="e5789-189">Estime le nombre de lignes, l'espace requis et l'espace disponible pour le stockage de chaque groupe de fichiers spécifié pour les partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="e5789-190">Ces valeurs s'affichent dans la grille en tant que valeurs en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e5789-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="e5789-191">La boîte de dialogue **Définir les valeurs limites** autorise les options supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5789-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="e5789-192">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="e5789-192">**Start date**</span></span>  
     <span data-ttu-id="e5789-193">Sélectionne la date de début pour les valeurs de plages de vos partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="e5789-194">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="e5789-194">**End date**</span></span>  
     <span data-ttu-id="e5789-195">Sélectionne la date de fin pour les valeurs de plages de vos partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="e5789-196">Si vous avez sélectionné l’option **Limite gauche** dans la page **Associer les partitions** , cette date est la dernière valeur de chaque groupe de fichiers/partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="e5789-197">Si vous avez sélectionné l’option **Limite droite** dans la page **Associer les partitions** , cette date est la première valeur du prochain groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="e5789-198">**Plage de dates**</span><span class="sxs-lookup"><span data-stu-id="e5789-198">**Date range**</span></span>  
     <span data-ttu-id="e5789-199">Sélectionne la granularité de date ou l'incrément de valeur de plage qui vous intéresse pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="e5789-200">Après avoir complété cette page, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="e5789-201">Sur la page **Sélectionner une option de sortie** , spécifiez de quelle manière vous souhaitez remplir votre table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e5789-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="e5789-202">Sélectionnez **Créer un script** pour créer un script SQL basé sur les pages précédentes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e5789-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="e5789-203">Sélectionnez **Exécuter immédiatement** pour créer la nouvelle table partitionnée après avoir complété toutes les pages restantes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e5789-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="e5789-204">Sélectionnez **Planification** pour créer la nouvelle table partitionnée à un moment prédéterminé dans le futur.</span><span class="sxs-lookup"><span data-stu-id="e5789-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="e5789-205">Si vous sélectionnez **Créer un script**, les options suivantes sont disponibles sous **Options de script**:</span><span class="sxs-lookup"><span data-stu-id="e5789-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="e5789-206">**Générer un script sur fichier**</span><span class="sxs-lookup"><span data-stu-id="e5789-206">**Script to file**</span></span>  
     <span data-ttu-id="e5789-207">Génère le script sous la forme d'un fichier .sql.</span><span class="sxs-lookup"><span data-stu-id="e5789-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="e5789-208">Entrez un nom de fichier et un emplacement dans la boîte de dialogue **Nom de fichier** ou cliquez sur **Parcourir** pour ouvrir la boîte de dialogue **Emplacement du fichier de script** .</span><span class="sxs-lookup"><span data-stu-id="e5789-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="e5789-209">Pour **Enregistrer sous**, sélectionnez **Texte Unicode** ou **Texte ANSI**.</span><span class="sxs-lookup"><span data-stu-id="e5789-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="e5789-210">**Générer un script sur le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="e5789-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="e5789-211">Enregistre le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="e5789-212">**Générer un script dans une nouvelle fenêtre de requête**</span><span class="sxs-lookup"><span data-stu-id="e5789-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="e5789-213">Génère le script dans une nouvelle fenêtre de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e5789-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="e5789-214">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="e5789-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="e5789-215">Si vous sélectionnez **Planification**, cliquez sur **Modifier la planification**.</span><span class="sxs-lookup"><span data-stu-id="e5789-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="e5789-216">Dans la boîte de dialogue **Nouvelle planification du travail**, dans la zone **Nom**, entrez le nom de la planification du travail.</span><span class="sxs-lookup"><span data-stu-id="e5789-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="e5789-217">Dans la liste **Type de planification** , sélectionnez le type de la planification :</span><span class="sxs-lookup"><span data-stu-id="e5789-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="e5789-218">**Lancer automatiquement au démarrage de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="e5789-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="e5789-219">**Démarrer dès que les processeurs sont inactifs**</span><span class="sxs-lookup"><span data-stu-id="e5789-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="e5789-220">**Périodique**.</span><span class="sxs-lookup"><span data-stu-id="e5789-220">**Recurring**.</span></span> <span data-ttu-id="e5789-221">Sélectionnez cette option si votre nouvelle table partitionnée est mise à jour régulièrement avec de nouvelles informations.</span><span class="sxs-lookup"><span data-stu-id="e5789-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="e5789-222">**Une fois**.</span><span class="sxs-lookup"><span data-stu-id="e5789-222">**One time**.</span></span> <span data-ttu-id="e5789-223">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="e5789-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="e5789-224">Activez ou désactivez la case à cocher **Activé** pour activer ou désactiver la planification.</span><span class="sxs-lookup"><span data-stu-id="e5789-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="e5789-225">Si vous sélectionnez **Périodique**:</span><span class="sxs-lookup"><span data-stu-id="e5789-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="e5789-226">Sous **Fréquence**, dans la liste **Périodicité** , spécifiez la fréquence d'occurrence :</span><span class="sxs-lookup"><span data-stu-id="e5789-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="e5789-227">Si vous sélectionnez **Quotidienne**, dans la zone **Répéter toutes les** , entrez la fréquence de répétition du travail de planification en jours.</span><span class="sxs-lookup"><span data-stu-id="e5789-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="e5789-228">Si vous sélectionnez **Hebdomadaire**, dans la zone **Répéter toutes les** , entrez la fréquence de répétition du travail de planification en semaines.</span><span class="sxs-lookup"><span data-stu-id="e5789-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="e5789-229">Sélectionnez le jour ou les jours de la semaine pendant lesquels la planification du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="e5789-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="e5789-230">Si vous sélectionnez **Mensuelle**, sélectionnez **Jour** ou **Le**.</span><span class="sxs-lookup"><span data-stu-id="e5789-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="e5789-231">Si vous sélectionnez **Jour**, entrez la date du mois à laquelle vous souhaitez que la planification du travail s'exécute, ainsi que la fréquence de répétition de la planification du travail en mois.</span><span class="sxs-lookup"><span data-stu-id="e5789-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="e5789-232">Par exemple, si vous souhaitez que la planification du travail s’exécute le 15 du mois un mois sur deux, sélectionnez **Jour**, puis entrez « 15 » dans la première zone et « 2 » dans la deuxième zone.</span><span class="sxs-lookup"><span data-stu-id="e5789-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="e5789-233">Notez que le nombre maximum autorisé dans la deuxième zone est « 99 ».</span><span class="sxs-lookup"><span data-stu-id="e5789-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="e5789-234">Si vous sélectionnez **Le**, sélectionnez le jour spécifique de la semaine et du mois pendant lequel vous voulez que la planification du travail s'exécute et la fréquence à laquelle la planification du travail doit se répéter en mois.</span><span class="sxs-lookup"><span data-stu-id="e5789-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="e5789-235">Par exemple, si vous souhaitez que la planification du travail s’exécute le dernier jour de la semaine un mois sur deux, sélectionnez **Jour**, puis **dernier** dans la première liste, **jour ouvrable** dans la deuxième liste et « 2 » dans la dernière zone.</span><span class="sxs-lookup"><span data-stu-id="e5789-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="e5789-236">Vous pouvez également sélectionner **premier**, **deuxième**, **troisième**ou **quatrième**, ainsi que des jours de la semaine spécifiques (par exemple, dimanche ou mercredi) dans les deux premières listes.</span><span class="sxs-lookup"><span data-stu-id="e5789-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="e5789-237">Notez que le nombre maximum autorisé dans la dernière zone est « 99 ».</span><span class="sxs-lookup"><span data-stu-id="e5789-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="e5789-238">Sous **Fréquence quotidienne**, spécifiez la fréquence à laquelle la planification du travail se répète le jour de son exécution :</span><span class="sxs-lookup"><span data-stu-id="e5789-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="e5789-239">Si vous sélectionnez **Une fois à**, entrez l'heure spécifique à laquelle la planification du travail doit s'exécuter dans la zone **Une fois à** .</span><span class="sxs-lookup"><span data-stu-id="e5789-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="e5789-240">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="e5789-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="e5789-241">Si vous sélectionnez **Toutes les**, spécifiez la fréquence à laquelle la planification du travail s'exécute pendant la journée choisie sous **Fréquence**.</span><span class="sxs-lookup"><span data-stu-id="e5789-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="e5789-242">Par exemple, si vous souhaitez que la planification du travail se répète toutes les 2 heures le jour d’exécution de la planification du travail, sélectionnez **Toutes les**, entrez « 2 » dans la première zone, puis sélectionnez **heure(s)** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e5789-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="e5789-243">Dans cette liste, vous pouvez également sélectionner **minute(s)** et **seconde(s)** .</span><span class="sxs-lookup"><span data-stu-id="e5789-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="e5789-244">Notez que le nombre maximum autorisé dans la première zone est « 100 ».</span><span class="sxs-lookup"><span data-stu-id="e5789-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="e5789-245">Dans la zone **Début** , entrez l'heure à laquelle l'exécution de la planification du travail doit démarrer.</span><span class="sxs-lookup"><span data-stu-id="e5789-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="e5789-246">Dans la zone **Fin** , entrez l'heure à laquelle la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="e5789-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="e5789-247">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="e5789-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="e5789-248">Sous **Durée**, dans la zone **Date de début**, entrez la date à laquelle vous souhaitez que l'exécution de la planification du travail commence.</span><span class="sxs-lookup"><span data-stu-id="e5789-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="e5789-249">Sélectionnez **Date de fin** ou **Aucune date de fin** pour indiquer à quel moment l'exécution de la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="e5789-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="e5789-250">Si vous sélectionnez **Date de fin**, entrez la date à laquelle l'exécution de la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="e5789-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="e5789-251">Si vous sélectionnez **Une fois**sous **Une seule occurrence**, dans la zone **Date** , entrez la date à laquelle la planification du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="e5789-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="e5789-252">Dans la zone **Heure** , entrez l'heure à laquelle la planification du travail sera exécutée.</span><span class="sxs-lookup"><span data-stu-id="e5789-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="e5789-253">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="e5789-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="e5789-254">Sous **Résumé**, dans **Description**, vérifiez que tous les paramètres de planification du travail sont corrects.</span><span class="sxs-lookup"><span data-stu-id="e5789-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="e5789-255">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5789-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="e5789-256">Après avoir complété cette page, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e5789-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="e5789-257">Dans la page **Vérifier le résumé** , sous **Vérifier vos sélections**, développez toutes les options disponibles pour vérifier que tous les paramètres de partition sont corrects.</span><span class="sxs-lookup"><span data-stu-id="e5789-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="e5789-258">Si tout est conforme à vos attentes, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e5789-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="e5789-259">Sur la page **Progression de l'Assistant Création de partition** , surveillez les informations d'état relatives aux actions de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="e5789-260">Selon les options sélectionnées dans l'Assistant, la page de progression peut contenir une ou plusieurs actions.</span><span class="sxs-lookup"><span data-stu-id="e5789-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="e5789-261">La zone supérieure affiche l'état global de l'Assistant et le nombre des messages d'état, d'erreur et d'avertissement qu'il a reçus.</span><span class="sxs-lookup"><span data-stu-id="e5789-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="e5789-262">Les options suivantes sont disponibles sur la page **Progression de l'Assistant Création de partition** :</span><span class="sxs-lookup"><span data-stu-id="e5789-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="e5789-263">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e5789-263">**Details**</span></span>  
     <span data-ttu-id="e5789-264">Indique l'action, l'état et tous les messages retournés suite à l'action entreprise par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="e5789-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="e5789-265">**Action**</span><span class="sxs-lookup"><span data-stu-id="e5789-265">**Action**</span></span>  
     <span data-ttu-id="e5789-266">Indique le type et le nom de chaque action.</span><span class="sxs-lookup"><span data-stu-id="e5789-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="e5789-267">**État**</span><span class="sxs-lookup"><span data-stu-id="e5789-267">**Status**</span></span>  
     <span data-ttu-id="e5789-268">Indique si l’action de l’Assistant dans son ensemble a retourné la valeur **Réussite** ou **Échec**.</span><span class="sxs-lookup"><span data-stu-id="e5789-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="e5789-269">**Message**</span><span class="sxs-lookup"><span data-stu-id="e5789-269">**Message**</span></span>  
     <span data-ttu-id="e5789-270">Indique les messages d'erreur ou d'avertissement retournés par le processus.</span><span class="sxs-lookup"><span data-stu-id="e5789-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="e5789-271">**Report**</span><span class="sxs-lookup"><span data-stu-id="e5789-271">**Report**</span></span>  
     <span data-ttu-id="e5789-272">Crée un rapport qui contient les résultats de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="e5789-273">Les options sont **Afficher le rapport**, **Enregistrer le rapport dans un fichier**, **Copier le rapport dans le Presse-papiers**et **Envoyer le rapport sous forme de courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="e5789-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="e5789-274">**Afficher le rapport**</span><span class="sxs-lookup"><span data-stu-id="e5789-274">**View Report**</span></span>  
     <span data-ttu-id="e5789-275">Ouvre la boîte de dialogue **Afficher le rapport** , qui contient un rapport au format texte de la progression de l’Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="e5789-276">**Enregistrer le rapport dans un fichier**</span><span class="sxs-lookup"><span data-stu-id="e5789-276">**Save Report to File**</span></span>  
     <span data-ttu-id="e5789-277">Ouvre la boîte de dialogue **Enregistrer le rapport sous** .</span><span class="sxs-lookup"><span data-stu-id="e5789-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="e5789-278">**Copier le rapport dans le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="e5789-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="e5789-279">Copie les résultats du rapport de progression de l’Assistant dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="e5789-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="e5789-280">**Envoyer le rapport sous forme de courrier électronique**</span><span class="sxs-lookup"><span data-stu-id="e5789-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="e5789-281">Copie les résultats du rapport de progression de l’Assistant dans un e-mail.</span><span class="sxs-lookup"><span data-stu-id="e5789-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="e5789-282">Une fois terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e5789-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="e5789-283">L'Assistant Création de partition crée la fonction de partition et le schéma, puis applique le partitionnement à la table spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e5789-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="e5789-284">Pour vérifier le partitionnement de table, dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e5789-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="e5789-285">Cliquez sur la page **Stockage** .</span><span class="sxs-lookup"><span data-stu-id="e5789-285">Click the **Storage** page.</span></span> <span data-ttu-id="e5789-286">La page affiche des informations telles que le nom de la fonction de partition et du schéma, ainsi que le nombre de partitions.</span><span class="sxs-lookup"><span data-stu-id="e5789-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e5789-287">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5789-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="e5789-288">Pour créer une table partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="e5789-289">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5789-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5789-290">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e5789-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5789-291">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5789-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e5789-292">L'exemple crée des groupes de fichiers, une fonction de partition et un schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e5789-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="e5789-293">Une nouvelle table est créée avec le schéma de partition spécifié comme emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="e5789-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;   
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="e5789-294">Pour déterminer si une table est partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="e5789-295">La requête suivante renvoie une ou plusieurs lignes si la table `PartitionTable` est partitionnée.</span><span class="sxs-lookup"><span data-stu-id="e5789-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="e5789-296">Si la table n'est pas partitionnée, aucune ligne n'est retournée.</span><span class="sxs-lookup"><span data-stu-id="e5789-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="e5789-297">Pour déterminer les valeurs limites pour une table partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="e5789-298">La requête suivante renvoie les valeurs limites pour chaque partition de la table `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="e5789-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="e5789-299">Pour déterminer la colonne de partition pour une table partitionnée</span><span class="sxs-lookup"><span data-stu-id="e5789-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="e5789-300">La requête suivante renvoie le nom de la colonne de partitionnement pour une table.</span><span class="sxs-lookup"><span data-stu-id="e5789-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="e5789-301">`PartitionTable`.</span><span class="sxs-lookup"><span data-stu-id="e5789-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="e5789-302">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5789-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="e5789-303">Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5789-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="e5789-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5789-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="e5789-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5789-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="e5789-306">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5789-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
