---
title: Filtrer des événements dans une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706928"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="09b80-102">Filtrer des événements dans une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="09b80-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="09b80-103">Les filtres limitent les événements recueillis dans une trace.</span><span class="sxs-lookup"><span data-stu-id="09b80-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="09b80-104">Si aucun filtre n'est défini, tous les événements des classes d'événements sélectionnées sont retournés dans le résultat de trace.</span><span class="sxs-lookup"><span data-stu-id="09b80-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="09b80-105">Il n'est pas obligatoire de définir un filtre pour une trace.</span><span class="sxs-lookup"><span data-stu-id="09b80-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="09b80-106">Toutefois, un filtre réduit la charge liée aux opérations de traçage.</span><span class="sxs-lookup"><span data-stu-id="09b80-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="09b80-107">Pour ajouter un filtre à une définition de trace, vous devez utiliser l’onglet **Sélection des événements** de la boîte de dialogue **Propriétés de la trace** ou **Propriétés du modèle de trace** .</span><span class="sxs-lookup"><span data-stu-id="09b80-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="09b80-108">Pour filtrer les événements dans une trace</span><span class="sxs-lookup"><span data-stu-id="09b80-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="09b80-109">Dans la boîte de dialogue **Propriétés de la trace** ou **Propriétés du modèle de trace** , cliquez sur l’onglet **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="09b80-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="09b80-110">L’onglet **Sélection des événements** contient un contrôle de grille.</span><span class="sxs-lookup"><span data-stu-id="09b80-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="09b80-111">Le contrôle de grille est une table qui contient chacune des classes d'événements traçables.</span><span class="sxs-lookup"><span data-stu-id="09b80-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="09b80-112">La table contient une ligne par classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="09b80-112">The table contains one row for each event class.</span></span> <span data-ttu-id="09b80-113">Les classes d'événements peuvent différer légèrement, selon le type et la version du serveur auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="09b80-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="09b80-114">Les classes d’événements sont identifiées dans la colonne **Events**de la grille, et groupées par catégorie d’événement.</span><span class="sxs-lookup"><span data-stu-id="09b80-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="09b80-115">Les autres colonnes répertorient les colonnes de données pouvant être retournées pour chaque classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="09b80-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="09b80-116">Cliquez sur **Filtres de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="09b80-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="09b80-117">La boîte de dialogue **Modifier le filtre**s’affiche.</span><span class="sxs-lookup"><span data-stu-id="09b80-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="09b80-118">La boîte de dialogue **Modifier le filtre** contient une liste d’opérateurs de comparaison que vous pouvez utiliser pour filtrer les événements dans une trace.</span><span class="sxs-lookup"><span data-stu-id="09b80-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="09b80-119">Pour appliquer un filtre, cliquez sur l'opérateur de comparaison et tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="09b80-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="09b80-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="09b80-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="09b80-121">**Considérations :**</span><span class="sxs-lookup"><span data-stu-id="09b80-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="09b80-122">Si vous définissez un filtre sur les colonnes **StartTime** et **EndTime** de l’onglet Sélection des événements, vérifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="09b80-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="09b80-123">La date est saisie au format suivant : `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="09b80-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="09b80-124">OU</span><span class="sxs-lookup"><span data-stu-id="09b80-124">-OR-</span></span>  
  
    -   <span data-ttu-id="09b80-125">La case**Utiliser des paramètres régionaux pour afficher les valeurs de date et d’heure** est cochée dans la boîte de dialogue **Options générales** .</span><span class="sxs-lookup"><span data-stu-id="09b80-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="09b80-126">Pour afficher la boîte de dialogue **Options générales**, dans le menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Outils**, cliquez sur **Option**.</span><span class="sxs-lookup"><span data-stu-id="09b80-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="09b80-127">\- ET -</span><span class="sxs-lookup"><span data-stu-id="09b80-127">-AND-</span></span>  
  
    -   <span data-ttu-id="09b80-128">La date saisie se situe entre le 1er janvier 1753 et le 31 décembre 9999.</span><span class="sxs-lookup"><span data-stu-id="09b80-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="09b80-129">Si le traçage des événements est réalisé avec l’utilitaire **osql** ou **sqlcmd** , il faut toujours ajouter **%** aux filtres de la colonne de données **TextData** .</span><span class="sxs-lookup"><span data-stu-id="09b80-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b80-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09b80-130">See Also</span></span>  
 [<span data-ttu-id="09b80-131">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="09b80-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
