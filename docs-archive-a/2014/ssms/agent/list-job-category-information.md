---
title: Répertorier les informations de catégorie de travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704680"
---
# <a name="list-job-category-information"></a><span data-ttu-id="4cc8a-102">Répertorier les informations de catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="4cc8a-102">List Job Category Information</span></span>
  <span data-ttu-id="4cc8a-103">Comment répertorier les informations de catégorie de travaux dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4cc8a-104">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4cc8a-104">Security</span></span>  
 <span data-ttu-id="4cc8a-105">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4cc8a-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4cc8a-106">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cc8a-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="4cc8a-107">Pour répertorier les informations de catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="4cc8a-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="4cc8a-108">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc8a-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cc8a-109">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4cc8a-110">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="4cc8a-111">Pour plus d’informations, consultez [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cc8a-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4cc8a-112">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="4cc8a-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="4cc8a-113">**Pour répertorier les informations de catégorie de travaux**</span><span class="sxs-lookup"><span data-stu-id="4cc8a-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="4cc8a-114">Utilisez la classe `JobCategory` dans le langage de programmation de votre choix, par exemple Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cc8a-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="4cc8a-115">Pour plus d’informations, consultez [SQL Server Management Objects &#40;SMO&#41; Guide de programmation](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="4cc8a-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  
