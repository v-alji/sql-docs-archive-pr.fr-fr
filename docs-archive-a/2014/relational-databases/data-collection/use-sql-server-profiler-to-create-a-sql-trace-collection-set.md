---
title: Utiliser SQL Server Profiler pour créer un jeu d’collections trace SQL (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace collector set
ms.assetid: b6941dc0-50f5-475d-82eb-ce7c68117489
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9c9514fef8069cef615d1480aad1e0acd1582cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612967"
---
# <a name="use-sql-server-profiler-to-create-a-sql-trace-collection-set-sql-server-management-studio"></a><span data-ttu-id="f8af3-102">Utiliser SQL Server Profiler pour créer un jeu d'éléments de collecte Trace SQL (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f8af3-102">Use SQL Server Profiler to Create a SQL Trace Collection Set (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f8af3-103">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , vous pouvez exploiter les fonctions de trace côté serveur de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour exporter une définition de trace que vous pouvez utiliser afin de créer un jeu d’éléments de collecte qui utilise le type de collecteur Trace SQL générique.</span><span class="sxs-lookup"><span data-stu-id="f8af3-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] you can exploit the server-side trace capabilities of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to export a trace definition that you can use to create a collection set that uses the Generic SQL Trace collector type.</span></span> <span data-ttu-id="f8af3-104">Ce processus se décompose en deux parties :</span><span class="sxs-lookup"><span data-stu-id="f8af3-104">There are two parts to this process:</span></span>  
  
1.  <span data-ttu-id="f8af3-105">Créer et exporter une trace [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8af3-105">Create and export a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace.</span></span>  
  
2.  <span data-ttu-id="f8af3-106">Écrire un nouveau script de jeu d'éléments de collecte basé sur une trace exportée.</span><span class="sxs-lookup"><span data-stu-id="f8af3-106">Script a new collection set based on an exported trace.</span></span>  
  
 <span data-ttu-id="f8af3-107">Le scénario des procédures suivantes implique la collecte de données relatives à toute procédure stockée dont l'exécution requiert 80 millisecondes ou plus.</span><span class="sxs-lookup"><span data-stu-id="f8af3-107">The scenario for the following procedures involves collecting data about any stored procedure that requires 80 milliseconds or longer to complete.</span></span> <span data-ttu-id="f8af3-108">Pour effectuer ces procédures, vous devez être en mesure :</span><span class="sxs-lookup"><span data-stu-id="f8af3-108">In order to complete these procedures you should be able to:</span></span>  
  
-   <span data-ttu-id="f8af3-109">d'utiliser [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour créer et configurer une trace ;</span><span class="sxs-lookup"><span data-stu-id="f8af3-109">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create and configure a trace.</span></span>  
  
-   <span data-ttu-id="f8af3-110">d'utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour ouvrir, modifier et exécuter une requête.</span><span class="sxs-lookup"><span data-stu-id="f8af3-110">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open, edit, and execute a query.</span></span>  
  
### <a name="create-and-export-a-sql-server-profiler-trace"></a><span data-ttu-id="f8af3-111">Créer et exporter une trace SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f8af3-111">Create and export a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="f8af3-112">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8af3-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f8af3-113">(Dans le menu **Outils** , cliquez sur **SQL Server Profiler**.)</span><span class="sxs-lookup"><span data-stu-id="f8af3-113">(On the **Tools** menu, click **SQL Server Profiler**.)</span></span>  
  
2.  <span data-ttu-id="f8af3-114">Dans la boîte de dialogue **Se connecter au serveur** , cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-114">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="f8af3-115">Pour ce scénario, veillez à ce que les valeurs de durée soient configurées pour s'afficher en millisecondes (la valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="f8af3-115">For this scenario, ensure that duration values are configured to display in milliseconds (the default).</span></span> <span data-ttu-id="f8af3-116">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8af3-116">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="f8af3-117">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-117">On the **Tools** menu, click **Options**.</span></span>  
  
    2.  <span data-ttu-id="f8af3-118">Dans la zone **Options d'affichage** , assurez-vous que la case à cocher Affiche les valeurs dans la colonne Durée en microsecondes est désactivée.</span><span class="sxs-lookup"><span data-stu-id="f8af3-118">In the **Display Options** area, ensure that the Show values in Duration column in microseconds check box is cleared.</span></span>  
  
    3.  <span data-ttu-id="f8af3-119">Cliquez sur **OK** pour fermer la boîte de dialogue **Options générales** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-119">Click **OK** to close the **General Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="f8af3-120">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-120">On the **File** menu, click **New Trace**.</span></span>  
  
5.  <span data-ttu-id="f8af3-121">Dans la boîte de dialogue **Se connecter au serveur** , sélectionnez le serveur auquel vous souhaitez vous connecter, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-121">In the **Connect to Server** dialog box, select the server that you want to connect to, and then click **Connect**.</span></span>  
  
     <span data-ttu-id="f8af3-122">La boîte de dialogue **Propriétés de la trace** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f8af3-122">The **Trace Properties** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="f8af3-123">Sous l'onglet **Général** , effectuez les paramétrages suivants :</span><span class="sxs-lookup"><span data-stu-id="f8af3-123">On the **General** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="f8af3-124">Dans la zone **Nom de la trace** , tapez le nom que vous souhaitez utiliser pour la trace.</span><span class="sxs-lookup"><span data-stu-id="f8af3-124">In the **Trace name** box, type the name that you want to use for the trace.</span></span> <span data-ttu-id="f8af3-125">Pour cet exemple, le nom de la trace est `SPgt80`.</span><span class="sxs-lookup"><span data-stu-id="f8af3-125">For this example, the trace name is `SPgt80`.</span></span>  
  
    2.  <span data-ttu-id="f8af3-126">Dans la liste **Utiliser le modèle**, sélectionnez le modèle à utiliser pour la trace.</span><span class="sxs-lookup"><span data-stu-id="f8af3-126">In the **Use the template list**, select the template to use for the trace.</span></span> <span data-ttu-id="f8af3-127">Pour cet exemple, cliquez sur **TSQL_SPs**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-127">For this example, click **TSQL_SPs**.</span></span>  
  
7.  <span data-ttu-id="f8af3-128">Sous l'onglet **Sélection des événements** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8af3-128">On the **Events Selection** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="f8af3-129">Identifiez les événements à utiliser pour la trace.</span><span class="sxs-lookup"><span data-stu-id="f8af3-129">Identify the events to use for the trace.</span></span> <span data-ttu-id="f8af3-130">Pour cet exemple, désactivez toutes les cases à cocher de la colonne **Événements** , sauf **ExistingConnection** et **SP:Completed**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-130">For this example, clear all check boxes in the **Events** column, except for **ExistingConnection** and **SP:Completed**.</span></span>  
  
    2.  <span data-ttu-id="f8af3-131">Dans l’angle inférieur droit, cochez la case **Afficher toutes les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-131">In the lower-right corner, select the **Show all columns** check box.</span></span>  
  
    3.  <span data-ttu-id="f8af3-132">Cliquez sur la ligne **SP:Completed** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-132">Click the **SP:Completed** row.</span></span>  
  
    4.  <span data-ttu-id="f8af3-133">Faites défiler la ligne jusqu'à la colonne **Durée** , puis activez la case à cocher **Durée** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-133">Scroll across the row to the **Duration** column, and then select the **Duration** check box.</span></span>  
  
8.  <span data-ttu-id="f8af3-134">Dans l’angle inférieur droit, cliquez sur **Filtres de colonnes** pour ouvrir la boîte de dialogue **Modifier le filtre** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-134">In the lower-right corner, click **Column Filters** to open the **Edit Filter** dialog box.</span></span> <span data-ttu-id="f8af3-135">Dans la boîte de dialogue **Modifier le filtre** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8af3-135">In the **Edit Filter** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f8af3-136">Dans la liste de filtres, cliquez sur **Durée**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-136">In the filter list, click **Duration**.</span></span>  
  
    2.  <span data-ttu-id="f8af3-137">Dans la fenêtre opérateur booléen, développez le nœud **supérieur ou égal** à, tapez `80` comme valeur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-137">In the Boolean operator window, expand the **Greater than or equal** node, type `80` as the value, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="f8af3-138">Cliquez sur **Exécuter** pour démarrer la trace.</span><span class="sxs-lookup"><span data-stu-id="f8af3-138">Click **Run** to start the trace.</span></span>  
  
10. <span data-ttu-id="f8af3-139">Dans la barre d'outils, cliquez sur **Arrêter la trace sélectionnée** ou **Suspendre la trace sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-139">On the toolbar, click **Stop Selected Trace** or **Pause Selected Trace**.</span></span>  
  
11. <span data-ttu-id="f8af3-140">Dans le menu **Fichier** , pointez sur **Exporter**, sur **Générer un script de la définition de la trace**, puis cliquez sur **Pour le jeu d'éléments de collecte Trace SQL**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-140">On the **File** menu, point to **Export**, point to **Script Trace Definition**, and then click **For SQL Trace Collection Set**.</span></span>  
  
12. <span data-ttu-id="f8af3-141">Dans la boîte de dialogue **Enregistrer sous** , tapez le nom que vous souhaitez utiliser pour la définition de la trace dans la zone **Nom de fichier** , puis enregistrez-le à l'emplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f8af3-141">In the **Save As** dialog box, type the name that you want to use for the trace definition in the **File name** box, and then save it in the location that you want.</span></span> <span data-ttu-id="f8af3-142">Pour cet exemple, le nom du fichier est identique au nom de la trace (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="f8af3-142">For this example, the file name is the same as the trace name (SPgt80).</span></span>  
  
13. <span data-ttu-id="f8af3-143">Cliquez sur **OK** lorsqu'un message indiquant que le fichier a bien été enregistré s'affiche, puis fermez [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8af3-143">Click **OK** when you receive a message that the file was successfully saved, and then close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="script-a-new-collection-set-from-a-sql-server-profiler-trace"></a><span data-ttu-id="f8af3-144">Générer un nouveau jeu d'éléments de collecte à partir d'une trace SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f8af3-144">Script a new collection set from a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="f8af3-145">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Fichier** , pointez sur **Ouvrir** , puis cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="f8af3-146">Dans la boîte de dialogue **Ouvrir un fichier** , recherchez et ouvrez le fichier que vous avez créé au cours de la procédure précédente (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="f8af3-146">In the **Open File** dialog box, locate and then open the file that you created in the previous procedure (SPgt80).</span></span>  
  
     <span data-ttu-id="f8af3-147">Les informations de trace que vous avez enregistrées sont ouvertes dans une fenêtre de requête et fusionnées dans un script que vous pouvez exécuter pour créer le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="f8af3-147">The trace information that you saved is opened in a Query window and merged into a script that you can run to create the new collection set.</span></span>  
  
3.  <span data-ttu-id="f8af3-148">Faites défiler le script et effectuez les remplacements suivants, notés dans le texte de commentaire du script :</span><span class="sxs-lookup"><span data-stu-id="f8af3-148">Scroll through the script and make the following replacements, which are noted in the script comment text:</span></span>  
  
    -   <span data-ttu-id="f8af3-149">Remplacez **SQLTrace Collection Set Name Here** par le nom que vous souhaitez utiliser pour le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="f8af3-149">Replace **SQLTrace Collection Set Name Here** with the name that you want to use for the collection set.</span></span> <span data-ttu-id="f8af3-150">Pour cet exemple, nommez le jeu d’éléments de collecte `SPROC_CollectionSet`.</span><span class="sxs-lookup"><span data-stu-id="f8af3-150">For this example, name the collection set `SPROC_CollectionSet`.</span></span>  
  
    -   <span data-ttu-id="f8af3-151">Remplacez **SQLTrace Collection Item Name Here** par le nom que vous souhaitez utiliser pour l'élément de collecte.</span><span class="sxs-lookup"><span data-stu-id="f8af3-151">Replace **SQLTrace Collection Item Name Here** with the name that you want to use for the collection item.</span></span> <span data-ttu-id="f8af3-152">Pour cet exemple, nommez l’élément de collecte `SPROC_Collection_Item`.</span><span class="sxs-lookup"><span data-stu-id="f8af3-152">For this example, name the collection item `SPROC_Collection_Item`.</span></span>  
  
4.  <span data-ttu-id="f8af3-153">Cliquez sur **Exécuter** pour exécuter la requête et créer le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="f8af3-153">Click **Execute** to run the query and to create the collection set.</span></span>  
  
5.  <span data-ttu-id="f8af3-154">Dans l'Explorateur d'objets, vérifiez que le jeu d'éléments de collecte a été créé.</span><span class="sxs-lookup"><span data-stu-id="f8af3-154">In Object Explorer, verify that the collection set was created.</span></span> <span data-ttu-id="f8af3-155">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8af3-155">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="f8af3-156">Cliquez avec le bouton droit sur **Gestion**, puis cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-156">Right-click **Management**, and then click **Refresh**.</span></span>  
  
    2.  <span data-ttu-id="f8af3-157">Développez **Gestion**, puis **Collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="f8af3-157">Expand **Management**, and then expand **Data Collection**.</span></span>  
  
     <span data-ttu-id="f8af3-158">Le `SPROC_CollectionSet` jeu d’collections apparaît au même niveau que le nœud Jeux d’élément de **collecte de données système** .</span><span class="sxs-lookup"><span data-stu-id="f8af3-158">The `SPROC_CollectionSet` collection set appears at the same level as the **System Data Collection Sets** node.</span></span> <span data-ttu-id="f8af3-159">Par défaut, le jeu d'éléments de collecte est désactivé.</span><span class="sxs-lookup"><span data-stu-id="f8af3-159">By default, the collection set is disabled.</span></span>  
  
6.  <span data-ttu-id="f8af3-160">Utilisez l'Explorateur d'objets pour modifier les propriétés de SPROC_CollectionSet, tel que le mode de collecte et la planification de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="f8af3-160">Use Object Explorer to edit the properties of SPROC_CollectionSet, such as the collection mode and upload schedule.</span></span> <span data-ttu-id="f8af3-161">Procédez de la même manière que pour les jeux d'éléments de collecte de données système fournis avec le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="f8af3-161">Follow the same procedures that you would for the System Data collection sets that are provided with the data collector.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8af3-162">Exemple</span><span class="sxs-lookup"><span data-stu-id="f8af3-162">Example</span></span>  
 <span data-ttu-id="f8af3-163">L'exemple de code suivant est le script final obtenu après l'exécution des étapes documentées dans les procédures précédentes.</span><span class="sxs-lookup"><span data-stu-id="f8af3-163">The following code sample is the final script resulting from the steps documented in the preceding procedures.</span></span>  
  
```  
/*************************************************************/  
-- SQL Trace collection set generated from SQL Server Profiler  
-- Date: 11/19/2007  12:55:31 AM  
/*************************************************************/  
  
USE msdb  
GO  
  
BEGIN TRANSACTION  
BEGIN TRY  
  
-- Define collection set  
-- ***  
-- *** Replace 'SqlTrace Collection Set Name Here' in the   
-- *** following script with the name you want  
-- *** to use for the collection set.  
-- ***  
DECLARE @collection_set_id int;  
EXEC [dbo].[sp_syscollector_create_collection_set]  
    @name = N'SPROC_CollectionSet',  
    @schedule_name = N'CollectorSchedule_Every_15min',  
    @collection_mode = 0, -- cached mode needed for Trace collections  
    @logging_level = 0, -- minimum logging  
    @days_until_expiration = 5,  
    @description = N'Collection set generated by SQL Server Profiler',  
    @collection_set_id = @collection_set_id output;  
SELECT @collection_set_id;  
  
-- Define input and output variables for the collection item.  
DECLARE @trace_definition xml;  
DECLARE @collection_item_id int;  
  
-- Define the trace parameters as an XML variable  
SELECT @trace_definition = convert(xml,   
N'<ns:SqlTraceCollector xmlns:ns"DataCollectorType" use_default="0">  
<Events>  
  <EventType name="Sessions">  
    <Event id="17" name="ExistingConnection" columnslist="1,2,14,26,3,35,12" />  
  </EventType>  
  <EventType name="Stored Procedures">  
    <Event id="43" name="SP:Completed" columnslist="1,2,26,34,3,35,12,13,14,22" />  
  </EventType>  
</Events>  
<Filters>  
  <Filter columnid="13" columnname="Duration" logical_operator="AND" comparison_operator="GE" value="80000L" />  
</Filters>  
</ns:SqlTraceCollector>  
');  
  
-- Retrieve the collector type GUID for the trace collector type.  
DECLARE @collector_type_GUID uniqueidentifier;  
SELECT @collector_type_GUID = collector_type_uid FROM [dbo].[syscollector_collector_types] WHERE name = N'Generic SQL Trace Collector Type';  
  
-- Create the trace collection item.  
-- ***  
-- *** Replace 'SqlTrace Collection Item Name Here' in   
-- *** the following script with the name you want to  
-- *** use for the collection item.  
-- ***  
EXEC [dbo].[sp_syscollector_create_collection_item]  
   @collection_set_id = @collection_set_id,  
   @collector_type_uid = @collector_type_GUID,  
   @name = N'SPROC_Collection_Item',  
   @frequency = 900, -- specified the frequency for checking to see if trace is still running  
   @parameters = @trace_definition,  
   @collection_item_id = @collection_item_id output;  
SELECT @collection_item_id;  
  
COMMIT TRANSACTION;  
END TRY  
  
BEGIN CATCH  
ROLLBACK TRANSACTION;  
DECLARE @ErrorMessage nvarchar(4000);  
DECLARE @ErrorSeverity int;  
DECLARE @ErrorState int;  
DECLARE @ErrorNumber int;  
DECLARE @ErrorLine int;  
DECLARE @ErrorProcedure nvarchar(200);  
SELECT @ErrorLine = ERROR_LINE(),  
       @ErrorSeverity = ERROR_SEVERITY(),  
       @ErrorState = ERROR_STATE(),  
       @ErrorNumber = ERROR_NUMBER(),  
       @ErrorMessage = ERROR_MESSAGE(),  
       @ErrorProcedure = ISNULL(ERROR_PROCEDURE(), '-');  
RAISERROR (14684, @ErrorSeverity, 1 , @ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure, @ErrorLine, @ErrorMessage);  
END CATCH;  
GO  
```  
  
  
