---
title: Définir les options de traitement (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700769"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="fda8a-102">Définir les options de traitement (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="fda8a-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="fda8a-103">Vous pouvez définir des options de traitement sur un rapport [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour déterminer le moment où le traitement des données a lieu.</span><span class="sxs-lookup"><span data-stu-id="fda8a-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="fda8a-104">Vous pouvez également définir une valeur d'expiration pour le traitement des rapports, ainsi que des options qui déterminent si l'historique du rapport en cours est activé.</span><span class="sxs-lookup"><span data-stu-id="fda8a-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="fda8a-105">Vous pouvez exécuter un rapport en tant qu'instantané de rapport afin d'éviter qu'il soit exécuté à des moments inopportuns (par exemple, pendant une sauvegarde programmée).</span><span class="sxs-lookup"><span data-stu-id="fda8a-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="fda8a-106">En général, un instantané de rapport est créé et actualisé ultérieurement selon une planification, vous permettant ainsi de déterminer précisément le moment auquel le traitement du rapport et des données se produit.</span><span class="sxs-lookup"><span data-stu-id="fda8a-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="fda8a-107">Si un rapport est basé sur des requêtes dont l'exécution est longue ou qui utilisent des données d'une source de données que vous ne souhaitez pas rendre accessible à certaines heures, vous devez exécuter le rapport en tant qu'instantané.</span><span class="sxs-lookup"><span data-stu-id="fda8a-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="fda8a-108">Un serveur de rapports peut mettre en mémoire cache la copie d'un rapport traité et retourner cette copie lorsqu'un utilisateur ouvre le rapport.</span><span class="sxs-lookup"><span data-stu-id="fda8a-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="fda8a-109">La mise en cache est une technique d'optimisation des performances.</span><span class="sxs-lookup"><span data-stu-id="fda8a-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="fda8a-110">La mise en cache peut raccourcir le temps nécessaire à la récupération d'un rapport si celui-ci est volumineux ou fréquemment consulté.</span><span class="sxs-lookup"><span data-stu-id="fda8a-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="fda8a-111">L'historique de rapport est un ensemble de copies d'un rapport ayant fait l'objet d'une exécution précédente.</span><span class="sxs-lookup"><span data-stu-id="fda8a-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="fda8a-112">Vous pouvez utiliser l'historique de rapport pour conserver un enregistrement d'un rapport dans le temps.</span><span class="sxs-lookup"><span data-stu-id="fda8a-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="fda8a-113">L'historique de rapport ne convient pas aux rapports contenant des données confidentielles ou des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="fda8a-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="fda8a-114">Pour cette raison, l'historique de rapport peut inclure uniquement les rapports qui interrogent une source de données à l'aide d'un ensemble unique d'informations d'identification (soit stockées, soit utilisées pour l'exécution de rapport sans assistance) qui sont mises à la disposition de tous les utilisateurs qui exécutent un rapport.</span><span class="sxs-lookup"><span data-stu-id="fda8a-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="fda8a-115">avec SharePoint utilise les fonctionnalités de gestion du contenu extrait et archivé de SharePoint pour enregistrer les mises à jour des types de contenu de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fda8a-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="fda8a-116">Cela inclut la création d'instantanés de rapports.</span><span class="sxs-lookup"><span data-stu-id="fda8a-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="fda8a-117">Par conséquent, si vous avez activé le contrôle de version sur une bibliothèque de documents, vous verrez la version actualisée du rapport lorsqu'une nouvelle capture instantanée d'historique de rapport est créée.</span><span class="sxs-lookup"><span data-stu-id="fda8a-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="fda8a-118">Il s'agit d'un effet secondaire de la mise à jour des captures d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="fda8a-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="fda8a-119">Lorsqu'un instantané est mis à jour, la propriété LastExecution du rapport est modifiée, ce qui modifie la version du rapport.</span><span class="sxs-lookup"><span data-stu-id="fda8a-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="fda8a-120">Vous pouvez spécifier des valeurs de délai d'attente pour fixer des limites à l'utilisation des ressources système.</span><span class="sxs-lookup"><span data-stu-id="fda8a-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="fda8a-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="fda8a-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="fda8a-122">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="fda8a-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="fda8a-123">Pour définir les options d'actualisation des données</span><span class="sxs-lookup"><span data-stu-id="fda8a-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="fda8a-124">Pour définir les options de mise en cache de rapport</span><span class="sxs-lookup"><span data-stu-id="fda8a-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="fda8a-125">Pour définir des délais d'expiration de traitement</span><span class="sxs-lookup"><span data-stu-id="fda8a-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="fda8a-126">Pour définir les options et limites de l'historique de rapport</span><span class="sxs-lookup"><span data-stu-id="fda8a-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="fda8a-127">Définir le délai d'attente de base de données</span><span class="sxs-lookup"><span data-stu-id="fda8a-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="fda8a-128">Pour définir les options d’actualisation des données</span><span class="sxs-lookup"><span data-stu-id="fda8a-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="fda8a-129">Pointez vers un rapport de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="fda8a-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="fda8a-130">Cliquez sur la flèche vers le bas et sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="fda8a-131">Dans **Options d'actualisation des données**, cliquez sur **Utiliser les données d'instantanés**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="fda8a-132">Si le message « Ce rapport ne peut pas être exécuté à partir d'un instantané parce qu'une ou plusieurs des informations d'identification des sources de données ne sont pas stockées » s'affiche, le rapport n'est pas configuré pour être exécuté sans assistance. Vous devez donc modifier les sources de données pour qu'elles utilisent les informations d'identification stockées avant de définir cette option.</span><span class="sxs-lookup"><span data-stu-id="fda8a-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="fda8a-133">Dans **Options d'instantanés des données**, sélectionnez **Planifier le traitement des données**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="fda8a-134">Sélectionnez **Suivant une planification partagée** si vous disposez d'une planification partagée existante que vous pouvez utiliser ; sinon, cliquez sur **Suivant une planification personnalisée**, puis sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="fda8a-135">Sélectionnez la fréquence, la planification et les dates de début et de fin, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="fda8a-136">Dans **Options d'instantanés des données**, sélectionnez **Créer ou mettre à jour l'instantané lorsque cette page est enregistrée** si vous souhaitez créer immédiatement les données d'instantané à utiliser avec le rapport sans attendre le traitement planifié des données.</span><span class="sxs-lookup"><span data-stu-id="fda8a-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="fda8a-137">Pour définir les options de mise en cache d’un rapport</span><span class="sxs-lookup"><span data-stu-id="fda8a-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="fda8a-138">Pointez vers un rapport de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="fda8a-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="fda8a-139">Cliquez sur la flèche vers le bas et sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="fda8a-140">Dans **Options d'actualisation des données**, cliquez sur **Utiliser les données en cache**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="fda8a-141">Si le message « Ce rapport ne peut pas être mis en cache parce qu'une ou plusieurs informations d'identification des sources de données ne sont pas stockées » s'affiche, le rapport n'est pas configuré pour être exécuté sans assistance. Avant de définir cette option, vous devez donc modifier les sources de données pour qu'elles utilisent les informations d'identification stockées.</span><span class="sxs-lookup"><span data-stu-id="fda8a-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="fda8a-142">Dans **Options de cache**, spécifiez comment le cache expirera :</span><span class="sxs-lookup"><span data-stu-id="fda8a-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="fda8a-143">Entrez le nombre de minutes avant l'expiration du cache.</span><span class="sxs-lookup"><span data-stu-id="fda8a-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="fda8a-144">Utilisez une planification partagée pour effacer le cache à des instants spécifiés dans la planification.</span><span class="sxs-lookup"><span data-stu-id="fda8a-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="fda8a-145">Créez une planification personnalisée pour effacer le cache à un instant que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="fda8a-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="fda8a-146">Pour définir des valeurs de délai d’attente de traitement</span><span class="sxs-lookup"><span data-stu-id="fda8a-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="fda8a-147">Pointez vers un rapport de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="fda8a-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="fda8a-148">Cliquez sur la flèche vers le bas et sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="fda8a-149">Dans **Délai de traitement**, sélectionnez **Utiliser le paramètre par défaut de site** si vous voulez utiliser la valeur spécifiée au niveau du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fda8a-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="fda8a-150">Sinon, sélectionnez **Ne pas spécifier de délai d’exécution lors du traitement du rapport** ou **Limiter le traitement des rapports (en secondes)** pour remplacer cette valeur par un délai d’expiration différent ou par aucun délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="fda8a-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="fda8a-151">Pour définir les options et les limites de l’historique de rapport</span><span class="sxs-lookup"><span data-stu-id="fda8a-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="fda8a-152">Pointez vers un rapport de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="fda8a-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="fda8a-153">Cliquez sur la flèche vers le bas et sélectionnez **Gérer les options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="fda8a-154">Dans **Options des instantanés d'historique**, spécifiez comment et quand le traitement des données a lieu et est enregistré.</span><span class="sxs-lookup"><span data-stu-id="fda8a-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="fda8a-155">Dans **Limites des instantanés d'historique**, sélectionnez **Utiliser le paramètre par défaut de site** si vous voulez utiliser la valeur spécifiée au niveau du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="fda8a-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="fda8a-156">Sinon, sélectionnez **Ne pas limiter le nombre d'instantanés** ou **Limiter le nombre d'instantanés à** pour spécifier une valeur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fda8a-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="fda8a-157">Définir le délai d’expiration de base de données</span><span class="sxs-lookup"><span data-stu-id="fda8a-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="fda8a-158">Utilisez Windows PowerShell pour définir le délai d'attente de base de données sur un serveur de rapports SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fda8a-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="fda8a-159">Pour plus d’informations, consultez la section « obtenir et définir les propriétés de la base de données d’application Reporting Services » de la rubrique [applets de commande PowerShell pour Reporting Services mode SharePoint](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fda8a-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda8a-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fda8a-160">See Also</span></span>  
 <span data-ttu-id="fda8a-161">[Définir les propriétés de traitement d’un rapport](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fda8a-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="fda8a-162">[Mise en cache de rapports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fda8a-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="fda8a-163">Définition des valeurs de délai d’attente pour le traitement d’un rapport et d’un dataset partagé &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fda8a-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
