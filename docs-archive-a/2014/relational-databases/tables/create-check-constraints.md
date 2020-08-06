---
title: Créer des contraintes de validation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615096"
---
# <a name="create-check-constraints"></a><span data-ttu-id="0bc5c-102">Créer des contraintes de validation</span><span class="sxs-lookup"><span data-stu-id="0bc5c-102">Create Check Constraints</span></span>
  <span data-ttu-id="0bc5c-103">Vous pouvez créer une contrainte de validation dans une table pour spécifier les valeurs de données admises dans une ou plusieurs colonnes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bc5c-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0bc5c-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0bc5c-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0bc5c-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0bc5c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0bc5c-107">**Pour créer une nouvelle contrainte de validation à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="0bc5c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0bc5c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0bc5c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0bc5c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0bc5c-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0bc5c-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0bc5c-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0bc5c-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0bc5c-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0bc5c-112">Permissions</span></span>  
 <span data-ttu-id="0bc5c-113">Requiert des autorisations ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0bc5c-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0bc5c-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="0bc5c-115">Pour créer une nouvelle contrainte de validation</span><span class="sxs-lookup"><span data-stu-id="0bc5c-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="0bc5c-116">Dans **l’Explorateur d’objets**, développez la table à laquelle vous souhaitez ajouter une contrainte de validation, cliquez avec le bouton droit sur **Contraintes** , puis cliquez sur **Nouvelle contrainte**.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="0bc5c-117">Dans la boîte de dialogue **Vérifier les contraintes**, cliquez dans le champ **Expression**, puis sur le bouton de sélection **(...)** .</span><span class="sxs-lookup"><span data-stu-id="0bc5c-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="0bc5c-118">Dans la boîte de dialogue **Expression de contrainte de validation** , tapez l'expression SQL de la contrainte de validation.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="0bc5c-119">Par exemple, pour limiter les entrées dans la colonne `SellEndDate` de la table `Product` à une valeur supérieure ou égale à la date de la colonne `SellStartDate` ou à la valeur NULL, tapez :</span><span class="sxs-lookup"><span data-stu-id="0bc5c-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="0bc5c-120">Ou, pour exiger que les entrées dans la colonne `zip` comportent 5 chiffres, tapez :</span><span class="sxs-lookup"><span data-stu-id="0bc5c-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0bc5c-121">Veillez à placer toutes les valeurs de contrainte non numériques entre des guillemets simples (').</span><span class="sxs-lookup"><span data-stu-id="0bc5c-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="0bc5c-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0bc5c-123">Dans la catégorie **Identity** , vous pouvez modifier le nom de la contrainte de validation et ajouter une description (propriété étendue) pour la contrainte.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="0bc5c-124">Dans la catégorie **Concepteur de tables** , vous pouvez définir le moment où la contrainte est appliquée.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="0bc5c-125">**À :**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-125">**To:**</span></span>|<span data-ttu-id="0bc5c-126">**Sélectionnez Oui dans les champs suivants :**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="0bc5c-127">Tester la contrainte sur les données qui existaient avant d'avoir créé la contrainte</span><span class="sxs-lookup"><span data-stu-id="0bc5c-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="0bc5c-128">**Vérifier les données existantes à la création ou à l'activation**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="0bc5c-129">Appliquer la contrainte lorsqu'une opération de réplication se produit sur cette table</span><span class="sxs-lookup"><span data-stu-id="0bc5c-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="0bc5c-130">**Appliquer la réplication**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="0bc5c-131">Appliquer la contrainte lorsqu'une ligne de cette table est insérée ou mise à jour</span><span class="sxs-lookup"><span data-stu-id="0bc5c-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="0bc5c-132">**Appliquer INSERTs et UPDATEs**</span><span class="sxs-lookup"><span data-stu-id="0bc5c-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="0bc5c-133">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0bc5c-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0bc5c-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="0bc5c-135">Pour créer une nouvelle contrainte de validation</span><span class="sxs-lookup"><span data-stu-id="0bc5c-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="0bc5c-136">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bc5c-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0bc5c-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0bc5c-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0bc5c-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="0bc5c-139">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0bc5c-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
