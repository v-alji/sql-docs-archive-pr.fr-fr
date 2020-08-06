---
title: Créer un profil de messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603550"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="29cd7-102">Créer un profil de messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="29cd7-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="29cd7-103">Utilisez l' **Assistant Configuration de la messagerie de base de données** ou [!INCLUDE[tsql](../../includes/tsql-md.md)] pour créer des profils privés et publics de messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29cd7-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="29cd7-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="29cd7-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="29cd7-105">Prerequisites</span></span>  
 <span data-ttu-id="29cd7-106">Créez un ou plusieurs comptes de messagerie de base de données pour le profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="29cd7-107">Pour plus d’informations sur la création de comptes de messagerie de base de données, consultez [Créer un compte de messagerie de base de données](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="29cd7-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29cd7-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="29cd7-108">Security</span></span>  
 <span data-ttu-id="29cd7-109">Un profil public permet à tout utilisateur ayant accès à la base de données **msdb** d’envoyer des e-mails à l’aide de ce profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="29cd7-110">Un profil privé peut être utilisé par un utilisateur ou par un rôle.</span><span class="sxs-lookup"><span data-stu-id="29cd7-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="29cd7-111">Accorder l'accès de rôles aux profils permet de créer une architecture plus facile à maintenir.</span><span class="sxs-lookup"><span data-stu-id="29cd7-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="29cd7-112">Pour envoyer du courrier, vous devez être membre du rôle **DatabaseMailUserRole** de la base de données **msdb** et disposer d'au moins un accès à un profil de messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29cd7-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="29cd7-113">Permissions</span></span>  
 <span data-ttu-id="29cd7-114">L'utilisateur qui crée les comptes de profils et exécute des procédures stockées doit être membre du rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="29cd7-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29cd7-115">Utilisation de l'Assistant Configuration de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="29cd7-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="29cd7-116">**Pour créer un profil de messagerie de base de données**</span><span class="sxs-lookup"><span data-stu-id="29cd7-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="29cd7-117">Dans l'Explorateur d'objets, connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur laquelle vous voulez configurer la messagerie de base de données, puis développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="29cd7-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="29cd7-118">Développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="29cd7-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="29cd7-119">Double-cliquez sur Messagerie de base de données pour ouvrir l'Assistant Configuration de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="29cd7-120">Dans la page **Sélectionner une tâche de configuration** , sélectionnez l’option **gérer les comptes et les profils Database mail** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="29cd7-121">Dans la page **Gérer les profils et les comptes** , sélectionnez l'option **Créer un nouveau profil** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="29cd7-122">Dans la page **Nouveau profil**, spécifiez le nom de profil et la description, et ajoutez des comptes à inclure dans le profil, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="29cd7-123">Dans la page **Terminer l'Assistant** , examinez les actions à exécuter, puis cliquez sur **Terminer** pour terminer la création du nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="29cd7-124">**Pour configurer un profil privé de messagerie de base de données :**</span><span class="sxs-lookup"><span data-stu-id="29cd7-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="29cd7-125">Ouvrez l'Assistant Configuration de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="29cd7-126">Dans la page **Sélectionner une tâche de configuration** , sélectionnez l'option **Gérer les comptes et les profils de messagerie de base de données** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-127">Dans la page **Gérer les profils et les comptes** , sélectionnez l'option **Gérer la sécurité des profils** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-128">Sous l'onglet **Profils privés** , activez la case à cocher du profil que vous souhaitez configurer et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-129">Dans la page **Terminer l'Assistant** , examinez les actions à exécuter, puis cliquez sur **Terminer** pour terminer la configuration du profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="29cd7-130">**Pour configurer un profil public de messagerie de base de données :**</span><span class="sxs-lookup"><span data-stu-id="29cd7-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="29cd7-131">Ouvrez l'Assistant Configuration de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="29cd7-132">Dans la page **Sélectionner une tâche de configuration** , sélectionnez l'option **Gérer les comptes et les profils de messagerie de base de données** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-133">Dans la page **Gérer les profils et les comptes** , sélectionnez l'option **Gérer la sécurité des profils** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-134">Sous l'onglet **Profils publics** , activez la case à cocher du profil que vous souhaitez configurer et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="29cd7-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="29cd7-135">Dans la page **Terminer l'Assistant** , examinez les actions à exécuter, puis cliquez sur **Terminer** pour terminer la configuration du profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="29cd7-136">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29cd7-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a><span data-ttu-id="29cd7-137">Pour créer un profil privé Database Mail</span><span class="sxs-lookup"><span data-stu-id="29cd7-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="29cd7-138">Connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29cd7-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="29cd7-139">Pour créer un profil, exécutez la procédure stockée système [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="29cd7-141">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="29cd7-142">*@description*= '*Description*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="29cd7-143">où *@profile_name* est le nom du profil et *@description* est la description du profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="29cd7-144">Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="29cd7-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="29cd7-145">Pour chaque compte, exécutez la procédure stockée [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="29cd7-147">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="29cd7-148">*@account_name*= '*Nom du compte*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="29cd7-149">*@sequence_number*= '*numéro de séquence du compte dans le profil.*</span><span class="sxs-lookup"><span data-stu-id="29cd7-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="29cd7-150">'</span><span class="sxs-lookup"><span data-stu-id="29cd7-150">'</span></span>  
  
     <span data-ttu-id="29cd7-151">où *@profile_name* est le nom du profil, et *@account_name* est le nom du compte à ajouter au profil, *@sequence_number* détermine l’ordre dans lequel les comptes sont utilisés dans le profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="29cd7-152">Octroyez une autorisation d'accès au profil à chaque rôle de base de données ou à chaque utilisateur qui enverra des messages électroniques via ce profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="29cd7-153">Pour ce faire, exécutez la procédure stockée [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="29cd7-155">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="29cd7-156">*@ principal_name* = ’*nom_de_l’utilisateur_de_base_de_données_ou_rôle*’</span><span class="sxs-lookup"><span data-stu-id="29cd7-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="29cd7-157">*@is_default*= '*État du profil par défaut* '</span><span class="sxs-lookup"><span data-stu-id="29cd7-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="29cd7-158">où *@profile_name* est le nom du profil, et *@principal_name* est le nom de l’utilisateur ou du rôle de base de données, *@is_default* détermine si ce profil est le paramètre par défaut pour l’utilisateur ou le rôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="29cd7-159">L'exemple suivant crée un compte et un profil privé de messagerie de base de données, puis ajoute le compte au profil et octroie au rôle de base de données **DBMailUsers** dans la base de données **msdb** l'accès à ce profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a><span data-ttu-id="29cd7-160">Pour créer un profil public Database Mail</span><span class="sxs-lookup"><span data-stu-id="29cd7-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="29cd7-161">Connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29cd7-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="29cd7-162">Pour créer un profil, exécutez la procédure stockée système [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="29cd7-164">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="29cd7-165">*@description*= '*Description*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="29cd7-166">où *@profile_name* est le nom du profil et *@description* est la description du profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="29cd7-167">Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="29cd7-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="29cd7-168">Pour chaque compte, exécutez la procédure stockée [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="29cd7-170">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="29cd7-171">*@account_name*= '*Nom du compte*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="29cd7-172">*@sequence_number*= '*numéro de séquence du compte dans le profil.*</span><span class="sxs-lookup"><span data-stu-id="29cd7-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="29cd7-173">'</span><span class="sxs-lookup"><span data-stu-id="29cd7-173">'</span></span>  
  
     <span data-ttu-id="29cd7-174">où *@profile_name* est le nom du profil, et *@account_name* est le nom du compte à ajouter au profil, *@sequence_number* détermine l’ordre dans lequel les comptes sont utilisés dans le profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="29cd7-175">Pour accorder un accès public, exécutez la procédure stockée [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) comme suit :</span><span class="sxs-lookup"><span data-stu-id="29cd7-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="29cd7-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="29cd7-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="29cd7-177">*@profile_name*= '*Nom du profil*'</span><span class="sxs-lookup"><span data-stu-id="29cd7-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="29cd7-178">*@ principal_name* = '**public** ou **0**'</span><span class="sxs-lookup"><span data-stu-id="29cd7-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="29cd7-179">*@is_default*= '*État du profil par défaut* '</span><span class="sxs-lookup"><span data-stu-id="29cd7-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="29cd7-180">où *@profile_name* est le nom du profil, et *@principal_name* pour indiquer qu’il s’agit d’un profil public, *@is_default* détermine si ce profil est le paramètre par défaut pour l’utilisateur ou le rôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="29cd7-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="29cd7-181">L'exemple suivant crée un compte et un profil privé de messagerie de base de données, puis ajoute le compte au profil et octroie l'accès public au profil.</span><span class="sxs-lookup"><span data-stu-id="29cd7-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
