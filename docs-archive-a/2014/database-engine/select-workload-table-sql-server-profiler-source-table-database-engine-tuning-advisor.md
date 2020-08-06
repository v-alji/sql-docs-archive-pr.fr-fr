---
title: SQL Server Profiler-table source-Assistant Paramétrage du moteur de base de données sélectionner la table de charge de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604116"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="e36d5-102">SQL Server Profiler-table source-sélectionner une table de charge de travail Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="e36d5-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="e36d5-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] et l'Assistant Paramétrage de [!INCLUDE[ssDE](../includes/ssde-md.md)] utilisent cette boîte de dialogue pour sélectionner des tables.</span><span class="sxs-lookup"><span data-stu-id="e36d5-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="e36d5-104">Dans [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], utilisez la boîte de dialogue **Table source** pour spécifier une table source pour une table de trace.</span><span class="sxs-lookup"><span data-stu-id="e36d5-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="e36d5-105">Ceci est une table à partir de laquelle une trace est chargée et dont le contenu est affiché ou utilisé pour relire la trace.</span><span class="sxs-lookup"><span data-stu-id="e36d5-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="e36d5-106">Dans l’Assistant Paramétrage de [!INCLUDE[ssDE](../includes/ssde-md.md)], utilisez la boîte de dialogue **Sélectionner une table de charge de travail** pour sélectionner une table de base de données qui contient les informations de trace [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] à utiliser comme charge de travail de paramétrage, ou pour afficher l’aperçu du contenu de la table avant de commencer l’analyse du paramétrage.</span><span class="sxs-lookup"><span data-stu-id="e36d5-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e36d5-107">Options</span><span class="sxs-lookup"><span data-stu-id="e36d5-107">Options</span></span>  
 <span data-ttu-id="e36d5-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e36d5-108">**SQL Server**</span></span>  
 <span data-ttu-id="e36d5-109">Spécifie l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] actuellement connectée.</span><span class="sxs-lookup"><span data-stu-id="e36d5-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="e36d5-110">Ce champ est rempli automatiquement et ne peut pas être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="e36d5-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="e36d5-111">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="e36d5-111">**Database**</span></span>  
 <span data-ttu-id="e36d5-112">Spécifie la base de données dans laquelle se trouve la table de trace.</span><span class="sxs-lookup"><span data-stu-id="e36d5-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="e36d5-113">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="e36d5-113">**Owner**</span></span>  
 <span data-ttu-id="e36d5-114">Specifies the owner of the trace table.</span><span class="sxs-lookup"><span data-stu-id="e36d5-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="e36d5-115">Ce champ est rempli automatiquement comme **dbo**.</span><span class="sxs-lookup"><span data-stu-id="e36d5-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="e36d5-116">**Table**</span><span class="sxs-lookup"><span data-stu-id="e36d5-116">**Table**</span></span>  
 <span data-ttu-id="e36d5-117">Spécifie le nom de la table de trace à partir de laquelle la trace doit être lue.</span><span class="sxs-lookup"><span data-stu-id="e36d5-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36d5-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e36d5-118">See Also</span></span>  
 <span data-ttu-id="e36d5-119">[Enregistrer des résultats d’une trace dans une table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e36d5-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e36d5-120">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="e36d5-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="e36d5-121">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="e36d5-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
