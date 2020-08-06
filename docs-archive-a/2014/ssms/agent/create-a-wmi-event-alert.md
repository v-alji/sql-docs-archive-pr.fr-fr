---
title: Créer une alerte d’événement WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611496"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="b505f-102">Create a WMI Event Alert</span><span class="sxs-lookup"><span data-stu-id="b505f-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="b505f-103">Cette rubrique explique comment créer une alerte de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est déclenchée lorsqu'un événement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifique surveillé par le fournisseur WMI se produit pour les événements de serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b505f-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b505f-104">Pour plus d’informations sur l’utilisation du fournisseur WMI pour surveiller les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] événements, consultez [fournisseur WMI pour les concepts des événements de serveur](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="b505f-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="b505f-105">Pour plus d’informations sur les autorisations nécessaires pour recevoir des notifications d’alertes d’événements WMI, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="b505f-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="b505f-106">Pour plus d’informations sur WQL, consultez [Utilisation de WQL avec le fournisseur WMI pour les événements de serveur](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="b505f-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="b505f-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b505f-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b505f-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b505f-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b505f-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b505f-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b505f-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b505f-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b505f-111">**Pour créer une alerte d'événement WMI, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b505f-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="b505f-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b505f-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b505f-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b505f-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b505f-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b505f-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b505f-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b505f-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b505f-116">est un outil simple, fonctionnant en mode graphique, qui permet de gérer tout le système d'alerte. Son utilisation est recommandée pour configurer une infrastructure d'alertes.</span><span class="sxs-lookup"><span data-stu-id="b505f-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="b505f-117">Les événements créés à l’aide de **xp_logevent** surviennent dans la base de données master.</span><span class="sxs-lookup"><span data-stu-id="b505f-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="b505f-118">Ainsi, la procédure **xp_logevent** ne déclenche pas d’alerte sauf si la valeur de **@database_name** pour l’alerte est **'master'** ou NULL.</span><span class="sxs-lookup"><span data-stu-id="b505f-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="b505f-119">Seuls les espaces de noms WMI résidant sur l'ordinateur qui exécute l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b505f-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b505f-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b505f-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b505f-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b505f-121">Permissions</span></span>  
 <span data-ttu-id="b505f-122">Par défaut, seuls les membres du rôle serveur fixe **sysadmin** peuvent exécuter la procédure **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="b505f-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b505f-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b505f-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="b505f-124">Pour créer une alerte d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="b505f-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="b505f-125">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer une alerte d'événement WMI.</span><span class="sxs-lookup"><span data-stu-id="b505f-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="b505f-126">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b505f-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b505f-127">Cliquez avec le bouton droit sur **Alertes** , puis sélectionnez **Nouvelle alerte**.</span><span class="sxs-lookup"><span data-stu-id="b505f-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="b505f-128">Dans la boîte de dialogue **Nouvelle alerte** , dans la zone **Nom** , entrez un nom pour cette alerte.</span><span class="sxs-lookup"><span data-stu-id="b505f-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="b505f-129">Sélectionnez la case à cocher **Activer** afin d'activer l'alerte à exécuter.</span><span class="sxs-lookup"><span data-stu-id="b505f-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="b505f-130">Par défaut, l'option **Activer** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b505f-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="b505f-131">Dans la liste **Type** , sélectionnez **Alerte d'événement WMI**.</span><span class="sxs-lookup"><span data-stu-id="b505f-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="b505f-132">Sous **Définition d’une alerte d’événement WMI**, dans la zone **Espace de noms** , spécifiez l’espace de noms WMI pour l’instruction WQL (WMI Query Language) qui identifie l’événement WMI qui déclenchera cette alerte.</span><span class="sxs-lookup"><span data-stu-id="b505f-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="b505f-133">Dans la zone **Requête** , spécifiez l'instruction WQL qui identifie l'événement auquel cette alerte répond.</span><span class="sxs-lookup"><span data-stu-id="b505f-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="b505f-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b505f-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b505f-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b505f-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="b505f-136">Pour créer une alerte d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="b505f-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="b505f-137">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b505f-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b505f-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b505f-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b505f-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b505f-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="b505f-140">Pour plus d’informations, consultez [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b505f-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
