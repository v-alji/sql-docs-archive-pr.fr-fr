---
title: Modifier un modèle de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601640"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="32490-102">Modifier un modèle de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="32490-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="32490-103">Cette rubrique explique comment modifier un modèle de trace avec le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32490-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="32490-104">Pour modifier un modèle de trace</span><span class="sxs-lookup"><span data-stu-id="32490-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="32490-105">Dans le menu **Fichier** , pointez sur **Modèles**, puis cliquez sur **Modifier le modèle**.</span><span class="sxs-lookup"><span data-stu-id="32490-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="32490-106">Dans la boîte de dialogue **Propriétés du modèle de trace** , sous l’onglet **Général** , vous pouvez modifier le type de serveur et le nom de modèle, ou utiliser un modèle par défaut pour le type de serveur.</span><span class="sxs-lookup"><span data-stu-id="32490-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="32490-107">Dans l’onglet **sélection des événements**, utilisez le contrôle Grid pour ajouter ou supprimer des événements et des colonnes de données dans le fichier de trace comme suit.</span><span class="sxs-lookup"><span data-stu-id="32490-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="32490-108">Pour ajouter un événement, développez la catégorie d’événements appropriée dans la colonne **Événements** , puis sélectionnez le nom de l’événement.</span><span class="sxs-lookup"><span data-stu-id="32490-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="32490-109">Lorsque vous ajoutez un événement, toutes les colonnes de données sont incluses par défaut.</span><span class="sxs-lookup"><span data-stu-id="32490-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="32490-110">Pour supprimer une colonne de données d'un événement dans une trace, désactivez la case à cocher dans la colonne de données de l'événement.</span><span class="sxs-lookup"><span data-stu-id="32490-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="32490-111">Pour ajouter des filtres, cliquez sur le nom de la colonne de données et définissez les critères de filtrage dans la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="32490-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="32490-112">Vous pouvez également cliquer avec le bouton droit sur le nom de la colonne de données et cliquer sur **Modifier le filtre des colonnes** pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="32490-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="32490-113">Cliquez sur **OK** pour ajouter le filtre.</span><span class="sxs-lookup"><span data-stu-id="32490-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="32490-114">Cliquez sur **Enregistrer**ou **Enregistrer sous**pour enregistrer le modèle de trace sous un autre nom.</span><span class="sxs-lookup"><span data-stu-id="32490-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32490-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32490-115">See Also</span></span>  
 <span data-ttu-id="32490-116">[Spécifiez les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="32490-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="32490-117">[Dériver un modèle à partir d’une trace en cours d’exécution &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="32490-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="32490-118">[Dériver un modèle à partir d’un fichier de trace ou d’une table de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="32490-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="32490-119">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="32490-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="32490-120">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="32490-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
