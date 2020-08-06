---
title: Propriétés du modèle de trace (onglet sélection des événements) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707768"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="b9185-102">Propriétés du modèle de trace (onglet Sélection des événements)</span><span class="sxs-lookup"><span data-stu-id="b9185-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="b9185-103">L'onglet **Sélection des événements** de la boîte de dialogue **Propriétés du modèle de trace** vous permet d'afficher, de modifier ou de spécifier les classes d'événements et les colonnes de données à inclure dans un modèle de trace [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9185-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9185-104">Options</span><span class="sxs-lookup"><span data-stu-id="b9185-104">Options</span></span>  
 <span data-ttu-id="b9185-105">Colonne**Events**</span><span class="sxs-lookup"><span data-stu-id="b9185-105">**Events** column</span></span>  
 <span data-ttu-id="b9185-106">Permet de spécifier les événements à tracer en activant ou en désactivant la case à cocher dans la colonne d'événement.</span><span class="sxs-lookup"><span data-stu-id="b9185-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="b9185-107">Les événements sont organisés par catégorie d'événement.</span><span class="sxs-lookup"><span data-stu-id="b9185-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="b9185-108">Si vous avez sélectionné **Baser le nouveau modèle sur un modèle existant** sous l'onglet **Général** , des événements sont sélectionnés automatiquement en fonction du modèle spécifié.</span><span class="sxs-lookup"><span data-stu-id="b9185-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="b9185-109">Pour plus d'informations sur les classes d'événements, consultez [Référence de classe d'événements SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b9185-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="b9185-110">Colonnes de données</span><span class="sxs-lookup"><span data-stu-id="b9185-110">Data columns</span></span>  
 <span data-ttu-id="b9185-111">Permet de spécifier les colonnes de données à tracer en activant la case à cocher qui correspond à la colonne d'événement et de données dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="b9185-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="b9185-112">Toutes les colonnes d'événements appropriées sont sélectionnées par défaut pour chaque événement inclus dans la trace, si la case à cocher correspondant à l'événement est activée.</span><span class="sxs-lookup"><span data-stu-id="b9185-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="b9185-113">Si vous avez activé **Baser le nouveau modèle sur un modèle existant** sous l'onglet **Général** , les colonnes de données et les filtres sont sélectionnés automatiquement en fonction du modèle spécifié.</span><span class="sxs-lookup"><span data-stu-id="b9185-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="b9185-114">Spécifiez les filtres en cliquant sur les en-têtes de colonne de données et entrant les critères du filtre.</span><span class="sxs-lookup"><span data-stu-id="b9185-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="b9185-115">Les colonnes de données filtrées sont indiquées par une icône de filtre à gauche de l'étiquette de colonne dans la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="b9185-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="b9185-116">**Afficher tous les événements**</span><span class="sxs-lookup"><span data-stu-id="b9185-116">**Show all events**</span></span>  
 <span data-ttu-id="b9185-117">Affiche tous les événements disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9185-117">Show all available events.</span></span> <span data-ttu-id="b9185-118">Cette option est activée par défaut si vous créez un nouveau modèle qui n'est pas basé sur un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="b9185-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="b9185-119">Désactivez l'option pour masquer tous les événements non sélectionnés dans la grille **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="b9185-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="b9185-120">**Afficher toutes les colonnes**</span><span class="sxs-lookup"><span data-stu-id="b9185-120">**Show all columns**</span></span>  
 <span data-ttu-id="b9185-121">Affiche toutes les colonnes de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9185-121">Show all available data columns.</span></span> <span data-ttu-id="b9185-122">Cette option est activée par défaut si vous créez un nouveau modèle qui n'est pas basé sur un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="b9185-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="b9185-123">Désactivez l'option pour masquer toutes les colonnes de données non sélectionnées dans la grille **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="b9185-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="b9185-124">**Filtres de colonnes**</span><span class="sxs-lookup"><span data-stu-id="b9185-124">**Column Filters**</span></span>  
 <span data-ttu-id="b9185-125">Lance la boîte de dialogue **Modifier le filtre**, qui affiche une icône de filtre à gauche de l’étiquette d’une colonne de données.</span><span class="sxs-lookup"><span data-stu-id="b9185-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="b9185-126">La boîte de dialogue **Modifier le filtre** vous permet de modifier les filtres des colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="b9185-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="b9185-127">**Organiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="b9185-127">**Organize Columns**</span></span>  
 <span data-ttu-id="b9185-128">Modifie l'ordre des colonnes dans la trace et regroupe les résultats suivant une ou plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="b9185-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9185-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9185-129">See Also</span></span>  
 <span data-ttu-id="b9185-130">[Spécifiez les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="b9185-131">[Organiser les colonnes affichées dans une trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="b9185-132">[Filtrer les événements dans une trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="b9185-133">[Afficher les informations de filtre &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="b9185-134">[Modifier un filtre &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="b9185-135">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="b9185-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="b9185-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b9185-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
