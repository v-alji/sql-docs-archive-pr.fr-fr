---
title: Spécifier les événements et les colonnes de données d’un fichier de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599716"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="6e01f-102">Spécifier les événements et les colonnes de données d'un fichier de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="6e01f-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="6e01f-103">Cette rubrique explique comment spécifier les classes d'événements et les colonnes de données des traces à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e01f-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="6e01f-104">Pour spécifier les événements et les colonnes de données d'une trace</span><span class="sxs-lookup"><span data-stu-id="6e01f-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="6e01f-105">Dans la boîte de dialogue **Propriétés de la trace** ou **Propriétés du modèle de trace** , cliquez sur l’onglet **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="6e01f-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="6e01f-106">L’onglet **Sélection des événements** contient un contrôle de grille.</span><span class="sxs-lookup"><span data-stu-id="6e01f-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="6e01f-107">Le contrôle de grille est une table qui contient chacune des classes d'événements traçables.</span><span class="sxs-lookup"><span data-stu-id="6e01f-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="6e01f-108">La table contient une ligne par classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="6e01f-108">The table contains one row for each event class.</span></span> <span data-ttu-id="6e01f-109">Les classes d'événements peuvent différer légèrement selon le type et la version du serveur auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="6e01f-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="6e01f-110">Les classes d’événements sont identifiées dans la colonne **Events**de la grille, et groupées par catégorie d’événement.</span><span class="sxs-lookup"><span data-stu-id="6e01f-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="6e01f-111">Les autres colonnes répertorient les colonnes de données pouvant être retournées pour chaque classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="6e01f-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="6e01f-112">Sous l’onglet **Sélection des événements**, utilisez la grille pour ajouter ou supprimer des événements et des colonnes de données dans le fichier de trace.</span><span class="sxs-lookup"><span data-stu-id="6e01f-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="6e01f-113">Pour supprimer des événements de la trace, décochez la case dans la colonne **Événements** pour chaque classe d’événements.</span><span class="sxs-lookup"><span data-stu-id="6e01f-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="6e01f-114">Pour inclure des événements dans une trace, cochez la case dans la colonne **Événements** pour chaque classe d’événements ou activez une colonne de données qui correspond à un événement.</span><span class="sxs-lookup"><span data-stu-id="6e01f-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6e01f-115">Si vous envisagez de corréler la trace avec les données du Moniteur système ou de l’Analyseur de performances, vous devez inclure dans la trace les colonnes de données **Heure de début** et **Heure de fin** .</span><span class="sxs-lookup"><span data-stu-id="6e01f-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="6e01f-116">Lorsque vous incluez une classe d'événements, chaque colonne de données associée est également insérée dans la trace, sous réserve que vous ayez activé la case à cocher d'un événement.</span><span class="sxs-lookup"><span data-stu-id="6e01f-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="6e01f-117">Si vous avez activé la case à cocher d'une colonne particulière, seule cette colonne est incluse dans la trace.</span><span class="sxs-lookup"><span data-stu-id="6e01f-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="6e01f-118">Pour supprimer des colonnes de données d’une classe d’événements, décochez les cases de la colonne de données dans la ligne de la classe d’événements, ou cliquez avec le bouton droit sur l’en-tête de colonne, puis sélectionnez l’option **Désélectionner la colonne** .</span><span class="sxs-lookup"><span data-stu-id="6e01f-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="6e01f-119">Appliquez éventuellement des filtres à la trace.</span><span class="sxs-lookup"><span data-stu-id="6e01f-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="6e01f-120">Pour plus d’informations, consultez [Filtrer des événements dans une trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="6e01f-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e01f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e01f-121">See Also</span></span>  
 [<span data-ttu-id="6e01f-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6e01f-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
