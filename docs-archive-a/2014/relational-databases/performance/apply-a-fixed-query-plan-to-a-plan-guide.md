---
title: Appliquer un plan de requête fixe à un repère de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: bbf401f9-af7c-48e7-8a43-bf25e8af2fd7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 318955c4d0550e311873d8b4a6f79f72e04ac8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696747"
---
# <a name="apply-a-fixed-query-plan-to-a-plan-guide"></a><span data-ttu-id="ca6fb-102">Appliquer un plan de requête fixe à un repère de plan</span><span class="sxs-lookup"><span data-stu-id="ca6fb-102">Apply a Fixed Query Plan to a Plan Guide</span></span>
  <span data-ttu-id="ca6fb-103">Vous pouvez appliquer un plan de requête fixe à un repère de plan de type OBJET ou SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6fb-103">You can apply a fixed query plan to a plan guide of type OBJECT or SQL.</span></span> <span data-ttu-id="ca6fb-104">Les repères de plan qui appliquent un plan de requête fixe sont utiles lorsque vous avez connaissance d'un plan d'exécution existant plus performant que celui sélectionné par l'optimiseur pour une requête particulière.</span><span class="sxs-lookup"><span data-stu-id="ca6fb-104">Plan guides that apply a fixed query plan are useful when you know about an existing execution plan that performs better than the one selected by the optimizer for a particular query.</span></span>  
  
 <span data-ttu-id="ca6fb-105">L'exemple suivant crée un repère de plan pour une instruction SQL ad hoc simple.</span><span class="sxs-lookup"><span data-stu-id="ca6fb-105">The following example creates a plan guide for a simple ad hoc SQL statement.</span></span> <span data-ttu-id="ca6fb-106">Le plan de requête souhaité pour cette instruction est fourni dans le repère de plan en spécifiant directement le plan d'exécution XML pour la requête dans le paramètre `@hints` .</span><span class="sxs-lookup"><span data-stu-id="ca6fb-106">The desired query plan for this statement is provided in the plan guide by specifying the XML Showplan for the query directly in the `@hints` parameter.</span></span> <span data-ttu-id="ca6fb-107">L'exemple exécute en premier l'instruction SQL pour générer un plan dans le cache du plan.</span><span class="sxs-lookup"><span data-stu-id="ca6fb-107">The example first executes the SQL statement to generate a plan in the plan cache.</span></span> <span data-ttu-id="ca6fb-108">Pour les besoins de cet exemple, il est supposé que le plan généré est le plan souhaité et qu'aucune analyse de requête supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="ca6fb-108">For the purposes of this example, it is assumed that the generated plan is the desired plan and no additional query tuning is required.</span></span> <span data-ttu-id="ca6fb-109">Le plan d'exécution de requêtes XML pour la requête est obtenu en interrogeant les vues de gestion dynamique `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`et `sys.dm_exec_text_query_plan` , et est assigné à la variable `@xml_showplan` .</span><span class="sxs-lookup"><span data-stu-id="ca6fb-109">The XML Showplan for the query is obtained by querying the `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`, and `sys.dm_exec_text_query_plan` dynamic management views and is assigned to the `@xml_showplan` variable.</span></span> <span data-ttu-id="ca6fb-110">La variable `@xml_showplan` est ensuite transmise à l'instruction `sp_create_plan_guide` dans le paramètre `@hints` .</span><span class="sxs-lookup"><span data-stu-id="ca6fb-110">The `@xml_showplan` variable is then passed to the `sp_create_plan_guide` statement in the `@hints` parameter.</span></span> <span data-ttu-id="ca6fb-111">Vous pouvez aussi créer un repère de plan à partir d’un plan de requête dans le cache des plans à l’aide de la procédure stockée [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ca6fb-111">Or, you can create a plan guide from a query plan in the plan cache by using the [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;  
GO  
DECLARE @xml_showplan nvarchar(max);  
SET @xml_showplan = (SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%');  
  
EXEC sp_create_plan_guide   
    @name = N'Guide1_from_XML_showplan',   
    @stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',   
    @type = N'SQL',  
    @module_or_batch = NULL,   
    @params = NULL,   
    @hints = @xml_showplan;  
GO  
```  
  
  
