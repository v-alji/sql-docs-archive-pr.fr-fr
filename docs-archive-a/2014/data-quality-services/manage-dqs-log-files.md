---
title: Gérer les fichiers journaux DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ca85772b8cc8aca41b75ad05d028bc444f280378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613637"
---
# <a name="manage-dqs-log-files"></a><span data-ttu-id="df9b5-102">Gérer les fichiers journaux DQS</span><span class="sxs-lookup"><span data-stu-id="df9b5-102">Manage DQS Log Files</span></span>
  <span data-ttu-id="df9b5-103">Les fichiers journaux[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) vous aident dans le diagnostic et la résolution de problèmes avec [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]et [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-103">[!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) log files help you in diagnosing and troubleshooting issue with [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="df9b5-104">Des fichiers journaux distincts sont générés pour [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]et [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-104">Separate log files are generated for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
 <span data-ttu-id="df9b5-105">Vous pouvez utiliser [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] pour configurer le paramètre de gravité du journal pour les fonctionnalités et les modules [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df9b5-105">You can use [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] to configure the log severity setting for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] features and modules.</span></span> <span data-ttu-id="df9b5-106">En outre, vous pouvez également configurer d'autres paramètres (avancés) pour les fichiers journaux DQS en modifiant manuellement les paramètres de configuration des journaux DQS dans la base de données DQS_MAIN et un fichier XML sur l'ordinateur [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df9b5-106">Additionally, you can also configure some other (advanced) settings for the DQS log files by manually changing the DQS log configuration settings in the DQS_MAIN database and an XML file on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer.</span></span>  
  
##  <a name="data-quality-server-log-file"></a><a name="DQSServer"></a><span data-ttu-id="df9b5-107">Fichier journal du serveur de qualité des données</span><span class="sxs-lookup"><span data-stu-id="df9b5-107">Data Quality Server Log File</span></span>  
 <span data-ttu-id="df9b5-108">Le fichier journal [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , DQServerLog.DQS_MAIN.log, inclut les enregistrements des activités exécutées sur [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-108">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, DQServerLog.DQS_MAIN.log, includes logs of activities that are run on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="df9b5-109">Si vous avez installé l'instance par défaut de SQL Server, le fichier DQServerLog.DQS_MAIN.log est disponible sous C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span><span class="sxs-lookup"><span data-stu-id="df9b5-109">If you installed the default instance of SQL Server, the DQServerLog.DQS_MAIN.log file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log.</span></span> <span data-ttu-id="df9b5-110">Le fichier journal [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] contient les informations suivantes, chacune délimitée par une barre verticale (|) :</span><span class="sxs-lookup"><span data-stu-id="df9b5-110">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file contains the following pieces of information, each delimited by a pipe (|):</span></span>  
  
-   <span data-ttu-id="df9b5-111">Date et heure</span><span class="sxs-lookup"><span data-stu-id="df9b5-111">Date and time</span></span>  
  
-   <span data-ttu-id="df9b5-112">Nom du thread</span><span class="sxs-lookup"><span data-stu-id="df9b5-112">Thread name</span></span>  
  
-   <span data-ttu-id="df9b5-113">ID du thread</span><span class="sxs-lookup"><span data-stu-id="df9b5-113">Thread ID</span></span>  
  
-   <span data-ttu-id="df9b5-114">Gravité de l'enregistrement (FATAL, ERROR, WARN, INFO et DEBUG)</span><span class="sxs-lookup"><span data-stu-id="df9b5-114">Log severity (FATAL, ERROR, WARN, INFO, and DEBUG)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df9b5-115">La gravité DEBUG est identique à Commentaires.</span><span class="sxs-lookup"><span data-stu-id="df9b5-115">The DEBUG logging severity is same as Verbose.</span></span>  
  
-   <span data-ttu-id="df9b5-116">UID (ID infrastructure DQS interne)</span><span class="sxs-lookup"><span data-stu-id="df9b5-116">UID (internal DQS infrastructure ID)</span></span>  
  
-   <span data-ttu-id="df9b5-117">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="df9b5-117">Namespace</span></span>  
  
-   <span data-ttu-id="df9b5-118">Classe et méthode</span><span class="sxs-lookup"><span data-stu-id="df9b5-118">Class and method</span></span>  
  
-   <span data-ttu-id="df9b5-119">Message</span><span class="sxs-lookup"><span data-stu-id="df9b5-119">Message</span></span>  
  
 <span data-ttu-id="df9b5-120">Outre ces informations, le fichier journal affiche aussi des informations sur la version de l'application, le nom de l'ordinateur, le nom d'utilisateur et le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="df9b5-120">Along with these, the log file also displays information about the application version, computer name, user name, and operating system.</span></span>  
  
 <span data-ttu-id="df9b5-121">Un exemple d'entrée du fichier journal [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="df9b5-121">A sample entry in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file looks like the following:</span></span>  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 <span data-ttu-id="df9b5-122">Le fichier DQServerLog.DQS_MAIN.log est un fichier de restauration et un nouveau fichier journal est créé une fois que le fichier journal existant dépasse la limite de la taille du fichier par progression spécifiée dans les paramètres de configuration du journal [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df9b5-122">The DQServerLog.DQS_MAIN.log file is a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="df9b5-123">Pour plus d'informations, consultez [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="df9b5-123">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="data-quality-client-log-file"></a><a name="DQSClient"></a><span data-ttu-id="df9b5-124">Fichier journal Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="df9b5-124">Data Quality Client Log File</span></span>  
 <span data-ttu-id="df9b5-125">Le fichier journal [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , DQClientLog.log, inclut les enregistrements côté client.</span><span class="sxs-lookup"><span data-stu-id="df9b5-125">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file, DQClientLog.log, includes the client side logs.</span></span> <span data-ttu-id="df9b5-126">Le fichier journal [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] est disponible à %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="df9b5-126">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="df9b5-127">Le fichier journal [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] contient un ensemble d'informations similaires à celles du fichier journal du serveur, mais pour le côté client.</span><span class="sxs-lookup"><span data-stu-id="df9b5-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file contains similar set of information as in the server log file, but for the client side.</span></span>  
  
 <span data-ttu-id="df9b5-128">Comme pour le fichier journal [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , le fichier journal [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] est aussi un fichier par progression et un nouveau fichier journal est créé une fois que le fichier journal existant dépasse la limite de la taille du fichier par progression spécifiée dans les paramètres de configuration du journal [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df9b5-128">As with the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log file, the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log file is also a rolling file, and a new log file is created once the existing log file exceeds the rolling file size limit specified in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log configuration settings.</span></span> <span data-ttu-id="df9b5-129">Pour plus d'informations, consultez [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="df9b5-129">For more information, see [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md).</span></span>  
  
##  <a name="dqs-cleansing-component-log-file"></a><a name="DQSCleansing"></a><span data-ttu-id="df9b5-130">Fichier journal du composant de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="df9b5-130">DQS Cleansing Component Log File</span></span>  
 <span data-ttu-id="df9b5-131">Le fichier journal [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] , DQSSSISLog.log, inclut les enregistrements des activités effectuées à l'aide de [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-131">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file, DQSSSISLog.log, includes logs of activities performed using the [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)].</span></span> <span data-ttu-id="df9b5-132">Le fichier journal du composant [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] est disponible à %APPDATA%\SSDQS\Log.</span><span class="sxs-lookup"><span data-stu-id="df9b5-132">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] component log file is available at %APPDATA%\SSDQS\Log.</span></span> <span data-ttu-id="df9b5-133">Le fichier journal [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] contient un ensemble d'informations similaires à celles du fichier journal du serveur, mais pour le [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-133">The [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] log file contains similar set of information as in the server log file, but for the [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)].</span></span>  
  
##  <a name="related-tasks"></a><a name="RT"></a> <span data-ttu-id="df9b5-134">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="df9b5-134">Related Tasks</span></span>  
  
|<span data-ttu-id="df9b5-135">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="df9b5-135">Task Description</span></span>|<span data-ttu-id="df9b5-136">Rubrique</span><span class="sxs-lookup"><span data-stu-id="df9b5-136">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="df9b5-137">Décrit comment configurer les paramètres de gravité du journal pour les fichiers journaux DQS avec [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9b5-137">Describes how to configure log severity settings for DQS log files using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>|[<span data-ttu-id="df9b5-138">Configurer les niveaux de gravité pour les fichiers journaux DQS</span><span class="sxs-lookup"><span data-stu-id="df9b5-138">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|<span data-ttu-id="df9b5-139">Explique comment configurer manuellement les paramètres avancés des fichiers journaux DQS.</span><span class="sxs-lookup"><span data-stu-id="df9b5-139">Describes how to manually configure advanced settings for DQS log files.</span></span>|[<span data-ttu-id="df9b5-140">Configurer les paramètres avancés pour les fichiers journaux DQS</span><span class="sxs-lookup"><span data-stu-id="df9b5-140">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a><span data-ttu-id="df9b5-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df9b5-141">See Also</span></span>  
 [<span data-ttu-id="df9b5-142">administration de dqs</span><span class="sxs-lookup"><span data-stu-id="df9b5-142">DQS Administration</span></span>](../../2014/data-quality-services/dqs-administration.md)  
  
  
