---
title: Filtrer des événements en fonction de leur heure de début (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706927"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="1c909-102">Filtrer des événements en fonction de l'heure de début de l'événement (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1c909-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="1c909-103">Cette rubrique explique comment filtrer des événements de trace en fonction de leur heure de début à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c909-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="1c909-104">Pour filtrer un événement en fonction de son heure de début</span><span class="sxs-lookup"><span data-stu-id="1c909-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="1c909-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c909-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="1c909-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="1c909-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c909-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="1c909-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="1c909-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="1c909-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="1c909-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="1c909-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="1c909-110">Dans la liste de noms **Utiliser le modèle**, sélectionnez un modèle de trace.</span><span class="sxs-lookup"><span data-stu-id="1c909-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="1c909-111">Le cas échéant, spécifiez une destination pour les résultats de la trace.</span><span class="sxs-lookup"><span data-stu-id="1c909-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="1c909-112">Sous l’onglet **Sélection des événements**, cliquez sur l’en-tête de colonne **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="1c909-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="1c909-113">Vous pouvez également cliquer avec le bouton droit sur l’en-tête puis cliquer sur **Modifier le filtre des colonnes** pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="1c909-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="1c909-114">Développez **supérieur à** ou **inférieur à**, puis entrez une `datetime` valeur dans le champ qui apparaît sous l’opérateur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="1c909-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c909-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c909-115">See Also</span></span>  
 [<span data-ttu-id="1c909-116">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1c909-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
