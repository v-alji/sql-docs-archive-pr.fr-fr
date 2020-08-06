---
title: Définir les options d’index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707551"
---
# <a name="set-index-options"></a><span data-ttu-id="e5ef4-102">Définir les options d'index</span><span class="sxs-lookup"><span data-stu-id="e5ef4-102">Set Index Options</span></span>
  <span data-ttu-id="e5ef4-103">Cette rubrique explique comment modifier les propriétés d'un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5ef4-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e5ef4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e5ef4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e5ef4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e5ef4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e5ef4-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5ef4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e5ef4-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5ef4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e5ef4-108">**Pour modifier les propriétés d'un index, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e5ef4-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="e5ef4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5ef4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e5ef4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5ef4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5ef4-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e5ef4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e5ef4-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5ef4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e5ef4-113">Les options suivantes sont immédiatement appliquées à l'index à l'aide de la clause SET de l'instruction ALTER INDEX : ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY et STATISTICS_NORECOMPUTE.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="e5ef4-114">Les options suivantes peuvent toutefois être définies lorsque vous reconstruisez un index à l’aide de l’instruction ALTER INDEX REBUILD ou CREATE INDEX WITH DROP_EXISTING : PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP et DROP_EXISTING (CREATE INDEX uniquement).</span><span class="sxs-lookup"><span data-stu-id="e5ef4-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e5ef4-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5ef4-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e5ef4-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e5ef4-116">Permissions</span></span>  
 <span data-ttu-id="e5ef4-117">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e5ef4-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5ef4-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="e5ef4-119">Pour modifier les propriétés d'un index dans le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="e5ef4-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="e5ef4-120">Dans l’Explorateur d’objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez modifier les propriétés d’un index.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="e5ef4-121">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="e5ef4-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e5ef4-122">Cliquez avec le bouton droit sur la table sur laquelle vous voulez modifier les propriétés d’un index et sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="e5ef4-123">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="e5ef4-124">Sélectionnez l'index à modifier.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-124">Select the index that you want to modify.</span></span> <span data-ttu-id="e5ef4-125">Ses propriétés apparaîtront dans la grille principale.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="e5ef4-126">Modifiez les paramètres de l'ensemble de propriétés pour personnaliser l'index.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="e5ef4-127">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="e5ef4-128">Dans le menu **Fichier** , sélectionnez **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="e5ef4-129">Pour modifier les propriétés d'un index dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="e5ef4-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="e5ef4-130">Dans l’Explorateur d’objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez modifier les propriétés d’un index.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="e5ef4-131">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="e5ef4-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e5ef4-132">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez modifier les propriétés d’un index.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="e5ef4-133">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="e5ef4-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e5ef4-134">Cliquez avec le bouton droit sur l’index dont vous voulez modifier les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e5ef4-135">Sous **Sélectionner une page**, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="e5ef4-136">Modifiez les paramètres de l'ensemble de propriétés pour personnaliser l'index.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="e5ef4-137">Pour ajouter, supprimer ou déplacer une colonne d’index, sélectionnez la page **Général** dans la boîte de dialogue **Propriétés de l’index -** _nom_index_.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="e5ef4-138">Pour plus d'informations, consultez [Index Properties F1 Help](index-properties-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="e5ef4-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e5ef4-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5ef4-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="e5ef4-140">Pour afficher les propriétés de tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="e5ef4-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="e5ef4-141">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5ef4-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5ef4-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5ef4-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="e5ef4-144">Pour définir les propriétés d'un index</span><span class="sxs-lookup"><span data-stu-id="e5ef4-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="e5ef4-145">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5ef4-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5ef4-146">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5ef4-147">Copiez et collez les exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="e5ef4-148">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5ef4-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
