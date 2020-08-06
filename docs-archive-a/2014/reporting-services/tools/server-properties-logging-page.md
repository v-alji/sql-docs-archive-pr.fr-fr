---
title: Propriétés du serveur (page Enregistrement) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610967"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="b14b8-102">Propriétés du serveur (page Enregistrement)</span><span class="sxs-lookup"><span data-stu-id="b14b8-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="b14b8-103">Utilisez cette page pour définir des limites sur les données du rapport d'exécution qui sont recueillies par un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b14b8-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="b14b8-104">Les données d'exécution sont stockées en interne dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b14b8-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="b14b8-105">Vous pouvez effectuer le suivi de l'activité des rapports pour le serveur de rapports qui s'exécute en mode natif ou mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b14b8-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="b14b8-106">Si le serveur de rapports fait partie d'un déploiement avec montée en puissance parallèle, le journal d'exécution des rapports gère un enregistrement de l'ensemble de l'activité des rapports pour tout le déploiement dans un seul fichier journal.</span><span class="sxs-lookup"><span data-stu-id="b14b8-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="b14b8-107">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, cliquez avec le bouton droit sur le nom du serveur de rapports et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b14b8-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="b14b8-108">Cliquez sur **Enregistrement** pour ouvrir cette page.</span><span class="sxs-lookup"><span data-stu-id="b14b8-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b14b8-109">Options</span><span class="sxs-lookup"><span data-stu-id="b14b8-109">Options</span></span>  
 <span data-ttu-id="b14b8-110">**Activer la journalisation de l’exécution des rapports**</span><span class="sxs-lookup"><span data-stu-id="b14b8-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="b14b8-111">Cliquez pour créer et stocker des informations sur l'activité des rapports sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b14b8-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="b14b8-112">Si cette option est activée, le serveur de rapports effectuera le suivi des rapports qui sont utilisés, de la fréquence de traitement des rapports, du type d'opération de rapport effectuée, du format de sortie et de la personne qui a exécuté le rapport.</span><span class="sxs-lookup"><span data-stu-id="b14b8-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="b14b8-113">Pour plus d’informations sur les points de données supplémentaires capturés dans le journal, consultez [Journal d’exécution du serveur de rapports et vue ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="b14b8-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="b14b8-114">**Supprimer les entrées du journal antérieures au nombre de jours suivant**</span><span class="sxs-lookup"><span data-stu-id="b14b8-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="b14b8-115">Spécifiez le nombre de jours après lesquels les entrées du journal seront effacées du journal d'exécution des rapports.</span><span class="sxs-lookup"><span data-stu-id="b14b8-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="b14b8-116">La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="b14b8-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14b8-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b14b8-117">See Also</span></span>  
 <span data-ttu-id="b14b8-118">[Définir les propriétés du serveur de rapports &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b14b8-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="b14b8-119">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b14b8-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="b14b8-120">[Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="b14b8-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="b14b8-121">[Serveur de rapports dans Management Studio aide (F1)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b14b8-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="b14b8-122">Journal des exécutions du serveur de rapports et vue ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="b14b8-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
