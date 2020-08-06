---
title: Définir la réponse à une alerte (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699216"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="43c51-102">Définir la réponse à une alerte (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="43c51-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="43c51-103">Cette rubrique explique comment définir la manière dont [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] répond aux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertes de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de ou de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43c51-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="43c51-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="43c51-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43c51-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="43c51-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43c51-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="43c51-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="43c51-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="43c51-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43c51-108">**Pour définir la réponse à une alerte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="43c51-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="43c51-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43c51-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43c51-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43c51-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43c51-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="43c51-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="43c51-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="43c51-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="43c51-113">Les options du récepteur de radiomessagerie et **net send** seront supprimées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43c51-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="43c51-114">Évitez d'utiliser ces fonctionnalités dans une nouvelle tâche de développement et prévoyez de modifier les applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="43c51-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="43c51-115">Remarque : SQL Server Agent doit être configuré pour utiliser la messagerie de base de données pour envoyer des notifications aux opérateurs par messagerie électronique ou radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="43c51-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="43c51-116">Pour plus d'informations, consultez [Affecter des alertes à un opérateur](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="43c51-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="43c51-117">est un outil dont l'interface graphique permet de gérer facilement les travaux. Son utilisation est recommandée pour créer et gérer l'infrastructure des travaux.</span><span class="sxs-lookup"><span data-stu-id="43c51-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43c51-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="43c51-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43c51-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="43c51-119">Permissions</span></span>  
 <span data-ttu-id="43c51-120">Seuls les membres du rôle serveur fixe **sysadmin** peuvent définir la réponse à une alerte.</span><span class="sxs-lookup"><span data-stu-id="43c51-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43c51-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43c51-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="43c51-122">Pour définir la réponse à une alerte</span><span class="sxs-lookup"><span data-stu-id="43c51-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="43c51-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'alerte sur laquelle vous souhaitez définir une réponse.</span><span class="sxs-lookup"><span data-stu-id="43c51-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="43c51-124">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="43c51-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="43c51-125">Cliquez sur le signe plus (+) pour développer le dossier **Alertes** .</span><span class="sxs-lookup"><span data-stu-id="43c51-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="43c51-126">Cliquez avec le bouton droit sur l'alerte dont vous voulez définir une réponse, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43c51-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="43c51-127">Dans la boîte de dialogue Propriétés de l'**alerte** _Alert_name_, sous **Sélectionner une page**, sélectionnez **réponse**.</span><span class="sxs-lookup"><span data-stu-id="43c51-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="43c51-128">Sélectionnez la case à cocher **Exécuter le travail** , puis dans la liste figurant sous la case à cocher **Exécuter le travail** , sélectionnez un travail à exécuter quand une alerte se produit.</span><span class="sxs-lookup"><span data-stu-id="43c51-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="43c51-129">Vous pouvez créer un nouveau travail en cliquant sur **Nouveau travail**.</span><span class="sxs-lookup"><span data-stu-id="43c51-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="43c51-130">Vous pouvez afficher plus d'informations sur le travail en cliquant sur **Afficher le travail**.</span><span class="sxs-lookup"><span data-stu-id="43c51-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="43c51-131">Pour plus d’informations sur les options disponibles dans les boîtes de dialogue **nouveau travail** et **propriétés du travail**_Job_name_ , consultez [créer un travail](create-a-job.md) et [afficher un travail](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="43c51-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="43c51-132">Activez la case à cocher **Notifier les opérateurs** si vous souhaitez avertir les opérateurs lorsque l'alerte est activée.</span><span class="sxs-lookup"><span data-stu-id="43c51-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="43c51-133">Dans **Liste d'opérateurs**, sélectionnez une ou plusieurs des méthodes suivantes pour notifier le ou les opérateurs : **Messagerie électronique**, **Radiomessagerie**ou **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="43c51-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="43c51-134">Vous pouvez créer un nouvel opérateur en cliquant sur **Nouvel opérateur**.</span><span class="sxs-lookup"><span data-stu-id="43c51-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="43c51-135">Vous pouvez afficher plus d'informations sur un opérateur en cliquant sur **Afficher l'opérateur**.</span><span class="sxs-lookup"><span data-stu-id="43c51-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="43c51-136">Pour plus d'informations sur les options disponibles dans les boîtes de dialogue **Nouvel opérateur** et **Afficher les propriétés de l'opérateur** , consultez [Create an Operator](create-an-operator.md) et [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="43c51-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="43c51-137">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="43c51-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43c51-138">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43c51-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="43c51-139">Pour définir la réponse à une alerte</span><span class="sxs-lookup"><span data-stu-id="43c51-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="43c51-140">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43c51-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43c51-141">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="43c51-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43c51-142">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43c51-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="43c51-143">Pour plus d’informations, consultez [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43c51-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
