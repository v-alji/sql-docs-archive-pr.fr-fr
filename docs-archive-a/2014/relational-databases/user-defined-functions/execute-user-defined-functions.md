---
title: Exécuter des fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615076"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="aa7d6-102">Exécuter des fonctions définies par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="aa7d6-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="aa7d6-103">Vous pouvez exécuter une fonction définie par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa7d6-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="aa7d6-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="aa7d6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aa7d6-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="aa7d6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aa7d6-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="aa7d6-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aa7d6-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aa7d6-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aa7d6-108">**Pour exécuter une fonction définie par l'utilisateur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="aa7d6-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="aa7d6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa7d6-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa7d6-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="aa7d6-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aa7d6-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="aa7d6-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="aa7d6-112">Dans Transact-SQL, vous pouvez fournir les paramètres à l’aide de *value* ou à l’aide de @*nom_paramètre*=*value.*</span><span class="sxs-lookup"><span data-stu-id="aa7d6-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="aa7d6-113">Un paramètre ne fait pas partie d’une transaction. Ainsi, si vous modifiez l’un d’eux dans une transaction et que vous restaurez cette dernière par la suite, le paramètre ne reprend pas sa valeur initiale.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="aa7d6-114">La valeur renvoyée à l'appelant est toujours la valeur au moment du renvoie du module.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa7d6-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aa7d6-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa7d6-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="aa7d6-116">Permissions</span></span>  
 <span data-ttu-id="aa7d6-117">Aucune autorisation n'est requise pour exécuter l'instruction EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="aa7d6-118">Cependant, des autorisations sont requises sur les éléments sécurisables référencés dans la chaîne EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="aa7d6-119">Par exemple, si la chaîne contient une instruction INSERT, l'appelant de l'instruction EXECUTE doit posséder l'autorisation INSERT sur la table cible.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="aa7d6-120">Les autorisations sont vérifiées au moment où l'instruction EXECUTE est rencontrée, même si celle-ci est incluse dans un module.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="aa7d6-121">Pour plus d’informations, consultez [execute &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="aa7d6-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aa7d6-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa7d6-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="aa7d6-123">Pour exécuter une fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="aa7d6-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="aa7d6-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa7d6-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa7d6-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa7d6-126">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="aa7d6-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="aa7d6-127">Pour plus d’informations, consultez [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aa7d6-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
