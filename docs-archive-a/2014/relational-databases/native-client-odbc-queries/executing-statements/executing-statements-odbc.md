---
title: Exécution d’instructions (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600859"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="122f2-102">Exécution d'instructions (ODBC)</span><span class="sxs-lookup"><span data-stu-id="122f2-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="122f2-103">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client offre plusieurs moyens d’exécuter des instructions SQL dans une [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] base de données :</span><span class="sxs-lookup"><span data-stu-id="122f2-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="122f2-104">Exécution directe</span><span class="sxs-lookup"><span data-stu-id="122f2-104">Direct execution</span></span>  
  
-   <span data-ttu-id="122f2-105">Exécution préparée</span><span class="sxs-lookup"><span data-stu-id="122f2-105">Prepared execution</span></span>  
  
 <span data-ttu-id="122f2-106">L’exécution directe implique la génération d’une chaîne de caractères contenant une [!INCLUDE[tsql](../../../includes/tsql-md.md)] instruction et son envoi en vue d’une exécution à l’aide de la fonction **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="122f2-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="122f2-107">L'exécution préparée implique la génération d'une chaîne de caractères contenant une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] et son exécution en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="122f2-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="122f2-108">La première étape utilise la fonction [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) pour analyser et compiler le plan d’exécution de l’instruction dans le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="122f2-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="122f2-109">La deuxième étape utilise la fonction **SQLExecute** pour exécuter le plan d’exécution précédemment préparé.</span><span class="sxs-lookup"><span data-stu-id="122f2-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="122f2-110">Cela permet de réduire la charge d'analyse et de compilation pour chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="122f2-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="122f2-111">L'exécution préparée est couramment utilisée par les applications pour exécuter de manière répétée la même instruction SQL paramétrable.</span><span class="sxs-lookup"><span data-stu-id="122f2-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="122f2-112">Les exécutions directe et préparée peuvent exécuter une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] unique ou un lot d'instructions SQL, ou elles peuvent appeler une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="122f2-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="122f2-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="122f2-113">In This Section</span></span>  
  
-   [<span data-ttu-id="122f2-114">Exécution directe</span><span class="sxs-lookup"><span data-stu-id="122f2-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="122f2-115">Exécution préparée</span><span class="sxs-lookup"><span data-stu-id="122f2-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="122f2-116">Procédures</span><span class="sxs-lookup"><span data-stu-id="122f2-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="122f2-117">Lots d'instructions</span><span class="sxs-lookup"><span data-stu-id="122f2-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="122f2-118">Conséquences des options ISO</span><span class="sxs-lookup"><span data-stu-id="122f2-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="122f2-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="122f2-119">See Also</span></span>  
 [<span data-ttu-id="122f2-120">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="122f2-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
