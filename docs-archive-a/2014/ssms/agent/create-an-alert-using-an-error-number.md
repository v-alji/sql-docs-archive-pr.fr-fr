---
title: Créer une alerte utilisant un numéro d’erreur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- alerts [SQL Server], error numbers
ms.assetid: 03dd7fac-5073-4f86-babd-37e45a86023c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a98f64bc5b9dffc3e2494a0c36c8fc04cdfb6fa2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610959"
---
# <a name="create-an-alert-using-an-error-number"></a><span data-ttu-id="23b08-102">Créer une alerte avec un numéro d’erreur</span><span class="sxs-lookup"><span data-stu-id="23b08-102">Create an Alert Using an Error Number</span></span>
  <span data-ttu-id="23b08-103">Cette rubrique explique comment créer une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerte de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] qui est déclenchée lorsqu’une erreur d’un nombre spécifique se produit à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23b08-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that will be raised when an error of a specific number occurs by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="23b08-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="23b08-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="23b08-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="23b08-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="23b08-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="23b08-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="23b08-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="23b08-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="23b08-108">**Pour créer une alerte avec un numéro d’erreur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="23b08-108">**To create an alert using an error number, using:**</span></span>  
  
     [<span data-ttu-id="23b08-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23b08-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="23b08-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23b08-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="23b08-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="23b08-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="23b08-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="23b08-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="23b08-113">est un outil simple, fonctionnant en mode graphique, qui permet de gérer tout le système d'alerte. Son utilisation est recommandée pour configurer une infrastructure d'alertes.</span><span class="sxs-lookup"><span data-stu-id="23b08-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="23b08-114">Les événements créés à l’aide de **xp_logevent** surviennent dans la base de données master.</span><span class="sxs-lookup"><span data-stu-id="23b08-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="23b08-115">Ainsi, la procédure **xp_logevent** ne déclenche pas d’alerte sauf si la valeur de **@database_name** pour l’alerte est **'master'** ou NULL.</span><span class="sxs-lookup"><span data-stu-id="23b08-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="23b08-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="23b08-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="23b08-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="23b08-117">Permissions</span></span>  
 <span data-ttu-id="23b08-118">Par défaut, seuls les membres du rôle serveur fixe **sysadmin** peuvent exécuter la procédure **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="23b08-118">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="23b08-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23b08-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="23b08-120">Pour créer une alerte avec un numéro d'erreur</span><span class="sxs-lookup"><span data-stu-id="23b08-120">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="23b08-121">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer une alerte avec un numéro d'erreur.</span><span class="sxs-lookup"><span data-stu-id="23b08-121">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using an error number.</span></span>  
  
2.  <span data-ttu-id="23b08-122">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b08-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="23b08-123">Cliquez avec le bouton droit sur **Alertes** , puis sélectionnez **Nouvelle alerte**.</span><span class="sxs-lookup"><span data-stu-id="23b08-123">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="23b08-124">Dans la boîte de dialogue **Nouvelle alerte** , dans la zone **Nom** , entrez un nom pour cette alerte.</span><span class="sxs-lookup"><span data-stu-id="23b08-124">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="23b08-125">Sélectionnez la case à cocher **Activer** afin d'activer l'alerte à exécuter.</span><span class="sxs-lookup"><span data-stu-id="23b08-125">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="23b08-126">Par défaut, l'option **Activer** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="23b08-126">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="23b08-127">Dans la liste **Type** , sélectionnez **Alerte d'événement SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="23b08-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
7.  <span data-ttu-id="23b08-128">Sous **Définition d'une alerte d'événement**, dans la liste **Nom de base de données** , sélectionnez une base de données pour restreindre l'alerte à une base de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="23b08-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
8.  <span data-ttu-id="23b08-129">Sous **Les alertes seront déclenchées selon**, cliquez sur **Numéro d'erreur**, puis tapez un numéro d'erreur valide pour l'alerte.</span><span class="sxs-lookup"><span data-stu-id="23b08-129">Under **Alerts will be raised based on**, click **Error number**, and then type a valid error number for the alert.</span></span> <span data-ttu-id="23b08-130">Vous pouvez également cliquer sur **Gravité** , puis sélectionner la gravité spécifique qui déclenchera l'alerte.</span><span class="sxs-lookup"><span data-stu-id="23b08-130">Alternately, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
9. <span data-ttu-id="23b08-131">Activez la case à cocher correspondant à **Déclencher une alerte quand le message contient** afin de limiter l'alerte à une certaine séquence de caractères, puis entrez un mot clé ou une chaîne de caractères pour le **Texte du message**.</span><span class="sxs-lookup"><span data-stu-id="23b08-131">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="23b08-132">Le nombre maximal de caractères autorisé est de 100.</span><span class="sxs-lookup"><span data-stu-id="23b08-132">The maximum number of characters is 100.</span></span>  
  
10. <span data-ttu-id="23b08-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="23b08-133">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="23b08-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23b08-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="23b08-135">Pour créer une alerte avec un numéro d'erreur</span><span class="sxs-lookup"><span data-stu-id="23b08-135">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="23b08-136">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23b08-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="23b08-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="23b08-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="23b08-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="23b08-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="23b08-139">Pour plus d’informations, consultez [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="23b08-139">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
