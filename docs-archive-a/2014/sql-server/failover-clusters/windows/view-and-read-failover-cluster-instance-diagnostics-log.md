---
title: Afficher et lire le journal de diagnostic de l’instance de cluster de basculement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605007"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="b02a3-102">Afficher et lire le journal de diagnostic de l'instance de cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="b02a3-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="b02a3-103">Toutes les erreurs et tous les événements d'avertissements critiques pour la DLL de ressource SQL Server sont écrits dans le journal des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="b02a3-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="b02a3-104">Un journal en cours des informations de diagnostic spécifiques de SQL Server est capturé par la procédure stockée système [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) ; il est écrit dans les fichiers journaux de diagnostics du cluster de basculement de SQL Server (également appelés journaux *SQLDIAG*).</span><span class="sxs-lookup"><span data-stu-id="b02a3-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="b02a3-105">**Avant de commencer :**  [Recommandations](#Recommendations), [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="b02a3-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="b02a3-106">**Pour afficher le journal de diagnostics, à l’aide de :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="b02a3-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="b02a3-107">**Pour configurer les paramètres du journal de diagnostics, à l’aide de :** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="b02a3-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b02a3-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b02a3-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b02a3-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="b02a3-109">Recommendations</span></span>  
 <span data-ttu-id="b02a3-110">Par défaut, le SQLDIAG est stocké sous un dossier LOG local du répertoire SQL Server instance, par exemple, «C\Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\LOG’du nœud propriétaire de l’instance de cluster de basculement AlwaysOn (FCI).</span><span class="sxs-lookup"><span data-stu-id="b02a3-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="b02a3-111">La taille de chaque fichier journal SQLDIAG est fixée à 100 Mo.</span><span class="sxs-lookup"><span data-stu-id="b02a3-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="b02a3-112">Dix fichiers journaux de ce type sont stockés sur l'ordinateur avant qu'ils ne soient recyclés pour les nouveaux journaux.</span><span class="sxs-lookup"><span data-stu-id="b02a3-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="b02a3-113">Les journaux utilisent le format de fichier d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="b02a3-113">The logs use the extended events file format.</span></span> <span data-ttu-id="b02a3-114">La fonction système **sys.fn_xe_file_target_read_file** peut être utilisée pour lire les fichiers créés par les événements étendus.</span><span class="sxs-lookup"><span data-stu-id="b02a3-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="b02a3-115">Au format XML, un événement par ligne est retourné.</span><span class="sxs-lookup"><span data-stu-id="b02a3-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="b02a3-116">Interrogez la vue système pour analyser les données XML définies comme ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="b02a3-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="b02a3-117">Pour plus d’informations, consultez [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b02a3-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b02a3-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b02a3-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b02a3-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b02a3-119">Permissions</span></span>  
 <span data-ttu-id="b02a3-120">L’autorisation VIEW SERVER STATE est exigée pour exécuter **fn_xe_file_target_read_file**.</span><span class="sxs-lookup"><span data-stu-id="b02a3-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="b02a3-121">Ouvrez SQL Server Management Studio en tant qu'administrateur</span><span class="sxs-lookup"><span data-stu-id="b02a3-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b02a3-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b02a3-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b02a3-123">**Pour afficher les fichiers journaux de diagnostics :**</span><span class="sxs-lookup"><span data-stu-id="b02a3-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="b02a3-124">Dans le menu de **Fichier** , sélectionnez **Ouvrir**, puis **Fichier**et choisissez le fichier journal de diagnostics à afficher.</span><span class="sxs-lookup"><span data-stu-id="b02a3-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="b02a3-125">Les événements sont affichés sous forme de lignes dans le volet droit. Par défaut, seules les colonnes **name**et **timestamp** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="b02a3-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="b02a3-126">Cela permet également d'activer le menu **ExtendedEvents** .</span><span class="sxs-lookup"><span data-stu-id="b02a3-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="b02a3-127">Pour afficher plus de colonnes, allez dans le menu de **ExtendedEvents** , puis sélectionnez **Choisir les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="b02a3-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="b02a3-128">Une boîte de dialogue dans laquelle vous pouvez sélectionner les colonnes à afficher s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b02a3-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="b02a3-129">Vous pouvez filtrer et trier les données d'événement à l'aide du menu **ExtendedEvents** , en sélectionnant l'option **Filtre** .</span><span class="sxs-lookup"><span data-stu-id="b02a3-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b02a3-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b02a3-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="b02a3-131">**Pour afficher les fichiers journaux de diagnostics :**</span><span class="sxs-lookup"><span data-stu-id="b02a3-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="b02a3-132">Pour consulter tous les éléments de journal du fichier journal SQLDIAG, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="b02a3-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b02a3-133">Vous pouvez filtrer les résultats pour des composants spécifiques ou exécuter une déclaration à l'aide de la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="b02a3-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="b02a3-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b02a3-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="b02a3-135">**Pour configurer les propriétés du journal de diagnostics**</span><span class="sxs-lookup"><span data-stu-id="b02a3-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b02a3-136">Pour obtenir un exemple de cette procédure, consultez [Exemple (Transact-SQL)](#TsqlExample)plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="b02a3-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="b02a3-137">À l’aide de l’instruction DDL (Data Definition Language), `ALTER SERVER CONFIGURATION` , vous pouvez démarrer ou arrêter la journalisation des données de diagnostic capturées par la procédure [Sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) et définir des paramètres de configuration du journal SQLdiag, tels que le nombre de substitutions du fichier journal, la taille du fichier journal et l’emplacement du fichier.</span><span class="sxs-lookup"><span data-stu-id="b02a3-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="b02a3-138">Pour plus d'informations sur la syntaxe, consultez [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="b02a3-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="b02a3-139">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b02a3-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="b02a3-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="b02a3-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="b02a3-141">Les exemples de cette section montrent comment définir les valeurs de l'option de journal de diagnostics.</span><span class="sxs-lookup"><span data-stu-id="b02a3-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="b02a3-142">R.</span><span class="sxs-lookup"><span data-stu-id="b02a3-142">A.</span></span> <span data-ttu-id="b02a3-143">Début de la journalisation des diagnostics</span><span class="sxs-lookup"><span data-stu-id="b02a3-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="b02a3-144">L'exemple suivant démarre la journalisation de données de diagnostics.</span><span class="sxs-lookup"><span data-stu-id="b02a3-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="b02a3-145">B.</span><span class="sxs-lookup"><span data-stu-id="b02a3-145">B.</span></span> <span data-ttu-id="b02a3-146">Fin de la journalisation des diagnostics</span><span class="sxs-lookup"><span data-stu-id="b02a3-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="b02a3-147">L'exemple suivant met fin à la journalisation des données de diagnostics.</span><span class="sxs-lookup"><span data-stu-id="b02a3-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="b02a3-148">C.</span><span class="sxs-lookup"><span data-stu-id="b02a3-148">C.</span></span> <span data-ttu-id="b02a3-149">Spécification de l'emplacement des journaux de diagnostics</span><span class="sxs-lookup"><span data-stu-id="b02a3-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="b02a3-150">L'exemple suivant définit l'emplacement des journaux de diagnostics sur le chemin d'accès au fichier spécifié.</span><span class="sxs-lookup"><span data-stu-id="b02a3-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="b02a3-151">D.</span><span class="sxs-lookup"><span data-stu-id="b02a3-151">D.</span></span> <span data-ttu-id="b02a3-152">Spécification de la taille maximale de chaque journal de diagnostics</span><span class="sxs-lookup"><span data-stu-id="b02a3-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="b02a3-153">L'exemple suivant définit la taille maximale de chaque journal de diagnostics sur 10 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="b02a3-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b02a3-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b02a3-154">See Also</span></span>  
 [<span data-ttu-id="b02a3-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="b02a3-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
