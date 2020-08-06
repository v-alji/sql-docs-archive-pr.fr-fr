---
title: Migrer les plans de requête | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703264"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="39242-102">Migrer des plans de requête</span><span class="sxs-lookup"><span data-stu-id="39242-102">Migrate Query Plans</span></span>
  <span data-ttu-id="39242-103">Dans la plupart des cas, la mise à niveau d'une base de données vers la dernière version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] améliore les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="39242-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="39242-104">Toutefois, si vous avez des requêtes critiques réglées avec soin pour la performance, vous pouvez conserver les plans de requête pour ces requêtes avant d'effectuer la mise à niveau en créant un repère de plan pour chaque requête.</span><span class="sxs-lookup"><span data-stu-id="39242-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="39242-105">Si, après avoir effectué la mise à niveau, l'optimiseur de requête choisit un plan moins efficace pour l'une ou plusieurs des requêtes, vous pouvez activer les repères de plan et forcer l'optimiseur de requête à utiliser les plans de pré-mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="39242-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="39242-106">Pour créer des repères de plan avant d'effectuer la mise à niveau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="39242-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="39242-107">Enregistrez le plan actuel pour chaque requête critique à l’aide de la procédure stockée [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) et en spécifiant le plan de requête dans l’indicateur de requête USE plan.</span><span class="sxs-lookup"><span data-stu-id="39242-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="39242-108">Vérifiez que le repère de plan est appliqué à la requête.</span><span class="sxs-lookup"><span data-stu-id="39242-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="39242-109">Mettez la base de données à niveau vers la dernière version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39242-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="39242-110">Les plans sont conservés dans la base de données mise à niveau, dans les repères de plan et servent de secours en cas de régressions de plan après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="39242-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="39242-111">Nous vous recommandons de ne pas activer les repères de plan après la mise à niveau, car vous risquez de passer à côté d'opportunités de meilleurs plans dans la nouvelle version ou de recompilations bénéfiques en raison de statistiques mises à jour.</span><span class="sxs-lookup"><span data-stu-id="39242-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="39242-112">Si des plans moins efficaces sont choisis après la mise à niveau, activez l'ensemble ou un sous-ensemble des repères de plan pour remplacer les nouveaux plans.</span><span class="sxs-lookup"><span data-stu-id="39242-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39242-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="39242-113">Example</span></span>  
 <span data-ttu-id="39242-114">L'exemple suivant indique comment enregistrer un plan de pré-mise à niveau pour une requête en créant un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="39242-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="39242-115">Étape 1 : collecter le plan</span><span class="sxs-lookup"><span data-stu-id="39242-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="39242-116">Le plan de requête enregistré dans le repère de plan doit être au format XML.</span><span class="sxs-lookup"><span data-stu-id="39242-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="39242-117">Les plans de requête XML peuvent être générés des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="39242-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="39242-118">SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="39242-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="39242-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="39242-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="39242-120">Interrogation de la colonne query_plan de la fonction de gestion dynamique [sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="39242-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="39242-121">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Classes d’événements [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)et [Showplan XML for Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="39242-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="39242-122">L'exemple suivant collecte le plan de requête pour l'instruction `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` en interrogeant des vues de gestion dynamique.</span><span class="sxs-lookup"><span data-stu-id="39242-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="39242-123">Étape 2 : créer le repère de plan nécessaire à l'application forcée du plan</span><span class="sxs-lookup"><span data-stu-id="39242-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="39242-124">À l'aide du plan de requête au format XML (obtenu à l'aide de n'importe laquelle des méthodes décrites précédemment) dans le repère de plan, copiez et collez le plan de requête en tant que littéral de chaîne à l'intérieur de l'indicateur de requête USE PLAN spécifié dans la clause OPTION de sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="39242-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="39242-125">Dans le plan XML lui-même, échappez les guillemets (') qui apparaissent dans le plan en ajoutant un deuxième guillemet avant de créer le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="39242-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="39242-126">Par exemple, si un plan contient `WHERE A.varchar = 'This is a string'`, vous devez utiliser un caractère d'échappement en modifiant le code par `WHERE A.varchar = ''This is a string''`.</span><span class="sxs-lookup"><span data-stu-id="39242-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="39242-127">L'exemple suivant crée un repère de plan pour le plan de requête collecté lors de l'étape 1 et insère le plan d'exécution XML pour la requête dans le paramètre `@hints`.</span><span class="sxs-lookup"><span data-stu-id="39242-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="39242-128">Pour des raisons de concision, une partie seulement de la sortie du plan d'exécution est incluse dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="39242-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="39242-129">Étape 3 : vérifier que le repère de plan est appliqué à la requête</span><span class="sxs-lookup"><span data-stu-id="39242-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="39242-130">Réexécutez la requête et examinez le plan de requête produit.</span><span class="sxs-lookup"><span data-stu-id="39242-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="39242-131">Vous devez constater que le plan correspond à celui que vous avez spécifié dans le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="39242-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39242-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39242-132">See Also</span></span>  
 <span data-ttu-id="39242-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39242-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="39242-134">[Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="39242-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="39242-135">Repères de plan</span><span class="sxs-lookup"><span data-stu-id="39242-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
