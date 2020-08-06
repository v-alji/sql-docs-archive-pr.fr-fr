---
title: Configurer SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, configuring
- accounts [SQL Server], SQL Server Agent
- SQL Server Agent, permissions
- security [SQL Server], SQL Server Agent
ms.assetid: 2e361a62-9e92-4fcd-80d7-d6960f127900
author: stevestein
ms.author: sstein
ms.openlocfilehash: 81c78faf733fac5ffb9a6e74dbf03f8caaff03d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604813"
---
# <a name="configure-sql-server-agent"></a><span data-ttu-id="86b41-102">Configurer SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="86b41-102">Configure SQL Server Agent</span></span>
  <span data-ttu-id="86b41-103">Cette rubrique explique comment spécifier certaines options de configuration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lors de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86b41-103">This topic describes how to specify some configuration options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86b41-104">L’ensemble complet des options de configuration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent n’est disponible que dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], les objets SMO ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects) ou dans les procédures stockées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="86b41-104">The full set of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent configuration options is only available within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures.</span></span>  
  
 <span data-ttu-id="86b41-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="86b41-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="86b41-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="86b41-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="86b41-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="86b41-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="86b41-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="86b41-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="86b41-109">Pour configurer SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="86b41-109">To configure SQL Server Agent</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="86b41-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="86b41-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="86b41-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="86b41-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="86b41-112">Cliquez sur **SQL Server Agent** dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour administrer des travaux, des opérateurs, des alertes et le service de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="86b41-112">Click **SQL Server Agent** in Object Explorer of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to administer jobs, operators, alerts, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="86b41-113">Cependant, l'Explorateur d'objets n'affiche le nœud [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="86b41-113">However, Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="86b41-114">Le redémarrage automatique ne doit pas être activé pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou le service de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sur les instances de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="86b41-114">Auto-restart should not be enabled for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on failover cluster instances.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="86b41-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="86b41-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="86b41-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="86b41-116">Permissions</span></span>  
 <span data-ttu-id="86b41-117">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86b41-117">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86b41-118">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b41-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="86b41-119">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="86b41-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="86b41-120">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="86b41-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="86b41-121">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="86b41-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="86b41-122">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="86b41-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="86b41-123">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="86b41-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="86b41-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="86b41-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent"></a><span data-ttu-id="86b41-125">Pour configurer SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="86b41-125">To configure SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="86b41-126">Cliquez sur le bouton **Démarrer** , puis, dans le menu **Démarrer**  , cliquez sur **Panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="86b41-126">Click the **Start** button, and then, on the **Start**  menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="86b41-127">Dans le Panneau de configuration, cliquez sur **Système et sécurité**, puis sur **Outils d'administration**et sélectionnez **Stratégie de sécurité locale**.</span><span class="sxs-lookup"><span data-stu-id="86b41-127">In Control Panel, click **System and Security**, click **Administrative Tools**, and then select **Local Security Policy**.</span></span>  
  
3.  <span data-ttu-id="86b41-128">Dans Stratégie de sécurité locale, cliquez sur le chevron pour développer le dossier **Stratégies locales** , puis cliquez sur le dossier **Attribution des droits utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="86b41-128">In Local Security Policy, click the chevron to expand the **Local Policies** folder, and then click the **User Rights Assignment** folder.</span></span>  
  
4.  <span data-ttu-id="86b41-129">Cliquez avec le bouton droit sur l’autorisation à configurer pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="86b41-129">Right-click a permission that you want to configure for use with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="86b41-130">Dans la boîte de dialogue des propriétés de l'autorisation, vérifiez que le compte sous lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent s'exécute est répertorié.</span><span class="sxs-lookup"><span data-stu-id="86b41-130">In the permission's properties dialog box, verify that the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs is listed.</span></span> <span data-ttu-id="86b41-131">Sinon, cliquez sur **Ajouter un utilisateur ou un groupe**, entrez le compte sous lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent s'exécute dans la boîte de dialogue **Choisir des utilisateurs, des ordinateurs ou des groupes** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="86b41-131">If not, click **Add User or Group**, enter the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="86b41-132">Répétez ces étapes pour chaque autorisation à ajouter pour l'exécution de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="86b41-132">Repeat for each permission that you want to add to run with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="86b41-133">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="86b41-133">When finished, click **OK**.</span></span>  
  
  
