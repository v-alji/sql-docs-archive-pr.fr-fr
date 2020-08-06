---
title: Démarrer et arrêter le service Report Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605078"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="91962-102">Démarrer et arrêter le service Report Server</span><span class="sxs-lookup"><span data-stu-id="91962-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="91962-103">Un serveur de rapports est implémenté comme un service Windows unique qui contient le service Web Report Server, le Gestionnaire de rapports et une application de traitement en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="91962-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="91962-104">Le service doit s'exécuter afin que vous puissiez utiliser les fonctionnalités du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="91962-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="91962-105">L'arrêt du service interrompt toutes les opérations du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="91962-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="91962-106">Pendant que le service est arrêté, les requêtes de traitement des abonnements et des rapports planifiés, qui auraient eu lieu si le service était en cours d'exécution, sont ajoutées à la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="91962-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="91962-107">En effet, les travaux exécutés par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] créent les événements.</span><span class="sxs-lookup"><span data-stu-id="91962-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="91962-108">Si vous souhaitez éviter la création d'un journal des travaux en souffrance pendant que le service est interrompu, songez à arrêter également l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91962-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="91962-109">Vous disposez de toute une série d'outils pour démarrer ou arrêter le service Report Server, notamment l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que l'outil Services proposé dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="91962-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="91962-110">Si vous ne vous limitez pas au démarrage et à l'arrêt du service, par exemple si vous modifiez également le compte de service, vous devez utiliser l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91962-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="91962-111">L'utilisation d'autres outils pour modifier le compte de service peut endommager votre installation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91962-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="91962-112">Pour plus d’informations, consultez [Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="91962-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="91962-113">Vous ne pouvez pas interrompre et reprendre le service.</span><span class="sxs-lookup"><span data-stu-id="91962-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="91962-114">Il n'y a pas de paramètres de démarrage.</span><span class="sxs-lookup"><span data-stu-id="91962-114">There are no start parameters.</span></span> <span data-ttu-id="91962-115">Même s'il n'existe pas de dépendances explicites, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être en cours d'exécution si le serveur prend en charge des abonnements ou des opérations de rapport planifiées.</span><span class="sxs-lookup"><span data-stu-id="91962-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="91962-116">Pour démarrer ou arrêter le service à l'aide de l'outil de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="91962-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="91962-117">Démarrez l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , puis connectez-vous au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="91962-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="91962-118">Sur la page d'état du serveur de rapports, cliquez sur **Arrêter** ou sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="91962-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="91962-119">Pour démarrer ou arrêter le service à l'aide de l'outil Services dans les Outils d'administration</span><span class="sxs-lookup"><span data-stu-id="91962-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="91962-120">Dans Outils d’administration, ouvrez Services, cliquez avec le bouton droit sur **SQL Server Reporting Services (MSSQLSERVER)**, puis cliquez sur **Arrêter** ou sur **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="91962-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="91962-121">Si vous exécutez plusieurs instances ou si le serveur de rapports s'exécute en tant qu'instance nommée, vérifiez que le nom de l'instance entre parenthèses correspond à l'instance du serveur de rapports que vous voulez arrêter ou redémarrer.</span><span class="sxs-lookup"><span data-stu-id="91962-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="91962-122">Pour démarrer ou arrêter le service à l'aide du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="91962-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="91962-123">Démarrez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91962-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="91962-124">Sélectionnez Services SQL Server, cliquez avec le bouton droit sur **SQL Server Reporting Services**, puis cliquez sur **Arrêter** ou sur **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="91962-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91962-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91962-125">See Also</span></span>  
 [<span data-ttu-id="91962-126">Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="91962-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
