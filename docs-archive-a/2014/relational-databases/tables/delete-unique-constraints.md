---
title: Supprimer des contraintes uniques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611655"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="6d7ce-102">Supprimer des contraintes UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6d7ce-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="6d7ce-103">Vous pouvez supprimer une contrainte unique dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d7ce-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6d7ce-104">En supprimant une contrainte unique, vous supprimez la condition d'unicité requise pour les valeurs entrées dans la colonne ou la combinaison de colonnes incluses à l'intérieur de l'expression de contrainte et vous supprimez l'index unique correspondant.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="6d7ce-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6d7ce-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6d7ce-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6d7ce-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6d7ce-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6d7ce-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6d7ce-108">**Pour supprimer une contrainte unique à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="6d7ce-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="6d7ce-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d7ce-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6d7ce-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d7ce-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6d7ce-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6d7ce-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6d7ce-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6d7ce-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6d7ce-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6d7ce-113">Permissions</span></span>  
 <span data-ttu-id="6d7ce-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6d7ce-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d7ce-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="6d7ce-116">Pour supprimer une contrainte unique à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="6d7ce-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="6d7ce-117">Dans l'Explorateur d'objets, développez la table qui contient la contrainte unique puis développez **Contraintes**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="6d7ce-118">Cliquez avec le bouton droit sur la clé, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="6d7ce-119">Dans la boîte de dialogue **Supprimer un objet** , vérifiez que la clé correcte est spécifiée et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="6d7ce-120">Pour supprimer une contrainte unique à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="6d7ce-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="6d7ce-121">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table avec la contrainte unique, puis cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="6d7ce-122">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="6d7ce-123">Dans la boîte de dialogue **Index/Clés** , sélectionnez la clé unique dans la liste **Index ou clé unique/primaire sélectionné(e)** .</span><span class="sxs-lookup"><span data-stu-id="6d7ce-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="6d7ce-124">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="6d7ce-125">Dans le menu **Fichier**, cliquez sur **Enregistrer** _nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6d7ce-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d7ce-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="6d7ce-127">Pour supprimer une contrainte unique</span><span class="sxs-lookup"><span data-stu-id="6d7ce-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="6d7ce-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d7ce-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d7ce-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6d7ce-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6d7ce-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="6d7ce-131">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) et [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6d7ce-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
