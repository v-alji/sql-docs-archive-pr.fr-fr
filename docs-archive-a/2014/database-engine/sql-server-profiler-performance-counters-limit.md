---
title: SQL Server Profiler-limite des compteurs de performances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.performancecounterlimit.f1
helpviewer_keywords:
- Performance Counters List dialog box
ms.assetid: d10140ef-36c4-449c-b365-1cff1b2524e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27bda135abaf9d91b078e36a69a87098a734acbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705375"
---
# <a name="sql-server-profiler---performance-counters-limit"></a><span data-ttu-id="fe0b8-102">Générateur de profils SQL Server - Limite des compteurs de performances</span><span class="sxs-lookup"><span data-stu-id="fe0b8-102">SQL Server Profiler - Performance Counters Limit</span></span>
  <span data-ttu-id="fe0b8-103">Utilisez la boîte de dialogue Limite des compteurs de performances pour limiter les informations provenant d'un fichier journal de performances du Moniteur système lors de sa corrélation avec une trace du [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe0b8-103">Use the Performance Counters Limit dialog box to limit the information from a System Monitor performance log file when correlating it with a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace.</span></span> <span data-ttu-id="fe0b8-104">Cette boîte de dialogue vous permet de sélectionner les compteurs qui doivent être affichés et utilisés pour la corrélation.</span><span class="sxs-lookup"><span data-stu-id="fe0b8-104">You can use this dialog box to select counters that should be displayed and used for correlation.</span></span>  
  
 <span data-ttu-id="fe0b8-105">La boîte de dialogue **Limite des compteurs de performances** est remplie avec les objets et compteurs de performances contenus dans le fichier journal de performances.</span><span class="sxs-lookup"><span data-stu-id="fe0b8-105">The **Performance Counters Limit** dialog box is populated with the performance objects and counters that the performance log file contains.</span></span>  
  
### <a name="to-select-performance-objects-and-counters-to-correlate-with-a-trace"></a><span data-ttu-id="fe0b8-106">Pour sélectionner les objets et compteurs de performances à corréler avec une trace</span><span class="sxs-lookup"><span data-stu-id="fe0b8-106">To select performance objects and counters to correlate with a trace</span></span>  
  
1.  <span data-ttu-id="fe0b8-107">Développez un objet de performance pour déterminer les compteurs qui sont inclus dans le fichier journal de performances.</span><span class="sxs-lookup"><span data-stu-id="fe0b8-107">Expand a performance object to see which counters are included in the performance log file.</span></span>  
  
2.  <span data-ttu-id="fe0b8-108">Activez les compteurs que vous souhaitez corréler avec le fichier de trace du [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe0b8-108">Check the counters that you want to correlate with the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace file.</span></span>  
  
     <span data-ttu-id="fe0b8-109">Si vous souhaitez sélectionner tous les compteurs pour un objet de performance, activez la case à cocher adjacente à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="fe0b8-109">If you want to select all counters for a performance object, check the box that is adjacent to the performance object.</span></span> <span data-ttu-id="fe0b8-110">L'activation du nœud de premier niveau, qui indique l'ordinateur, entraîne la sélection de tous les objets et compteurs de performances contenus dans le fichier journal de performances.</span><span class="sxs-lookup"><span data-stu-id="fe0b8-110">Checking the topmost node, which indicates the computer, selects all performance objects and counters contained in the performance log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0b8-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe0b8-111">See Also</span></span>  
 [<span data-ttu-id="fe0b8-112">Corréler une trace aux données du journal de performances Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="fe0b8-112">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data.md)  
  
  
