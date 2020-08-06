---
title: Autorisations nécessaires pour exécuter SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705763"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="77ef4-102">Autorisations nécessaires pour exécuter SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="77ef4-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="77ef4-103">Par défaut, l'exécution du [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] exige les mêmes autorisations utilisateur que les procédures stockées Transact-SQL utilisées pour créer des traces.</span><span class="sxs-lookup"><span data-stu-id="77ef4-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="77ef4-104">Pour exécuter le [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], les utilisateurs doivent disposer de l'autorisation ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="77ef4-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="77ef4-105">Pour plus d’informations, consultez [Autorisations de serveur GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77ef4-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="77ef4-106">Les utilisateurs qui disposent des autorisations SHOWPLAN, ALTER TRACE ou VIEW SERVER STATE peuvent afficher les requêtes capturées dans une sortie Showplan.</span><span class="sxs-lookup"><span data-stu-id="77ef4-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="77ef4-107">Ces requêtes peuvent contenir des informations critiques telles que les mots de passe.</span><span class="sxs-lookup"><span data-stu-id="77ef4-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="77ef4-108">C'est pourquoi, il est recommandé de n'accorder ces autorisations qu'aux utilisateurs qui sont autorisés à afficher les informations critiques, tels que les membres du rôle de base de données fixe db_owner ou les membres du rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="77ef4-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="77ef4-109">Il est également recommandé d'enregistrer les fichiers Showplan ou de trace qui contiennent des événements Showplan uniquement sur un emplacement qui utilise le système de fichiers NTFS et que vous limitiez l'accès aux utilisateurs qui sont autorisés à afficher les informations critiques.</span><span class="sxs-lookup"><span data-stu-id="77ef4-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="77ef4-110">Autorisations utilisées pour relire des traces</span><span class="sxs-lookup"><span data-stu-id="77ef4-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="77ef4-111">La relecture de traces exige également que l'utilisateur qui effectue cette opération dispose de l'autorisation ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="77ef4-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="77ef4-112">Cependant, lors de la relecture, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] utilise la commande EXECUTE AS si un événement Audit Login est rencontré dans la trace en cours de relecture.</span><span class="sxs-lookup"><span data-stu-id="77ef4-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="77ef4-113">utilise la commande EXECUTE AS pour emprunter l’identité de l’utilisateur associé à l’événement de connexion.</span><span class="sxs-lookup"><span data-stu-id="77ef4-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="77ef4-114">Si [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] rencontre un événement de connexion dans la trace en cours de relecture, les contrôles des autorisations suivants sont effectués :</span><span class="sxs-lookup"><span data-stu-id="77ef4-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="77ef4-115">Utilisateur1, qui dispose de l'autorisation ALTER TRACE, lance la relecture d'une trace.</span><span class="sxs-lookup"><span data-stu-id="77ef4-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="77ef4-116">Un événement de connexion pour Utilisateur2 est rencontré dans la trace relue.</span><span class="sxs-lookup"><span data-stu-id="77ef4-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="77ef4-117">utilise la commande EXECUTE AS pour emprunter l’identité de l’Utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="77ef4-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="77ef4-118">tente d’authentifier l’Utilisateur2, et selon les résultats, une des actions suivantes se produit :</span><span class="sxs-lookup"><span data-stu-id="77ef4-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="77ef4-119">Si l'Utilisateur2 ne peut pas être authentifié, le [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] retourne une erreur et poursuit la relecture de la trace en tant qu'Utilisateur1.</span><span class="sxs-lookup"><span data-stu-id="77ef4-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="77ef4-120">Si l'Utilisateur2 est correctement authentifié, la relecture de la trace en tant qu'Utilisateur2 se poursuit.</span><span class="sxs-lookup"><span data-stu-id="77ef4-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="77ef4-121">Les autorisations de l'Utilisateur2 sont vérifiées sur la base de données cible et selon les résultats, une des actions suivantes se produit :</span><span class="sxs-lookup"><span data-stu-id="77ef4-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="77ef4-122">Si l'Utilisateur2 dispose d'autorisations sur la base de données cible, l'emprunt d'identité a réussi et la trace est relue en tant qu'Utilisateur2.</span><span class="sxs-lookup"><span data-stu-id="77ef4-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="77ef4-123">Si l'Utilisateur2 ne dispose pas d'autorisations sur la base de données cible, le serveur recherche un utilisateur Invité sur cette base de données.</span><span class="sxs-lookup"><span data-stu-id="77ef4-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="77ef4-124">Une vérification de l'existence d'un utilisateur Invité s'effectue sur la base de données et selon les résultats, une des actions suivantes se produit :</span><span class="sxs-lookup"><span data-stu-id="77ef4-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="77ef4-125">S'il existe un compte Invité, la trace est relue en tant que compte Invité.</span><span class="sxs-lookup"><span data-stu-id="77ef4-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="77ef4-126">Si aucun compte Invité n'existe sur la base de données cible, une erreur est retournée et la trace est relue en tant qu'Utilisateur1.</span><span class="sxs-lookup"><span data-stu-id="77ef4-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="77ef4-127">Le schéma suivant illustre ce processus de vérification de l'autorisation lors de la relecture de traces :</span><span class="sxs-lookup"><span data-stu-id="77ef4-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="77ef4-128">![Autorisations de trace de relecture de SQL Server Profiler](../../database-engine/media/replaytracedecisiontree.gif "Autorisations de trace de relecture de SQL Server Profiler")</span><span class="sxs-lookup"><span data-stu-id="77ef4-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="77ef4-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77ef4-129">See Also</span></span>
 <span data-ttu-id="77ef4-130">[SQL Server Profiler procédures stockées &#40;les](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [suivis de relecture](replay-traces.md)&#41;Transact-SQL [créent une trace &#40;SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;[relire une table de trace &#40;](replay-a-trace-table-sql-server-profiler.md) SQL Server Profiler [relecture d’un fichier de trace&#41;](replay-a-trace-file-sql-server-profiler.md) &#40;SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="77ef4-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


