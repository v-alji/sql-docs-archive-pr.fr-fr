---
title: Visionneuse du fichier journal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603987"
---
# <a name="log-file-viewer"></a><span data-ttu-id="77fe6-102">Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="77fe6-102">Log File Viewer</span></span>
  <span data-ttu-id="77fe6-103">La Visionneuse du fichier journal dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permet d'accéder aux informations sur les erreurs et événements capturés dans les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="77fe6-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="77fe6-104">Avantages liés à l'utilisation de la Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="77fe6-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="77fe6-105">Vous pouvez consulter des fichiers journaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'une instance locale ou distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsque l'instance cible est hors connexion ou ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="77fe6-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="77fe6-106">Vous pouvez accéder aux fichiers journaux hors connexion à partir des serveurs inscrits, ou par programmation via des requêtes WMI et WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="77fe6-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="77fe6-107">Pour plus d’informations, consultez [Afficher les fichiers journaux hors connexion](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="77fe6-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="77fe6-108">Voici les types de fichiers journaux auxquels vous pouvez accéder à l'aide de la Visionneuse du fichier journal :</span><span class="sxs-lookup"><span data-stu-id="77fe6-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="77fe6-109">Collection d'audits</span><span class="sxs-lookup"><span data-stu-id="77fe6-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="77fe6-110">Collecte de données</span><span class="sxs-lookup"><span data-stu-id="77fe6-110">Data Collection</span></span>  
  
-   <span data-ttu-id="77fe6-111">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="77fe6-111">Database Mail</span></span>  
  
-   <span data-ttu-id="77fe6-112">Historique des travaux</span><span class="sxs-lookup"><span data-stu-id="77fe6-112">Job History</span></span>  
  
-   <span data-ttu-id="77fe6-113">Plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="77fe6-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="77fe6-114">Plans de maintenance distants</span><span class="sxs-lookup"><span data-stu-id="77fe6-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="77fe6-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="77fe6-115">SQL Server</span></span>  
  
-   <span data-ttu-id="77fe6-116">SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="77fe6-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="77fe6-117">Windows NT (ces événements Windows sont également accessibles à partir de l'Observateur d'événements)</span><span class="sxs-lookup"><span data-stu-id="77fe6-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="77fe6-118">Tâches de la Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="77fe6-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="77fe6-119">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="77fe6-119">Task Description</span></span>|<span data-ttu-id="77fe6-120">Rubrique</span><span class="sxs-lookup"><span data-stu-id="77fe6-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="77fe6-121">Explique comment ouvrir la Visionneuse du fichier journal de différentes façons, selon les informations que vous souhaitez consulter.</span><span class="sxs-lookup"><span data-stu-id="77fe6-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="77fe6-122">Ouvrir la Visionneuse du fichier journal</span><span class="sxs-lookup"><span data-stu-id="77fe6-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="77fe6-123">Explique comment afficher des fichiers journaux hors ligne par le biais de serveurs inscrits et comment vérifier les autorisations WMI.</span><span class="sxs-lookup"><span data-stu-id="77fe6-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="77fe6-124">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="77fe6-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="77fe6-125">Fournit l'aide (accessible à l'aide de la touche F1) relative à la Visionneuse du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="77fe6-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="77fe6-126">Visionneuse du fichier journal - Aide (F1)</span><span class="sxs-lookup"><span data-stu-id="77fe6-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="77fe6-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77fe6-127">See Also</span></span>  
 <span data-ttu-id="77fe6-128">[SQL Server Audit &#40moteur de base de données&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="77fe6-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="77fe6-129">Journal des erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="77fe6-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
