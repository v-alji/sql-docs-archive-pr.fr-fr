---
title: MSSQLSERVER_137 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612920"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="e15f1-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="e15f1-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="e15f1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e15f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e15f1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e15f1-104">Product Name</span></span>|<span data-ttu-id="e15f1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e15f1-105">SQL Server</span></span>|  
|<span data-ttu-id="e15f1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e15f1-106">Event ID</span></span>|<span data-ttu-id="e15f1-107">137</span><span class="sxs-lookup"><span data-stu-id="e15f1-107">137</span></span>|  
|<span data-ttu-id="e15f1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e15f1-108">Event Source</span></span>|<span data-ttu-id="e15f1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e15f1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e15f1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e15f1-110">Component</span></span>|<span data-ttu-id="e15f1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e15f1-111">SQLEngine</span></span>|  
|<span data-ttu-id="e15f1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e15f1-112">Symbolic Name</span></span>|<span data-ttu-id="e15f1-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="e15f1-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="e15f1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e15f1-114">Message Text</span></span>|<span data-ttu-id="e15f1-115">La variable scalaire « %.\*ls » doit être déclarée.</span><span class="sxs-lookup"><span data-stu-id="e15f1-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e15f1-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e15f1-116">Explanation</span></span>  
 <span data-ttu-id="e15f1-117">Cette erreur se produit lorsqu'une variable utilisée dans un script SQL n'a pas été préalablement déclarée.</span><span class="sxs-lookup"><span data-stu-id="e15f1-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="e15f1-118">L’exemple suivant retourne l’erreur 137 pour les instructions SET et SELECT car **@mycol** n’est pas déclaré.</span><span class="sxs-lookup"><span data-stu-id="e15f1-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="e15f1-119">SET @mycol = 'ContactName';</span><span class="sxs-lookup"><span data-stu-id="e15f1-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="e15f1-120">SELECT @mycol;</span><span class="sxs-lookup"><span data-stu-id="e15f1-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="e15f1-121">L'une des causes les plus compliquées de cette erreur est l'utilisation d'une variable qui a été déclarée en dehors de l'instruction EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="e15f1-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="e15f1-122">Par exemple, la variable **@mycol** spécifiée dans l’instruction SELECT est locale à l’instruction SELECT ; elle est donc en dehors de l’instruction EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="e15f1-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="e15f1-123">USE AdventureWorks2012 ;</span><span class="sxs-lookup"><span data-stu-id="e15f1-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="e15f1-124">GO</span><span class="sxs-lookup"><span data-stu-id="e15f1-124">GO</span></span>  
  
 <span data-ttu-id="e15f1-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="e15f1-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="e15f1-126">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="e15f1-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="e15f1-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span><span class="sxs-lookup"><span data-stu-id="e15f1-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e15f1-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e15f1-128">User Action</span></span>  
 <span data-ttu-id="e15f1-129">Vérifiez que toutes variables utilisées dans un script SQL ont été déclarées avant d'être utilisées par ailleurs dans le script.</span><span class="sxs-lookup"><span data-stu-id="e15f1-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="e15f1-130">Réécrivez le script afin qu'il ne fasse pas référence aux variables de l'instruction EXECUTE déclarées en dehors.</span><span class="sxs-lookup"><span data-stu-id="e15f1-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="e15f1-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e15f1-131">For example:</span></span>  
  
 <span data-ttu-id="e15f1-132">USE AdventureWorks2012 ;</span><span class="sxs-lookup"><span data-stu-id="e15f1-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="e15f1-133">GO</span><span class="sxs-lookup"><span data-stu-id="e15f1-133">GO</span></span>  
  
 <span data-ttu-id="e15f1-134">DECLARE @mycol nvarchar(20) ;</span><span class="sxs-lookup"><span data-stu-id="e15f1-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="e15f1-135">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="e15f1-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="e15f1-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span><span class="sxs-lookup"><span data-stu-id="e15f1-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15f1-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e15f1-137">See Also</span></span>  
 <span data-ttu-id="e15f1-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e15f1-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="e15f1-139">[Instructions SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e15f1-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="e15f1-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e15f1-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
