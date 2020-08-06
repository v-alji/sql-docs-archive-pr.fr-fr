---
title: Déplacer un index existant dans un autre groupe de fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614047"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="86be7-102">Déplacer un index existant dans un autre groupe de fichiers</span><span class="sxs-lookup"><span data-stu-id="86be7-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="86be7-103">Cette rubrique explique comment déplacer un index existant d'un groupe de fichiers à un autre à l'aide de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86be7-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="86be7-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="86be7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="86be7-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="86be7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="86be7-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="86be7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="86be7-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="86be7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="86be7-108">**Pour placer un index existant dans un autre groupe de fichiers à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="86be7-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="86be7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="86be7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="86be7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="86be7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="86be7-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="86be7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="86be7-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="86be7-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="86be7-113">Si une table possède un index cluster, le déplacement de celui-ci vers un nouveau groupe de fichiers entraîne le déplacement de la table vers ce groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="86be7-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="86be7-114">Vous ne pouvez pas déplacer des index créés à l'aide de la contrainte UNIQUE ou PRIMARY KEY en utilisant [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86be7-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="86be7-115">Pour déplacer ces index, utilisez l’instruction [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) avec l’option (DROP_EXISTING=ON) dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86be7-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="86be7-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="86be7-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="86be7-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="86be7-117">Permissions</span></span>  
 <span data-ttu-id="86be7-118">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="86be7-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="86be7-119">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="86be7-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="86be7-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="86be7-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="86be7-121">Pour placer un index existant dans un autre groupe de fichiers à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="86be7-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="86be7-122">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table avec l'index que vous souhaitez déplacer.</span><span class="sxs-lookup"><span data-stu-id="86be7-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="86be7-123">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="86be7-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="86be7-124">Cliquez avec le bouton droit sur la table avec l’index que vous souhaitez déplacer et sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="86be7-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="86be7-125">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="86be7-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="86be7-126">Sélectionnez l'index à déplacer.</span><span class="sxs-lookup"><span data-stu-id="86be7-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="86be7-127">Dans la grille principale, développez **Spécification de l'espace de données**.</span><span class="sxs-lookup"><span data-stu-id="86be7-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="86be7-128">Sélectionnez **Nom du schéma de partition ou du groupe de fichiers** , puis sélectionnez dans la liste le groupe de fichiers ou le schéma de partition où vous souhaitez déplacer l'index.</span><span class="sxs-lookup"><span data-stu-id="86be7-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="86be7-129">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="86be7-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="86be7-130">Dans le menu **Fichier** , sélectionnez **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="86be7-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="86be7-131">Pour placer un index existant dans un autre groupe de fichiers dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="86be7-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="86be7-132">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table avec l'index que vous souhaitez déplacer.</span><span class="sxs-lookup"><span data-stu-id="86be7-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="86be7-133">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="86be7-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="86be7-134">Cliquez sur le signe plus (+) pour développer la table contenant l'index à déplacer.</span><span class="sxs-lookup"><span data-stu-id="86be7-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="86be7-135">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="86be7-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="86be7-136">Cliquez avec le bouton droit sur l’index à déplacer, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="86be7-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="86be7-137">Sous **Sélectionner une page**, sélectionnez **Stockage**.</span><span class="sxs-lookup"><span data-stu-id="86be7-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="86be7-138">Sélectionnez le groupe de fichiers vers lequel vous souhaitez déplacer l'index.</span><span class="sxs-lookup"><span data-stu-id="86be7-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="86be7-139">Si la table ou l'index est partitionné(e), sélectionnez le schéma de partition vers lequel déplacer l'index.</span><span class="sxs-lookup"><span data-stu-id="86be7-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="86be7-140">Pour plus d'informations sur les index partitionnés, consultez [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="86be7-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="86be7-141">Si vous déplacez un index cluster, vous pouvez procéder en ligne.</span><span class="sxs-lookup"><span data-stu-id="86be7-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="86be7-142">Le traitement en ligne autorise l'accès des utilisateurs aux données sous-jacentes et aux index non cluster pendant l'opération sur l'index.</span><span class="sxs-lookup"><span data-stu-id="86be7-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="86be7-143">Pour plus d'informations, consultez [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="86be7-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="86be7-144">Sur les ordinateurs multiprocesseurs qui utilisent [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pouvez configurer le nombre de processeurs utilisés pour exécuter l'instruction sur l'index en spécifiant un degré maximal de parallélisme.</span><span class="sxs-lookup"><span data-stu-id="86be7-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="86be7-145">La fonctionnalité permettant les opérations d'index parallèles ne sont pas disponibles dans toutes les édition de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86be7-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86be7-146">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="86be7-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="86be7-147">Pour plus d’informations sur les opérations d’index parallèles, consultez [Configurer des opérations d’index parallèles](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="86be7-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="86be7-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="86be7-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="86be7-149">Les informations suivantes sont disponibles dans la page **Stockage** de la boîte de dialogue **Propriétés de l’index -** _nom_index_ :</span><span class="sxs-lookup"><span data-stu-id="86be7-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="86be7-150">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="86be7-150">**Filegroup**</span></span>  
 <span data-ttu-id="86be7-151">Stocke l'index dans le groupe de fichiers spécifié.</span><span class="sxs-lookup"><span data-stu-id="86be7-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="86be7-152">La liste répertorie uniquement les groupes de fichiers standard (row).</span><span class="sxs-lookup"><span data-stu-id="86be7-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="86be7-153">Le groupe de fichiers PRIMARY de la base de données est sélectionné par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="86be7-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="86be7-154">**Groupe de fichiers Filestream**</span><span class="sxs-lookup"><span data-stu-id="86be7-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="86be7-155">Spécifie le groupe de fichiers pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="86be7-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="86be7-156">Cette liste affiche uniquement des groupes de fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="86be7-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="86be7-157">Le groupe de fichiers sélectionné par défaut dans la liste est le groupe PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="86be7-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="86be7-158">**Schéma de partition**</span><span class="sxs-lookup"><span data-stu-id="86be7-158">**Partition scheme**</span></span>  
 <span data-ttu-id="86be7-159">Stocke l'index dans un schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="86be7-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="86be7-160">En cliquant sur **Schéma de partition** , vous activez la grille ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="86be7-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="86be7-161">Le schéma de partition sélectionné par défaut dans la liste est celui qui est utilisé pour stocker les données de la table.</span><span class="sxs-lookup"><span data-stu-id="86be7-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="86be7-162">Si vous sélectionnez un autre schéma de partition dans la liste, les informations affichées dans la grille sont actualisées.</span><span class="sxs-lookup"><span data-stu-id="86be7-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="86be7-163">L'option Schéma de partition n'est pas disponible s'il n'y a pas de schémas de partition dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="86be7-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="86be7-164">**Schéma de partition Filestream**</span><span class="sxs-lookup"><span data-stu-id="86be7-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="86be7-165">Spécifie le schéma de partition utilisé pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="86be7-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="86be7-166">Ce schéma de partition doit être symétrique avec celui spécifié dans l'option **Schéma de partition** .</span><span class="sxs-lookup"><span data-stu-id="86be7-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="86be7-167">Si la table n'est pas partitionnée, le champ est vide.</span><span class="sxs-lookup"><span data-stu-id="86be7-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="86be7-168">**Paramètre du schéma de partition**</span><span class="sxs-lookup"><span data-stu-id="86be7-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="86be7-169">Affiche le nom de la colonne qui participe au schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="86be7-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="86be7-170">**Colonne de table**</span><span class="sxs-lookup"><span data-stu-id="86be7-170">**Table Column**</span></span>  
 <span data-ttu-id="86be7-171">Sélectionnez la table ou vue à mapper avec le schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="86be7-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="86be7-172">**Type de données de la colonne**</span><span class="sxs-lookup"><span data-stu-id="86be7-172">**Column Data Type**</span></span>  
 <span data-ttu-id="86be7-173">Affiche des informations sur les types de données figurant dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="86be7-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86be7-174">Si la colonne de table est une colonne calculée, **Type de données de la colonne** contient la mention « colonne calculée ».</span><span class="sxs-lookup"><span data-stu-id="86be7-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="86be7-175">**Autoriser le traitement en ligne des instructions DML lors du déplacement de l'index**</span><span class="sxs-lookup"><span data-stu-id="86be7-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="86be7-176">Permet aux utilisateurs d'accéder à la table sous-jacente ou aux données des index cluster et à tous les index non-cluster associés pendant l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="86be7-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86be7-177">Cette option n'est pas disponible pour les index XML ou si l'index est un index cluster désactivé.</span><span class="sxs-lookup"><span data-stu-id="86be7-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="86be7-178">**Définir le degré maximal de parallélisme**</span><span class="sxs-lookup"><span data-stu-id="86be7-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="86be7-179">Limite le nombre de processeurs à utiliser pendant l'exécution des plans parallèles.</span><span class="sxs-lookup"><span data-stu-id="86be7-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="86be7-180">La valeur par défaut est 0, indiquant que le nombre réel de processeurs disponibles est utilisé.</span><span class="sxs-lookup"><span data-stu-id="86be7-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="86be7-181">Spécifier la valeur 1 supprime la génération d'un plan parallèle ; spécifier une valeur supérieure à 1 limite le nombre maximal de processeurs utilisés au cours de l'exécution d'une requête simple.</span><span class="sxs-lookup"><span data-stu-id="86be7-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="86be7-182">Cette option est disponible seulement si la boîte de dialogue est dans l'état **Reconstruire** ou **Recréer** .</span><span class="sxs-lookup"><span data-stu-id="86be7-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86be7-183">Si une valeur supérieure au nombre d'UC disponibles est spécifiée, le nombre réel d'UC est utilisé.</span><span class="sxs-lookup"><span data-stu-id="86be7-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="86be7-184">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="86be7-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="86be7-185">Pour placer un index existant dans un autre groupe de fichiers</span><span class="sxs-lookup"><span data-stu-id="86be7-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="86be7-186">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86be7-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="86be7-187">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="86be7-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="86be7-188">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="86be7-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="86be7-189">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86be7-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
