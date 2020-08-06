---
title: Créer un compte de messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603551"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="d0ca5-102">Créer un compte de messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="d0ca5-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="d0ca5-103">Utilisez l' **Assistant Configuration de la messagerie de base de données** ou [!INCLUDE[tsql](../../includes/tsql-md.md)] pour créer un compte de messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="d0ca5-104">**Avant de commencer :**  [Prérequis](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="d0ca5-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="d0ca5-105">**Pour créer un compte Database Mail, à l’aide de :**  [ Assistant Configuration de Database Mail](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="d0ca5-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="d0ca5-106">**Suivi :**  [Étapes suivantes pour configurer Database Mail](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d0ca5-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0ca5-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d0ca5-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d0ca5-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d0ca5-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="d0ca5-109">Déterminez le nom de serveur et le numéro de port du serveur SMTP (Simple Mail Transfer Protocol) utilisé pour l'envoi du courrier électronique. Si le serveur SMTP nécessite une authentification, déterminez le nom d'utilisateur et le mot de passe du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="d0ca5-110">Si vous le souhaitez, vous pouvez également spécifier le type de serveur et le numéro de port du serveur.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="d0ca5-111">Le type de serveur est toujours SMTP pour le courrier sortant.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="d0ca5-112">La plupart des serveurs SMTP utilisent le numéro de port par défaut 25.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d0ca5-113">Utilisation de l'Assistant Configuration de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="d0ca5-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="d0ca5-114">**Pour créer un compte de messagerie de base de données à l'aide d'un Assistant**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="d0ca5-115">Dans l'Explorateur d'objets, connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur laquelle vous voulez configurer la messagerie de base de données, puis développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="d0ca5-116">Développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="d0ca5-117">Double-cliquez sur Messagerie de base de données pour ouvrir l'Assistant Configuration de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="d0ca5-118">Dans la page **Sélectionner une tâche de configuration** , sélectionnez **Gérer les comptes et les profils de messagerie de base de données**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="d0ca5-119">Dans la page **Gérer les profils et les comptes** , sélectionnez **Créer un nouveau compte** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="d0ca5-120">Dans la page **Nouveau compte** , spécifiez le nom du compte, sa description, les informations du serveur de messagerie et le type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="d0ca5-121">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="d0ca5-122">Dans la page **Terminer l'Assistant** , examinez les actions à exécuter, puis cliquez sur **Terminer** pour terminer la création du nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d0ca5-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0ca5-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="d0ca5-124">**Pour créer un compte de messagerie de base de données à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="d0ca5-125">Exécutez la procédure stockée **msdb.dbo.sysmail_add_account_sp** pour créer le compte et spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0ca5-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="d0ca5-126">Le nom du compte à créer.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="d0ca5-127">Une description facultative du compte.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="d0ca5-128">L'adresse électronique à afficher sur les messages électroniques sortants.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="d0ca5-129">Le nom complet à afficher sur les messages électroniques sortants.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="d0ca5-130">Le nom du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="d0ca5-131">Le nom d'utilisateur à utiliser pour la connexion au serveur SMTP, si celui-ci nécessite une authentification.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="d0ca5-132">Le mot de passe à utiliser pour la connexion au serveur SMTP, si celui-ci nécessite une authentification.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="d0ca5-133">L'exemple ci-dessous crée un compte de messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a> <span data-ttu-id="d0ca5-134">Suivi : Étapes suivantes pour configurer Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0ca5-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="d0ca5-135">Créer un profil de messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="d0ca5-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
