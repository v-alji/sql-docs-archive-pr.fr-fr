---
title: Propriétés de la trace (onglet sélection des événements) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703231"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="4804f-102">Propriétés de la trace (onglet Sélection des événements)</span><span class="sxs-lookup"><span data-stu-id="4804f-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="4804f-103">Utilisez l'onglet **Sélection des événements** de la boîte de dialogue **Propriétés de la trace** pour afficher ou spécifier les événements à tracer et les colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="4804f-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4804f-104">Options</span><span class="sxs-lookup"><span data-stu-id="4804f-104">Options</span></span>  
 <span data-ttu-id="4804f-105">Colonne**Events**</span><span class="sxs-lookup"><span data-stu-id="4804f-105">**Events** column</span></span>  
 <span data-ttu-id="4804f-106">Spécifiez les événements à tracer en activant ou en désactivant les cases à cocher dans la colonne des événements.</span><span class="sxs-lookup"><span data-stu-id="4804f-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="4804f-107">Les**événements** sont organisés par catégorie.</span><span class="sxs-lookup"><span data-stu-id="4804f-107">**Events** are organized by event category.</span></span> <span data-ttu-id="4804f-108">Les classes d'événements spécifiées dans le modèle sont automatiquement sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="4804f-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="4804f-109">Pour plus d'informations, consultez [Référence de classe d'événements SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4804f-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="4804f-110">Colonnes de données</span><span class="sxs-lookup"><span data-stu-id="4804f-110">Data columns</span></span>  
 <span data-ttu-id="4804f-111">Précisez les colonnes de données à tracer en activant la case à cocher correspondant à l'événement et à la colonne de données requis.</span><span class="sxs-lookup"><span data-stu-id="4804f-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="4804f-112">Toutes les colonnes d'événements pertinentes sont cochées par défaut pour chaque événement inclus dans la trace.</span><span class="sxs-lookup"><span data-stu-id="4804f-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="4804f-113">Spécifiez les filtres en cliquant sur les en-têtes de colonne de données et entrant les critères du filtre.</span><span class="sxs-lookup"><span data-stu-id="4804f-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="4804f-114">Les colonnes de données filtrées sont indiquées par une icône de filtre à gauche de l'étiquette de colonne dans la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="4804f-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4804f-115">Pour plus d’informations, consultez [SQL Server Profiler - Modifier le filtre](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="4804f-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="4804f-116">**Afficher tous les événements**</span><span class="sxs-lookup"><span data-stu-id="4804f-116">**Show all events**</span></span>  
 <span data-ttu-id="4804f-117">Affiche tous les événements disponibles.</span><span class="sxs-lookup"><span data-stu-id="4804f-117">Show all available events.</span></span> <span data-ttu-id="4804f-118">Par défaut, seules les lignes sélectionnées dans la grille **Sélection des événements** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="4804f-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="4804f-119">Désactivez cette case à cocher pour masquer tous les événements non sélectionnés dans la grille **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="4804f-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="4804f-120">**Afficher toutes les colonnes**</span><span class="sxs-lookup"><span data-stu-id="4804f-120">**Show all columns**</span></span>  
 <span data-ttu-id="4804f-121">Affiche toutes les colonnes de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="4804f-121">Show all available data columns.</span></span> <span data-ttu-id="4804f-122">Par défaut, seules les colonnes de données sélectionnées sont affichées.</span><span class="sxs-lookup"><span data-stu-id="4804f-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="4804f-123">Désactivez cette case à cocher pour masquer toutes les colonnes de données non sélectionnées dans la grille **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="4804f-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="4804f-124">**Filtres de colonnes**</span><span class="sxs-lookup"><span data-stu-id="4804f-124">**Column Filters**</span></span>  
 <span data-ttu-id="4804f-125">Affiche la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="4804f-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4804f-126">Vous pouvez utiliser celle-ci pour modifier les filtres de colonnes de données.</span><span class="sxs-lookup"><span data-stu-id="4804f-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="4804f-127">**Organiser les colonnes**</span><span class="sxs-lookup"><span data-stu-id="4804f-127">**Organize Columns**</span></span>  
 <span data-ttu-id="4804f-128">Modifie l'ordre des colonnes dans la trace et regroupe les résultats suivant une ou plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="4804f-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4804f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4804f-129">See Also</span></span>  
 <span data-ttu-id="4804f-130">[Spécifiez les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4804f-131">[Organiser les colonnes affichées dans une trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4804f-132">[Filtrer les événements dans une trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4804f-133">[Afficher les informations de filtre &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4804f-134">[Modifier un filtre &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4804f-135">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="4804f-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="4804f-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4804f-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
