---
title: Créer des index avec colonnes incluses | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708311"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="b21f8-102">Créer des index avec colonnes incluses</span><span class="sxs-lookup"><span data-stu-id="b21f8-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="b21f8-103">Cette rubrique explique comment ajouter des colonnes incluses (ou non-clés) pour étendre les fonctionnalités des index non cluster dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b21f8-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b21f8-104">L'inclusion de colonnes non-clés permet de créer des index non-cluster qui couvrent davantage de requêtes.</span><span class="sxs-lookup"><span data-stu-id="b21f8-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="b21f8-105">En effet, les colonnes non-clés présentent les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="b21f8-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="b21f8-106">Elles peuvent contenir des types de données qui ne sont pas autorisés dans les colonnes de clés d'index.</span><span class="sxs-lookup"><span data-stu-id="b21f8-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="b21f8-107">Elles ne sont pas prises en compte par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] lors du calcul du nombre de colonnes clés d'index ou de la taille de la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="b21f8-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="b21f8-108">Un index contenant des colonnes non-clés peut améliorer considérablement les performances des requêtes lorsque toutes les colonnes de la requête sont incluses dans l'index en tant que colonnes clés ou non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="b21f8-109">Les gains de performances sont dus au fait que l'optimiseur de requête peut localiser toutes les valeurs des colonnes dans l'index ; l'accès aux données de table et d'index n'a pas lieu, produisant ainsi un nombre moindre d'opérations d'E/S sur le disque.</span><span class="sxs-lookup"><span data-stu-id="b21f8-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b21f8-110">Quand un index contient toutes les colonnes auxquelles une requête fait référence, on dit qu’il *couvre la requête*.</span><span class="sxs-lookup"><span data-stu-id="b21f8-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="b21f8-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b21f8-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b21f8-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b21f8-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b21f8-113">Recommandations pour la conception</span><span class="sxs-lookup"><span data-stu-id="b21f8-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="b21f8-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b21f8-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b21f8-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b21f8-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b21f8-116">**Pour créer un index avec des colonnes non-clés, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b21f8-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="b21f8-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b21f8-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b21f8-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b21f8-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b21f8-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b21f8-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="b21f8-120">Recommandations relatives à la conception</span><span class="sxs-lookup"><span data-stu-id="b21f8-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="b21f8-121">La conception d'index non-cluster doit être réalisée avec une clé d'index de grande taille, de sorte que seules les colonnes utilisées pour la recherche sont les colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="b21f8-122">Toutes les autres colonnes qui couvrent la requête doivent être des colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="b21f8-123">De cette manière, vous disposez de toutes les colonnes nécessaires pour couvrir la requête, mais la clé d'index elle-même est petite et efficace.</span><span class="sxs-lookup"><span data-stu-id="b21f8-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="b21f8-124">Incluez les colonnes non-clés dans un index non cluster pour éviter de dépasser les limitations actuelles de taille d'index, établies à 16 colonnes clés au maximum et une taille de clé d'index de 900 octets au maximum.</span><span class="sxs-lookup"><span data-stu-id="b21f8-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="b21f8-125">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ne tient pas compte des colonnes non-clés lors du calcul du nombre de colonnes clés d'index ou de la taille de la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="b21f8-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b21f8-126">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b21f8-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b21f8-127">Les colonnes non-clés peuvent uniquement être définies sur des index non cluster.</span><span class="sxs-lookup"><span data-stu-id="b21f8-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="b21f8-128">Tous les types de données, à l'exception de `text`, de `ntext` et de `image`, peuvent être utilisés en tant que colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="b21f8-129">Les colonnes calculées déterministes et précises ou imprécises peuvent être des colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="b21f8-130">Pour plus d'informations, consultez [Indexes on Computed Columns](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="b21f8-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="b21f8-131">Les colonnes calculées dérivées des types de données `image`, `ntext` et `text` peuvent être des colonnes non-clés tant que le type de données de la colonne calculée est autorisé en tant que colonne d'index non-clé.</span><span class="sxs-lookup"><span data-stu-id="b21f8-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="b21f8-132">Les colonnes non-clés ne peuvent pas être supprimées d’une table, sauf si l’index de cette table est d’abord supprimé.</span><span class="sxs-lookup"><span data-stu-id="b21f8-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="b21f8-133">Les colonnes non-clés ne peuvent pas être modifiées, sauf pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b21f8-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="b21f8-134">modifier la possibilité de valeur NULL de la colonne de NOT NULL à NULL ;</span><span class="sxs-lookup"><span data-stu-id="b21f8-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="b21f8-135">augmenter la longueur des colonnes `varchar`, `nvarchar` ou `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="b21f8-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b21f8-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b21f8-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b21f8-137">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b21f8-137">Permissions</span></span>  
 <span data-ttu-id="b21f8-138">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="b21f8-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="b21f8-139">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b21f8-140">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b21f8-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="b21f8-141">Pour créer un index avec des colonnes non-clés</span><span class="sxs-lookup"><span data-stu-id="b21f8-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="b21f8-142">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez créer un index avec des colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="b21f8-143">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b21f8-144">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez créer un index avec des colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="b21f8-145">Cliquez avec le bouton droit sur le dossier **Index**, pointez sur **Nouvel index**, puis sélectionnez **Index non cluster...** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="b21f8-146">Dans la boîte de dialogue **Nouvel index** , sur la page **Général** , entrez le nom du nouvel index dans la zone **Nom de l'index** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="b21f8-147">Sous l’onglet **Colonnes clés d’index**, cliquez sur **Ajouter…** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="b21f8-148">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la ou les cases à cocher de la ou des colonnes de table à ajouter à l’index.</span><span class="sxs-lookup"><span data-stu-id="b21f8-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="b21f8-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b21f8-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="b21f8-150">Sous l’onglet **Colonnes incluses**, cliquez sur **Ajouter...** .</span><span class="sxs-lookup"><span data-stu-id="b21f8-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="b21f8-151">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la ou les cases à cocher de la ou des colonnes de table à ajouter à l’index en tant que colonnes non-clés.</span><span class="sxs-lookup"><span data-stu-id="b21f8-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="b21f8-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b21f8-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b21f8-153">Dans la boîte de dialogue **Nouvel index** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b21f8-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b21f8-154">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b21f8-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="b21f8-155">Pour créer un index avec des colonnes non-clés</span><span class="sxs-lookup"><span data-stu-id="b21f8-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="b21f8-156">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b21f8-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b21f8-157">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b21f8-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b21f8-158">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b21f8-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="b21f8-159">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b21f8-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
