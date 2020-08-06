---
title: Créer des clés primaires | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615093"
---
# <a name="create-primary-keys"></a><span data-ttu-id="ab04c-102">Créer des clés primaires</span><span class="sxs-lookup"><span data-stu-id="ab04c-102">Create Primary Keys</span></span>
  <span data-ttu-id="ab04c-103">Vous pouvez définir une clé primaire dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab04c-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ab04c-104">La création d'une clé primaire crée automatiquement un correspondant unique, index cluster ou non-cluster.</span><span class="sxs-lookup"><span data-stu-id="ab04c-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="ab04c-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ab04c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab04c-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ab04c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab04c-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ab04c-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ab04c-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab04c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab04c-109">**Pour créer une clé primaire à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ab04c-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="ab04c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab04c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ab04c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab04c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab04c-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ab04c-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ab04c-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ab04c-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ab04c-114">Une table ne peut contenir qu'une seule contrainte PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="ab04c-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="ab04c-115">Toutes les colonnes définies dans une contrainte PRIMARY KEY doivent avoir la valeur NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="ab04c-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="ab04c-116">Si vous ne spécifiez pas la possibilité ou non de valeurs NULL, toutes les colonnes participant à une contrainte PRIMARY KEY sont définies à NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="ab04c-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab04c-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab04c-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab04c-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ab04c-118">Permissions</span></span>  
 <span data-ttu-id="ab04c-119">La création d'une nouvelle table avec une clé primaire nécessite une autorisation CREATE TABLE dans la base de données et une autorisation ALTER pour le schéma dans lequel la table a été créée.</span><span class="sxs-lookup"><span data-stu-id="ab04c-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="ab04c-120">La création d'une clé primaire dans une table existante nécessite l'autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="ab04c-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab04c-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab04c-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="ab04c-122">Pour créer une clé primaire</span><span class="sxs-lookup"><span data-stu-id="ab04c-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="ab04c-123">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table à laquelle vous souhaitez ajouter une contrainte unique, puis cliquez sur **conception**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="ab04c-124">Dans le **Concepteur de tables**, cliquez sur le sélecteur de ligne correspondant à la colonne de base de données que vous voulez définir comme clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ab04c-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="ab04c-125">Si vous voulez sélectionner plusieurs colonnes, appuyez sur la touche CTRL et, tout en la maintenant enfoncée, cliquez sur les sélecteurs de ligne des autres colonnes.</span><span class="sxs-lookup"><span data-stu-id="ab04c-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="ab04c-126">Cliquez avec le bouton droit sur le sélecteur de ligne de la colonne et cliquez sur **Définir la clé primaire**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ab04c-127">Si vous voulez redéfinir la clé primaire, vous devez supprimer toutes les relations avec la clé primaire existante avant de pouvoir créer la nouvelle clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ab04c-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="ab04c-128">Un message vous avertira que les relations existantes seront automatiquement supprimées dans le cadre de ce processus.</span><span class="sxs-lookup"><span data-stu-id="ab04c-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="ab04c-129">Une colonne clé primaire est identifiée par un symbole de clé primaire dans son sélecteur de ligne.</span><span class="sxs-lookup"><span data-stu-id="ab04c-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="ab04c-130">Si une clé primaire comporte plusieurs colonnes, les doublons sont autorisés dans une colonne, mais chaque combinaison de valeurs provenant de toutes les colonnes de la clé primaire doit être unique.</span><span class="sxs-lookup"><span data-stu-id="ab04c-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="ab04c-131">Si vous définissez une clé composée, l'ordre des colonnes dans la clé primaire correspond à l'ordre des colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="ab04c-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="ab04c-132">Vous pouvez cependant modifier l'ordre des colonnes après la création de la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ab04c-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="ab04c-133">Pour plus d’informations, consultez [Modifier des clés primaires](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ab04c-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ab04c-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab04c-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="ab04c-135">Pour créer une clé primaire dans une table existante</span><span class="sxs-lookup"><span data-stu-id="ab04c-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="ab04c-136">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab04c-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab04c-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ab04c-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ab04c-139">L'exemple crée une clé primaire sur la colonne `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="ab04c-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="ab04c-140">Pour créer une clé primaire dans une nouvelle table</span><span class="sxs-lookup"><span data-stu-id="ab04c-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="ab04c-141">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab04c-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab04c-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ab04c-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ab04c-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ab04c-144">L'exemple crée une table et affecte une clé primaire sur la colonne `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="ab04c-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="ab04c-145">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) et [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab04c-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
