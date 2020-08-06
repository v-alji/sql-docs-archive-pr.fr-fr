---
title: Enregistrer les résultats de trace dans un fichier | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601289"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="fa33c-102">Enregistrer les résultats de trace dans un fichier</span><span class="sxs-lookup"><span data-stu-id="fa33c-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="fa33c-103">Vous pouvez enregistrer les résultats d'une trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="fa33c-103">You can save trace results to a file.</span></span> <span data-ttu-id="fa33c-104">Un fichier de trace est un fichier dans lequel sont écrits les résultats d'une trace.</span><span class="sxs-lookup"><span data-stu-id="fa33c-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="fa33c-105">Un fichier de trace peut se situer dans un répertoire local (tel que C:\\*nom_dossier*\\*nom_fichier.trc*) ou un répertoire réseau (tel que \\\nom_ordinateur\nom_partage\nom_fichier.trc).</span><span class="sxs-lookup"><span data-stu-id="fa33c-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="fa33c-106">Vous pouvez utiliser les fichiers de trace pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa33c-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="fa33c-107">Relire des traces</span><span class="sxs-lookup"><span data-stu-id="fa33c-107">Replay traces</span></span>  
  
-   <span data-ttu-id="fa33c-108">Auditer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa33c-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="fa33c-109">Mener des analyses des performances</span><span class="sxs-lookup"><span data-stu-id="fa33c-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="fa33c-110">Corréler des événements de trace et des compteurs de performances pour améliorer la détection des problèmes</span><span class="sxs-lookup"><span data-stu-id="fa33c-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="fa33c-111">Effectuer une analyse de l'Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="fa33c-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="fa33c-112">Exécuter une optimisation de requête</span><span class="sxs-lookup"><span data-stu-id="fa33c-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fa33c-113">enregistre les résultats de trace dans un fichier quand un chemin d’accès et un nom de fichier sont spécifiés pour l' **@tracefile** argument de la procédure stockée **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="fa33c-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa33c-114">Si un chemin est spécifié pour la procédure stockée **sp_trace_create** pour l’enregistrement du fichier de trace, le répertoire doit être accessible au serveur.</span><span class="sxs-lookup"><span data-stu-id="fa33c-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="fa33c-115">Sachez également que si un répertoire local est spécifié pour **sp_trace_create**, il s’agit d’un répertoire local sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="fa33c-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="fa33c-116">Si le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] est utilisé, il vous permet d'enregistrer les résultats de trace dans un fichier ou dans une table.</span><span class="sxs-lookup"><span data-stu-id="fa33c-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="fa33c-117">L'enregistrement des résultats de trace dans une table donne le même accès que l'enregistrement de la trace dans un fichier, et vous pouvez en plus rechercher des événements spécifiques dans la table.</span><span class="sxs-lookup"><span data-stu-id="fa33c-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="fa33c-118">Pour plus d’informations sur l’enregistrement des résultats de trace, consultez [Enregistrer des résultats d’une trace dans une table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) et [Enregistrer des résultats d’une trace dans un fichier &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="fa33c-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa33c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa33c-119">See Also</span></span>  
 <span data-ttu-id="fa33c-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa33c-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="fa33c-121">[Créer une trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="fa33c-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="fa33c-122">Créer une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="fa33c-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
