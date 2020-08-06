---
title: Traçage et relecture des événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700932"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="f72c4-102">Événements de traçage et de relecture</span><span class="sxs-lookup"><span data-stu-id="f72c4-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="f72c4-103">Dans SMO, les objets `Trace` et `Replay` de l'espace de noms <xref:Microsoft.SqlServer.Management.Trace> fournissent l'accès par programme à la fonctionnalité [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], qui est utilisée pour surveiller une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f72c4-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f72c4-104">Vous pouvez capturer et enregistrer des données sur chaque événement dans un fichier ou dans une table en vue d'une analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f72c4-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="f72c4-105">Par exemple, vous pouvez surveiller un environnement de production pour savoir quelles sont les procédures qui compromettent les performances en s'exécutant trop lentement.</span><span class="sxs-lookup"><span data-stu-id="f72c4-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="f72c4-106">Les objets `Trace` et `Replay` fournissent un jeu d'objets qui peuvent être utilisés pour créer des traces sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f72c4-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f72c4-107">Ces objets peuvent être utilisés au sein de vos propres applications pour créer manuellement des traces pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f72c4-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f72c4-108">En outre, les objets SMO `Trace` peuvent être utilisés pour lire des fichiers et des tables SQL Trace créés en surveillant [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou l'enregistrement DTS.</span><span class="sxs-lookup"><span data-stu-id="f72c4-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="f72c4-109">Les objets SMO `Trace` vous permettent de réaliser les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f72c4-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="f72c4-110">Créer une trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="f72c4-111">Définir des filtres sur la trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="f72c4-112">Définir les événements qui sont tracés.</span><span class="sxs-lookup"><span data-stu-id="f72c4-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="f72c4-113">Arrêter ou démarrer une trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="f72c4-114">Lire des fichiers ou des tables de trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="f72c4-115">Obtenir des informations sur les événements d'une trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="f72c4-116">Obtenir des informations sur les filtres d'une trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="f72c4-117">Manipuler des données de trace par programme.</span><span class="sxs-lookup"><span data-stu-id="f72c4-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="f72c4-118">Écrire des fichiers ou des tables de trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="f72c4-119">Relire des fichiers ou des tables de trace.</span><span class="sxs-lookup"><span data-stu-id="f72c4-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="f72c4-120">Les données de trace des `Trace` `Replay` objets et peuvent être utilisées par l’application Smo, ou elles peuvent être examinées manuellement à l’aide de [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f72c4-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="f72c4-121">Les données de trace sont également compatibles avec les procédures stockées [SQL Trace](../../sql-trace/sql-trace.md) qui proposent également des fonctionnalités de suivi.</span><span class="sxs-lookup"><span data-stu-id="f72c4-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="f72c4-122">Les objets de trace SMO résident dans l'espace de noms <xref:Microsoft.SqlServer.Management.Trace>, qui requiert une référence au fichier Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="f72c4-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="f72c4-123">Les objets `Trace` et `Replay` requièrent un objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> pour établir une connexion à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f72c4-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f72c4-124">L'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> réside dans l'espace de noms <xref:Microsoft.SqlServer.Management.Common>, qui requiert une référence au fichier Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="f72c4-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f72c4-125">Les objets `Trace` et `Replay` ne sont pas pris en charge sur une plate-forme 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f72c4-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
