---
title: Hiérarchie des autorisations (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697751"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="ec40d-102">Hiérarchie des autorisations (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="ec40d-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="ec40d-103">[!INCLUDE[ssDE](../../../includes/ssde-md.md)] gère une collection hiérarchisée d’entités qui peuvent être sécurisées à l’aide d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="ec40d-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="ec40d-104">Ces entités sont appelées *éléments sécurisables*.</span><span class="sxs-lookup"><span data-stu-id="ec40d-104">These entities are known as *securables*.</span></span> <span data-ttu-id="ec40d-105">Les éléments sécurisables les plus proéminents sont les serveurs et les bases de données, mais les autorisations discrètes peuvent être définies à un niveau beaucoup plus fin.</span><span class="sxs-lookup"><span data-stu-id="ec40d-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ec40d-106">règle les actions des principaux sur des éléments sécurisables en vérifiant que les autorisations appropriées leur ont été octroyées.</span><span class="sxs-lookup"><span data-stu-id="ec40d-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="ec40d-107">L'illustration suivante montre les relations entre les hiérarchies des autorisations du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec40d-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="ec40d-108">![Diagramme de hiérarchies d’autorisations de moteur de base de données](../../database-engine/media/wj-security-layers.gif "Diagramme de hiérarchies d’autorisations de moteur de base de données")</span><span class="sxs-lookup"><span data-stu-id="ec40d-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="ec40d-109">Graphique des autorisations SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec40d-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="ec40d-110">Pour obtenir un graphique de la taille d’une affiche de toutes les autorisations du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] au format PDF, consultez [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span><span class="sxs-lookup"><span data-stu-id="ec40d-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="ec40d-111">Utilisation des autorisations</span><span class="sxs-lookup"><span data-stu-id="ec40d-111">Working with Permissions</span></span>
 <span data-ttu-id="ec40d-112">Les autorisations peuvent être gérées avec les requêtes GRANT, DENY et REVOKE [!INCLUDE[tsql](../../includes/tsql-md.md)] habituelles.</span><span class="sxs-lookup"><span data-stu-id="ec40d-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="ec40d-113">Les informations sur les autorisations sont visibles dans les affichages catalogue [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) et [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ec40d-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="ec40d-114">Il existe également une assistance permettant d'obtenir des informations sur les autorisations à l'aide de fonctions intégrées.</span><span class="sxs-lookup"><span data-stu-id="ec40d-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec40d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec40d-115">See Also</span></span>
 <span data-ttu-id="ec40d-116">[Sécurisation](securing-sql-server.md) des [autorisations SQL Server &#40;moteur de base de données&#41;](permissions-database-engine.md) éléments [sécurisables](securables.md) [&#40;moteur de base de données](authentication-access/principals-database-engine.md) [&#41;&#40;&#41;](/sql/t-sql/statements/grant-transact-sql) [Transact-](/sql/t-sql/functions/has-perms-by-name-transact-sql) sql &#40;[sys.&#41;&#40;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) transact [-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [sys. HAS_PERMS_BY_NAME &#40;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) Transact [-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [sys. fn_builtin_permissions &#40;de](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) Transact-SQL&#41;sys. server_permissions &#40;.&#41;s Transact-SQL database_permissions</span><span class="sxs-lookup"><span data-stu-id="ec40d-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


