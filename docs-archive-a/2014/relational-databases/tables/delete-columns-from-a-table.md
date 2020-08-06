---
title: Supprimer des colonnes d’une table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610987"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="e5452-102">Supprimer des colonnes d'une table</span><span class="sxs-lookup"><span data-stu-id="e5452-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="e5452-103">Cette rubrique explique comment supprimer des colonnes de table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5452-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e5452-104">Lorsque vous supprimez une colonne d'une table, toutes les données qu'elle contient sont supprimées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5452-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="e5452-105">Il est impossible d’annuler cette opération.</span><span class="sxs-lookup"><span data-stu-id="e5452-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="e5452-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e5452-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e5452-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e5452-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e5452-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5452-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e5452-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5452-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e5452-110">**Pour supprimer une colonne d'une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="e5452-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="e5452-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5452-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e5452-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5452-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5452-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e5452-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e5452-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e5452-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e5452-115">Vous ne pouvez pas supprimer une colonne qui a une contrainte CHECK.</span><span class="sxs-lookup"><span data-stu-id="e5452-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="e5452-116">Vous devez d'abord supprimer la contrainte.</span><span class="sxs-lookup"><span data-stu-id="e5452-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="e5452-117">Vous ne pouvez pas supprimer une colonne qui a des contraintes PRIMARY KEY ou FOREIGN KEY ou d'autres dépendances, sauf en utilisant le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="e5452-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="e5452-118">Si vous utilisez l'Explorateur d'objets ou [!INCLUDE[tsql](../../includes/tsql-md.md)], vous devez d'abord supprimer toutes les dépendances à la colonne.</span><span class="sxs-lookup"><span data-stu-id="e5452-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e5452-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e5452-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e5452-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e5452-120">Permissions</span></span>  
 <span data-ttu-id="e5452-121">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="e5452-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e5452-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5452-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="e5452-123">Pour supprimer des colonnes à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="e5452-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="e5452-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5452-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5452-125">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table dans laquelle vous souhaitez supprimer des colonnes et choisissez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e5452-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="e5452-126">Dans la boîte de dialogue **Supprimer un objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5452-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="e5452-127">Si la colonne contient des contraintes ou d'autres dépendances, un message d'erreur s'affichera dans la boîte de dialogue **Supprimer un objet** .</span><span class="sxs-lookup"><span data-stu-id="e5452-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="e5452-128">Résolvez l'erreur en supprimant les contraintes référencées.</span><span class="sxs-lookup"><span data-stu-id="e5452-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="e5452-129">Pour supprimer des colonnes à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="e5452-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="e5452-130">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table dans laquelle vous souhaitez supprimer des colonnes et choisissez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="e5452-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="e5452-131">Cliquez avec le bouton droit sur la colonne à supprimer et, dans le menu contextuel, cliquez sur **Supprimer une colonne** .</span><span class="sxs-lookup"><span data-stu-id="e5452-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="e5452-132">Si les colonnes à supprimer participent à une relation (FOREIGN KEY ou PRIMARY KEY), un message vous demande confirmation avant la suppression des colonnes sélectionnées et de leurs relations.</span><span class="sxs-lookup"><span data-stu-id="e5452-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="e5452-133">Choisissez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e5452-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e5452-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5452-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="e5452-135">Pour supprimer des colonnes</span><span class="sxs-lookup"><span data-stu-id="e5452-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="e5452-136">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5452-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5452-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e5452-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5452-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e5452-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="e5452-139">Si la colonne contient des contraintes ou d'autres dépendances, un message d'erreur est retourné.</span><span class="sxs-lookup"><span data-stu-id="e5452-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="e5452-140">Résolvez l'erreur en supprimant les contraintes référencées.</span><span class="sxs-lookup"><span data-stu-id="e5452-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="e5452-141">Pour obtenir des exemples supplémentaires, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5452-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
