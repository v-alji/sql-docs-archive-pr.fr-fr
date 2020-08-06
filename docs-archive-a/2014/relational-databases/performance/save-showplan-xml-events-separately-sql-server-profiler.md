---
title: Enregistrer séparément des événements Showplan XML (Générateur de profils SQL Server) | Microsoft Docs
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
ms.assetid: 33320a7a-36e8-401c-876d-5b82c49abd85
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 240fb408bb3ed8585ecc915ba4829ac21285d241
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613992"
---
# <a name="save-showplan-xml-events-separately-sql-server-profiler"></a><span data-ttu-id="5b6cb-102">Enregistrer séparément des événements Showplan XML (Générateur de profils SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5b6cb-102">Save Showplan XML Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="5b6cb-103">Cette rubrique explique comment enregistrer des événements **Showplan XML** qui sont capturés dans des traces dans des fichiers .SQLPlan différents avec le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6cb-103">This topic describes how to save **Showplan XML** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="5b6cb-104">Vous pouvez ouvrir les fichiers des événements **Showplan XML** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ce qui vous permet de voir le plan d'exécution graphique pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-104">You can open the **Showplan XML** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-events-separately"></a><span data-ttu-id="5b6cb-105">Pour enregistrer séparément des événements Showplan XML</span><span class="sxs-lookup"><span data-stu-id="5b6cb-105">To save Showplan XML events separately</span></span>  
  
1.  <span data-ttu-id="5b6cb-106">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="5b6cb-107">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b6cb-108">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="5b6cb-109">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="5b6cb-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="5b6cb-110">Dans la zone **Nom de la trace** de la boîte de dialogue **Propriétés de la trace** , entrez le nom de la trace.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="5b6cb-111">Dans la liste **Utiliser le modèle** , sélectionnez un modèle de trace comme base ou sélectionnez **Vide** si vous ne souhaitez pas utiliser de modèle.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="5b6cb-112">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5b6cb-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="5b6cb-113">Activez la case à cocher**Enregistrer dans le fichier** pour capturer la trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="5b6cb-114">Spécifiez une valeur dans **Définir la taille de fichier maximale**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-114">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="5b6cb-115">Au besoin, activez les cases à cocher **Activer la substitution de fichier** et **Le serveur traite les données de trace** .</span><span class="sxs-lookup"><span data-stu-id="5b6cb-115">Optionally, select the **Enable file rollover** and **Server processes trace data** check boxes.</span></span>  
  
    -   <span data-ttu-id="5b6cb-116">Activez la case à cocher**Enregistrer dans la table** pour capturer la trace dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-116">Select the**Save to table** check box to capture the trace to a database table.</span></span> <span data-ttu-id="5b6cb-117">Éventuellement, spécifiez une valeur dans **Définir le nombre de lignes maximal**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="5b6cb-118">Le cas échéant, activez la case à cocher **Activer l'heure d'arrêt de la trace** et indiquez une date et une heure d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="5b6cb-119">Cliquez sur l’onglet **Sélection des événements**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="5b6cb-120">Dans la zone **Événements,** développez la catégorie d'événements **Performance,** puis activez la case à cocher **Showplan XML**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML**check box.</span></span> <span data-ttu-id="5b6cb-121">Si la catégorie d'événements **Performance** n'est pas visible, activez la case à cocher **Afficher tous les événements** pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="5b6cb-122">La boîte de dialogue **Paramètres d’extraction des événements**est ajoutée à la boîte de dialogue **Propriétés de la trace**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="5b6cb-123">Dans le menu **Paramètres d’extraction des événements**, cliquez sur **Enregistrer les événements Showplan XML séparément**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="5b6cb-124">Dans la boîte de dialogue **Enregistrer sous** , entrez le nom du fichier dans lequel vous souhaitez stocker les événements **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="5b6cb-124">In the **Save As** dialog box, enter the name of the file in which to store the **Showplan XML** events.</span></span>  
  
10. <span data-ttu-id="5b6cb-125">Cliquez sur **Tous les lots Showplan XML dans un seul fichier** pour enregistrer tous les événements **Showplan XML** dans un seul fichier XML ou cliquez sur **Chaque lot Showplan XML dans un fichier différent**pour créer un nouveau fichier XML pour chaque événement **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="5b6cb-125">Click **All XML Showplan batches in a single file** to save all **Showplan XML** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML** event.</span></span>  
  
11. <span data-ttu-id="5b6cb-126">Pour afficher le fichier d'événements **Showplan XML** dans SQL Server Management Studio, ouvrez le menu **Fichier** , pointez sur **Ouvrir**, puis cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-126">To view the **Showplan XML** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="5b6cb-127">Recherchez le répertoire où vous avez enregistré le ou les fichiers d'événements **Showplan XML** pour en sélectionner un et l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-127">Navigate to the directory where you saved the **Showplan XML** event file or files to select one and open it.</span></span> <span data-ttu-id="5b6cb-128">Les fichiers d'événements**Showplan XML** ont l'extension .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="5b6cb-128">**Showplan XML** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6cb-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b6cb-129">See Also</span></span>  
 [<span data-ttu-id="5b6cb-130">Analyser des requêtes avec des résultats SHOWPLAN dans SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5b6cb-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
