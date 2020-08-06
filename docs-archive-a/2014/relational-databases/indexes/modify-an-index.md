---
title: Modifier un index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707555"
---
# <a name="modify-an-index"></a><span data-ttu-id="a6ad7-102">Modifier un index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-102">Modify an Index</span></span>
  <span data-ttu-id="a6ad7-103">Cette rubrique explique comment modifier un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ad7-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6ad7-104">Les index résultant d'une contrainte PRIMARY KEY ou UNIQUE ne peuvent pas être modifiés au moyen de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="a6ad7-105">Dans ce cas, c'est la contrainte qui doit être modifiée.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="a6ad7-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a6ad7-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a6ad7-107">**Pour modifier un index à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="a6ad7-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="a6ad7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6ad7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a6ad7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6ad7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a6ad7-110">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6ad7-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="a6ad7-111">Pour modifier un index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="a6ad7-112">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a6ad7-113">Développez **Bases de données**, développez la base de données à laquelle appartient la table, puis cliquez sur **Tables**.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="a6ad7-114">Développez la table à laquelle l'index appartient, puis développez **Index**.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="a6ad7-115">Cliquez avec le bouton droit sur l’index à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a6ad7-116">Dans la boîte de dialogue **Propriétés de l'index** , apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="a6ad7-117">Par exemple, vous pouvez ajouter ou supprimer une colonne de la clé d'index, ou modifier le paramètre d'une option d'index.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="a6ad7-118">Pour modifier des colonnes d'index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="a6ad7-119">Pour ajouter, supprimer ou déplacer une colonne d'index, cliquez sur la page **Général** dans la boîte de dialogue **Propriétés de l'index** .</span><span class="sxs-lookup"><span data-stu-id="a6ad7-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a6ad7-120">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6ad7-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="a6ad7-121">Pour modifier un index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="a6ad7-122">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ad7-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6ad7-123">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a6ad7-124">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a6ad7-125">Cet exemple supprime et recrée un index existant sur la colonne `ProductID` de la table `Production.WorkOrder` avec l'option `DROP_EXISTING` .</span><span class="sxs-lookup"><span data-stu-id="a6ad7-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="a6ad7-126">Les options `FILLFACTOR` et `PAD_INDEX` sont également définies.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="a6ad7-127">L'exemple suivant utilise ALTER INDEX pour définir plusieurs options de l'index `AK_SalesOrderHeader_SalesOrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="a6ad7-128">Pour modifier des colonnes d'index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="a6ad7-129">Pour ajouter, supprimer, ou modifier la position d'une colonne d'index, vous devez supprimer et recréer l'index.</span><span class="sxs-lookup"><span data-stu-id="a6ad7-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ad7-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6ad7-130">See Also</span></span>  
 <span data-ttu-id="a6ad7-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="a6ad7-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="a6ad7-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="a6ad7-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="a6ad7-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="a6ad7-136">[Définir les options d'index](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="a6ad7-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="a6ad7-137">Renommer des index</span><span class="sxs-lookup"><span data-stu-id="a6ad7-137">Rename Indexes</span></span>](indexes.md)  
  
  
