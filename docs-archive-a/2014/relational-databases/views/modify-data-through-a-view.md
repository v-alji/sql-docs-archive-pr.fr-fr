---
title: Modifier les données par l’intermédiaire d’une vue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600707"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="5e150-102">Modifier les données par l'intermédiaire d'une vue</span><span class="sxs-lookup"><span data-stu-id="5e150-102">Modify Data Through a View</span></span>
  <span data-ttu-id="5e150-103">Vous pouvez modifier les données d'une table de base sous-jacente dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e150-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5e150-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5e150-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e150-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5e150-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e150-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5e150-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5e150-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5e150-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e150-108">**Pour modifier les données de table par le biais d'une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5e150-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="5e150-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e150-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e150-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e150-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e150-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5e150-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5e150-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5e150-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5e150-113">Consultez la section « Vues pouvant être mises à jour » dans [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e150-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e150-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5e150-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e150-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5e150-115">Permissions</span></span>  
 <span data-ttu-id="5e150-116">Nécessite des autorisations UPDATE, INSERT ou DELETE sur la table cible, selon l'action effectuée.</span><span class="sxs-lookup"><span data-stu-id="5e150-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e150-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e150-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="5e150-118">Pour modifier les données de table par le biais d'une vue</span><span class="sxs-lookup"><span data-stu-id="5e150-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="5e150-119">Dans l' **Explorateur d'objets**, développez la base de données qui contient la vue, puis développez **Vues**.</span><span class="sxs-lookup"><span data-stu-id="5e150-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="5e150-120">Cliquez avec le bouton droit sur la vue et sélectionnez **Modifier les 200 lignes du haut**.</span><span class="sxs-lookup"><span data-stu-id="5e150-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="5e150-121">Vous devrez peut-être modifier l'instruction SELECT dans le volet **SQL** pour retourner les lignes à modifier.</span><span class="sxs-lookup"><span data-stu-id="5e150-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="5e150-122">Dans le volet de **résultats** , recherchez la ligne à modifier ou à supprimer.</span><span class="sxs-lookup"><span data-stu-id="5e150-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="5e150-123">Pour supprimer la ligne, cliquez dessus avec le bouton droit et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5e150-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="5e150-124">Pour modifier des données dans une ou plusieurs colonnes, modifiez les données dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="5e150-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5e150-125">Vous ne pouvez pas supprimer une ligne si la vue référence plusieurs table de base.</span><span class="sxs-lookup"><span data-stu-id="5e150-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="5e150-126">Vous pouvez uniquement mettre à jour les colonnes qui appartiennent à une seule table de base.</span><span class="sxs-lookup"><span data-stu-id="5e150-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="5e150-127">Pour insérer une ligne, faites défiler les lignes jusqu'à la fin et insérez les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="5e150-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5e150-128">Vous ne pouvez pas insérer une ligne si la vue référence plusieurs table de base.</span><span class="sxs-lookup"><span data-stu-id="5e150-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e150-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e150-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="5e150-130">Pour mettre à jour les données de table par le biais d'une vue</span><span class="sxs-lookup"><span data-stu-id="5e150-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="5e150-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e150-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e150-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5e150-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e150-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5e150-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5e150-134">Cet exemple remplace la valeur des colonnes `StartDate` et `EndDate` d'un employé spécifique par les colonnes de référence dans la vue `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="5e150-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="5e150-135">Cette vue retourne des valeurs de deux tables.</span><span class="sxs-lookup"><span data-stu-id="5e150-135">This view returns values from two tables.</span></span> <span data-ttu-id="5e150-136">Cette instruction réussit car les colonnes qui sont modifiées proviennent uniquement d'une des tables de base.</span><span class="sxs-lookup"><span data-stu-id="5e150-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="5e150-137">Pour plus d’informations, consultez [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e150-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="5e150-138">Pour insérer des données de table par le biais d'une vue</span><span class="sxs-lookup"><span data-stu-id="5e150-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="5e150-139">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e150-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e150-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5e150-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e150-141">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5e150-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5e150-142">L'exemple insère une nouvelle ligne dans la table de base `HumanResouces.Department` en spécifiant les colonnes appropriées de la vue `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="5e150-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="5e150-143">L'instruction réussit car seules les colonnes d'une même table de base sont spécifiées et les autres colonnes de la table de base utilisent des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="5e150-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="5e150-144">Pour plus d’informations, consultez [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e150-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
