---
title: Écrire des messages de trace d’exécution dans le journal des erreurs SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703719"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="234fa-102">Écrire des messages de trace d'exécution dans le journal des erreurs de SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="234fa-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="234fa-103">Cette rubrique explique comment configurer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent pour inclure des messages de trace d’exécution dans le journal des erreurs dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="234fa-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="234fa-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="234fa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="234fa-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="234fa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="234fa-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="234fa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="234fa-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="234fa-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="234fa-108">Pour écrire des messages de trace d'exécution dans le journal des erreurs de SQL Server Agent à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="234fa-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="234fa-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="234fa-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="234fa-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="234fa-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="234fa-111">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="234fa-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="234fa-112">Étant donné que cette option peut entraîner une augmentation importante de la taille du journal des erreurs, n'incluez que les messages de trace d'exécution dans les journaux des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lors de l'investigation d'un problème spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="234fa-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="234fa-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="234fa-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="234fa-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="234fa-114">Permissions</span></span>  
 <span data-ttu-id="234fa-115">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="234fa-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="234fa-116">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="234fa-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="234fa-117">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="234fa-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="234fa-118">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="234fa-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="234fa-119">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="234fa-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="234fa-120">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="234fa-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="234fa-121">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="234fa-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="234fa-122">Pour écrire des messages de trace d'exécution dans le journal des erreurs de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="234fa-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="234fa-123">Dans **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans lequel vous souhaitez écrire des messages de trace d'exécution.</span><span class="sxs-lookup"><span data-stu-id="234fa-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="234fa-124">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="234fa-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="234fa-125">Dans la boîte de dialogue Propriétés de la **SQL Server Agent-**_SERVER_NAME_ , sous **Journal des erreurs** dans la page **général** , activez la case à cocher inclure les messages de **trace d’exécution** .</span><span class="sxs-lookup"><span data-stu-id="234fa-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="234fa-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="234fa-126">Click **OK**.</span></span>  
  
  
