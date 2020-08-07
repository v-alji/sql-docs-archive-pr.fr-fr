---
title: Enregistrer des graphiques d’interblocage (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611729"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="92e99-102">Enregistrer les événements Deadlock Graph (Générateur de profils SQL Server)</span><span class="sxs-lookup"><span data-stu-id="92e99-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="92e99-103">Cette rubrique décrit comment enregistrer un événement Deadlock Graph à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e99-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="92e99-104">Les événements Deadlock Graph sont enregistrés sous forme de fichiers XML.</span><span class="sxs-lookup"><span data-stu-id="92e99-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="92e99-105">Pour enregistrer séparément les événements Deadlock Graph</span><span class="sxs-lookup"><span data-stu-id="92e99-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="92e99-106">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="92e99-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="92e99-107">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="92e99-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92e99-108">Si la case **Démarrer le suivi juste après avoir établi la connexion** est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et la trace se lance.</span><span class="sxs-lookup"><span data-stu-id="92e99-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="92e99-109">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="92e99-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="92e99-110">Dans la boîte de dialogue Propriétés de la trace, saisissez un nom pour la trace dans la zone**Nom de la trace** .</span><span class="sxs-lookup"><span data-stu-id="92e99-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="92e99-111">Dans la liste **Utiliser le modèle** , sélectionnez un modèle de trace comme base ou sélectionnez **Vide** si vous ne souhaitez pas utiliser de modèle.</span><span class="sxs-lookup"><span data-stu-id="92e99-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="92e99-112">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="92e99-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="92e99-113">Activez la case à cocher**Enregistrer dans le fichier** pour capturer la trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="92e99-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="92e99-114">Spécifiez une valeur dans **Définir la taille de fichier maximale**.</span><span class="sxs-lookup"><span data-stu-id="92e99-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="92e99-115">Au besoin, activez les cases à cocher **Activer la substitution de fichier** et **Le serveur traite les données de trace**.</span><span class="sxs-lookup"><span data-stu-id="92e99-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="92e99-116">Activez la case à cocher **Enregistrer dans la table** pour capturer la trace dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="92e99-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="92e99-117">Si vous le souhaitez, cliquez sur **définir le nombre maximal de lignes**et spécifiez une valeur.</span><span class="sxs-lookup"><span data-stu-id="92e99-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="92e99-118">Le cas échéant, activez la case à cocher **Activer l'heure d'arrêt de la trace** et indiquez une date et une heure d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="92e99-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="92e99-119">Cliquez sur l’onglet **Sélection des événements**.</span><span class="sxs-lookup"><span data-stu-id="92e99-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="92e99-120">Dans la liste **Événements,** développez la catégorie d’événements **Verrous**et sélectionnez la case à cocher **Deadlock graph**.</span><span class="sxs-lookup"><span data-stu-id="92e99-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="92e99-121">Si la catégorie d'événements Verrous n'est pas disponible, activez la case à cocher **Afficher tous les événements** pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="92e99-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="92e99-122">La boîte de dialogue **Paramètres d’extraction des événements**est ajoutée à la boîte de dialogue **Propriétés de la trace**.</span><span class="sxs-lookup"><span data-stu-id="92e99-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="92e99-123">Dans le menu **Paramètres d’extraction des événements**cliquez sur **Enregistrer les événements Deadlock XML séparément**.</span><span class="sxs-lookup"><span data-stu-id="92e99-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="92e99-124">Dans la boîte de dialogue **Enregistrer sous** , entrez le nom du fichier dans lequel les événements Deadlock Graph doivent être stockés.</span><span class="sxs-lookup"><span data-stu-id="92e99-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="92e99-125">Cliquez sur **Tous les lots Deadlock XML dans un seul fichier** pour enregistrer tous les événements Deadlock Graph dans un seul fichier XML, ou cliquez sur **Chaque lot Deadlock XML dans un fichier différent**pour créer un fichier XML pour chaque événement Deadlock Graph.</span><span class="sxs-lookup"><span data-stu-id="92e99-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="92e99-126">Après avoir enregistré le fichier Deadlock, vous pouvez l'ouvrir dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e99-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="92e99-127">Pour plus d’informations, consultez [ouvrir, afficher et imprimer un fichier de blocage &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92e99-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e99-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92e99-128">See Also</span></span>  
 [<span data-ttu-id="92e99-129">Analyser des blocages à l'aide de SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="92e99-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
