---
title: Journal des exécutions du serveur de rapports et vue ExecutionLog3 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602752"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="e052a-102">Journal des exécutions du serveur de rapports et vue ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="e052a-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="e052a-103">Le journal d'exécution du serveur de rapports contient des informations sur les rapports qui sont exécutés sur le serveur ou sur plusieurs serveurs en mode natif regroupés dans un déploiement évolutif ou une batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e052a-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="e052a-104">Vous pouvez l'utiliser pour connaître la fréquence de demande d'un rapport, les formats de sortie les plus utilisés et le nombre de millisecondes de traitement consacré à chaque phrase du traitement.</span><span class="sxs-lookup"><span data-stu-id="e052a-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="e052a-105">Le journal contient des informations sur le temps passé pour l'exécution d'une requête de dataset dans un rapport et le temps passé pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="e052a-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="e052a-106">Si vous êtes administrateur de serveur de rapports, vous pouvez passer en revue les informations du journal, identifier les tâches longues et faire des suggestions aux auteurs de rapports pour améliorer des zones du rapport (dataset ou traitement).</span><span class="sxs-lookup"><span data-stu-id="e052a-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="e052a-107">Les serveurs de rapports configurés pour le mode SharePoint peuvent également utiliser les journaux ULS de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e052a-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="e052a-108">Pour plus d’informations, consultez [Activer des événements Reporting Services pour le journal des traces SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="e052a-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="e052a-109">Affichage des informations des journaux</span><span class="sxs-lookup"><span data-stu-id="e052a-109">Viewing Log Information</span></span>  
 <span data-ttu-id="e052a-110">Le serveur de rapports consigne les données sur l'exécution des rapports dans une table de base de données interne.</span><span class="sxs-lookup"><span data-stu-id="e052a-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="e052a-111">Les informations de la table sont fournies par les vues de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e052a-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="e052a-112">Le journal d'exécution des rapports est stocké dans la base de données du serveur de rapports nommée par défaut **ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="e052a-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="e052a-113">Les vues SQL fournissent les informations associées au journal d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="e052a-114">Les vues « 2 » et « 3 » ont été ajoutées dans les dernières versions et contiennent de nouveaux champs ou des champs avec des noms plus conviviaux que dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="e052a-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="e052a-115">Les anciennes vues sont toujours présentes dans le produit de sorte que les applications personnalisées qui dépendent d'elles ne sont pas impactées.</span><span class="sxs-lookup"><span data-stu-id="e052a-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="e052a-116">Si vous n'avez pas de dépendance sur une vue plus ancienne, par exemple ExecutionLog, il est recommandé d'utiliser la vue la plus récente, soit ExecutionLog**3**.</span><span class="sxs-lookup"><span data-stu-id="e052a-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="e052a-117">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="e052a-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="e052a-118">Paramètres de configuration d'un serveur de rapports en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="e052a-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="e052a-119">Paramètres de configuration d'un serveur de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="e052a-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="e052a-120">Champs de journalisation (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="e052a-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="e052a-121">Champ AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="e052a-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="e052a-122">Champs de journalisation (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="e052a-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="e052a-123">Champs de journalisation (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="e052a-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="e052a-124">Paramètres de configuration d'un serveur de rapports en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="e052a-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="e052a-125">Vous pouvez activer ou désactiver la journalisation de l'exécution des rapports dans les paramètres système d'une application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e052a-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="e052a-126">Par défaut, les entrées de journal sont conservées pendant 60 jours.</span><span class="sxs-lookup"><span data-stu-id="e052a-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="e052a-127">Au-delà de cette date, les entrées sont supprimées à 02:00</span><span class="sxs-lookup"><span data-stu-id="e052a-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="e052a-128">tous les jours.</span><span class="sxs-lookup"><span data-stu-id="e052a-128">every day.</span></span> <span data-ttu-id="e052a-129">Dans une installation déjà rodée, seuls 60 jours d'informations sont disponibles à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e052a-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="e052a-130">Vous ne pouvez pas définir de limites pour le nombre de lignes ou le type d'entrées enregistrées.</span><span class="sxs-lookup"><span data-stu-id="e052a-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="e052a-131">**Pour activer la journalisation des exécutions :**</span><span class="sxs-lookup"><span data-stu-id="e052a-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="e052a-132">Depuis l'Administration centrale de SharePoint, dans le groupe **Gestion des applications** , cliquez sur **Gérer les applications de service** .</span><span class="sxs-lookup"><span data-stu-id="e052a-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="e052a-133">Cliquez sur le nom de l'application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="e052a-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="e052a-134">Cliquez sur **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="e052a-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="e052a-135">Sélectionnez **Activer la journalisation des exécutions** dans la section **Enregistrement** .</span><span class="sxs-lookup"><span data-stu-id="e052a-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="e052a-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e052a-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="e052a-137">**Pour activer la journalisation verbose :**</span><span class="sxs-lookup"><span data-stu-id="e052a-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="e052a-138">Vous devez activer la journalisation comme décrit dans les étapes précédentes, puis effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e052a-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="e052a-139">Dans la page **Paramètres système** de votre application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , recherchez la section **Défini par l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="e052a-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="e052a-140">Modifiez **ExecutionLogLevel** en **verbose**.</span><span class="sxs-lookup"><span data-stu-id="e052a-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="e052a-141">Ce champ est un champ d'entrée de texte et les deux valeurs possibles sont **verbose** et **normal**.</span><span class="sxs-lookup"><span data-stu-id="e052a-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="e052a-142">Paramètres de configuration d'un serveur de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="e052a-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="e052a-143">Vous pouvez activer ou désactiver la journalisation de l'exécution de rapports dans la page Propriétés du serveur de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e052a-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="e052a-144">**EnableExecutionLogging** est une propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="e052a-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="e052a-145">Par défaut, les entrées de journal sont conservées pendant 60 jours.</span><span class="sxs-lookup"><span data-stu-id="e052a-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="e052a-146">Au-delà de cette date, les entrées sont supprimées à 02:00</span><span class="sxs-lookup"><span data-stu-id="e052a-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="e052a-147">tous les jours.</span><span class="sxs-lookup"><span data-stu-id="e052a-147">every day.</span></span> <span data-ttu-id="e052a-148">Dans une installation déjà rodée, seuls 60 jours d'informations sont disponibles à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e052a-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="e052a-149">Vous ne pouvez pas définir de limites pour le nombre de lignes ou le type d'entrées enregistrées.</span><span class="sxs-lookup"><span data-stu-id="e052a-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="e052a-150">**Pour activer la journalisation des exécutions :**</span><span class="sxs-lookup"><span data-stu-id="e052a-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="e052a-151">Ouvrez SQL Server Management Studio avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="e052a-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="e052a-152">Par exemple, cliquez avec le bouton droit sur l’icône Management Studio et cliquez sur « Exécuter en tant qu’administrateur ».</span><span class="sxs-lookup"><span data-stu-id="e052a-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="e052a-153">Connectez-vous au serveur de rapports souhaité.</span><span class="sxs-lookup"><span data-stu-id="e052a-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="e052a-154">Cliquez avec le bouton droit sur le nom du serveur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e052a-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="e052a-155">Si l'option Propriétés est désactivée, vérifiez que vous avez ouvert SQL Server Management Studio avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="e052a-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="e052a-156">Cliquez sur la page **Journalisation** .</span><span class="sxs-lookup"><span data-stu-id="e052a-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="e052a-157">Sélectionnez **Activer la journalisation de l'exécution des rapports**.</span><span class="sxs-lookup"><span data-stu-id="e052a-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="e052a-158">**Pour activer la journalisation verbose :**</span><span class="sxs-lookup"><span data-stu-id="e052a-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="e052a-159">Vous devez activer la journalisation comme décrit dans les étapes précédentes, puis effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e052a-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="e052a-160">Dans la boîte de dialogue **Propriétés du serveur** , cliquez sur la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="e052a-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="e052a-161">Dans la section **Défini par l’utilisateur** , modifiez **ExecutionLogLevel** sur **verbose**.</span><span class="sxs-lookup"><span data-stu-id="e052a-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="e052a-162">Ce champ est un champ d'entrée de texte et les deux valeurs possibles sont **verbose** et **normal**.</span><span class="sxs-lookup"><span data-stu-id="e052a-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="e052a-163">Champs de journalisation (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="e052a-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="e052a-164">Dans cette vue, un nœud de diagnostic de performances supplémentaire est ajouté dans la colonne **AdditionalInfo** basée sur XML.</span><span class="sxs-lookup"><span data-stu-id="e052a-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="e052a-165">La colonne AdditionalInfo contient une structure XML comportant de 1 à plusieurs champs d'informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="e052a-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="e052a-166">Voici un exemple d'instruction Transact SQL pour extraire des lignes de la vue ExecutionLog3.</span><span class="sxs-lookup"><span data-stu-id="e052a-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="e052a-167">L'exemple suppose que la base de données du serveur de rapports est nommée **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="e052a-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="e052a-168">La table suivante décrit les données qui sont capturées dans le journal d'exécution des rapports :</span><span class="sxs-lookup"><span data-stu-id="e052a-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="e052a-169">Colonne</span><span class="sxs-lookup"><span data-stu-id="e052a-169">Column</span></span>|<span data-ttu-id="e052a-170">Description</span><span class="sxs-lookup"><span data-stu-id="e052a-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e052a-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="e052a-171">InstanceName</span></span>|<span data-ttu-id="e052a-172">Nom de l'instance du serveur de rapports qui a géré la demande.</span><span class="sxs-lookup"><span data-stu-id="e052a-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="e052a-173">Si votre environnement inclut plusieurs serveurs de rapports, vous pouvez analyser la distribution InstanceName pour surveiller et déterminer si votre programme d'équilibrage de la charge réseau distribue les requêtes entre les différents serveurs de rapports comme prévu.</span><span class="sxs-lookup"><span data-stu-id="e052a-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="e052a-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="e052a-174">ItemPath</span></span>|<span data-ttu-id="e052a-175">Chemin de stockage d'un rapport ou d'un élément de rapport</span><span class="sxs-lookup"><span data-stu-id="e052a-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="e052a-176">UserName</span><span class="sxs-lookup"><span data-stu-id="e052a-176">UserName</span></span>|<span data-ttu-id="e052a-177">Identificateur de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e052a-177">User identifier.</span></span>|  
|<span data-ttu-id="e052a-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="e052a-178">ExecutionID</span></span>|<span data-ttu-id="e052a-179">Identificateur interne associé à une requête.</span><span class="sxs-lookup"><span data-stu-id="e052a-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="e052a-180">Les requêtes sur les mêmes sessions utilisateur partagent le même ID d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="e052a-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="e052a-181">RequestType</span></span>|<span data-ttu-id="e052a-182">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="e052a-182">Possible Values:</span></span><br /><span data-ttu-id="e052a-183">**Interactive**</span><span class="sxs-lookup"><span data-stu-id="e052a-183">**Interactive**</span></span><br /><span data-ttu-id="e052a-184">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="e052a-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="e052a-185">L'analyse des données de journal filtrées par RequestType=Subscription et triées par TimeStart peut identifier des périodes d'utilisation importante des abonnements ; si vous le souhaitez, il est par la suite possible de modifier l'heure de certains abonnements aux rapports.</span><span class="sxs-lookup"><span data-stu-id="e052a-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="e052a-186">Format</span><span class="sxs-lookup"><span data-stu-id="e052a-186">Format</span></span>|<span data-ttu-id="e052a-187">Format de rendu.</span><span class="sxs-lookup"><span data-stu-id="e052a-187">Rendering format.</span></span>|  
|<span data-ttu-id="e052a-188">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e052a-188">Parameters</span></span>|<span data-ttu-id="e052a-189">Valeurs des paramètres utilisées pour une exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="e052a-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="e052a-190">ItemAction</span></span>|<span data-ttu-id="e052a-191">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="e052a-191">Possible values:</span></span><br /><br /> <span data-ttu-id="e052a-192">**Render**</span><span class="sxs-lookup"><span data-stu-id="e052a-192">**Render**</span></span><br /><br /> <span data-ttu-id="e052a-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="e052a-193">**Sort**</span></span><br /><br /> <span data-ttu-id="e052a-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="e052a-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="e052a-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="e052a-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="e052a-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="e052a-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="e052a-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="e052a-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="e052a-198">**Effectue**</span><span class="sxs-lookup"><span data-stu-id="e052a-198">**Execute**</span></span><br /><br /> <span data-ttu-id="e052a-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="e052a-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="e052a-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="e052a-200">TimeStart</span></span>|<span data-ttu-id="e052a-201">Heures de début et de fin qui indiquent la durée d'un traitement de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="e052a-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="e052a-202">TimeEnd</span></span>||  
|<span data-ttu-id="e052a-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="e052a-203">TimeDataRetrieval</span></span>|<span data-ttu-id="e052a-204">Nombre de millisecondes passées pour la récupération des données.</span><span class="sxs-lookup"><span data-stu-id="e052a-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="e052a-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="e052a-205">TimeProcessing</span></span>|<span data-ttu-id="e052a-206">Nombre de millisecondes passées pour le traitement du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="e052a-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="e052a-207">TimeRendering</span></span>|<span data-ttu-id="e052a-208">Nombre de millisecondes passées pour le rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="e052a-209">Source</span><span class="sxs-lookup"><span data-stu-id="e052a-209">Source</span></span>|<span data-ttu-id="e052a-210">Source d'exécution du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-210">Source of the report execution.</span></span> <span data-ttu-id="e052a-211">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="e052a-211">Possible values:</span></span><br /><br /> <span data-ttu-id="e052a-212">**En direct**</span><span class="sxs-lookup"><span data-stu-id="e052a-212">**Live**</span></span><br /><br /> <span data-ttu-id="e052a-213">**Cache**: indique une exécution mise en cache, par exemple, les requêtes de DataSet ne sont pas exécutées en direct.</span><span class="sxs-lookup"><span data-stu-id="e052a-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="e052a-214">**Instantané**</span><span class="sxs-lookup"><span data-stu-id="e052a-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="e052a-215">**History**</span><span class="sxs-lookup"><span data-stu-id="e052a-215">**History**</span></span><br /><br /> <span data-ttu-id="e052a-216">**Adhoc** : indique soit un rapport d’extraction basé sur un modèle de rapport généré dynamiquement, soit un rapport d’générateur de rapports qui est affiché en aperçu sur un client utilisant le serveur de rapports pour le traitement et le rendu.</span><span class="sxs-lookup"><span data-stu-id="e052a-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="e052a-217">**Session**: indique une requête de suivi dans une session déjà établie.</span><span class="sxs-lookup"><span data-stu-id="e052a-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="e052a-218">Par exemple, la requête initiale concerne l'affichage de la page 1 et la requête de suivi concerne l'exportation vers Excel avec l'état de la session active.</span><span class="sxs-lookup"><span data-stu-id="e052a-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="e052a-219">**RDCE**: indique une extension de la personnalisation de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="e052a-220">Une extension RDCE personnalisée peut personnaliser dynamiquement une définition de rapport avant qu'elle ne soit passée au moteur de traitement lors de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="e052a-221">Statut</span><span class="sxs-lookup"><span data-stu-id="e052a-221">Status</span></span>|<span data-ttu-id="e052a-222">État (soit rsSuccess, soit un code d'erreur. En cas de plusieurs erreurs, seule la première est enregistrée).</span><span class="sxs-lookup"><span data-stu-id="e052a-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="e052a-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="e052a-223">ByteCount</span></span>|<span data-ttu-id="e052a-224">Taille en octets des rapports rendus.</span><span class="sxs-lookup"><span data-stu-id="e052a-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="e052a-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="e052a-225">RowCount</span></span>|<span data-ttu-id="e052a-226">Nombre de lignes retournées par les requêtes.</span><span class="sxs-lookup"><span data-stu-id="e052a-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="e052a-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="e052a-227">AdditionalInfo</span></span>|<span data-ttu-id="e052a-228">Conteneur de propriétés XML contenant des informations supplémentaires sur l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="e052a-229">Le contenu peut être différent pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="e052a-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="e052a-230">Champ AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="e052a-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="e052a-231">Le champ AdditionalInfo est un conteneur de propriétés ou une structure XML contenant des informations supplémentaires sur l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="e052a-232">Le contenu peut être différent pour chaque ligne dans le journal.</span><span class="sxs-lookup"><span data-stu-id="e052a-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="e052a-233">Les tableaux suivants sont des exemples de contenu du champ AddtionalInfo pour la journalisation standard et commentée :</span><span class="sxs-lookup"><span data-stu-id="e052a-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="e052a-234">**Exemple de journalisation standard d'AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="e052a-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="e052a-235">**Exemple de journalisation commentée d'AdditionalInfo**</span><span class="sxs-lookup"><span data-stu-id="e052a-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="e052a-236">La section suivante décrit certaines des propriétés que vous verrez dans le champ AdditionalInfo :</span><span class="sxs-lookup"><span data-stu-id="e052a-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="e052a-237">**ProcessingEngine**: 1 = SQL Server 2005, 2 = nouveau moteur de traitement à la demande.</span><span class="sxs-lookup"><span data-stu-id="e052a-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="e052a-238">Si la plupart de vos rapports affichent toujours la valeur 1, vous pouvez envisager de les reconcevoir afin qu'ils utilisent le nouveau moteur de traitement à la demande, plus efficace.</span><span class="sxs-lookup"><span data-stu-id="e052a-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="e052a-239">**ScalabilityTime**: nombre de millisecondes consacrées à l’exécution d’opérations liées à l’échelle dans le moteur de traitement.</span><span class="sxs-lookup"><span data-stu-id="e052a-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="e052a-240">La valeur 0 indique qu'aucune période de temps supplémentaire n'a été passée sur les opérations d'échelle et indique également que la demande ne présente pas une mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="e052a-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="e052a-241">**EstimatedMemoryUsageKB**: estimation de la quantité de mémoire maximale, en kilo-octets, consommée par chaque composant pendant une requête particulière.</span><span class="sxs-lookup"><span data-stu-id="e052a-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="e052a-242">**DataExtension**: types d’extensions de données ou de sources de données utilisés dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="e052a-243">Le nombre représente le nombre d'occurrences de la source de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="e052a-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="e052a-244">**ExternalImages** La valeur est dans millisecondes.</span><span class="sxs-lookup"><span data-stu-id="e052a-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="e052a-245">Ces données peuvent être utilisées pour diagnostiquer les problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="e052a-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="e052a-246">Le temps nécessaire pour récupérer des images d'un serveur web externe peut ralentir l'exécution globale des rapports.</span><span class="sxs-lookup"><span data-stu-id="e052a-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="e052a-247">Ajouté dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e052a-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="e052a-248">**Connexions**: structure à plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="e052a-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="e052a-249">Ajouté dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e052a-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a><span data-ttu-id="e052a-250">Champs de journalisation (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="e052a-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="e052a-251">Cette vue ajoute de nouveaux champs et contient des champs renommés.</span><span class="sxs-lookup"><span data-stu-id="e052a-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="e052a-252">Voici un exemple d'instruction Transact SQL pour extraire des lignes de la vue ExecutionLog2.</span><span class="sxs-lookup"><span data-stu-id="e052a-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="e052a-253">L'exemple suppose que la base de données du serveur de rapports est nommée **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="e052a-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="e052a-254">La table suivante décrit les données qui sont capturées dans le journal d'exécution des rapports :</span><span class="sxs-lookup"><span data-stu-id="e052a-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="e052a-255">Colonne</span><span class="sxs-lookup"><span data-stu-id="e052a-255">Column</span></span>|<span data-ttu-id="e052a-256">Description</span><span class="sxs-lookup"><span data-stu-id="e052a-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e052a-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="e052a-257">InstanceName</span></span>|<span data-ttu-id="e052a-258">Nom de l'instance du serveur de rapports qui a géré la demande.</span><span class="sxs-lookup"><span data-stu-id="e052a-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="e052a-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="e052a-259">ReportPath</span></span>|<span data-ttu-id="e052a-260">Structure du chemin d'accès au rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-260">The path structure to the report.</span></span>  <span data-ttu-id="e052a-261">Par exemple, pour un rapport nommé « test » qui se trouve dans le dossier racine du gestionnaire de rapports, le ReportPath sera « /test ».</span><span class="sxs-lookup"><span data-stu-id="e052a-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="e052a-262">Pour un rapport nommé « test » qui est enregistré dans le dossier « samples » du gestionnaire de rapports, le ReportPath sera « /Samples/test/ »</span><span class="sxs-lookup"><span data-stu-id="e052a-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="e052a-263">UserName</span><span class="sxs-lookup"><span data-stu-id="e052a-263">UserName</span></span>|<span data-ttu-id="e052a-264">Identificateur de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e052a-264">User identifier.</span></span>|  
|<span data-ttu-id="e052a-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="e052a-265">ExecutionID</span></span>||  
|<span data-ttu-id="e052a-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="e052a-266">RequestType</span></span>|<span data-ttu-id="e052a-267">Type de demande (utilisateur ou système).</span><span class="sxs-lookup"><span data-stu-id="e052a-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="e052a-268">Mettre en forme</span><span class="sxs-lookup"><span data-stu-id="e052a-268">Format</span></span>|<span data-ttu-id="e052a-269">Format de rendu.</span><span class="sxs-lookup"><span data-stu-id="e052a-269">Rendering format.</span></span>|  
|<span data-ttu-id="e052a-270">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e052a-270">Parameters</span></span>|<span data-ttu-id="e052a-271">Valeurs des paramètres utilisées pour une exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="e052a-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="e052a-272">ReportAction</span></span>|<span data-ttu-id="e052a-273">Valeurs possibles : Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="e052a-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="e052a-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="e052a-274">TimeStart</span></span>|<span data-ttu-id="e052a-275">Heures de début et de fin qui indiquent la durée d'un traitement de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="e052a-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="e052a-276">TimeEnd</span></span>||  
|<span data-ttu-id="e052a-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="e052a-277">TimeDataRetrieval</span></span>|<span data-ttu-id="e052a-278">Nombre de millisecondes consacré à la récupération des données, au traitement du rapport et au rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="e052a-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="e052a-279">TimeProcessing</span></span>||  
|<span data-ttu-id="e052a-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="e052a-280">TimeRendering</span></span>||  
|<span data-ttu-id="e052a-281">Source</span><span class="sxs-lookup"><span data-stu-id="e052a-281">Source</span></span>|<span data-ttu-id="e052a-282">Source de l'exécution du rapport (1=Direct, 2=Cache, 3=Instantané, 4=Historique).</span><span class="sxs-lookup"><span data-stu-id="e052a-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="e052a-283">Statut</span><span class="sxs-lookup"><span data-stu-id="e052a-283">Status</span></span>|<span data-ttu-id="e052a-284">État (soit rsSuccess, soit un code d'erreur. En cas de plusieurs erreurs, seule la première est enregistrée).</span><span class="sxs-lookup"><span data-stu-id="e052a-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="e052a-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="e052a-285">ByteCount</span></span>|<span data-ttu-id="e052a-286">Taille en octets des rapports rendus.</span><span class="sxs-lookup"><span data-stu-id="e052a-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="e052a-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="e052a-287">RowCount</span></span>|<span data-ttu-id="e052a-288">Nombre de lignes retournées par les requêtes.</span><span class="sxs-lookup"><span data-stu-id="e052a-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="e052a-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="e052a-289">AdditionalInfo</span></span>|<span data-ttu-id="e052a-290">Conteneur de propriétés XML contenant des informations supplémentaires sur l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e052a-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a><span data-ttu-id="e052a-291">Champs de journalisation (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="e052a-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="e052a-292">Voici un exemple d'instruction Transact SQL pour extraire des lignes de la vue ExecutionLog.</span><span class="sxs-lookup"><span data-stu-id="e052a-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="e052a-293">L'exemple suppose que la base de données du serveur de rapports est nommée **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="e052a-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="e052a-294">La table suivante décrit les données qui sont capturées dans le journal d'exécution des rapports :</span><span class="sxs-lookup"><span data-stu-id="e052a-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="e052a-295">Colonne</span><span class="sxs-lookup"><span data-stu-id="e052a-295">Column</span></span>|<span data-ttu-id="e052a-296">Description</span><span class="sxs-lookup"><span data-stu-id="e052a-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e052a-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="e052a-297">InstanceName</span></span>|<span data-ttu-id="e052a-298">Nom de l'instance du serveur de rapports qui a géré la demande.</span><span class="sxs-lookup"><span data-stu-id="e052a-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="e052a-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="e052a-299">ReportID</span></span>|<span data-ttu-id="e052a-300">Identificateur du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-300">Report identifier.</span></span>|  
|<span data-ttu-id="e052a-301">UserName</span><span class="sxs-lookup"><span data-stu-id="e052a-301">UserName</span></span>|<span data-ttu-id="e052a-302">Identificateur de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e052a-302">User identifier.</span></span>|  
|<span data-ttu-id="e052a-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="e052a-303">RequestType</span></span>|<span data-ttu-id="e052a-304">Valeurs possibles :</span><span class="sxs-lookup"><span data-stu-id="e052a-304">Possible values:</span></span><br /><br /> <span data-ttu-id="e052a-305">True = Demande d'abonnement</span><span class="sxs-lookup"><span data-stu-id="e052a-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="e052a-306">False= Demande interactive</span><span class="sxs-lookup"><span data-stu-id="e052a-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="e052a-307">Mettre en forme</span><span class="sxs-lookup"><span data-stu-id="e052a-307">Format</span></span>|<span data-ttu-id="e052a-308">Format de rendu.</span><span class="sxs-lookup"><span data-stu-id="e052a-308">Rendering format.</span></span>|  
|<span data-ttu-id="e052a-309">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e052a-309">Parameters</span></span>|<span data-ttu-id="e052a-310">Valeurs des paramètres utilisées pour une exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="e052a-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="e052a-311">TimeStart</span></span>|<span data-ttu-id="e052a-312">Heures de début et de fin qui indiquent la durée d'un traitement de rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="e052a-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="e052a-313">TimeEnd</span></span>||  
|<span data-ttu-id="e052a-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="e052a-314">TimeDataRetrieval</span></span>|<span data-ttu-id="e052a-315">Nombre de millisecondes consacré à la récupération des données, au traitement du rapport et au rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="e052a-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="e052a-316">TimeProcessing</span></span>||  
|<span data-ttu-id="e052a-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="e052a-317">TimeRendering</span></span>||  
|<span data-ttu-id="e052a-318">Source</span><span class="sxs-lookup"><span data-stu-id="e052a-318">Source</span></span>|<span data-ttu-id="e052a-319">Source d'exécution du rapport.</span><span class="sxs-lookup"><span data-stu-id="e052a-319">Source of the report execution.</span></span> <span data-ttu-id="e052a-320">Valeurs possibles : (1=Actif, 2=Cache, 3=Instantané, 4=Historique, 5=Adhoc, 6=Session, 7=RDCE).</span><span class="sxs-lookup"><span data-stu-id="e052a-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="e052a-321">Statut</span><span class="sxs-lookup"><span data-stu-id="e052a-321">Status</span></span>|<span data-ttu-id="e052a-322">Valeurs possibles : rsSuccess, rsProcessingAborted, ou un code d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e052a-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="e052a-323">Si plusieurs erreurs se produisent, seule la première erreur est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="e052a-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="e052a-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="e052a-324">ByteCount</span></span>|<span data-ttu-id="e052a-325">Taille en octets des rapports rendus.</span><span class="sxs-lookup"><span data-stu-id="e052a-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="e052a-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="e052a-326">RowCount</span></span>|<span data-ttu-id="e052a-327">Nombre de lignes retournées par les requêtes.</span><span class="sxs-lookup"><span data-stu-id="e052a-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e052a-328">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e052a-328">See Also</span></span>  
 <span data-ttu-id="e052a-329">[Activer les événements de Reporting Services pour le journal des traces SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="e052a-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="e052a-330">[Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="e052a-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="e052a-331">Guide de référence des erreurs et des événements &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e052a-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
