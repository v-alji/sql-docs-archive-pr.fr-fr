---
title: Définir le compte de démarrage du service pour SQL Server Agent (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699173"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="38513-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="38513-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="38513-103">Le compte de démarrage du service Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permet de définir le compte Windows sous lequel s'exécute l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que ses autorisations réseau.</span><span class="sxs-lookup"><span data-stu-id="38513-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="38513-104">Cette rubrique explique comment définir le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] avec [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38513-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="38513-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="38513-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="38513-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="38513-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="38513-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="38513-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="38513-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="38513-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="38513-109">Pour définir le compte de démarrage du service de SQL Server Agent à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38513-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="38513-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="38513-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="38513-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="38513-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="38513-112">À compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'exige plus que le compte de démarrage du service soit membre du groupe Administrateurs [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38513-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="38513-113">Toutefois, le compte de démarrage du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être membre du rôle serveur fixe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin.</span><span class="sxs-lookup"><span data-stu-id="38513-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="38513-114">En cas d’utilisation du traitement de travaux multiserveur, le compte doit être membre du rôle de base de données msdb TargetServersRole sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="38513-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="38513-115">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="38513-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="38513-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="38513-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="38513-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="38513-117">Permissions</span></span>  
 <span data-ttu-id="38513-118">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent doit être configuré pour utiliser les informations d’identification d’un compte membre du `sysadmin` rôle serveur fixe dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38513-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="38513-119">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="38513-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="38513-120">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="38513-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="38513-121">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="38513-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="38513-122">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="38513-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="38513-123">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="38513-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="38513-124">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="38513-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="38513-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38513-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="38513-126">Pour configurer le compte de démarrage du service pour l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="38513-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="38513-127">Dans **Serveurs inscrits**, cliquez sur le signe plus pour développer **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="38513-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="38513-128">Cliquez sur le signe plus pour développer le dossier **Groupes de serveurs locaux** .</span><span class="sxs-lookup"><span data-stu-id="38513-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="38513-129">Cliquez avec le bouton droit sur l’instance de serveur où vous souhaitez configurer le compte de démarrage du service, puis sélectionnez **Gestionnaire de configuration SQL Server...**.</span><span class="sxs-lookup"><span data-stu-id="38513-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="38513-130">Dans la boîte de dialogue **Contrôle de compte d’utilisateur**, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="38513-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="38513-131">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sélectionnez **Services SQL Server**dans le volet de la console.</span><span class="sxs-lookup"><span data-stu-id="38513-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="38513-132">Dans le volet d’informations, cliquez avec le bouton droit sur **SQL Server Agent**_(SERVER_NAME)_, où *SERVER_NAME* est le nom de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance d’agent pour laquelle vous souhaitez modifier le compte de démarrage du service, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="38513-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="38513-133">Dans la boîte de dialogue **Propriétés** de **SQL Server Agent**_(SERVER_NAME)_ , sous l’onglet **ouvrir une session** , sélectionnez l’une des options suivantes sous **ouvrir une session en tant que**:</span><span class="sxs-lookup"><span data-stu-id="38513-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="38513-134">**Compte intégré**: sélectionnez cette option si vos travaux nécessitent des ressources du serveur local uniquement.</span><span class="sxs-lookup"><span data-stu-id="38513-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="38513-135">Pour plus d’informations sur la façon de choisir un type de compte intégré Windows, consultez [Sélection d’un compte pour le service SQL Server Agent](https://msdn.microsoft.com/library/ms191543.aspx).</span><span class="sxs-lookup"><span data-stu-id="38513-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="38513-136"> Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne prend pas en charge le compte **Service local** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38513-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="38513-137">**Ce compte**: sélectionnez cette option si vos travaux nécessitent des ressources sur le réseau, notamment des ressources d’application, si vous souhaitez transférer des événements vers d’autres journaux d’applications Windows, ou si vous souhaitez notifier des opérateurs par courrier électronique ou radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="38513-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="38513-138">Si vous sélectionnez cette option :</span><span class="sxs-lookup"><span data-stu-id="38513-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="38513-139">Dans la zone **Nom du compte** , entrez le compte qui sera utilisé pour exécuter SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="38513-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="38513-140">Vous pouvez également cliquer sur **Parcourir** pour ouvrir la boîte de dialogue **Sélectionnez l'utilisateur ou le groupe** et sélectionner le compte à utiliser.</span><span class="sxs-lookup"><span data-stu-id="38513-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="38513-141">Dans la zone **Mot de passe** , entrez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="38513-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="38513-142">Dans la zone **Confirmer le mot de passe** , retapez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="38513-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="38513-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="38513-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="38513-144">Cliquez sur le bouton **Fermer**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le Gestionnaire de configuration.</span><span class="sxs-lookup"><span data-stu-id="38513-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
