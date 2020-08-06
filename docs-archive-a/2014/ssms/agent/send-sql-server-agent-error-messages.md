---
title: Envoyer des messages d’erreur SQL Server Agent| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611489"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="c5462-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="c5462-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="c5462-103">Cette rubrique explique comment configurer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent pour envoyer ses messages d’erreur par le biais de net send dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5462-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c5462-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c5462-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c5462-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c5462-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c5462-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c5462-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c5462-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c5462-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="c5462-108">Pour envoyer des messages d'erreur de SQL Server Agent à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5462-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5462-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c5462-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c5462-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c5462-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c5462-111">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="c5462-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="c5462-112">Le service [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger doit être en cours d'exécution pour recevoir les événements d'envoi sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c5462-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5462-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c5462-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5462-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c5462-114">Permissions</span></span>  
 <span data-ttu-id="c5462-115">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5462-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5462-116">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5462-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="c5462-117">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="c5462-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="c5462-118">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c5462-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="c5462-119">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c5462-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="c5462-120">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c5462-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="c5462-121">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c5462-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c5462-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5462-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="c5462-123">Pour envoyer des messages d'erreur de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c5462-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="c5462-124">Dans l' **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dont vous souhaitez envoyer des messages d'erreur via le réseau.</span><span class="sxs-lookup"><span data-stu-id="c5462-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="c5462-125">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c5462-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c5462-126">Dans la boîte de dialogue Propriétés de la **SQL Server Agent-**_SERVER_NAME_ , sous **Journal des erreurs** dans la page **général** , tapez le nom d’utilisateur ou le nom de l’ordinateur auquel vous souhaitez envoyer des messages d’erreur dans la zone **destinataire net send** .</span><span class="sxs-lookup"><span data-stu-id="c5462-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="c5462-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5462-127">Click **OK**.</span></span>  
  
  
