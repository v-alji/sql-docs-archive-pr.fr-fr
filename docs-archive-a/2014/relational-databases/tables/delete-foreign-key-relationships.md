---
title: Supprimer les relations entre les clés étrangères | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605324"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="5824c-102">Supprimer les relations entre les clés étrangères</span><span class="sxs-lookup"><span data-stu-id="5824c-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="5824c-103">Vous pouvez supprimer une contrainte de clé étrangère dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5824c-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5824c-104">La suppression d'une contrainte de clé étrangère supprime l'obligation d'appliquer l'intégrité référentielle.</span><span class="sxs-lookup"><span data-stu-id="5824c-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="5824c-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5824c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5824c-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5824c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5824c-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5824c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5824c-108">**Pour supprimer une contrainte de clé étrangère, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5824c-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="5824c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5824c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5824c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5824c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5824c-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5824c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5824c-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5824c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5824c-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5824c-113">Permissions</span></span>  
 <span data-ttu-id="5824c-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="5824c-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5824c-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5824c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="5824c-116">Pour supprimer une contrainte de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="5824c-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="5824c-117">Dans l' **Explorateur d'objets**, développez la table avec la contrainte, puis développez **Clés**.</span><span class="sxs-lookup"><span data-stu-id="5824c-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="5824c-118">Cliquez avec le bouton droit sur la contrainte, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5824c-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="5824c-119">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5824c-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5824c-120">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5824c-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="5824c-121">Pour supprimer une contrainte de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="5824c-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="5824c-122">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5824c-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5824c-123">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5824c-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5824c-124">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5824c-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="5824c-125">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5824c-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
