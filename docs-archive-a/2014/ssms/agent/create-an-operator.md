---
title: Créer un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699257"
---
# <a name="create-an-operator"></a><span data-ttu-id="25589-102">Créer un opérateur</span><span class="sxs-lookup"><span data-stu-id="25589-102">Create an Operator</span></span>
  <span data-ttu-id="25589-103">Cette rubrique explique comment configurer un utilisateur pour qu’il reçoive des notifications sur les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25589-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="25589-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="25589-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="25589-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="25589-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="25589-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="25589-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="25589-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="25589-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="25589-108">**Pour créer un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="25589-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="25589-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25589-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="25589-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25589-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="25589-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="25589-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="25589-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="25589-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="25589-113">Les options du récepteur de radiomessagerie et **net send** seront supprimées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25589-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25589-114">Évitez d'utiliser ces fonctionnalités dans une nouvelle tâche de développement et prévoyez de modifier les applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="25589-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="25589-115">Remarque : SQL Server Agent doit être configuré pour utiliser la messagerie de base de données pour envoyer des notifications aux opérateurs par messagerie électronique ou radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="25589-116">Pour plus d'informations, consultez [Affecter des alertes à un opérateur](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="25589-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="25589-117">est un outil dont l'interface graphique permet de gérer facilement les travaux. Son utilisation est recommandée pour créer et gérer l'infrastructure des travaux.</span><span class="sxs-lookup"><span data-stu-id="25589-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="25589-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="25589-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="25589-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="25589-119">Permissions</span></span>  
 <span data-ttu-id="25589-120">Seuls les membres du rôle serveur fixe **sysadmin** peuvent créer des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="25589-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="25589-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25589-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="25589-122">Pour créer un opérateur</span><span class="sxs-lookup"><span data-stu-id="25589-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="25589-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un opérateur de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="25589-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="25589-124">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="25589-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="25589-125">Cliquez avec le bouton droit sur le dossier **Opérateurs** , puis sélectionnez **Nouvel opérateur**.</span><span class="sxs-lookup"><span data-stu-id="25589-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="25589-126">Les options suivantes sont disponibles sur la page **Général** de la boîte de dialogue **Nouvel opérateur** :</span><span class="sxs-lookup"><span data-stu-id="25589-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="25589-127">**Nom**</span><span class="sxs-lookup"><span data-stu-id="25589-127">**Name**</span></span>  
     <span data-ttu-id="25589-128">Permet de modifier le nom de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="25589-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="25589-129">**Activé**</span><span class="sxs-lookup"><span data-stu-id="25589-129">**Enabled**</span></span>  
     <span data-ttu-id="25589-130">Permet d'activer l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="25589-130">Enable the operator.</span></span> <span data-ttu-id="25589-131">Aucune notification n'est envoyée à l'opérateur lorsque cette option est désactivée.</span><span class="sxs-lookup"><span data-stu-id="25589-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="25589-132">**Nom de messagerie électronique**</span><span class="sxs-lookup"><span data-stu-id="25589-132">**E-mail name**</span></span>  
     <span data-ttu-id="25589-133">Spécifie l'adresse de messagerie de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="25589-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="25589-134">**Adresse d'envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="25589-134">**Net send address**</span></span>  
     <span data-ttu-id="25589-135">Spécifie l’adresse à utiliser pour **net send**.</span><span class="sxs-lookup"><span data-stu-id="25589-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="25589-136">**Nom de l'adresse de radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="25589-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="25589-137">Spécifie l'adresse de messagerie à utiliser pour la radiomessagerie de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="25589-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="25589-138">**Planification de la radiomessagerie active**</span><span class="sxs-lookup"><span data-stu-id="25589-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="25589-139">Définit les périodes d'activité de la radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="25589-140">**Lundi - Dimanche**</span><span class="sxs-lookup"><span data-stu-id="25589-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="25589-141">Permet de sélectionner les jours d'activité de la radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="25589-142">**Début de journée**</span><span class="sxs-lookup"><span data-stu-id="25589-142">**Workday begin**</span></span>  
     <span data-ttu-id="25589-143">Sélectionne l’heure après laquelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent envoie des messages à la radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="25589-144">**Fin de journée**</span><span class="sxs-lookup"><span data-stu-id="25589-144">**Workday end**</span></span>  
     <span data-ttu-id="25589-145">Sélectionne l’heure après laquelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent n’envoie plus de messages à la radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="25589-146">Les options suivantes sont disponibles sur la page **Notifications** de la boîte de dialogue **Nouvel opérateur** :</span><span class="sxs-lookup"><span data-stu-id="25589-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="25589-147">**Alertes**</span><span class="sxs-lookup"><span data-stu-id="25589-147">**Alerts**</span></span>  
     <span data-ttu-id="25589-148">Affiche les alertes dans l'instance.</span><span class="sxs-lookup"><span data-stu-id="25589-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="25589-149">**Tâches**</span><span class="sxs-lookup"><span data-stu-id="25589-149">**Jobs**</span></span>  
     <span data-ttu-id="25589-150">Affiche les travaux dans l'instance.</span><span class="sxs-lookup"><span data-stu-id="25589-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="25589-151">**Liste d'alertes**</span><span class="sxs-lookup"><span data-stu-id="25589-151">**Alert list**</span></span>  
     <span data-ttu-id="25589-152">Affiche la liste des alertes dans l'instance.</span><span class="sxs-lookup"><span data-stu-id="25589-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="25589-153">**Liste des travaux**</span><span class="sxs-lookup"><span data-stu-id="25589-153">**Job list**</span></span>  
     <span data-ttu-id="25589-154">Affiche la liste des travaux dans l'instance.</span><span class="sxs-lookup"><span data-stu-id="25589-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="25589-155">**Courriel**</span><span class="sxs-lookup"><span data-stu-id="25589-155">**E-mail**</span></span>  
     <span data-ttu-id="25589-156">Notifie cet opérateur à l'aide d'un courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="25589-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="25589-157">**Radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="25589-157">**Pager**</span></span>  
     <span data-ttu-id="25589-158">Notifie cet opérateur en envoyant un courrier électronique à son adresse de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="25589-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="25589-159">**Envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="25589-159">**Net send**</span></span>  
     <span data-ttu-id="25589-160">Notifie cet opérateur à l’aide de **net send**.</span><span class="sxs-lookup"><span data-stu-id="25589-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="25589-161">Lorsque la création du nouvel opérateur est terminée, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="25589-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="25589-162">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25589-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="25589-163">Pour créer un opérateur</span><span class="sxs-lookup"><span data-stu-id="25589-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="25589-164">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25589-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="25589-165">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="25589-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="25589-166">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="25589-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="25589-167">Pour plus d’informations, consultez [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25589-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
