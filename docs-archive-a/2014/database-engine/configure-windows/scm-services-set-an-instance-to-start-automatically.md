---
title: Définir une instance de SQL Server pour qu’elle démarre automatiquement (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706744"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="0aea9-102">Définir le démarrage automatique d'une instance de SQL Server (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0aea9-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="0aea9-103">Cette rubrique explique comment définir une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin qu'elle démarre automatiquement dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0aea9-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="0aea9-104">Durant l'installation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est normalement configuré afin de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0aea9-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="0aea9-105">Si le démarrage automatique n'a pas été configuré, vous pouvez modifier ce paramètre lorsque vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="0aea9-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0aea9-106">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aea9-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="0aea9-107">Pour définir le démarrage automatique d'une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aea9-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="0aea9-108">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0aea9-109">Étant donné que le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est un composant logiciel enfichable pour le programme [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console et non pas un programme autonome, le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n’apparaît pas en tant qu’application dans les versions plus récentes de Windows.</span><span class="sxs-lookup"><span data-stu-id="0aea9-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="0aea9-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="0aea9-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="0aea9-111">Pour ouvrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, dans la **page de démarrage**, tapez SQLServerManager12. msc (pour [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="0aea9-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="0aea9-112">Pour les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , remplacez 12 par un nombre plus petit.</span><span class="sxs-lookup"><span data-stu-id="0aea9-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="0aea9-113">Le fait de cliquer sur SQLServerManager12.msc ouvre le Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="0aea9-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="0aea9-114">Pour épingler le Configuration Manager à la page de démarrage ou à la barre des tâches, cliquez avec le bouton droit sur SQLServerManager12. msc, puis cliquez sur **ouvrir l’emplacement du fichier**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="0aea9-115">Dans l’Explorateur de fichiers Windows, cliquez avec le bouton droit sur SQLServerManager12. msc, puis cliquez sur **épingler pour démarrer** ou **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="0aea9-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="0aea9-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="0aea9-117">Pour ouvrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, dans l’icône **Rechercher** , sous **applications**, tapez **SQLServerManager \<version> . msc** , par exemple `SQLServerManager12.msc` , puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="0aea9-118">Dans le **Gestionnaire de configuration SQL Server**, développez **Services**, puis cliquez sur **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="0aea9-119">Dans le volet d’informations, cliquez avec le bouton droit sur le nom de l’instance qui devra démarrer automatiquement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0aea9-120">Dans la boîte de dialogue **Propriétés de SQL Server \<***instancename***>** , définissez **Mode de démarrage** sur **Automatique**.</span><span class="sxs-lookup"><span data-stu-id="0aea9-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="0aea9-121">Cliquez sur **OK**, puis fermez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0aea9-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aea9-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0aea9-122">See Also</span></span>  
 <span data-ttu-id="0aea9-123">[Empêcher le démarrage automatique d’une instance de SQL Server &#40;Gestionnaire de configuration SQL Server&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="0aea9-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="0aea9-124">[Se connecter à un autre ordinateur &#40;Gestionnaire de configuration SQL Server&#41;](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="0aea9-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="0aea9-125">Configurer WMI pour afficher l'état du serveur dans les outils SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aea9-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
