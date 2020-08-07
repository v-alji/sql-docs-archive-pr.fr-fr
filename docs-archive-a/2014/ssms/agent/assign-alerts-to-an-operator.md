---
title: Affecter des alertes à un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604819"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="eb3e4-102">Assign Alerts to an Operator</span><span class="sxs-lookup"><span data-stu-id="eb3e4-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="eb3e4-103">Cette rubrique explique comment assigner [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des alertes d’agent à des opérateurs afin qu’ils puissent recevoir des notifications concernant des travaux dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb3e4-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="eb3e4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="eb3e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eb3e4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="eb3e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eb3e4-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="eb3e4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="eb3e4-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="eb3e4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eb3e4-108">**Pour affecter des alertes à un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="eb3e4-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="eb3e4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb3e4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eb3e4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb3e4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eb3e4-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="eb3e4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="eb3e4-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="eb3e4-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="eb3e4-113">est un outil simple, basé sur une interface graphique, qui permet de gérer le système d'alertes dans sa totalité.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="eb3e4-114">L’utilisation de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] est recommandée pour configurer l’infrastructure d’alertes.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="eb3e4-115">Pour envoyer une notification en réponse à une alerte, vous devez d'abord configurer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour l'envoi de messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="eb3e4-116">Pour plus d’informations, consultez [Configurer la messagerie de SQL Server Agent en vue de l’utilisation de la messagerie de base de données](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="eb3e4-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="eb3e4-117">En cas d’échec au moment de l’envoi d’un message par e-mail ou d’une notification par radiomessagerie, l’échec est consigné dans le journal des erreurs du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eb3e4-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="eb3e4-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eb3e4-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="eb3e4-119">Permissions</span></span>  
 <span data-ttu-id="eb3e4-120">Seuls les membres du rôle serveur fixe **sysadmin** peuvent affecter des alertes aux opérateurs.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eb3e4-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb3e4-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="eb3e4-122">Pour affecter des alertes à un opérateur</span><span class="sxs-lookup"><span data-stu-id="eb3e4-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="eb3e4-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'opérateur auquel vous souhaitez affecter une alerte.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="eb3e4-124">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="eb3e4-125">Cliquez sur le signe plus (+) pour développer le dossier **Opérateurs** .</span><span class="sxs-lookup"><span data-stu-id="eb3e4-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="eb3e4-126">Cliquez avec le bouton droit sur l’opérateur auquel vous souhaitez affecter une alerte et sélectionnez **Propriétés**, puis la page **Notifications** .</span><span class="sxs-lookup"><span data-stu-id="eb3e4-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="eb3e4-127">Dans la boîte de dialogue**Propriétés** du _Operator_name_, sous **Sélectionner une page**, sélectionnez **notifications**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="eb3e4-128">Sous **Afficher les notifications envoyées à cet utilisateur par**, sélectionnez **Alertes** pour afficher la liste des alertes envoyées à cet opérateur, ou sélectionnez **Travaux** pour afficher la liste des travaux qui envoient des notifications à cet opérateur.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="eb3e4-129">Cochez une ou plusieurs cases parmi les suivantes pour définir, en fonction de vos besoins, la méthode de notification pour chaque notification : **Messagerie électronique**, **Radiomessagerie**ou **Net send**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="eb3e4-130">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eb3e4-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eb3e4-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="eb3e4-132">Pour affecter des alertes à un opérateur</span><span class="sxs-lookup"><span data-stu-id="eb3e4-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="eb3e4-133">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb3e4-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb3e4-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eb3e4-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="eb3e4-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="eb3e4-136">Pour plus d’informations, consultez [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb3e4-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
