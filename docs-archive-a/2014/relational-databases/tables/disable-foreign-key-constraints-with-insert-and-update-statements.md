---
title: Désactiver les contraintes de clé étrangère avec des instructions INSERT et UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604411"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="98d7a-102">Désactiver les contraintes de clé étrangère avec des instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="98d7a-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="98d7a-103">Vous pouvez désactiver une contrainte de clé étrangère pendant les transactions INSERT et UPDATE dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d7a-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="98d7a-104">Utilisez cette option si vous savez que de nouvelles données violeront la contrainte existante ou si la contrainte s'applique uniquement aux données déjà dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="98d7a-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="98d7a-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="98d7a-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98d7a-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="98d7a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98d7a-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="98d7a-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="98d7a-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="98d7a-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98d7a-109">**Pour désactiver une contrainte de clé étrangère pour les instructions INSERT et UPDATE, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="98d7a-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="98d7a-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98d7a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98d7a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98d7a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98d7a-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="98d7a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="98d7a-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="98d7a-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="98d7a-114">Une fois ces contraintes désactivées, les insertions ou les mises à jour ultérieures sur la colonne ne sont pas validées par rapport aux conditions de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="98d7a-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98d7a-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="98d7a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98d7a-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="98d7a-116">Permissions</span></span>  
 <span data-ttu-id="98d7a-117">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="98d7a-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98d7a-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98d7a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="98d7a-119">Pour désactiver une contrainte de clé étrangère avec les instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="98d7a-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="98d7a-120">Dans l' **Explorateur d'objets**, développez la table avec la contrainte, puis développez le dossier **Clés** .</span><span class="sxs-lookup"><span data-stu-id="98d7a-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="98d7a-121">Cliquez avec le bouton droit sur la contrainte et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="98d7a-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="98d7a-122">Dans la grille sous **Concepteur de tables**, cliquez sur **Appliquer la contrainte de clé étrangère** et sélectionnez **Non** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="98d7a-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="98d7a-123">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="98d7a-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98d7a-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98d7a-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="98d7a-125">Pour désactiver une contrainte de clé étrangère avec les instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="98d7a-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="98d7a-126">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d7a-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98d7a-127">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="98d7a-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98d7a-128">Copiez et collez les exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="98d7a-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="98d7a-129">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98d7a-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
