---
title: Désactiver des contraintes de validation avec des instructions INSERT et UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605317"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="dfd67-102">Désactiver des contraintes de validation avec des instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="dfd67-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="dfd67-103">Vous pouvez désactiver une contrainte de validation pour des transactions INSERT et UPDATE dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfd67-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dfd67-104">Une fois les contraintes de validation désactivées, les insertions ou les mises à jour ultérieures sur la colonne ne sont pas validées par rapport aux conditions de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="dfd67-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="dfd67-105">Utilisez cette option si vous savez que de nouvelles données violeront la contrainte existante ou si la contrainte s'applique uniquement aux données déjà dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfd67-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="dfd67-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="dfd67-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dfd67-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dfd67-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dfd67-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dfd67-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dfd67-109">**Pour désactiver une contrainte de validation pour les instructions INSERT et UPDATE à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="dfd67-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="dfd67-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfd67-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dfd67-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dfd67-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dfd67-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dfd67-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dfd67-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dfd67-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dfd67-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dfd67-114">Permissions</span></span>  
 <span data-ttu-id="dfd67-115">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="dfd67-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dfd67-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfd67-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="dfd67-117">Pour désactiver une contrainte de validation pour les instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="dfd67-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="dfd67-118">Dans l' **Explorateur d'objets**, développez la table avec la contrainte, puis développez le dossier **Contraintes** .</span><span class="sxs-lookup"><span data-stu-id="dfd67-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="dfd67-119">Cliquez avec le bouton droit sur la contrainte et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="dfd67-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="dfd67-120">Dans la grille sous **Concepteur de tables**, cliquez sur **Appliquer INSERTs et UPDATEs** et sélectionnez **Non** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="dfd67-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="dfd67-121">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="dfd67-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dfd67-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dfd67-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="dfd67-123">Pour désactiver une contrainte de validation pour les instructions INSERT et UPDATE</span><span class="sxs-lookup"><span data-stu-id="dfd67-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="dfd67-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfd67-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dfd67-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="dfd67-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dfd67-126">Copiez et collez les exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="dfd67-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="dfd67-127">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfd67-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
