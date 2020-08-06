---
title: default trace enabled (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707856"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="fcda6-102">default trace enabled (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="fcda6-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="fcda6-103">Utilisez l’option **default trace enabled** pour activer ou désactiver les fichiers journaux de trace par défaut.</span><span class="sxs-lookup"><span data-stu-id="fcda6-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="fcda6-104">La fonctionnalité de trace par défaut comprend un journal enrichi et cohérent sur l'activité et les modifications principalement liées aux options de configuration.</span><span class="sxs-lookup"><span data-stu-id="fcda6-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="fcda6-105">Utilisez plutôt des événements étendus.</span><span class="sxs-lookup"><span data-stu-id="fcda6-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="fcda6-106">Objectif</span><span class="sxs-lookup"><span data-stu-id="fcda6-106">Purpose</span></span>  
 <span data-ttu-id="fcda6-107">La trace par défaut aide les administrateurs de bases de données à résoudre les problèmes en leur fournissant les données de journal qui leur permettent de les diagnostiquer dès leur première occurrence.</span><span class="sxs-lookup"><span data-stu-id="fcda6-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="fcda6-108">Affichage</span><span class="sxs-lookup"><span data-stu-id="fcda6-108">Viewing</span></span>  
 <span data-ttu-id="fcda6-109">Les journaux de trace par défaut peuvent être ouverts et examinés par le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou interrogés avec [!INCLUDE[tsql](../../includes/tsql-md.md)] par le biais de la fonction système `fn_trace_gettable` .</span><span class="sxs-lookup"><span data-stu-id="fcda6-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="fcda6-110">peut ouvrir les fichiers journaux de trace par défaut comme n’importe quel fichier de résultat de trace normal.</span><span class="sxs-lookup"><span data-stu-id="fcda6-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="fcda6-111">Par défaut, le journal de trace par défaut est stocké dans le répertoire `\MSSQL\LOG` au moyen d'un fichier de substitution.</span><span class="sxs-lookup"><span data-stu-id="fcda6-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="fcda6-112">Le nom de fichier de base du journal de trace par défaut est `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="fcda6-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="fcda6-113">Dans une installation classique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la trace par défaut est activée et devient donc TraceID 1.</span><span class="sxs-lookup"><span data-stu-id="fcda6-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="fcda6-114">Si elle est activée après l'installation et après la création d'autres traces, la trace TraceID peut s’incrémenter.</span><span class="sxs-lookup"><span data-stu-id="fcda6-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="fcda6-115">Pour plus d’informations sur l’utilisation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler pour afficher ce fichier de trace, consultez [Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="fcda6-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcda6-116">Exemple :</span><span class="sxs-lookup"><span data-stu-id="fcda6-116">Example:</span></span>  
 <span data-ttu-id="fcda6-117">L'instruction suivante ouvre le journal de trace par défaut dans l'emplacement par défaut :</span><span class="sxs-lookup"><span data-stu-id="fcda6-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="fcda6-118">Configuration</span><span class="sxs-lookup"><span data-stu-id="fcda6-118">Configuring</span></span>  
 <span data-ttu-id="fcda6-119">Quand elle a la valeur 1, l’option **default trace enabled** active la **trace par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fcda6-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="fcda6-120">Le paramètre par défaut pour cette option est 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="fcda6-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="fcda6-121">La valeur 0 désactive la trace.</span><span class="sxs-lookup"><span data-stu-id="fcda6-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="fcda6-122">L’option **default trace enabled** est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="fcda6-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="fcda6-123">Si vous utilisez la procédure stockée système **sp_configure** pour changer sa valeur, vous ne pouvez modifier l’option **default trace enabled** que si l’option **show advanced options** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="fcda6-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="fcda6-124">Le paramètre prend effet immédiatement (sans redémarrage du serveur).</span><span class="sxs-lookup"><span data-stu-id="fcda6-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcda6-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcda6-125">See Also</span></span>  
 <span data-ttu-id="fcda6-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fcda6-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fcda6-127">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fcda6-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="fcda6-128">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fcda6-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
