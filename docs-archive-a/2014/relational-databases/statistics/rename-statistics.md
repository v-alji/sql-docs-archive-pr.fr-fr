---
title: Renommer des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613367"
---
# <a name="rename-statistics"></a><span data-ttu-id="b4566-102">Renommer des statistiques</span><span class="sxs-lookup"><span data-stu-id="b4566-102">Rename Statistics</span></span>
  <span data-ttu-id="b4566-103">Vous pouvez renommer un objet de statistiques dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4566-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="b4566-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b4566-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b4566-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b4566-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b4566-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b4566-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b4566-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b4566-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b4566-108">**Pour renommer un objet de statistiques, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b4566-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="b4566-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4566-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b4566-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b4566-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b4566-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b4566-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b4566-112">Par défaut, la création d'un index crée une statistique sur les colonnes clés de cet index.</span><span class="sxs-lookup"><span data-stu-id="b4566-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="b4566-113">Par conséquent, renommer l'index renomme automatiquement l'objet de statistiques, et inversement.</span><span class="sxs-lookup"><span data-stu-id="b4566-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="b4566-114">La modification d'une partie du nom de l'objet peut provoquer des problèmes dans des scripts et des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="b4566-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="b4566-115">Au lieu de renommer un objet de statistiques, nous vous recommandons de le supprimer et de le recréer sous son nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b4566-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b4566-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b4566-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b4566-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b4566-117">Permissions</span></span>  
 <span data-ttu-id="b4566-118">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="b4566-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b4566-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4566-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="b4566-120">Pour renommer un objet de statistiques</span><span class="sxs-lookup"><span data-stu-id="b4566-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="b4566-121">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4566-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4566-122">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b4566-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4566-123">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b4566-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="b4566-124">Pour plus d’informations, consultez [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b4566-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
