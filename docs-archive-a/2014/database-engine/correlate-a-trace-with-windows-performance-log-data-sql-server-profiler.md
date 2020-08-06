---
title: Mettre en corrélation une trace avec les données du journal de performances Windows (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605712"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="968ae-102">Corréler une trace aux données du journal de performances Windows (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="968ae-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="968ae-103">peut corréler les compteurs du moniteur système Microsoft Windows avec [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] les [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] événements ou.</span><span class="sxs-lookup"><span data-stu-id="968ae-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="968ae-104">Le Moniteur système Windows consigne dans des journaux de performances l'activité du système pour des compteurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="968ae-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="968ae-105">Pour plus d'informations sur le partage de journaux entre plusieurs versions de Windows, consultez la procédure à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="968ae-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="968ae-106">Pour corréler une trace aux données du journal de performances</span><span class="sxs-lookup"><span data-stu-id="968ae-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="968ae-107">Dans [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], ouvrez un fichier de trace ou une table de trace enregistrée.</span><span class="sxs-lookup"><span data-stu-id="968ae-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="968ae-108">Il est impossible de corréler une trace d'exécution qui regroupe encore des données d'événement.</span><span class="sxs-lookup"><span data-stu-id="968ae-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="968ae-109">Pour garantir la précision de la corrélation aux données du Moniteur système, la trace doit contenir les colonnes de données **StartTime** et **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="968ae-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="968ae-110">Dans le menu [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File**, cliquez sur **Importer les données de performance**.</span><span class="sxs-lookup"><span data-stu-id="968ae-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="968ae-111">Dans la boîte de dialogue **Ouvrir** , sélectionnez un fichier qui contient un journal de performances.</span><span class="sxs-lookup"><span data-stu-id="968ae-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="968ae-112">Les données du journal de performances doivent être capturées pendant la même période que celle de la capture des données de trace.</span><span class="sxs-lookup"><span data-stu-id="968ae-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="968ae-113">Dans la boîte de dialogue **Limite des compteurs de performances** , activez les cases à cocher correspondant aux objets et aux compteurs du Moniteur système que vous souhaitez afficher aux côtés de la trace.</span><span class="sxs-lookup"><span data-stu-id="968ae-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="968ae-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="968ae-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="968ae-115">Sélectionnez un événement dans la fenêtre des événements de trace ou faites défiler plusieurs lignes adjacentes dans la fenêtre des événements de trace à l'aide des touches de direction.</span><span class="sxs-lookup"><span data-stu-id="968ae-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="968ae-116">La barre rouge verticale de la fenêtre **Données du Moniteur système** indique les données du journal de performances corrélées à l’événement de trace sélectionné.</span><span class="sxs-lookup"><span data-stu-id="968ae-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="968ae-117">Cliquez sur un point qui vous intéresse dans le graphique du Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="968ae-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="968ae-118">La ligne de trace correspondante la plus proche dans le temps est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="968ae-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="968ae-119">Pour agrandir un intervalle de temps, cliquez sur le pointeur de la souris et faites-le glisser dans le graphique du Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="968ae-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="968ae-120">Pour créer des journaux de performances pouvant être partagés avec différentes versions de Windows</span><span class="sxs-lookup"><span data-stu-id="968ae-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="968ae-121">Dans le Panneau de configuration, ouvrez **Outils d’administration**, puis double-cliquez sur **Performances**.</span><span class="sxs-lookup"><span data-stu-id="968ae-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="968ae-122">Dans la boîte de dialogue **Performances** , développez **Journaux et alertes de performances**, cliquez avec le bouton droit sur **Journaux de compteurs**, puis cliquez sur **Nouveaux paramètres de journal**.</span><span class="sxs-lookup"><span data-stu-id="968ae-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="968ae-123">Tapez un nom pour le journal de compteurs, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="968ae-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="968ae-124">Sous l’onglet **Général** , cliquez sur **Ajouter des compteurs**.</span><span class="sxs-lookup"><span data-stu-id="968ae-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="968ae-125">Dans la liste **Objet de performance** , sélectionnez un objet de performance à surveiller.</span><span class="sxs-lookup"><span data-stu-id="968ae-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="968ae-126">Les noms des objets de performances [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour des instances par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] commencent par [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et les instances nommées commencent par MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="968ae-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="968ae-127">Ajoutez autant de compteurs que nécessaire pour votre instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et d'autres valeurs importantes, telles que le temps processeur et le temps du disque.</span><span class="sxs-lookup"><span data-stu-id="968ae-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="968ae-128">Quand vous avez terminé d’ajouter les compteurs, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="968ae-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="968ae-129">Définissez les valeurs de l’intervalle **Période d’échantillonnage des données** .</span><span class="sxs-lookup"><span data-stu-id="968ae-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="968ae-130">Commencez par un intervalle modeste, par exemple 5 minutes, puis modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="968ae-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="968ae-131">Sous l’onglet **Fichiers journaux** choisissez **Fichier texte (séparé par des virgules)** dans la liste **Type de fichier journal** .</span><span class="sxs-lookup"><span data-stu-id="968ae-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="968ae-132">Vous pouvez partager entre plusieurs versions de Windows les fichiers texte de journal délimités par une virgule et les afficher ultérieurement dans des outils de création de rapports tels que Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="968ae-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="968ae-133">Sous l’onglet **Planification** , spécifiez une planification de surveillance.</span><span class="sxs-lookup"><span data-stu-id="968ae-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="968ae-134">Cliquez sur **OK** pour créer le journal de performances.</span><span class="sxs-lookup"><span data-stu-id="968ae-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968ae-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="968ae-135">See Also</span></span>  
 <span data-ttu-id="968ae-136">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="968ae-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="968ae-137">Démarrer SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="968ae-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
