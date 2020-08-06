---
title: Enregistrer les événements Showplan XML Statistics Profile séparément (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701099"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="ae35f-102">Enregistrer les événements Showplan XML Statistics Profile séparément (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ae35f-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="ae35f-103">Cette rubrique décrit comment enregistrer dans des fichiers .SQLPlan séparés les événements **Showplan XML Statistics Profile** capturés dans les traces à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae35f-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="ae35f-104">Vous pouvez ouvrir les fichiers des événements **Showplan XML Statistics Profile** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], qui vous permet d'afficher le plan d'exécution graphique de chaque événement.</span><span class="sxs-lookup"><span data-stu-id="ae35f-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="ae35f-105">Pour enregistrer séparément les événements de statistiques XML du plan d'exécution</span><span class="sxs-lookup"><span data-stu-id="ae35f-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="ae35f-106">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae35f-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="ae35f-107">La boîte de dialogue **Propriétés de la trace** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ae35f-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ae35f-108">Si la case à cocher **Démarrer le suivi juste après avoir établi la connexion**est activée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et la trace démarre.</span><span class="sxs-lookup"><span data-stu-id="ae35f-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="ae35f-109">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="ae35f-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="ae35f-110">Dans la zone **Nom de la trace** de la boîte de dialogue **Propriétés de la trace** , entrez le nom de la trace.</span><span class="sxs-lookup"><span data-stu-id="ae35f-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="ae35f-111">Dans la liste **Utiliser le modèle** , sélectionnez un modèle sur lequel baser la trace ou sélectionnez **Vide** pour ne pas utiliser de modèle.</span><span class="sxs-lookup"><span data-stu-id="ae35f-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="ae35f-112">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae35f-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="ae35f-113">Cliquez sur**Enregistrer dans le fichier**pour capturer la trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="ae35f-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="ae35f-114">Spécifiez une valeur dans **Définir la taille de fichier maximale**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="ae35f-115">Si vous le souhaitez, sélectionnez **activer la substitution de fichier** et traiter les données de trace des **processus serveur**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="ae35f-116">Cliquez sur**Enregistrer dans la table** pour capturer la trace dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="ae35f-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="ae35f-117">Éventuellement, spécifiez une valeur dans **Définir le nombre de lignes maximal**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="ae35f-118">Si vous le souhaitez, activez la case à cocher **activer l’heure d’arrêt** de la trace et spécifiez une date et une heure d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="ae35f-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="ae35f-119">Cliquez sur l’onglet **Sélection des événements**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="ae35f-120">Dans la zone **Events**, développez la catégorie d’événements **Performances**, puis activez la case à cocher **Showplan XML Statistics Profile**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="ae35f-121">Si la catégorie d'événements **Performance** n'est pas visible, activez la case à cocher **Afficher tous les événements** pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="ae35f-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="ae35f-122">La boîte de dialogue **Paramètres d’extraction des événements**est ajouté à la boîte de dialogue **Propriétés de la trace**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="ae35f-123">Dans le menu **Paramètres d’extraction des événements**, cliquez sur **Enregistrer les événements Showplan XML séparément**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="ae35f-124">Dans la boîte de dialogue **Enregistrer sous** , entrez le nom du fichier qui stocke les événements **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="ae35f-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="ae35f-125">Cliquez sur **Tous les traitements Showplan XML dans un seul fichier** pour enregistrer tous les événements **Showplan XML Statistics Profile** dans un même fichier XML ou sur **Chaque traitement Showplan XML dans un fichier différent**pour créer un nouveau fichier XML pour chaque événement **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="ae35f-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="ae35f-126">Pour afficher le fichier des événements **Showplan XML Statistics Profile** dans SQL Server Management Studio, dans le menu **Fichier** , pointez sur **Ouvrir**et cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="ae35f-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="ae35f-127">Placez-vous dans le répertoire où vous avez enregistré le ou les fichiers des événements **Showplan XML Statistics Profile** pour en sélectionner un et l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="ae35f-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="ae35f-128">Les fichiers des événements**Showplan XML Statistics Profile** possèdent l'extension .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="ae35f-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae35f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae35f-129">See Also</span></span>  
 [<span data-ttu-id="ae35f-130">Analyser des requêtes avec des résultats SHOWPLAN dans SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ae35f-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
