---
title: Créer des déclencheurs DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613891"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="d3433-102">Créer des déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="d3433-102">Create DML Triggers</span></span>
  <span data-ttu-id="d3433-103">Cette rubrique explique comment créer un déclencheur DML [!INCLUDE[tsql](../../includes/tsql-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et de l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER.</span><span class="sxs-lookup"><span data-stu-id="d3433-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="d3433-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d3433-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="d3433-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d3433-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d3433-106">Pour obtenir la liste des limitations et des restrictions liées à la création de déclencheurs DML, consultez [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d3433-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d3433-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d3433-107">Permissions</span></span>  
 <span data-ttu-id="d3433-108">Nécessite l'autorisation ALTER sur la table ou la vue sur laquelle le déclencheur est créé.</span><span class="sxs-lookup"><span data-stu-id="d3433-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="d3433-109">Comment créer un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="d3433-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="d3433-110">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d3433-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="d3433-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3433-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="d3433-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d3433-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d3433-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3433-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="d3433-114">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="d3433-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d3433-115">Développez successivement **Bases de données**, la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , **Tables** , puis la table **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="d3433-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="d3433-116">Cliquez avec le bouton droit sur **Déclencheurs**, puis sélectionnez **Nouveau déclencheur**.</span><span class="sxs-lookup"><span data-stu-id="d3433-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="d3433-117">Dans le menu **Requête** , cliquez sur **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="d3433-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="d3433-118">Vous pouvez aussi appuyer sur Ctrl-Maj-M pour ouvrir la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** .</span><span class="sxs-lookup"><span data-stu-id="d3433-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="d3433-119">Dans la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** , entrez les valeurs suivantes pour les paramètres affichés.</span><span class="sxs-lookup"><span data-stu-id="d3433-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="d3433-120">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d3433-120">Parameter</span></span>|<span data-ttu-id="d3433-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="d3433-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="d3433-122">Auteur</span><span class="sxs-lookup"><span data-stu-id="d3433-122">Author</span></span>|<span data-ttu-id="d3433-123">*Votre nom*</span><span class="sxs-lookup"><span data-stu-id="d3433-123">*Your name*</span></span>|  
    |<span data-ttu-id="d3433-124">Date de création</span><span class="sxs-lookup"><span data-stu-id="d3433-124">Create Date</span></span>|<span data-ttu-id="d3433-125">*Date du jour*</span><span class="sxs-lookup"><span data-stu-id="d3433-125">*Today's date*</span></span>|  
    |<span data-ttu-id="d3433-126">Description</span><span class="sxs-lookup"><span data-stu-id="d3433-126">Description</span></span>|<span data-ttu-id="d3433-127">Vérifie le degré de solvabilité du fournisseur avant d'autoriser l'insertion d'une nouvelle commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d3433-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="d3433-128">Schema_name</span><span class="sxs-lookup"><span data-stu-id="d3433-128">Schema_Name</span></span>|<span data-ttu-id="d3433-129">Achat</span><span class="sxs-lookup"><span data-stu-id="d3433-129">Purchasing</span></span>|  
    |<span data-ttu-id="d3433-130">Trigger_Name</span><span class="sxs-lookup"><span data-stu-id="d3433-130">Trigger_Name</span></span>|<span data-ttu-id="d3433-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="d3433-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="d3433-132">Table_Name</span><span class="sxs-lookup"><span data-stu-id="d3433-132">Table_Name</span></span>|<span data-ttu-id="d3433-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="d3433-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="d3433-134">Data_Modification_Statement</span><span class="sxs-lookup"><span data-stu-id="d3433-134">Data_Modification_Statement</span></span>|<span data-ttu-id="d3433-135">Supprimez UPDATE et DELETE de la liste.</span><span class="sxs-lookup"><span data-stu-id="d3433-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="d3433-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3433-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d3433-137">Dans l’ **Éditeur de requête**, remplacez le commentaire `-- Insert statements for trigger here` par l’instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="d3433-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
  
8.  <span data-ttu-id="d3433-138">Pour vérifier la validité de la syntaxe, dans le menu **Requête** , cliquez sur **Analyser**.</span><span class="sxs-lookup"><span data-stu-id="d3433-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="d3433-139">Si un message d'erreur est retourné, comparez l'instruction avec les informations ci-dessus, apportez les corrections nécessaires et répétez cette étape.</span><span class="sxs-lookup"><span data-stu-id="d3433-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="d3433-140">Pour créer le déclencheur DML, dans le menu **Requête** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d3433-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="d3433-141">Le déclencheur DML est créé en tant qu'objet dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3433-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="d3433-142">Pour afficher le déclencheur DML dans l’Explorateur d’objets, cliquez avec le bouton droit sur **Déclencheurs** , puis sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="d3433-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="d3433-143">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d3433-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d3433-144">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d3433-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="d3433-145">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="d3433-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d3433-146">Dans le menu **Fichier** , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d3433-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d3433-147">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d3433-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d3433-148">Cet exemple crée le même déclencheur DML stocké que dans la procédure ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d3433-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
    -- Trigger valid for multirow and single row inserts  
    -- and optimal for single row inserts.  
    USE AdventureWorks2012;  
    GO  
    CREATE TRIGGER NewPODetail3  
    ON Purchasing.PurchaseOrderDetail  
    FOR INSERT AS  
    IF @@ROWCOUNT = 1  
    BEGIN  
       UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal + LineTotal  
       FROM inserted  
       WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
  
    END  
    ELSE  
    BEGIN  
          UPDATE Purchasing.PurchaseOrderHeader  
       SET SubTotal = SubTotal +   
          (SELECT SUM(LineTotal)  
          FROM inserted  
          WHERE PurchaseOrderHeader.PurchaseOrderID  
           = inserted.PurchaseOrderID)  
       WHERE PurchaseOrderHeader.PurchaseOrderID IN  
          (SELECT PurchaseOrderID FROM inserted)  
    END;  
    ```  
