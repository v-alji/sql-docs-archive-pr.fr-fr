---
title: Modifier un filtre (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604333"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="c1a49-102">Modifier un filtre (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c1a49-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="c1a49-103">Vous ajoutez des filtres pour tracer des modèles, qui contiennent les définitions de trace, afin de limiter le nombre d'événements recueillis par une trace.</span><span class="sxs-lookup"><span data-stu-id="c1a49-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="c1a49-104">La limitation du nombre d'événements recueillis peut atténuer les effets du traçage sur les performances.</span><span class="sxs-lookup"><span data-stu-id="c1a49-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="c1a49-105">Si vous définissez des filtres pour un modèle de trace et remarquez que la trace ne recueille pas le type d'informations dont vous avez besoin, vous pouvez modifier le filtre.</span><span class="sxs-lookup"><span data-stu-id="c1a49-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="c1a49-106">Pour modifier un filtre</span><span class="sxs-lookup"><span data-stu-id="c1a49-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="c1a49-107">Dans [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], ouvrez le modèle du filtre de trace à modifier.</span><span class="sxs-lookup"><span data-stu-id="c1a49-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="c1a49-108">Dans le menu **Fichier** , cliquez sur **Modèles**, puis choisissez **Modifier le modèle**.</span><span class="sxs-lookup"><span data-stu-id="c1a49-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="c1a49-109">Dans la boîte de dialogue **Propriétés du modèle de trace** , sous l’onglet **Général** , sélectionnez un modèle dans la liste **Sélectionner le nom du modèle** .</span><span class="sxs-lookup"><span data-stu-id="c1a49-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="c1a49-110">Cliquez sur l’onglet **Sélection des événements** .</span><span class="sxs-lookup"><span data-stu-id="c1a49-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="c1a49-111">L’onglet **Sélection des événements** contient un contrôle de grille.</span><span class="sxs-lookup"><span data-stu-id="c1a49-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="c1a49-112">Le contrôle de grille est une table qui contient chacune des classes d'événements traçables.</span><span class="sxs-lookup"><span data-stu-id="c1a49-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="c1a49-113">La table contient une ligne par classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="c1a49-113">The table contains one row for each event class.</span></span> <span data-ttu-id="c1a49-114">Les classes d'événements peuvent différer légèrement, selon le type et la version du serveur auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="c1a49-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="c1a49-115">Les classes d’événements sont identifiées dans la colonne **Events**de la grille, et groupées par catégorie d’événement.</span><span class="sxs-lookup"><span data-stu-id="c1a49-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="c1a49-116">Les autres colonnes répertorient les colonnes de données pouvant être retournées pour chaque classe d'événements.</span><span class="sxs-lookup"><span data-stu-id="c1a49-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="c1a49-117">Cliquez sur **Filtres de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="c1a49-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="c1a49-118">Dans la boîte de dialogue **Modifier le filtre** , cliquez sur la valeur en regard de l’opérateur de comparaison à modifier, puis tapez la nouvelle valeur ou supprimez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c1a49-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="c1a49-119">Vous pouvez également ajouter des filtres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c1a49-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="c1a49-120">Cliquez sur **OK** et enregistrez le modèle.</span><span class="sxs-lookup"><span data-stu-id="c1a49-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a49-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1a49-121">See Also</span></span>  
 [<span data-ttu-id="c1a49-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c1a49-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
