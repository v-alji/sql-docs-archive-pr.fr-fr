---
title: Supprimer des tables (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706348"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="489e6-102">Supprimer des tables (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="489e6-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="489e6-103">Vous pouvez supprimer une table de votre base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="489e6-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="489e6-104">Ne supprimez une table qu'après mûre réflexion.</span><span class="sxs-lookup"><span data-stu-id="489e6-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="489e6-105">En effet, s'il existe des requêtes, des vues, des fonctions définies par l'utilisateur, des procédures stockées ou des programmes qui font référence à cette table, la suppression rend tous ces objets non valides.</span><span class="sxs-lookup"><span data-stu-id="489e6-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="489e6-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="489e6-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="489e6-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="489e6-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="489e6-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="489e6-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="489e6-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="489e6-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="489e6-110">**Pour supprimer une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="489e6-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="489e6-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="489e6-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="489e6-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="489e6-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="489e6-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="489e6-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="489e6-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="489e6-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="489e6-115">Vous ne pouvez pas supprimer une table qui est référencée par une contrainte FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="489e6-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="489e6-116">Vous devez au préalable supprimer la contrainte FOREIGN KEY ou la table qui la référence.</span><span class="sxs-lookup"><span data-stu-id="489e6-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="489e6-117">Si la table de référence et la table qui contient la clé primaire sont supprimées dans la même instruction DROP TABLE, la table de référence doit figurer en premier dans la liste.</span><span class="sxs-lookup"><span data-stu-id="489e6-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="489e6-118">Lorsqu'une table est supprimée, les règles et les valeurs par défaut liées à celle-ci sont dissociées et toutes les contraintes et les déclencheurs qui lui sont associés sont automatiquement supprimés.</span><span class="sxs-lookup"><span data-stu-id="489e6-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="489e6-119">Si vous recréez la table, vous devez réassocier les règles et valeurs par défaut appropriées, recréer les déclencheurs et ajouter les toutes les contraintes nécessaires.</span><span class="sxs-lookup"><span data-stu-id="489e6-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="489e6-120">Si vous supprimez une table qui contient une colonne `varbinary (max)` avec l'attribut FILESTREAM, toutes les données stockées dans le système de fichiers ne seront pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="489e6-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="489e6-121">DROP TABLE et CREATE TABLE ne doivent pas être exécutés sur la même table dans le même lot.</span><span class="sxs-lookup"><span data-stu-id="489e6-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="489e6-122">Sinon, une erreur inattendue risque de se produire.</span><span class="sxs-lookup"><span data-stu-id="489e6-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="489e6-123">Toute vue ou procédure stockée faisant référence à la table supprimée doit être supprimée ou modifiée explicitement pour supprimer la référence à la table.</span><span class="sxs-lookup"><span data-stu-id="489e6-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="489e6-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="489e6-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="489e6-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="489e6-125">Permissions</span></span>  
 <span data-ttu-id="489e6-126">Nécessite l’autorisation ALTER sur le schéma auquel appartient la table, l’autorisation CONTROL sur la table ou l’appartenance au rôle de base de données fixe **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="489e6-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="489e6-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="489e6-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="489e6-128">Pour supprimer une table de la base de données</span><span class="sxs-lookup"><span data-stu-id="489e6-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="489e6-129">Dans l'Explorateur d'objets, sélectionnez la table à supprimer.</span><span class="sxs-lookup"><span data-stu-id="489e6-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="489e6-130">Cliquez avec le bouton droit sur la table puis, dans le menu contextuel, cliquez sur **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="489e6-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="489e6-131">Un message vous demande de confirmer la suppression.</span><span class="sxs-lookup"><span data-stu-id="489e6-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="489e6-132">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="489e6-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="489e6-133">La suppression d'une table entraîne automatiquement celle de toutes les relations qu'elle entretient.</span><span class="sxs-lookup"><span data-stu-id="489e6-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="489e6-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="489e6-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="489e6-135">Pour supprimer une table dans l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="489e6-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="489e6-136">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="489e6-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="489e6-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="489e6-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="489e6-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="489e6-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="489e6-139">Pour plus d’informations, consultez [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="489e6-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
