---
title: Créer un repère de plan pour les requêtes paramétrables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614566"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="738d6-102">Créer un repère de plan pour les requêtes paramétrables</span><span class="sxs-lookup"><span data-stu-id="738d6-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="738d6-103">Un repère de plan TEMPLATE correspond à des requêtes autonomes paramétrables au format spécifié.</span><span class="sxs-lookup"><span data-stu-id="738d6-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="738d6-104">L'exemple suivant crée un repère de plan correspondant à la requête qui paramètre selon une forme donnée, et commande à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'imposer le paramétrage de la requête.</span><span class="sxs-lookup"><span data-stu-id="738d6-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="738d6-105">La syntaxe des deux requêtes suivantes est équivalente, seules leurs valeurs littérales constantes diffèrent.</span><span class="sxs-lookup"><span data-stu-id="738d6-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="738d6-106">Voici le repère de plan pour la forme paramétrable de la requête :</span><span class="sxs-lookup"><span data-stu-id="738d6-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="738d6-107">Dans l'exemple précédent, la valeur du paramètre `@stmt` correspond à la forme paramétrable de la requête.</span><span class="sxs-lookup"><span data-stu-id="738d6-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="738d6-108">La procédure stockée système [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) est la seule méthode fiable pour obtenir cette valeur et pouvoir l’utiliser dans sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="738d6-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="738d6-109">Vous pouvez utiliser le script suivant à la fois pour obtenir la requête paramétrable et créer ensuite un repère de plan à partir de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="738d6-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="738d6-110">Les valeurs littérales constantes du paramètre `@stmt` transmises à `sp_get_query_template` peuvent affecter le type de données choisi pour le paramètre qui remplace le littéral.</span><span class="sxs-lookup"><span data-stu-id="738d6-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="738d6-111">Ceci va également affecter la mise en correspondance du repère de plan.</span><span class="sxs-lookup"><span data-stu-id="738d6-111">This will affect plan guide matching.</span></span> <span data-ttu-id="738d6-112">Vous devrez peut-être créer plusieurs repères de plan pour traiter plusieurs plages de valeurs.</span><span class="sxs-lookup"><span data-stu-id="738d6-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="738d6-113">Vous pouvez combiner les repères de plan TEMPLATE et les repères de plan SQL.</span><span class="sxs-lookup"><span data-stu-id="738d6-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="738d6-114">Ainsi, vous pouvez créer un repère de plan TEMPLATE pour vous assurer qu'une classe de requêtes est paramétrable,</span><span class="sxs-lookup"><span data-stu-id="738d6-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="738d6-115">et ensuite créer un repère de plan SQL sur la forme paramétrable de cette requête.</span><span class="sxs-lookup"><span data-stu-id="738d6-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
