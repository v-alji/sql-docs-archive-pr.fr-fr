---
title: Filtrer des événements en fonction de leur heure de fin (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708851"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="1f5c3-102">Filtrer des événements en fonction de leur heure de fin (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1f5c3-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="1f5c3-103">Cette rubrique explique comment filtrer des événements de trace en fonction de leur heure de fin à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f5c3-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="1f5c3-104">Pour filtrer des événements en fonction de leur heure de fin</span><span class="sxs-lookup"><span data-stu-id="1f5c3-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="1f5c3-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f5c3-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="1f5c3-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f5c3-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="1f5c3-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="1f5c3-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="1f5c3-109">Dans la boîte de dialogue **Propriétés de la trace** , assurez-vous que l'onglet **Général** est sélectionné, puis entrez un nom dans la zone de texte **Nom de la trace** .</span><span class="sxs-lookup"><span data-stu-id="1f5c3-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="1f5c3-110">Dans la liste **Utiliser le modèle**, sélectionnez un modèle de trace.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="1f5c3-111">Le cas échéant, spécifiez un fichier ou une table de destination pour y enregistrer les résultats du suivi.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="1f5c3-112">Dans le menu **Sélection des événements**, cliquez sur la colonne de données **Heure de fin** pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="1f5c3-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="1f5c3-113">Vous pouvez également cliquer avec le bouton droit sur l’en-tête de la colonne, puis sélectionner **Modifier le filtre des colonnes**.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="1f5c3-114">Développez **supérieur à** ou **inférieur à**, puis entrez une `datetime` valeur dans le champ qui apparaît sous l’opérateur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="1f5c3-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f5c3-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f5c3-115">See Also</span></span>  
 <span data-ttu-id="1f5c3-116">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1f5c3-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="1f5c3-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1f5c3-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
