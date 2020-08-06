---
title: Obtenir des informations sur les déclencheurs DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613885"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="78475-102">Obtenir des informations sur les déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="78475-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="78475-103">Les affichages catalogue répertoriés dans cette section permettent d'obtenir des informations sur les déclencheurs DDL.</span><span class="sxs-lookup"><span data-stu-id="78475-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="78475-104">**Pour obtenir des informations sur les événements ou groupes d'événements sur lesquels un déclencheur DDL peut être activé.**</span><span class="sxs-lookup"><span data-stu-id="78475-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="78475-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="78475-106">**Pour afficher les dépendances d'un déclencheur**</span><span class="sxs-lookup"><span data-stu-id="78475-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="78475-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="78475-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="78475-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="78475-110">Déclencheurs DDL d'étendue de base de données</span><span class="sxs-lookup"><span data-stu-id="78475-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="78475-111">**Pour obtenir des informations sur les déclencheurs d'étendue de base de données**</span><span class="sxs-lookup"><span data-stu-id="78475-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="78475-112">sys.triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="78475-113">**Pour obtenir des informations sur les événements de base de données qui exécutent des déclencheurs**</span><span class="sxs-lookup"><span data-stu-id="78475-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="78475-114">sys.trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="78475-115">**Pour afficher la définition d'un déclencheur d'étendue de base de données**</span><span class="sxs-lookup"><span data-stu-id="78475-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="78475-116">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="78475-117">**Pour obtenir des informations sur les déclencheurs CLR d'étendue de base de données**</span><span class="sxs-lookup"><span data-stu-id="78475-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="78475-118">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="78475-119">Déclencheurs DDL d'étendue de serveur</span><span class="sxs-lookup"><span data-stu-id="78475-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="78475-120">**Pour obtenir des informations sur les déclencheurs d'étendue de serveur**</span><span class="sxs-lookup"><span data-stu-id="78475-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="78475-121">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="78475-122">**Pour obtenir des informations sur les événements de serveur qui exécutent des déclencheurs**</span><span class="sxs-lookup"><span data-stu-id="78475-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="78475-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="78475-124">**Pour afficher la définition d'un déclencheur d'étendue de serveur**</span><span class="sxs-lookup"><span data-stu-id="78475-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="78475-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="78475-126">**Pour obtenir des informations sur les déclencheurs CLR d'étendue de serveur**</span><span class="sxs-lookup"><span data-stu-id="78475-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="78475-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78475-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="78475-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78475-128">See Also</span></span>  
 [<span data-ttu-id="78475-129">Déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="78475-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
