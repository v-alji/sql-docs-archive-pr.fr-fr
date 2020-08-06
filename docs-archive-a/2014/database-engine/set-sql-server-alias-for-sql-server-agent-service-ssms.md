---
title: Définir un alias de SQL Server pour le service SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601068"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="f0b7f-102">Définir un alias SQL Server pour le service SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f0b7f-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f0b7f-103">Cette rubrique explique comment définir un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que l’agent doit utiliser pour se connecter au à l' [!INCLUDE[ssDE](../includes/ssde-md.md)] aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0b7f-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f0b7f-104">Par défaut, le service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent se connecte à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] par l'intermédiaire de canaux de communication nommés qui utilisent des noms de serveur dynamiques ne nécessitant aucune configuration supplémentaire du client.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="f0b7f-105">Vous devez configurer un alias de connexion serveur uniquement si vous n'utilisez pas le transport réseau par défaut ou si vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] via un autre canal nommé.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="f0b7f-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f0b7f-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0b7f-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f0b7f-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0b7f-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0b7f-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f0b7f-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0b7f-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="f0b7f-110">Pour définir un alias SQL Server pour le service SQL Server Agent à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0b7f-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0b7f-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0b7f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f0b7f-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0b7f-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="f0b7f-113">ne fonctionnera correctement que si vous sélectionnez un alias qui se réfère à l'instance locale de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b7f-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f0b7f-114">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0b7f-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0b7f-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0b7f-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0b7f-116">Permissions</span></span>  
 <span data-ttu-id="f0b7f-117">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b7f-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f0b7f-118">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0b7f-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="f0b7f-119">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="f0b7f-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="f0b7f-120">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f0b7f-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="f0b7f-121">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f0b7f-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="f0b7f-122">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="f0b7f-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="f0b7f-123">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f0b7f-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0b7f-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0b7f-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="f0b7f-125">Pour définir un alias SQL Server pour le service SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f0b7f-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="f0b7f-126">Dans l' **Explorateur d'objets,** connectez-vous à une instance de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f0b7f-127">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f0b7f-128">Dans la boîte de dialogue Propriétés de la **SQL Server Agent**_Server_name_ , sous **Sélectionner une page**, sélectionnez **connexion**, puis</span><span class="sxs-lookup"><span data-stu-id="f0b7f-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="f0b7f-129">Dans la zone **Alias du serveur hôte local** , tapez l'alias du serveur auquel l'agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit se connecter.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="f0b7f-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0b7f-130">Click **OK**.</span></span>  
  
  
