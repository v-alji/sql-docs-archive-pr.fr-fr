---
title: Démarrer, arrêter ou suspendre le service SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695248"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="30fab-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="30fab-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="30fab-103">Cette rubrique explique comment démarrer, arrêter ou redémarrer le service de l'Agent SQL Server dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30fab-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="30fab-104">Vous pouvez configurer le service l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour qu'il démarre automatiquement lorsque le système d'exploitation démarre, ou vous pouvez le démarrer manuellement lorsque vous avez besoin d'exécuter des travaux.</span><span class="sxs-lookup"><span data-stu-id="30fab-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="30fab-105">Vous pouvez arrêter ou interrompre le service de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour interrompre les travaux, les notifications de l'opérateur et les alertes.</span><span class="sxs-lookup"><span data-stu-id="30fab-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="30fab-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="30fab-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30fab-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="30fab-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="30fab-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="30fab-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="30fab-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="30fab-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="30fab-110">Pour démarrer, arrêter ou redémarrer le service de l'Agent SQL Server à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30fab-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30fab-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="30fab-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="30fab-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="30fab-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="30fab-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]L’agent doit être exécuté en tant que service pour automatiser les tâches d’administration.</span><span class="sxs-lookup"><span data-stu-id="30fab-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="30fab-114">Pour plus d’informations, consultez [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="30fab-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="30fab-115">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="30fab-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30fab-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="30fab-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30fab-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="30fab-117">Permissions</span></span>  
 <span data-ttu-id="30fab-118">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30fab-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="30fab-119">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="30fab-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="30fab-120">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="30fab-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="30fab-121">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="30fab-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="30fab-122">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="30fab-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="30fab-123">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="30fab-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="30fab-124">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="30fab-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30fab-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30fab-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="30fab-126">Pour démarrer, arrêter ou redémarrer le service de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="30fab-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="30fab-127">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez gérer le service de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30fab-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="30fab-128">Cliquez avec le bouton droit sur **SQL Server Agent**, puis sélectionnez **Démarrer**, **Arrêter**ou **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="30fab-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="30fab-129">Dans la boîte de dialogue **Contrôle de compte d’utilisateur**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="30fab-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="30fab-130">Lorsque vous y êtes invité, et si vous souhaitez exécuter l'action, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="30fab-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="30fab-131">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="30fab-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="30fab-132">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="30fab-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="30fab-133">Démarrer automatiquement SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="30fab-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
