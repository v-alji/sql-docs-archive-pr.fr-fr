---
title: Démarrer SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703576"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="3f59b-102">Démarrer SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3f59b-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="3f59b-103">Il existe différentes méthodes pour démarrer le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] afin de prendre en charge la collecte des sorties de trace dans divers scénarios.</span><span class="sxs-lookup"><span data-stu-id="3f59b-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="3f59b-104">Vous pouvez démarrer [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] à partir du menu **Démarrer** , du menu **Outils** dans l’Assistant Paramétrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou à partir de plusieurs autres emplacements dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f59b-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3f59b-105">Quand vous démarrez [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour la première fois et que vous sélectionnez **Nouvelle trace** dans le menu **Fichier** , l’application affiche la boîte de dialogue **Se connecter au serveur** dans laquelle vous pouvez spécifier l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="3f59b-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="3f59b-106">Pour démarrer le Générateur de profils SQL Server à partir du menu Démarrer</span><span class="sxs-lookup"><span data-stu-id="3f59b-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="3f59b-107">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], sur **Outils de performances**, puis cliquez sur **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="3f59b-108">Pour démarrer le Générateur de profils SQL Server dans l'Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="3f59b-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="3f59b-109">Dans le menu [!INCLUDE[ssDE](../../includes/ssde-md.md)] Outils **de l’Assistant Paramétrage du** , cliquez sur **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="3f59b-110">Démarrage du Générateur de profils SQL Server dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f59b-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3f59b-111">démarre chaque session de SQL Server Profiler dans sa propre instance et poursuit son exécution si vous arrêtez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f59b-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3f59b-112">Vous pouvez démarrer [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] à partir de plusieurs emplacements dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], comme illustré dans les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="3f59b-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="3f59b-113">Lorsque [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] démarre, il charge le contexte de connexion, le modèle de trace et le contexte du filtre de son point de lancement.</span><span class="sxs-lookup"><span data-stu-id="3f59b-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="3f59b-114">Pour démarrer le Générateur de profils SQL Server à partir du menu Outils</span><span class="sxs-lookup"><span data-stu-id="3f59b-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="3f59b-115">Dans le menu [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Outils**, cliquez sur **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="3f59b-116">Pour démarrer le Générateur de profils SQL Server à partir de l’Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="3f59b-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="3f59b-117">Dans la barre de menus de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="3f59b-118">Dans l’Éditeur de requête, cliquez avec le bouton droit, puis sélectionnez **Requête de trace dans SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f59b-119">Le contexte de connexion est la connexion d'éditeur, le modèle de trace est TSQL_SPs, et le filtre appliqué est SPID = SPID de la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="3f59b-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="3f59b-120">Pour démarrer le Générateur de profils SQL Server à partir du moniteur d'activité</span><span class="sxs-lookup"><span data-stu-id="3f59b-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="3f59b-121">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puis cliquez sur **Moniteur d’activité**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="3f59b-122">Cliquez sur le volet **Processus** , cliquez avec le bouton droit sur le processus à profiler, puis cliquez sur **Processus de trace dans SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="3f59b-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f59b-123">Lorsqu'un processus est sélectionné, le contexte de connexion correspond à la connexion de l'Explorateur d'objets à l'ouverture du moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="3f59b-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="3f59b-124">Le modèle de trace correspond à la valeur par défaut selon le type de serveur et le SPID est égal au SPID du processus sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3f59b-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3f59b-125">Sécurité du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f59b-125">.NET Framework Security</span></span>  
 <span data-ttu-id="3f59b-126">Avec le mode d'authentification Windows, le compte d'utilisateur utilisé pour exécuter le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] doit avoir l'autorisation de se connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f59b-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3f59b-127">Pour effectuer une opération de traçage à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], les utilisateurs doivent également avoir l'autorisation ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="3f59b-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f59b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f59b-128">See Also</span></span>  
 <span data-ttu-id="3f59b-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="3f59b-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="3f59b-130">Utiliser SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f59b-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
