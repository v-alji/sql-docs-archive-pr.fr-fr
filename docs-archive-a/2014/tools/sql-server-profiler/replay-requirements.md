---
title: Conditions requises pour la relecture | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705735"
---
# <a name="replay-requirements"></a><span data-ttu-id="4f136-102">Conditions préalables à la relecture</span><span class="sxs-lookup"><span data-stu-id="4f136-102">Replay Requirements</span></span>
  <span data-ttu-id="4f136-103">Pour relire les données de trace avec [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou Distributed Replay Utility, un jeu spécifique de classes et de colonnes d'événements doit être capturé dans la trace.</span><span class="sxs-lookup"><span data-stu-id="4f136-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="4f136-104">Ces paramètres sont activés par défaut si le modèle de trace **TSQL_Replay** est utilisé pour configurer une trace utilisée ultérieurement pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="4f136-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="4f136-105">Cette rubrique décrit ces paramètres et d’autres configurations préalables à la relecture.</span><span class="sxs-lookup"><span data-stu-id="4f136-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f136-106">Nous recommandons d'utiliser Distributed Replay Utility pour relire des applications OLTP exigeantes (avec de nombreuses connexions simultanées actives ou un débit élevé).</span><span class="sxs-lookup"><span data-stu-id="4f136-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="4f136-107">Distributed Replay Utility peut relire les données de trace de plusieurs ordinateurs, en simulant mieux les charges de travail sensibles.</span><span class="sxs-lookup"><span data-stu-id="4f136-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="4f136-108">Pour plus d'informations, consultez [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="4f136-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="4f136-109">Classes d'événements nécessaires à la relecture</span><span class="sxs-lookup"><span data-stu-id="4f136-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="4f136-110">Pour être relus par [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], les jeux de classes d'événements suivants doivent être capturés dans la trace, en plus de toutes les autres classes d'événements que vous souhaitez surveiller :</span><span class="sxs-lookup"><span data-stu-id="4f136-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="4f136-111">**CursorClose (** nécessaire uniquement pour la relecture de curseurs côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4f136-112">**CursorExecute** (nécessaire uniquement pour la relecture de curseurs côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4f136-113">**CursorOpen** (nécessaire uniquement pour la relecture de curseurs côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4f136-114">**CursorPrepare** (nécessaire uniquement pour la relecture de curseurs côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4f136-115">**CursorUnprepare** (nécessaire uniquement pour la relecture de curseurs côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="4f136-116">**Audit Login**</span><span class="sxs-lookup"><span data-stu-id="4f136-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="4f136-117">**Audit Logout**</span><span class="sxs-lookup"><span data-stu-id="4f136-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="4f136-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="4f136-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="4f136-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="4f136-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="4f136-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="4f136-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="4f136-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="4f136-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="4f136-122">**Exec Prepared SQL** (nécessaire uniquement pour la relecture d’instructions SQL préparées côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4f136-123">**Prepare SQL** (nécessaire uniquement pour la relecture d’instructions SQL préparées côté serveur)</span><span class="sxs-lookup"><span data-stu-id="4f136-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="4f136-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="4f136-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="4f136-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="4f136-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="4f136-126">Colonnes de données nécessaires à la relecture</span><span class="sxs-lookup"><span data-stu-id="4f136-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="4f136-127">En plus des autres colonnes de données que vous voudrez peut-être capturer, les colonnes de données suivantes doivent être capturées dans une trace pour permettre la relecture de la trace en question :</span><span class="sxs-lookup"><span data-stu-id="4f136-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="4f136-128">**Classe d'événements**</span><span class="sxs-lookup"><span data-stu-id="4f136-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="4f136-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="4f136-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="4f136-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="4f136-130">**TextData**</span></span>  
  
-   <span data-ttu-id="4f136-131">**Nom d’application**</span><span class="sxs-lookup"><span data-stu-id="4f136-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="4f136-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="4f136-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="4f136-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="4f136-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="4f136-134">**ID de base de données**</span><span class="sxs-lookup"><span data-stu-id="4f136-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="4f136-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="4f136-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="4f136-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="4f136-136">**HostName**</span></span>  
  
-   <span data-ttu-id="4f136-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="4f136-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="4f136-138">**Binary Data**</span><span class="sxs-lookup"><span data-stu-id="4f136-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="4f136-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="4f136-139">**SPID**</span></span>  
  
-   <span data-ttu-id="4f136-140">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="4f136-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="4f136-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="4f136-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="4f136-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="4f136-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="4f136-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="4f136-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="4f136-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="4f136-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="4f136-145">**Error**</span><span class="sxs-lookup"><span data-stu-id="4f136-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f136-146">Utilisez le modèle de trace **TSQL_Replay** pour les traces qui capturent des données à des fins de relecture.</span><span class="sxs-lookup"><span data-stu-id="4f136-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="4f136-147">Autres conditions préalables à la relecture</span><span class="sxs-lookup"><span data-stu-id="4f136-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="4f136-148">Dans Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la relecture vérifie la présence des événements et des colonnes nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4f136-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="4f136-149">Cette nouveauté permet d'améliorer la précision de la relecture en supprimant tout travail de devinette dans la réparation des relectures qui échouent en raison de données manquantes.</span><span class="sxs-lookup"><span data-stu-id="4f136-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="4f136-150">La relecture renvoie une erreur et s'arrête lorsque des données nécessaires sont manquantes dans une trace.</span><span class="sxs-lookup"><span data-stu-id="4f136-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="4f136-151">Pour relire une trace portant sur un serveur (cible) qui exécute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et qui n'est pas le serveur tracé au départ (source), vérifiez que les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="4f136-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="4f136-152">Tous les utilisateurs et connexions contenus dans la trace doivent déjà être créés sur la cible et dans la même base de données que la source.</span><span class="sxs-lookup"><span data-stu-id="4f136-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="4f136-153">Toutes les connexions d'accès et tous les utilisateurs contenus dans la cible doivent avoir les mêmes autorisations que dans la source.</span><span class="sxs-lookup"><span data-stu-id="4f136-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="4f136-154">Tous les mots de passe de connexion doivent être identiques à ceux de l'utilisateur qui exécute la relecture.</span><span class="sxs-lookup"><span data-stu-id="4f136-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="4f136-155">Les ID de base de données sur la cible doivent idéalement être identiques à ceux qui sont sur la source.</span><span class="sxs-lookup"><span data-stu-id="4f136-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="4f136-156">Si ce n’est pas le cas, la mise en correspondance peut être effectuée sur la base du **DatabaseName** s’il est présent dans la trace.</span><span class="sxs-lookup"><span data-stu-id="4f136-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="4f136-157">La base de données par défaut de chaque connexion d'accès contenue dans la trace doit être définie (sur la cible) en tant que base de données cible relative à la connexion.</span><span class="sxs-lookup"><span data-stu-id="4f136-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="4f136-158">Par exemple, la trace à relire contient les activités de la connexion **Fred**dans la base de données **Fred_Db** située sur la source.</span><span class="sxs-lookup"><span data-stu-id="4f136-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="4f136-159">Ainsi, sur la cible, la base de données par défaut de la connexion **Fred**doit être la base de données correspondant à **Fred_Db** (même si le nom de la base de données est différent).</span><span class="sxs-lookup"><span data-stu-id="4f136-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="4f136-160">Pour définir la base de données par défaut de la connexion, utilisez la procédure stockée **sp_defaultdb** .</span><span class="sxs-lookup"><span data-stu-id="4f136-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="4f136-161">La relecture d'événements associés à des connexions manquantes ou incorrectes va entraîner des erreurs de relecture, mais l'opération de relecture va se poursuivre.</span><span class="sxs-lookup"><span data-stu-id="4f136-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="4f136-162">Pour savoir quelles autorisations sont nécessaires pour relire une trace, consultez [Autorisations nécessaires pour exécuter SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4f136-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f136-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f136-163">See Also</span></span>  
 <span data-ttu-id="4f136-164">[Relire une table de trace &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4f136-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4f136-165">[Relire un fichier de trace &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4f136-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4f136-166">[Informations de référence sur la classe d’événements SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4f136-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="4f136-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f136-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="4f136-168">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="4f136-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
