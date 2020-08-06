---
title: Créer une trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694956"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="22840-102">Créer une trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="22840-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="22840-103">Cette rubrique décrit comment utiliser le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour créer une trace.</span><span class="sxs-lookup"><span data-stu-id="22840-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="22840-104">Pour créer une trace</span><span class="sxs-lookup"><span data-stu-id="22840-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="22840-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**et connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22840-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="22840-106">La boîte de dialogue **Propriétés de la trace** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="22840-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22840-107">La boîte de dialogue **Propriétés de la trace** ne s’affiche pas et la trace démarre en lieu et place, si l’option **Démarrer le suivi juste après avoir établi la connexion** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="22840-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="22840-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="22840-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="22840-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="22840-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="22840-110">Dans la liste **Utiliser le modèle** , sélectionnez un modèle de trace comme base ou sélectionnez **Vide** si vous ne souhaitez pas utiliser de modèle.</span><span class="sxs-lookup"><span data-stu-id="22840-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="22840-111">Pour enregistrer les résultats de la trace, réalisez l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="22840-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="22840-112">Cliquez sur **Enregistrer dans le fichier** pour capturer la trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="22840-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="22840-113">Spécifiez une valeur dans **Définir la taille de fichier maximale**.</span><span class="sxs-lookup"><span data-stu-id="22840-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="22840-114">La valeur par défaut est 5 mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="22840-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="22840-115">Éventuellement, sélectionnez **Activer la substitution de fichier** pour créer automatiquement de nouveaux fichiers quand la taille maximale du fichier est atteinte.</span><span class="sxs-lookup"><span data-stu-id="22840-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="22840-116">Vous pouvez également éventuellement sélectionner **Le serveur traite les données de trace**pour forcer le service exécutant la trace à traiter les données de trace en lieu et place de l’application cliente.</span><span class="sxs-lookup"><span data-stu-id="22840-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="22840-117">Lorsque le serveur traite les données de trace, aucun événement n'est ignoré, même dans des conditions extrêmes, mais les performances du serveur peuvent en être affectées.</span><span class="sxs-lookup"><span data-stu-id="22840-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="22840-118">Cliquez sur **Enregistrer dans la table** pour capturer la trace dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="22840-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="22840-119">Au besoin, cliquez sur **Définir le nombre de lignes maximal**et spécifiez une valeur.</span><span class="sxs-lookup"><span data-stu-id="22840-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="22840-120">Lorsque vous n'enregistrez pas les résultats de la trace dans un fichier ou dans une table, vous pouvez afficher la trace lorsque le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] est ouvert.</span><span class="sxs-lookup"><span data-stu-id="22840-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="22840-121">Cependant, vous perdez les résultats de la trace après l'avoir arrêtée et fermé le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22840-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="22840-122">Pour éviter de perdre les résultats de la trace, cliquez sur l’option **Enregistrer** du menu **Fichier** pour les enregistrer avant de fermer [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22840-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="22840-123">Le cas échéant, activez la case à cocher **Activer l'heure d'arrêt de la trace** et indiquez une date et une heure d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="22840-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="22840-124">Pour ajouter ou supprimer des événements, des colonnes de données ou des filtres, cliquez sur l’onglet **Sélection des événements**.</span><span class="sxs-lookup"><span data-stu-id="22840-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="22840-125">Pour plus d’informations, consultez [Spécifier les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="22840-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="22840-126">Cliquez sur **Exécuter** pour démarrer la trace.</span><span class="sxs-lookup"><span data-stu-id="22840-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22840-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22840-127">See Also</span></span>  
 <span data-ttu-id="22840-128">[Autorisations nécessaires pour exécuter SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="22840-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="22840-129">[Modèles et autorisations du générateur de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="22840-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="22840-130">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="22840-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="22840-131">Corréler une trace aux données du journal de performances Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="22840-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
