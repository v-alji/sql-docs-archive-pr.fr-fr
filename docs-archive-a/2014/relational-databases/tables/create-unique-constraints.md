---
title: Créer des contraintes uniques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- UNIQUE constraints [SQL Server], creating
- constraints [SQL Server], creating
- constraints [SQL Server], unique
ms.assetid: a86f9d6f-f242-43be-b65d-b3435b71b62a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 252de63f965f98734a6d62d94bfff9dc5774cab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706355"
---
# <a name="create-unique-constraints"></a><span data-ttu-id="4260d-102">Créer des contraintes uniques</span><span class="sxs-lookup"><span data-stu-id="4260d-102">Create Unique Constraints</span></span>
  <span data-ttu-id="4260d-103">Vous pouvez créer une contrainte unique dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)] pour interdire l'entrée de doublons dans des colonnes spécifiques qui ne participent pas à une clé primaire.</span><span class="sxs-lookup"><span data-stu-id="4260d-103">You can create a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to ensure no duplicate values are entered in specific columns that do not participate in a primary key.</span></span> <span data-ttu-id="4260d-104">La création d'une contrainte unique crée automatiquement un index unique correspondant.</span><span class="sxs-lookup"><span data-stu-id="4260d-104">Creating a unique constraint automatically creates a corresponding unique index.</span></span>  
  
 <span data-ttu-id="4260d-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4260d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4260d-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4260d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4260d-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4260d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4260d-108">**Pour créer une contrainte unique à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="4260d-108">**To create a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="4260d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4260d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4260d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4260d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4260d-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4260d-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4260d-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4260d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4260d-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4260d-113">Permissions</span></span>  
 <span data-ttu-id="4260d-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="4260d-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4260d-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4260d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="4260d-116">Pour créer une contrainte unique</span><span class="sxs-lookup"><span data-stu-id="4260d-116">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="4260d-117">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table à laquelle vous souhaitez ajouter une contrainte unique et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="4260d-117">In **Object Explorer**, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="4260d-118">Dans le menu **Concepteur de tables** , cliquez sur **index/clés**.</span><span class="sxs-lookup"><span data-stu-id="4260d-118">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="4260d-119">Dans la boîte de dialogue **Index/Clés** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4260d-119">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="4260d-120">Dans la grille sous **Général**, cliquez sur **Type** et choisissez **Clé unique** dans la zone de liste déroulante située à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="4260d-120">In the grid under **General**, click **Type** and choose **Unique Key** from the drop-down list box to the right of the property.</span></span>  
  
5.  <span data-ttu-id="4260d-121">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="4260d-121">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4260d-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4260d-122">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="4260d-123">Pour créer une contrainte unique</span><span class="sxs-lookup"><span data-stu-id="4260d-123">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="4260d-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4260d-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4260d-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4260d-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4260d-126">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4260d-126">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4260d-127">L'exemple crée la table `TransactionHistoryArchive4` et une contrainte unique sur la colonne `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="4260d-127">The example creates the table `TransactionHistoryArchive4` and creates a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive4  
     (  
       TransactionID int NOT NULL,   
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)   
    );   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-on-an-existing-table"></a><span data-ttu-id="4260d-128">Pour créer une contrainte unique sur une table existante</span><span class="sxs-lookup"><span data-stu-id="4260d-128">To create a unique constraint on an existing table</span></span>  
  
1.  <span data-ttu-id="4260d-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4260d-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4260d-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4260d-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4260d-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4260d-131">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4260d-132">L'exemple crée une contrainte unique sur les colonnes `PasswordHash` et `PasswordSalt` dans la table `Person.Password`.</span><span class="sxs-lookup"><span data-stu-id="4260d-132">The example creates a unique constraint on the columns `PasswordHash` and `PasswordSalt` in the table `Person.Password`.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    ALTER TABLE Person.Password   
    ADD CONSTRAINT AK_Password UNIQUE (PasswordHash, PasswordSalt);   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-in-an-new-table"></a><span data-ttu-id="4260d-133">Pour créer une contrainte unique sur une nouvelle table</span><span class="sxs-lookup"><span data-stu-id="4260d-133">To create a unique constraint in an new table</span></span>  
  
1.  <span data-ttu-id="4260d-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4260d-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4260d-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4260d-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4260d-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4260d-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4260d-137">L'exemple crée une table et définit une contrainte unique sur la colonne `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="4260d-137">The example creates a table and defines a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive2  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="4260d-138">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) et [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4260d-138">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
