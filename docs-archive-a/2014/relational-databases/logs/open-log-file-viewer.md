---
title: Ouvrir la Visionneuse du fichier journal | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603983"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="5a15a-102">Ouvrir la Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="5a15a-102">Open Log File Viewer</span></span>
  <span data-ttu-id="5a15a-103">Vous pouvez utiliser la Visionneuse du fichier journal dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour accéder aux informations sur les erreurs et événements capturés dans les journaux suivants :</span><span class="sxs-lookup"><span data-stu-id="5a15a-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="5a15a-104">Collection d'audits</span><span class="sxs-lookup"><span data-stu-id="5a15a-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="5a15a-105">Collecte de données</span><span class="sxs-lookup"><span data-stu-id="5a15a-105">Data Collection</span></span>  
  
-   <span data-ttu-id="5a15a-106">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="5a15a-106">Database Mail</span></span>  
  
-   <span data-ttu-id="5a15a-107">Historique des travaux</span><span class="sxs-lookup"><span data-stu-id="5a15a-107">Job History</span></span>  
  
-   <span data-ttu-id="5a15a-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a15a-108">SQL Server</span></span>  
  
-   <span data-ttu-id="5a15a-109">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5a15a-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="5a15a-110">Événements Windows (ces événements Windows sont également accessibles à partir de l'observateur d'événements).</span><span class="sxs-lookup"><span data-stu-id="5a15a-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="5a15a-111">Depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], vous pouvez utiliser les serveurs inscrits pour consulter les fichiers journaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] depuis des instances locales ou distantes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a15a-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a15a-112">En utilisant les serveurs inscrits, vous pouvez consulter les fichiers journaux lorsque les instances sont ou en ligne ou hors connexion.</span><span class="sxs-lookup"><span data-stu-id="5a15a-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="5a15a-113">Pour plus d’informations sur l’accès en ligne, consultez la procédure « Pour consulter des fichiers journaux en ligne à partir des serveurs inscrits », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5a15a-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="5a15a-114">Pour plus d’informations sur les modalités d’accès aux fichiers journaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hors connexion, consultez [Afficher les fichiers journaux hors connexion](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="5a15a-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="5a15a-115">Vous pouvez ouvrir la Visionneuse du fichier journal de différentes façons, selon les informations que vous souhaitez consulter.</span><span class="sxs-lookup"><span data-stu-id="5a15a-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a15a-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5a15a-116">Permissions</span></span>  
 <span data-ttu-id="5a15a-117">Pour accéder aux fichiers journaux pour les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui sont en ligne, l’appartenance au rôle serveur fixe securityadmin est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5a15a-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="5a15a-118">L’accès aux fichiers journaux des instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hors connexion nécessite un accès en lecture à l’espace de noms WMI **Root\Microsoft\SqlServer\ComputerManagement10** et au dossier où sont stockés les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="5a15a-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="5a15a-119">Pour plus d’informations, consultez la section Sécurité de la rubrique [Afficher les fichiers journaux hors connexion](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="5a15a-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="5a15a-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a15a-120">Security</span></span>  
 <span data-ttu-id="5a15a-121">Nécessite l'appartenance en tant que membre au rôle serveur fixe securityadmin.</span><span class="sxs-lookup"><span data-stu-id="5a15a-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="5a15a-122">Afficher les fichiers journaux</span><span class="sxs-lookup"><span data-stu-id="5a15a-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="5a15a-123">Pour afficher les journaux relatifs à l'activité générale de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a15a-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="5a15a-124">Dans l’Explorateur d’objets, développez **Gestion**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="5a15a-125">Effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a15a-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="5a15a-126">Cliquez avec le bouton droit sur **Journaux SQL Server**, pointez sur **Afficher**, puis cliquez sur **Journal SQL Server** ou sur **Journal de SQL Server et de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="5a15a-127">Développez **Journaux SQL Server**, cliquez avec le bouton droit sur un fichier journal, puis cliquez sur **Afficher le journal SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="5a15a-128">Vous pouvez également double-cliquer sur un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="5a15a-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="5a15a-129">Les journaux incluent **Messagerie de base de données**, **SQL Server**, **SQL Server Agent**et **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="5a15a-130">Pour afficher les journaux relatifs aux travaux</span><span class="sxs-lookup"><span data-stu-id="5a15a-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="5a15a-131">Dans l’Explorateur d’objets, développez **SQL Server Agent**, cliquez avec le bouton droit sur **Travaux**, puis cliquez sur **Afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="5a15a-132">Les journaux incluent **Messagerie de base de données**, **Historique des travaux**et **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="5a15a-133">Pour afficher les journaux relatifs aux plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="5a15a-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="5a15a-134">Dans l’Explorateur d’objets, développez **Gestion**, cliquez avec le bouton droit sur **Plans de maintenance**, puis cliquez sur **Afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="5a15a-135">Les journaux incluent **Messagerie de base de données**, **Historique du travail**, **Plans de maintenance**, **Plans de maintenance distants**et **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="5a15a-136">Pour afficher les journaux relatifs à la collecte de données</span><span class="sxs-lookup"><span data-stu-id="5a15a-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="5a15a-137">Dans l’Explorateur d’objets, développez **Gestion**, cliquez avec le bouton droit sur **Collecte de données**, puis cliquez sur **Afficher les journaux**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="5a15a-138">Les journaux incluent **Collecte de données**, **Historique du travail**et **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="5a15a-139">Pour afficher les journaux relatifs à la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="5a15a-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="5a15a-140">Dans l’Explorateur d’objets, développez **Gestion**, cliquez avec le bouton droit sur **Messagerie de base de données**, puis cliquez sur **Afficher le journal de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="5a15a-141">Les journaux incluent **Messagerie de base de données, Historique du travail**, **Plans de maintenance**, **Plans de maintenance distants**, **SQL Server**, **SQL Server Agent**et **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="5a15a-142">Pour afficher les journaux relatifs aux collections d'audits</span><span class="sxs-lookup"><span data-stu-id="5a15a-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="5a15a-143">Dans l’Explorateur d’objets, développez **Sécurité**et **Audits**, cliquez avec le bouton droit sur un audit, puis sélectionnez **Afficher les journaux d’audit**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="5a15a-144">Les journaux incluent **Collection d’audits** et **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="5a15a-145">Pour afficher les journaux relatifs aux collections d'audits</span><span class="sxs-lookup"><span data-stu-id="5a15a-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="5a15a-146">Dans l’Explorateur d’objets, développez **Sécurité**et **Audits**, cliquez avec le bouton droit sur un audit, puis sélectionnez **Afficher les journaux d’audit**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="5a15a-147">Les journaux incluent **Collection d’audits** et **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="5a15a-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a15a-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a15a-148">See Also</span></span>  
 <span data-ttu-id="5a15a-149">[Visionneuse du fichier journal](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="5a15a-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="5a15a-150">[SQL Server Audit &#40moteur de base de données&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="5a15a-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="5a15a-151">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="5a15a-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
