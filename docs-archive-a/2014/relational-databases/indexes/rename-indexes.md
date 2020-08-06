---
title: Renommer des index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614043"
---
# <a name="rename-indexes"></a><span data-ttu-id="de005-102">Renommer des index</span><span class="sxs-lookup"><span data-stu-id="de005-102">Rename Indexes</span></span>
  <span data-ttu-id="de005-103">Cette rubrique explique comment renommer un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de005-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="de005-104">Le changement du nom d'un index remplace le nom actuel de l'index par le nouveau nom fourni.</span><span class="sxs-lookup"><span data-stu-id="de005-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="de005-105">Le nom spécifié doit être unique dans la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="de005-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="de005-106">Par exemple, deux tables peuvent contenir un index nommé **XPK_1**, mais la même table ne peut pas avoir deux index nommés **XPK_1**.</span><span class="sxs-lookup"><span data-stu-id="de005-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="de005-107">Vous ne pouvez pas créer un index dont le nom est le même qu'un index désactivé existant.</span><span class="sxs-lookup"><span data-stu-id="de005-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="de005-108">Le changement du nom d'un index ne provoque pas sa reconstruction.</span><span class="sxs-lookup"><span data-stu-id="de005-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="de005-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="de005-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de005-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="de005-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de005-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="de005-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de005-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="de005-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="de005-113">**Pour renommer un index, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="de005-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="de005-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de005-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="de005-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de005-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de005-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="de005-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de005-117">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="de005-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="de005-118">Quand vous créez une contrainte PRIMARY KEY ou UNIQUE sur une table, un index du même nom que la contrainte est automatiquement créé pour la table.</span><span class="sxs-lookup"><span data-stu-id="de005-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="de005-119">Comme les noms d'index doivent être uniques dans la table, vous ne pouvez pas créer ou renommer un index pour qu'il porte le même nom qu'une contrainte PRIMARY KEY ou UNIQUE sur la table.</span><span class="sxs-lookup"><span data-stu-id="de005-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de005-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="de005-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de005-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="de005-121">Permissions</span></span>  
 <span data-ttu-id="de005-122">Requiert une autorisation ALTER sur l'index.</span><span class="sxs-lookup"><span data-stu-id="de005-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de005-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de005-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="de005-124">Pour renommer un index à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="de005-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="de005-125">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez renommer un index.</span><span class="sxs-lookup"><span data-stu-id="de005-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="de005-126">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="de005-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="de005-127">Cliquez avec le bouton droit sur la table sur laquelle vous souhaitez renommer un index et sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="de005-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="de005-128">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="de005-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="de005-129">Sélectionnez l’index à renommer dans la zone de texte **Clé ou index Primary/Unique sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="de005-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="de005-130">Dans la grille, cliquez sur **Nom** et tapez un nouveau nom dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="de005-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="de005-131">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="de005-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="de005-132">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="de005-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="de005-133">Pour renommer un index à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="de005-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="de005-134">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez renommer un index.</span><span class="sxs-lookup"><span data-stu-id="de005-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="de005-135">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="de005-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="de005-136">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez renommer un index.</span><span class="sxs-lookup"><span data-stu-id="de005-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="de005-137">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="de005-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="de005-138">Cliquez avec le bouton droit sur l’index que vous souhaitez renommer et sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="de005-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="de005-139">Tapez le nouveau nom de l’index et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="de005-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="de005-140">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de005-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="de005-141">Pour renommer un index</span><span class="sxs-lookup"><span data-stu-id="de005-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="de005-142">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de005-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de005-143">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="de005-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de005-144">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="de005-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="de005-145">Pour plus d’informations, consultez [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="de005-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
