---
title: Afficher les informations de filtre (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603186"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="98671-102">Afficher des informations de filtre (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="98671-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="98671-103">Cette rubrique indique comment afficher des filtres sur des colonnes de données pour des classes d'événements en utilisant [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98671-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="98671-104">Pour afficher les informations de filtrage</span><span class="sxs-lookup"><span data-stu-id="98671-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="98671-105">Ouvrez un fichier de trace, une table de trace ou un script SQL, et dans le menu **Fichier** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="98671-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="98671-106">Si vous modifiez un modèle de trace ou créez une nouvelle trace, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="98671-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="98671-107">Sous l’onglet **Sélection des événements** , cliquez avec le bouton droit sur le nom de la colonne de données du filtre à afficher, puis cliquez sur **Modifier le filtre des colonnes**.</span><span class="sxs-lookup"><span data-stu-id="98671-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="98671-108">Dans la boîte de dialogue **Modifier le filtre** , développez les opérateurs de comparaison de filtre pour afficher la valeur affectée pour le critère spécifié.</span><span class="sxs-lookup"><span data-stu-id="98671-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="98671-109">Recommencez les étapes 2 et 3 pour toutes les colonnes pour lesquelles vous souhaitez afficher des informations de filtre.</span><span class="sxs-lookup"><span data-stu-id="98671-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98671-110">Les opérateurs de comparaison avec des valeurs affectées apparaissent en caractères gras.</span><span class="sxs-lookup"><span data-stu-id="98671-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98671-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98671-111">See Also</span></span>  
 [<span data-ttu-id="98671-112">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="98671-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
