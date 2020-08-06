---
title: Configuration de la visibilité des métadonnées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610562"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="1004f-102">Configuration de la visibilité des métadonnées</span><span class="sxs-lookup"><span data-stu-id="1004f-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="1004f-103">La visibilité des métadonnées est limitée aux éléments sécurisables qu'un utilisateur détient ou pour lesquels des autorisations lui ont été accordées.</span><span class="sxs-lookup"><span data-stu-id="1004f-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="1004f-104">Par exemple, la requête suivante retourne une ligne si l'utilisateur bénéficie d'une autorisation telle que SELECT ou INSERT sur la table `myTable`.</span><span class="sxs-lookup"><span data-stu-id="1004f-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="1004f-105">Toutefois, si l'utilisateur ne dispose pas d'autorisation sur `myTable`, la requête renvoie un jeu de résultats vide.</span><span class="sxs-lookup"><span data-stu-id="1004f-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="1004f-106">Portée et impact de la configuration de la visibilité des métadonnées</span><span class="sxs-lookup"><span data-stu-id="1004f-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="1004f-107">La configuration de la visibilité des métadonnées ne s'applique qu'aux éléments sécurisables ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1004f-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1004f-108">Affichages catalogue</span><span class="sxs-lookup"><span data-stu-id="1004f-108">Catalog views</span></span>|<span data-ttu-id="1004f-109">Procédures stockées **sp_help** du [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1004f-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="1004f-110">Métadonnées exposant des fonctions intégrées</span><span class="sxs-lookup"><span data-stu-id="1004f-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="1004f-111">Affichages des schémas d'information</span><span class="sxs-lookup"><span data-stu-id="1004f-111">Information schema views</span></span>|  
|<span data-ttu-id="1004f-112">vues de compatibilité ;</span><span class="sxs-lookup"><span data-stu-id="1004f-112">Compatibility views</span></span>|<span data-ttu-id="1004f-113">Propriétés étendues</span><span class="sxs-lookup"><span data-stu-id="1004f-113">Extended properties</span></span>|  
  
 <span data-ttu-id="1004f-114">La configuration de la visibilité des métadonnées ne s'applique pas aux éléments sécurisables ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1004f-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1004f-115">Tables système de copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="1004f-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1004f-116">Tables système de l’Agent</span><span class="sxs-lookup"><span data-stu-id="1004f-116">Agent system tables</span></span>|  
