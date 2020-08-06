---
title: Définir la connexion SQL Server pour le service SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30f68967d6bdb8b0495cbddb1a5b0bd447cd5168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614973"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="cfef6-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cfef6-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cfef6-103">Cette rubrique décrit la configuration de la connexion entre l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] au moyen de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfef6-103">This topic describes how to set the connection between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cfef6-104">Le service de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut se connecter à une instance locale de SQL Server en utilisant l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cfef6-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can connect to a local instance of SQL Server by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="cfef6-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="cfef6-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cfef6-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="cfef6-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cfef6-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cfef6-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cfef6-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cfef6-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cfef6-109">**Pour définir la connexion SQL Server pour SQL Server Agent à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="cfef6-109">**To set the SQL Server Connection for the SQL Server Agent, using:**</span></span>  
  
     [<span data-ttu-id="cfef6-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfef6-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfef6-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="cfef6-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cfef6-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cfef6-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cfef6-113">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfef6-113">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="cfef6-114">À compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne prend pas en charge l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfef6-114">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="cfef6-115">Cette option est disponible uniquement lorsque vous administrez une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfef6-115">This option is available only when you administer an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfef6-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cfef6-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cfef6-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="cfef6-117">Permissions</span></span>  
 <span data-ttu-id="cfef6-118">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfef6-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cfef6-119">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="cfef6-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="cfef6-120">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="cfef6-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="cfef6-121">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfef6-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="cfef6-122">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfef6-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="cfef6-123">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfef6-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="cfef6-124">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cfef6-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cfef6-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfef6-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-sql-server-connection"></a><span data-ttu-id="cfef6-126">Pour configurer la connexion à SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfef6-126">To set the SQL Server connection</span></span>  
  
1.  <span data-ttu-id="cfef6-127">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur que vous souhaitez configurer avec une connexion à son service SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="cfef6-127">In **Object Explorer**, click the plus sign to expand the server that you want to set up with a connection to its SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="cfef6-128">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="cfef6-128">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="cfef6-129">Dans la boîte de dialogue **Propriétés de SQL Server Agent**, sous **Sélectionner une page**, cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="cfef6-129">In the **SQL Server Agent Properties** dialog box, under **Select a page**, click **Connection**.</span></span>  
  
4.  <span data-ttu-id="cfef6-130">Sous **Connexion SQL Server**, sélectionnez **Utiliser l'authentification Windows** pour permettre à l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de se connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] avec [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span><span class="sxs-lookup"><span data-stu-id="cfef6-130">Under **SQL Server connection**, select **Use Windows Authentication** to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="cfef6-131">Les connexions aux bases de données [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures nécessitent l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cfef6-131">Connections to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later databases require Windows Authentication.</span></span>  
  
  
