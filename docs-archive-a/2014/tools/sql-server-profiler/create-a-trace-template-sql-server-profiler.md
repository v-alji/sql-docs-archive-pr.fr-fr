---
title: Créer un modèle de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694939"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="be79a-102">Créer un modèle de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="be79a-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="be79a-103">Cette rubrique décrit la façon de créer un nouveau modèle de trace au moyen du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be79a-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="be79a-104">Pour créer un modèle de trace</span><span class="sxs-lookup"><span data-stu-id="be79a-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="be79a-105">Dans le menu **Fichier** , pointez sur **Modèles**, puis cliquez sur **Nouveau modèle**.</span><span class="sxs-lookup"><span data-stu-id="be79a-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="be79a-106">Dans la boîte de dialogue **Propriétés du modèle de trace** , sélectionnez un type de serveur dans la liste **Sélectionner le type de serveur**.</span><span class="sxs-lookup"><span data-stu-id="be79a-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="be79a-107">Dans la zone **Nom du nouveau modèle** , entrez un nom de modèle.</span><span class="sxs-lookup"><span data-stu-id="be79a-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="be79a-108">Éventuellement, cliquez sur **Baser le nouveau modèle sur un modèle existant**, puis sélectionnez un modèle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="be79a-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="be79a-109">Tous les événements, les colonnes de données et les filtres sont initialement définis comme spécifiés dans le modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="be79a-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="be79a-110">Éventuellement, cliquez sur **Utiliser comme modèle par défaut pour le type de serveur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="be79a-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="be79a-111">Sous l’onglet **Sélection des événements** , ajoutez, supprimez ou modifiez des événements, des colonnes de données ou des filtres.</span><span class="sxs-lookup"><span data-stu-id="be79a-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="be79a-112">Sous l’onglet **Sélection des événements**, utilisez le contrôle de la grille pour ajouter ou supprimer des événements et des colonnes de données dans le fichier de trace comme suit :</span><span class="sxs-lookup"><span data-stu-id="be79a-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="be79a-113">Pour ajouter un événement, développez la catégorie d’événements appropriée dans la colonne **Événements** , puis sélectionnez le nom de l’événement.</span><span class="sxs-lookup"><span data-stu-id="be79a-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="be79a-114">Lorsque vous ajoutez un événement, toutes les colonnes de données sont incluses par défaut.</span><span class="sxs-lookup"><span data-stu-id="be79a-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="be79a-115">Pour supprimer une colonne de données d'un événement dans une trace, désactivez la case à cocher dans la colonne de données de l'événement.</span><span class="sxs-lookup"><span data-stu-id="be79a-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="be79a-116">Pour ajouter des filtres, cliquez sur le nom de la colonne de données et définissez les critères de filtrage dans la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="be79a-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="be79a-117">Vous pouvez également cliquer avec le bouton droit sur le nom de la colonne de données et cliquer sur **Modifier le filtre des colonnes** pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="be79a-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="be79a-118">Cliquez sur **OK** pour ajouter le filtre.</span><span class="sxs-lookup"><span data-stu-id="be79a-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="be79a-119">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="be79a-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be79a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be79a-120">See Also</span></span>  
 <span data-ttu-id="be79a-121">[Spécifier les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="be79a-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="be79a-122">[Dériver un modèle à partir d’une trace en cours d’exécution &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="be79a-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="be79a-123">[Dériver un modèle à partir d’un fichier de trace ou d’une table de trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="be79a-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="be79a-124">[Modèles et autorisations du générateur de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="be79a-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="be79a-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="be79a-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
