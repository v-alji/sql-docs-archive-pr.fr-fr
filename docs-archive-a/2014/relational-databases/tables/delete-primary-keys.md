---
title: Supprimer des clés primaires | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615084"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="06b56-102">Supprimer des clés primaires</span><span class="sxs-lookup"><span data-stu-id="06b56-102">Delete Primary Keys</span></span>
  <span data-ttu-id="06b56-103">Vous pouvez supprimer une clé primaire dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b56-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="06b56-104">Lorsque la clé primaire est supprimée, l'index correspondant l'est également.</span><span class="sxs-lookup"><span data-stu-id="06b56-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="06b56-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="06b56-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="06b56-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="06b56-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="06b56-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="06b56-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="06b56-108">**Pour supprimer une clé primaire à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="06b56-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="06b56-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b56-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="06b56-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b56-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="06b56-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="06b56-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="06b56-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="06b56-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06b56-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="06b56-113">Permissions</span></span>  
 <span data-ttu-id="06b56-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="06b56-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="06b56-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b56-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="06b56-116">Pour supprimer une contrainte de clé primaire à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="06b56-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="06b56-117">Dans l'Explorateur d'objets, développez la table qui contient la clé primaire, puis développez **Clés**.</span><span class="sxs-lookup"><span data-stu-id="06b56-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="06b56-118">Cliquez avec le bouton droit sur la clé, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="06b56-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="06b56-119">Dans la boîte de dialogue **Supprimer un objet** , vérifiez que la clé correcte est spécifiée et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="06b56-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="06b56-120">Pour supprimer une contrainte de clé primaire à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="06b56-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="06b56-121">Dans l’Explorateur d'objets, cliquez avec le bouton droit sur la table avec la clé primaire, puis cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="06b56-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="06b56-122">Dans la grille de la table, cliquez avec le bouton droit sur la ligne contenant la clé primaire et choisissez **Supprimer la clé primaire** pour désactiver le paramètre.</span><span class="sxs-lookup"><span data-stu-id="06b56-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="06b56-123">Pour annuler cette action, fermez la table sans enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="06b56-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="06b56-124">La suppression d'une clé primaire ne peut pas être annulée sans perdre toutes les autres modifications apportées à la table.</span><span class="sxs-lookup"><span data-stu-id="06b56-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="06b56-125">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="06b56-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="06b56-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b56-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="06b56-127">Pour supprimer une contrainte de clé primaire</span><span class="sxs-lookup"><span data-stu-id="06b56-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="06b56-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b56-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b56-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="06b56-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b56-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="06b56-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="06b56-131">L'exemple identifie d'abord le nom de la contrainte de clé primaire et supprime ensuite la contrainte.</span><span class="sxs-lookup"><span data-stu-id="06b56-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="06b56-132">Pour plus d’informations, consultez [ALTER TABLE& #40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) et [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="06b56-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