|<span data-ttu-id="1004f-117">Tables système des plans de maintenance de base de données</span><span class="sxs-lookup"><span data-stu-id="1004f-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="1004f-118">Tables système de sauvegardes</span><span class="sxs-lookup"><span data-stu-id="1004f-118">Backup system tables</span></span>|  
|<span data-ttu-id="1004f-119">Tables système de réplication</span><span class="sxs-lookup"><span data-stu-id="1004f-119">Replication system tables</span></span>|<span data-ttu-id="1004f-120">Procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sp_help **de la réplication et de l’Agent**</span><span class="sxs-lookup"><span data-stu-id="1004f-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="1004f-121">Une accessibilité restreinte aux métadonnées implique les conséquences suivantes :</span><span class="sxs-lookup"><span data-stu-id="1004f-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="1004f-122">Les applications qui sous-entendent un accès aux métadonnées **public** s’interrompront.</span><span class="sxs-lookup"><span data-stu-id="1004f-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="1004f-123">Les requêtes portant sur les vues système risqueront de renvoyer simplement un sous-ensemble de lignes et même parfois un jeu de résultats vide.</span><span class="sxs-lookup"><span data-stu-id="1004f-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="1004f-124">Les fonctions intégrées émettant des métadonnées telles que OBJECTPROPERTYEX peuvent renvoyer une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="1004f-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="1004f-125">Les procédures stockées **sp_help** du [!INCLUDE[ssDE](../../includes/ssde-md.md)]peuvent uniquement retourner un sous-ensemble de lignes ou la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="1004f-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="1004f-126">Les modules SQL, tels que les procédures stockées et les déclencheurs, fonctionnent dans le contexte de sécurité de l'appelant et, par conséquent, auront un accès limité aux métadonnées.</span><span class="sxs-lookup"><span data-stu-id="1004f-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="1004f-127">Dans le code suivant par exemple, lorsque la procédure stockée tente d'accéder aux métadonnées de la table `myTable` pour laquelle l'appelant n'a aucune autorisation, un jeu de résultats vide est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="1004f-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="1004f-128">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], une ligne est renvoyée.</span><span class="sxs-lookup"><span data-stu-id="1004f-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="1004f-129">Si vous voulez autoriser les appelants à consulter les métadonnées, vous pouvez leur accorder l'autorisation VIEW DEFINITION avec une étendue appropriée : niveau de l'objet, niveau de la base de données ou niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="1004f-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="1004f-130">Si, dans le cas de l'exemple précédent, l'appelant bénéficie d'une autorisation VIEW DEFINITION sur `myTable`, la procédure stockée renvoie une ligne.</span><span class="sxs-lookup"><span data-stu-id="1004f-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="1004f-131">Pour plus d’informations, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) et [GRANT – octroi d’autorisations de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1004f-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="1004f-132">Vous pouvez également modifier la procédure stockée pour qu'elle s'exécute avec les informations d'identification du propriétaire.</span><span class="sxs-lookup"><span data-stu-id="1004f-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="1004f-133">Si le propriétaire de la procédure et celui de la table sont identiques, le chaînage des propriétés s'applique et le contexte de sécurité du propriétaire de la procédure permet d'accéder aux métadonnées de `myTable`.</span><span class="sxs-lookup"><span data-stu-id="1004f-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="1004f-134">Dans ces circonstances, le code suivant renvoie une ligne de métadonnées à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="1004f-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1004f-135">L’exemple suivant utilise l’affichage catalogue [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) au lieu de l’affichage de compatibilité [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="1004f-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1004f-136">Vous pouvez utiliser EXECUTE AS pour basculer temporairement dans le contexte de sécurité de l'appelant.</span><span class="sxs-lookup"><span data-stu-id="1004f-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="1004f-137">Pour plus d’informations, consultez [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1004f-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="1004f-138">Avantages et inconvénients de la configuration de la visibilité des métadonnées</span><span class="sxs-lookup"><span data-stu-id="1004f-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="1004f-139">La configuration de la visibilité des métadonnées peut jouer un rôle important dans votre plan de sécurité global.</span><span class="sxs-lookup"><span data-stu-id="1004f-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="1004f-140">Sachez quand même qu'il existe des cas où un utilisateur expérimenté et déterminé peut enfreindre la confidentialité de certaines métadonnées.</span><span class="sxs-lookup"><span data-stu-id="1004f-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="1004f-141">Nous vous recommandons de déployer des autorisations d'accès aux métadonnées comme d'autres mesures préventives efficaces.</span><span class="sxs-lookup"><span data-stu-id="1004f-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="1004f-142">Il est théoriquement possible d'imposer l'émission de métadonnées dans les messages d'erreur en manipulant l'ordre d'évaluation de prédicat dans les requêtes.</span><span class="sxs-lookup"><span data-stu-id="1004f-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="1004f-143">L’éventualité d’ *attaques de type essai et erreur* de cette sorte n’est pas propre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1004f-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1004f-144">Elle provient implicitement des transformations associatives et commutatives autorisées en algèbre relationnel.</span><span class="sxs-lookup"><span data-stu-id="1004f-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="1004f-145">Vous pouvez réduire ce risque en limitant les informations retournées dans les messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1004f-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="1004f-146">Pour restreindre encore la visibilité des métadonnées dans ce sens, vous pouvez démarrer le serveur avec l'indicateur de trace 3625.</span><span class="sxs-lookup"><span data-stu-id="1004f-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="1004f-147">Cet indicateur de trace limite la quantité d'informations affichées dans les messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1004f-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="1004f-148">À son tour, cela contribue à éviter les divulgations forcées.</span><span class="sxs-lookup"><span data-stu-id="1004f-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="1004f-149">En échange, les messages d'erreur seront succincts et plus difficiles à utiliser à des fins de débogage.</span><span class="sxs-lookup"><span data-stu-id="1004f-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="1004f-150">Pour plus d’informations, consultez [Options de démarrage du service moteur de base de données](../../database-engine/configure-windows/database-engine-service-startup-options.md) et [Indicateurs de trace &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1004f-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="1004f-151">Les métadonnées suivantes ne peuvent pas être violées :</span><span class="sxs-lookup"><span data-stu-id="1004f-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="1004f-152">Valeur stockée dans la colonne **provider_string** de **sys.servers**.</span><span class="sxs-lookup"><span data-stu-id="1004f-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="1004f-153">Sans autorisation ALTER ANY LINKED SERVER, un utilisateur verra une valeur NULL dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="1004f-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="1004f-154">Définition source d'un objet défini par l'utilisateur tel qu'une procédure stockée ou un déclencheur.</span><span class="sxs-lookup"><span data-stu-id="1004f-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="1004f-155">Le code source n'est visible que si l'une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="1004f-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="1004f-156">L'utilisateur dispose de l'autorisation VIEW DEFINITION pour l'objet.</span><span class="sxs-lookup"><span data-stu-id="1004f-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="1004f-157">L'autorisation VIEW DEFINITION pour l'objet n'a pas été refusée à l'utilisateur et ce dernier bénéficie de l'autorisation CONTROL, ALTER ou TAKE OWNERSHIP sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="1004f-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="1004f-158">Tous les autres utilisateurs verront la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="1004f-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="1004f-159">Colonnes de définitions qui se trouvent dans les affichages catalogue suivants :</span><span class="sxs-lookup"><span data-stu-id="1004f-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="1004f-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="1004f-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="1004f-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="1004f-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="1004f-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="1004f-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="1004f-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="1004f-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="1004f-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="1004f-164">**sys.default_constraints**</span></span>|<span data-ttu-id="1004f-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="1004f-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="1004f-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="1004f-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="1004f-167">Colonne **ctext** de l’affichage de compatibilité **syscomments**</span><span class="sxs-lookup"><span data-stu-id="1004f-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="1004f-168">Sortie de la procédure stockée **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="1004f-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="1004f-169">Colonnes suivantes des affichages des schémas d'information :</span><span class="sxs-lookup"><span data-stu-id="1004f-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="1004f-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="1004f-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="1004f-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1004f-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="1004f-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1004f-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="1004f-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1004f-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="1004f-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1004f-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="1004f-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1004f-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="1004f-176">Fonction OBJECT_DEFINITION()</span><span class="sxs-lookup"><span data-stu-id="1004f-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="1004f-177">Valeur stockée dans la colonne password_hash de **sys.sql_logins**.</span><span class="sxs-lookup"><span data-stu-id="1004f-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="1004f-178">Un utilisateur qui ne possède pas l'autorisation CONTROL SERVER verra une valeur NULL dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="1004f-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1004f-179">Les définitions SQL des procédures et des fonctions système intégrées sont visibles par tous par l’intermédiaire de l’affichage catalogue **sys.system_sql_modules** , de la procédure stockée **sp_helptext** et de la fonction OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="1004f-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="1004f-180">Principes généraux de la visibilité des métadonnées</span><span class="sxs-lookup"><span data-stu-id="1004f-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="1004f-181">Voici quelques points à prendre en compte en termes de visibilité des métadonnées :</span><span class="sxs-lookup"><span data-stu-id="1004f-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="1004f-182">Autorisations implicites des rôles fixes</span><span class="sxs-lookup"><span data-stu-id="1004f-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="1004f-183">Étendue des autorisations</span><span class="sxs-lookup"><span data-stu-id="1004f-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="1004f-184">Priorité de DENY</span><span class="sxs-lookup"><span data-stu-id="1004f-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="1004f-185">Visibilité des métadonnées des sous-composants</span><span class="sxs-lookup"><span data-stu-id="1004f-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="1004f-186">Rôles fixes et autorisations implicites</span><span class="sxs-lookup"><span data-stu-id="1004f-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="1004f-187">Les métadonnées accessibles par les rôles fixes dépendent des autorisations implicites qui s'y rapportent.</span><span class="sxs-lookup"><span data-stu-id="1004f-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="1004f-188">Étendue des autorisations</span><span class="sxs-lookup"><span data-stu-id="1004f-188">Scope of Permissions</span></span>  
 <span data-ttu-id="1004f-189">Les autorisations délivrées à une étendue impliquent la possibilité de voir les métadonnées à ce niveau et à tous les niveaux inférieurs qui en dépendent.</span><span class="sxs-lookup"><span data-stu-id="1004f-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="1004f-190">Par exemple, si une autorisation SELECT a été accordée à un utilisateur sur un schéma, le bénéficiaire possède l'autorisation SELECT sur tous les éléments sécurisables contenus dans ce schéma.</span><span class="sxs-lookup"><span data-stu-id="1004f-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="1004f-191">L'octroi de l'autorisation SELECT sur un schéma permet donc à un utilisateur de consulter les métadonnées du schéma ainsi que des tables, vues, fonctions, procédures, files d'attente, synonymes, types et collections de schémas XML qu'il renferme.</span><span class="sxs-lookup"><span data-stu-id="1004f-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="1004f-192">Pour plus d’informations sur les étendues, consultez [Hiérarchie des autorisations &#40;moteur de base de données&#41;](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="1004f-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="1004f-193">Priorité de DENY</span><span class="sxs-lookup"><span data-stu-id="1004f-193">Precedence of DENY</span></span>  
 <span data-ttu-id="1004f-194">DENY a généralement la priorité sur toutes les autres autorisations.</span><span class="sxs-lookup"><span data-stu-id="1004f-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="1004f-195">Par exemple, si un utilisateur de base de données dispose d'une autorisation EXECUTE sur un schéma, mais que l'autorisation EXECUTE lui a été refusée sur une procédure stockée de ce schéma, l'utilisateur ne peut pas voir les métadonnées de cette procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="1004f-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="1004f-196">De plus, si un utilisateur se voit refuser l'autorisation EXECUTE pour un schéma alors qu'il dispose de l'autorisation EXECUTE pour une procédure stockée de ce schéma, l'utilisateur ne peut pas voir les métadonnées de cette procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="1004f-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="1004f-197">Prenons un autre exemple. Si l'autorisation EXECUTE a été accordée, puis refusée à un utilisateur sur une procédure stockée, ce qui est possible par le biais de diverses appartenances aux rôles, DENY reste prioritaire et l'utilisateur ne peut pas voir les métadonnées de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="1004f-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="1004f-198">Visibilité des métadonnées des sous-composants</span><span class="sxs-lookup"><span data-stu-id="1004f-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="1004f-199">La visibilité des sous-composants que sont les index, les contraintes de validation et les déclencheurs est déterminée par les autorisations accordées au parent.</span><span class="sxs-lookup"><span data-stu-id="1004f-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="1004f-200">Ces sous-composants ne bénéficient pas d'autorisations transmissibles.</span><span class="sxs-lookup"><span data-stu-id="1004f-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="1004f-201">Par exemple, si un utilisateur dispose d'une autorisation sur une table, il peut voir les métadonnées correspondant aux colonnes de la table, aux index, aux contraintes de validation, aux déclencheurs et à d'autres sous-composants de la sorte.</span><span class="sxs-lookup"><span data-stu-id="1004f-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="1004f-202">Métadonnées accessibles à tous les utilisateurs de la base de données</span><span class="sxs-lookup"><span data-stu-id="1004f-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="1004f-203">Certaines métadonnées doivent rester accessibles à tous les utilisateurs dans une base de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="1004f-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="1004f-204">Par exemple, dans la mesure où les groupes de fichiers ne peuvent pas recevoir d'autorisations, il est impossible d'octroyer à un utilisateur l'autorisation de consulter les métadonnées d'un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1004f-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="1004f-205">En revanche, tout utilisateur qui peut créer une table doit pouvoir accéder aux métadonnées du groupe de fichiers pour utiliser les clauses ON *groupe_fichiers* ou TEXTIMAGE_ON *groupe_fichiers* de l’instruction CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="1004f-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="1004f-206">Les métadonnées renvoyées par les fonctions DB_ID() et DB_NAME() sont visibles par tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1004f-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="1004f-207">Le tableau ci-dessous répertorie les affichages catalogue qui sont visibles par le rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="1004f-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1004f-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="1004f-208">**sys.partition_functions**</span></span>|<span data-ttu-id="1004f-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="1004f-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="1004f-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="1004f-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="1004f-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="1004f-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="1004f-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="1004f-212">**sys.filegroups**</span></span>|<span data-ttu-id="1004f-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="1004f-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="1004f-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="1004f-214">**sys.database_files**</span></span>|<span data-ttu-id="1004f-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="1004f-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="1004f-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="1004f-216">**sys.partitions**</span></span>|<span data-ttu-id="1004f-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="1004f-217">**sys.messages**</span></span>|  
|<span data-ttu-id="1004f-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="1004f-218">**sys.schemas**</span></span>|<span data-ttu-id="1004f-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="1004f-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="1004f-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="1004f-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="1004f-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="1004f-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="1004f-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="1004f-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="1004f-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="1004f-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1004f-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1004f-224">See Also</span></span>  
 <span data-ttu-id="1004f-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1004f-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="1004f-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1004f-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="1004f-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1004f-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="1004f-228">[Clause EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1004f-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="1004f-229">[Affichages catalogue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1004f-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="1004f-230">Affichages de compatibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1004f-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
