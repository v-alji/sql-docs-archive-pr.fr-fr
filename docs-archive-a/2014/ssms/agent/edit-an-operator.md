---
title: Modifier un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600469"
---
# <a name="edit-an-operator"></a><span data-ttu-id="70370-102">Modifier un opérateur</span><span class="sxs-lookup"><span data-stu-id="70370-102">Edit an Operator</span></span>
  <span data-ttu-id="70370-103">Cette rubrique explique comment modifier la disponibilité d'un opérateur pour recevoir des notifications et leurs adresses d'envoi par courrier électronique, récepteur de radiomessagerie et réseau dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70370-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="70370-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="70370-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="70370-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="70370-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="70370-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="70370-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="70370-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="70370-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="70370-108">**Pour modifier un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="70370-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="70370-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70370-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="70370-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70370-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="70370-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="70370-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="70370-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="70370-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="70370-113">Les options du récepteur de radiomessagerie et **net send** seront supprimées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70370-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="70370-114">Évitez d'utiliser ces fonctionnalités dans une nouvelle tâche de développement et prévoyez de modifier les applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="70370-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="70370-115">Remarque : SQL Server Agent doit être configuré pour utiliser la messagerie de base de données pour envoyer des notifications aux opérateurs par messagerie électronique ou radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="70370-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="70370-116">Pour plus d'informations, consultez [Affecter des alertes à un opérateur](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="70370-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="70370-117">est un outil dont l'interface graphique permet de gérer facilement les travaux. Son utilisation est recommandée pour créer et gérer l'infrastructure des travaux.</span><span class="sxs-lookup"><span data-stu-id="70370-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="70370-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="70370-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="70370-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="70370-119">Permissions</span></span>  
 <span data-ttu-id="70370-120">Seuls les membres du rôle serveur fixe **sysadmin** peuvent modifier des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="70370-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="70370-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70370-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="70370-122">Pour modifier un opérateur</span><span class="sxs-lookup"><span data-stu-id="70370-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="70370-123">Dans **l’Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'opérateur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="70370-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="70370-124">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="70370-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="70370-125">Cliquez sur le signe plus (+) pour développer le dossier **Opérateurs** .</span><span class="sxs-lookup"><span data-stu-id="70370-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="70370-126">Cliquez avec le bouton droit sur l’opérateur que vous souhaitez modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="70370-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="70370-127">Pour plus d’informations sur les options disponibles contenues dans la boîte de dialogue _Propriétés de_**nom_opérateur** , consultez :</span><span class="sxs-lookup"><span data-stu-id="70370-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="70370-128">Propriétés de l’opérateur et nouvel opérateur &#40;&#41;page général</span><span class="sxs-lookup"><span data-stu-id="70370-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="70370-129">Propriétés de l’opérateur : nouvel opérateur &#40;page notifications&#41;</span><span class="sxs-lookup"><span data-stu-id="70370-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="70370-130">Propriétés Opérateur &#40;page Historique&#41;</span><span class="sxs-lookup"><span data-stu-id="70370-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="70370-131">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="70370-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="70370-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70370-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="70370-133">Pour modifier un opérateur</span><span class="sxs-lookup"><span data-stu-id="70370-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="70370-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70370-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="70370-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="70370-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="70370-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="70370-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="70370-137">Pour plus d’informations, consultez [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70370-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
