---
title: Supprimer des contraintes de validation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605326"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="5b1ca-102">Supprimer des contraintes de validation</span><span class="sxs-lookup"><span data-stu-id="5b1ca-102">Delete Check Constraints</span></span>
  <span data-ttu-id="5b1ca-103">Vous pouvez supprimer une contrainte de validation dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b1ca-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b1ca-104">En supprimant des contraintes de validation, vous supprimez les restrictions sur les valeurs de données acceptées dans la ou les colonnes incluses dans l'expression de contrainte.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="5b1ca-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5b1ca-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b1ca-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5b1ca-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b1ca-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5b1ca-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b1ca-108">**Pour supprimer une contrainte de validation à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="5b1ca-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="5b1ca-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b1ca-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b1ca-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b1ca-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b1ca-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5b1ca-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b1ca-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5b1ca-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b1ca-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5b1ca-113">Permissions</span></span>  
 <span data-ttu-id="5b1ca-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b1ca-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b1ca-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="5b1ca-116">Pour supprimer une contrainte de validation</span><span class="sxs-lookup"><span data-stu-id="5b1ca-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="5b1ca-117">Dans l' **Explorateur d'objets**, développez la table avec la contrainte de validation.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="5b1ca-118">Développez  **Contraintes**.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="5b1ca-119">Cliquez sur la contrainte avec le bouton droit, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="5b1ca-120">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b1ca-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b1ca-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="5b1ca-122">Pour supprimer une contrainte de validation</span><span class="sxs-lookup"><span data-stu-id="5b1ca-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="5b1ca-123">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b1ca-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b1ca-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b1ca-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5b1ca-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="5b1ca-126">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b1ca-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
