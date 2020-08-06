---
title: Supprimer un index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708292"
---
# <a name="delete-an-index"></a><span data-ttu-id="2687d-102">Supprimer un index</span><span class="sxs-lookup"><span data-stu-id="2687d-102">Delete an Index</span></span>
  <span data-ttu-id="2687d-103">Cette rubrique explique comment supprimer un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2687d-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2687d-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2687d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2687d-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2687d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2687d-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2687d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2687d-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2687d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2687d-108">**Pour supprimer un index, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2687d-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="2687d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2687d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2687d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2687d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2687d-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2687d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2687d-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2687d-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2687d-113">Les index résultant d'une contrainte PRIMARY KEY ou UNIQUE ne peuvent pas être supprimés au moyen de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="2687d-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="2687d-114">Dans ce cas, c'est la contrainte qui doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="2687d-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="2687d-115">Pour supprimer la contrainte et l'index correspondant, utilisez [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) avec la clause DROP CONSTRAINT dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2687d-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2687d-116">Pour plus d’informations, consultez [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="2687d-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2687d-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2687d-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2687d-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2687d-118">Permissions</span></span>  
 <span data-ttu-id="2687d-119">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="2687d-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="2687d-120">L’autorisation est accordée par défaut au rôle serveur fixe **sysadmin** et aux rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="2687d-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2687d-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2687d-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="2687d-122">Pour supprimer un index à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="2687d-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="2687d-123">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez supprimer un index.</span><span class="sxs-lookup"><span data-stu-id="2687d-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="2687d-124">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="2687d-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2687d-125">Développez la table contenant l'index à supprimer.</span><span class="sxs-lookup"><span data-stu-id="2687d-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="2687d-126">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="2687d-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="2687d-127">Cliquez avec le bouton droit sur l’index à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2687d-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="2687d-128">Dans la boîte de dialogue **Supprimer un objet** , vérifiez que l'index correct figure dans la grille **Objet à supprimer** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2687d-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="2687d-129">Pour supprimer un index à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="2687d-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="2687d-130">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez supprimer un index.</span><span class="sxs-lookup"><span data-stu-id="2687d-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="2687d-131">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="2687d-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2687d-132">Cliquez avec le bouton droit sur la table contenant l'index que vous souhaitez supprimer et cliquez sur Conception.</span><span class="sxs-lookup"><span data-stu-id="2687d-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="2687d-133">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="2687d-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="2687d-134">Dans la boîte de dialogue **Index/Clés** , sélectionnez l’index que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="2687d-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="2687d-135">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2687d-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="2687d-136">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="2687d-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="2687d-137">Dans le menu **Fichier** , sélectionnez **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="2687d-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2687d-138">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2687d-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="2687d-139">Pour supprimer un index</span><span class="sxs-lookup"><span data-stu-id="2687d-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="2687d-140">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2687d-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2687d-141">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2687d-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2687d-142">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2687d-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="2687d-143">Pour plus d’informations, consultez [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2687d-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
