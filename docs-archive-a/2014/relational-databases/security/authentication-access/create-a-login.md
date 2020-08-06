---
title: Créer un compte de connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697757"
---
# <a name="create-a-login"></a><span data-ttu-id="c64b0-102">Créer un compte de connexion</span><span class="sxs-lookup"><span data-stu-id="c64b0-102">Create a Login</span></span>
  <span data-ttu-id="c64b0-103">Cette rubrique explique comment créer un compte de connexion dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c64b0-104">Un compte de connexion est l'identité de la personne ou du processus qui se connecte à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c64b0-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c64b0-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c64b0-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c64b0-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c64b0-107">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="c64b0-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="c64b0-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c64b0-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c64b0-109">**Pour créer un compte de connexion, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c64b0-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="c64b0-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c64b0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c64b0-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c64b0-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c64b0-112">**Suivi :**  [Mesures à prendre après avoir créé une connexion](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c64b0-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="c64b0-113">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="c64b0-113">Background</span></span>  
 <span data-ttu-id="c64b0-114">Un compte de connexion est un principal de sécurité, ou une entité qui peut être authentifiée par un système sécurisé.</span><span class="sxs-lookup"><span data-stu-id="c64b0-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="c64b0-115">Pour se connecter à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les utilisateurs doivent disposer d'un compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c64b0-116">Vous pouvez créer un compte de connexion basé sur un principal Windows (tel qu'un utilisateur de domaine ou un groupe de domaines Windows) ou créer un compte de connexion qui n'est pas basé sur un principal Windows (tel qu'un compte de connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="c64b0-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c64b0-117">Pour utiliser l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] doit utiliser une authentification en mode mixte.</span><span class="sxs-lookup"><span data-stu-id="c64b0-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="c64b0-118">Pour plus d’informations, consultez [Choisir un mode d’authentification](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="c64b0-119">En tant que principal de sécurité, il est possible d'accorder des autorisations à des comptes de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="c64b0-120">L'étendue d'un compte de connexion est l'intégralité du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c64b0-121">Pour se connecter à une base de données spécifique sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un compte de connexion doit être mappé à un utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="c64b0-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="c64b0-122">Les autorisations dans la base de données sont accordées et refusées à l'utilisateur de la base de données, pas au compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="c64b0-123">Les autorisations dont l'étendue englobe la totalité de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (par exemple, l'autorisation `CREATE ENDPOINT`), peuvent être accordées à un compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c64b0-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c64b0-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="c64b0-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c64b0-125">Permissions</span></span>  
 <span data-ttu-id="c64b0-126">Requiert l'autorisation `ALTER ANY LOGIN` ou `ALTER LOGIN` sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c64b0-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c64b0-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="c64b0-128">Pour créer un compte de connexion SQL Server</span><span class="sxs-lookup"><span data-stu-id="c64b0-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="c64b0-129">Dans l'Explorateur d'objets, développez le dossier de l'instance du serveur où vous souhaitez créer le compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="c64b0-130">Cliquez avec le bouton droit sur le dossier **Sécurité**, pointez sur **Nouveau**, puis sélectionnez **Connexion…** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="c64b0-131">Dans la boîte de dialogue **Nouvelle connexion**, dans la page **Général**, entrez le nom d’un utilisateur dans la zone **Nom de la connexion**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="c64b0-132">Vous pouvez également cliquer sur **Rechercher…** pour ouvrir la boîte de dialogue **Sélectionner un utilisateur ou un groupe**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="c64b0-133">Si vous cliquez sur **Rechercher…**  :</span><span class="sxs-lookup"><span data-stu-id="c64b0-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="c64b0-134">Sous **Sélectionner ce type d’objet**, cliquez sur **Types d’objet...** pour ouvrir la boîte de dialogue **Types d’objet** et sélectionnez tout ou partie des éléments suivants : **Entités de sécurité intégrées**, **Groupes** et **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="c64b0-135">Les options**Principaux de sécurité intégrés** et **Utilisateurs** sont sélectionnées par défaut.</span><span class="sxs-lookup"><span data-stu-id="c64b0-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="c64b0-136">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="c64b0-137">Sous **À partir de cet emplacement**, cliquez sur **Emplacements…** pour ouvrir la boîte de dialogue **Emplacements** et sélectionner un des emplacements de serveur disponibles.</span><span class="sxs-lookup"><span data-stu-id="c64b0-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="c64b0-138">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="c64b0-139">Sous **Entrez le nom de l’objet à sélectionner (exemples)** , entrez l’utilisateur ou le nom de groupe que vous souhaitez rechercher.</span><span class="sxs-lookup"><span data-stu-id="c64b0-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="c64b0-140">Pour plus d'informations, consultez [Boîte de dialogue Choisir des utilisateurs, des ordinateurs ou des groupes](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="c64b0-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="c64b0-141">Cliquez sur **Avancé…** pour obtenir davantage d’options de recherche avancée.</span><span class="sxs-lookup"><span data-stu-id="c64b0-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="c64b0-142">Pour plus d’informations, consultez [Boîte de dialogue Choisir des utilisateurs, des ordinateurs ou des groupes - Page Avancé](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="c64b0-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="c64b0-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="c64b0-144">Pour créer un compte de connexion selon un principal Windows, sélectionnez **Authentification Windows**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="c64b0-145">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="c64b0-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="c64b0-146">Pour créer un compte de connexion qui est enregistré sur une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , sélectionnez **Authentification SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="c64b0-147">Dans la zone **Mot de passe** , entrez un mot de passe pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="c64b0-148">Entrez de nouveau ce mot de passe dans la zone **Confirmer le mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="c64b0-149">Lorsque vous modifiez un mot de passe existant, sélectionnez **Spécifier l'ancien mot de passe**, puis tapez l'ancien mot de passe dans la zone **Ancien mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="c64b0-150">Pour appliquer des options de stratégie de mot de passe pour la complexité et l'application, sélectionnez **Conserver la stratégie de mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="c64b0-151">Pour plus d'informations, consultez [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="c64b0-152">Il s'agit d'une option par défaut lorsque **Authentification SQL Server** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c64b0-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="c64b0-153">Pour appliquer des options de stratégie de mot de passe pour l'expiration, sélectionnez **Conserver l'expiration du mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="c64b0-154">L'option**Conserver la stratégie de mot de passe** doit être sélectionnée pour activer cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="c64b0-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="c64b0-155">Il s'agit d'une option par défaut lorsque **Authentification SQL Server** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c64b0-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="c64b0-156">Pour forcer l'utilisateur à créer un nouveau mot de passe après la première utilisation du compte de connexion, sélectionnez **L'utilisateur doit changer de mot de passe à la prochaine connexion**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="c64b0-157">L'option**Conserver l'expiration du mot de passe** doit être sélectionnée pour activer cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="c64b0-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="c64b0-158">Il s'agit d'une option par défaut lorsque **Authentification SQL Server** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c64b0-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="c64b0-159">Pour associer le compte de connexion à un certificat de sécurité autonome, sélectionnez **Mappé au certificat** , puis sélectionnez le nom d’un certificat existant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c64b0-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="c64b0-160">Pour associer le compte de connexion à une clé asymétrique autonome, sélectionnez **Mappé à la clé asymétrique** , puis sélectionnez le nom d’une clé existante dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c64b0-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="c64b0-161">Pour associer le compte de connexion à des informations d'identification de sécurité, activez la case à cocher **Mappé aux informations d'identification** , puis sélectionnez des informations d'identification existantes dans la liste ou cliquez sur **Ajouter** pour créer de nouvelles informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="c64b0-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="c64b0-162">Pour supprimer du compte de connexion un mappage à des informations d'identification de sécurité, sélectionnez les informations d'identification dans **Informations d'identification mappées** et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="c64b0-163">Pour plus d’informations sur les informations d’identification en général, consultez [Informations d’identification &#40;moteur de base de données&#41;](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="c64b0-164">Sélectionnez une base de données par défaut pour le compte de connexion dans la liste **Base de données par défaut** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="c64b0-165">**Master** est la valeur par défaut pour cette option.</span><span class="sxs-lookup"><span data-stu-id="c64b0-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="c64b0-166">Dans la liste **Langue par défaut** , sélectionnez une langue par défaut pour le compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="c64b0-167">Options supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c64b0-167">Additional Options</span></span>  
 <span data-ttu-id="c64b0-168">La boîte de dialogue **Connexion – Nouvelle** offre également des options sur quatre pages supplémentaires : **Rôles de serveur**, **Mappage utilisateur**, **Éléments sécurisables** et **État**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="c64b0-169">Rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="c64b0-169">Server Roles</span></span>  
 <span data-ttu-id="c64b0-170">La page **Rôles de serveur** répertorie tous les rôles possibles qui peuvent être affectés au nouveau compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="c64b0-171">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="c64b0-171">The following options are available:</span></span>  
  
 <span data-ttu-id="c64b0-172">Case à cocher**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="c64b0-173">Les membres du rôle serveur fixe **bulkadmin** peuvent exécuter l’instruction BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="c64b0-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="c64b0-174">Case à cocher**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="c64b0-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="c64b0-175">Les membres du rôle serveur fixe **dbcreator** peuvent créer, modifier, supprimer et restaurer n’importe quelle base de données.</span><span class="sxs-lookup"><span data-stu-id="c64b0-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="c64b0-176">Case à cocher**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="c64b0-177">Les membres du rôle serveur fixe **diskadmin** peuvent gérer les fichiers de disque.</span><span class="sxs-lookup"><span data-stu-id="c64b0-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="c64b0-178">Case à cocher**processadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-178">**processadmin** check box</span></span>  
 <span data-ttu-id="c64b0-179">Les membres du rôle serveur fixe **processadmin** peuvent arrêter les processus en cours d’exécution dans une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="c64b0-180">Case à cocher**public**</span><span class="sxs-lookup"><span data-stu-id="c64b0-180">**public** check box</span></span>  
 <span data-ttu-id="c64b0-181">Tous les utilisateurs, groupes et rôles SQL Server appartiennent au rôle serveur fixe **public** par défaut.</span><span class="sxs-lookup"><span data-stu-id="c64b0-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="c64b0-182">Case à cocher**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="c64b0-183">Les membres du rôle serveur fixe **securityadmin** gèrent les connexions et leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="c64b0-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="c64b0-184">Ils peuvent assigner des autorisations GRANT, DENY et REVOKE au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="c64b0-185">Ils peuvent aussi assigner des autorisations GRANT, DENY et REVOKE au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c64b0-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="c64b0-186">En outre, ils peuvent réinitialiser les mots de passe pour les connexions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c64b0-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="c64b0-187">Case à cocher**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="c64b0-188">Les membres du rôle serveur fixe **serveradmin** peuvent modifier les options de configuration à l’échelle du serveur et arrêter le serveur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="c64b0-189">Case à cocher**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="c64b0-190">Les membres du rôle serveur fixe **setupadmin** peuvent ajouter et supprimer des serveurs liés et exécuter certaines procédures stockées du système.</span><span class="sxs-lookup"><span data-stu-id="c64b0-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="c64b0-191">Case à cocher**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="c64b0-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="c64b0-192">Les membres du rôle serveur fixe **sysadmin** peuvent exécuter n’importe quelle activité dans le [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="c64b0-193">Mappage de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c64b0-193">User Mapping</span></span>  
 <span data-ttu-id="c64b0-194">La page **Mappage de l'utilisateur** répertorie toutes les bases de données possibles et les appartenances de rôle de base de données sur ces bases de données qui peuvent être appliquées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="c64b0-195">Les bases de données sélectionnées déterminent les appartenances aux rôles disponibles pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="c64b0-196">Les options suivantes sont disponibles sur cette page :</span><span class="sxs-lookup"><span data-stu-id="c64b0-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="c64b0-197">**Utilisateurs mappés à cette connexion**</span><span class="sxs-lookup"><span data-stu-id="c64b0-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="c64b0-198">Sélectionnez les bases de données auxquelles cette connexion peut accéder.</span><span class="sxs-lookup"><span data-stu-id="c64b0-198">Select the databases that this login can access.</span></span> <span data-ttu-id="c64b0-199">Lorsque vous sélectionnez une base de données, ses rôles de base de données valides s’affichent dans le volet **Appartenance au rôle de base de données pour :** _nom_base_de_données_ .</span><span class="sxs-lookup"><span data-stu-id="c64b0-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="c64b0-200">**Map**</span><span class="sxs-lookup"><span data-stu-id="c64b0-200">**Map**</span></span>  
 <span data-ttu-id="c64b0-201">Autorise la connexion à accéder aux bases de données répertoriées au-dessous.</span><span class="sxs-lookup"><span data-stu-id="c64b0-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="c64b0-202">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="c64b0-202">**Database**</span></span>  
 <span data-ttu-id="c64b0-203">Répertorie les bases de données disponibles sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="c64b0-204">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="c64b0-204">**User**</span></span>  
 <span data-ttu-id="c64b0-205">Spécifiez un utilisateur de la base de données à mapper sur cette connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="c64b0-206">Par défaut, l'utilisateur a le même nom que la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="c64b0-207">**Schéma par défaut**</span><span class="sxs-lookup"><span data-stu-id="c64b0-207">**Default Schema**</span></span>  
 <span data-ttu-id="c64b0-208">Spécifie le schéma par défaut de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="c64b0-209">Lors de la création d'un utilisateur, son schéma par défaut est **dbo**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="c64b0-210">Il est possible de spécifier un schéma par défaut qui n'existe pas encore.</span><span class="sxs-lookup"><span data-stu-id="c64b0-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="c64b0-211">Vous ne pouvez pas spécifier de schéma par défaut pour un utilisateur mappé sur un groupe Windows, un certificat ou une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="c64b0-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="c64b0-212">**Compte Invité activé pour :**  _nom_base_de_données_</span><span class="sxs-lookup"><span data-stu-id="c64b0-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="c64b0-213">Attribut en lecture seule indiquant si le compte Invité est activé sur la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c64b0-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="c64b0-214">Utilisez la page **État** de la boîte de dialogue **Propriétés de la connexion** du compte Invité pour activer ou désactiver le compte Invité.</span><span class="sxs-lookup"><span data-stu-id="c64b0-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="c64b0-215">**Appartenance au rôle de base de données pour :**  _nom_base_de_données_</span><span class="sxs-lookup"><span data-stu-id="c64b0-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="c64b0-216">Sélectionnez les rôles pour l'utilisateur dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c64b0-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="c64b0-217">Tous les utilisateurs sont membres du rôle **public** de chaque base de données et ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="c64b0-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="c64b0-218">Pour plus d’informations sur les rôles de base de données, consultez [Rôles au niveau de la base de données](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="c64b0-219">Éléments sécurisables</span><span class="sxs-lookup"><span data-stu-id="c64b0-219">Securables</span></span>  
 <span data-ttu-id="c64b0-220">La page **Éléments sécurisables** répertorie tous les éléments sécurisables possibles et les autorisations sur ces éléments sécurisables qui peuvent être accordées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="c64b0-221">Les options suivantes sont disponibles sur cette page :</span><span class="sxs-lookup"><span data-stu-id="c64b0-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="c64b0-222">**Grille supérieure**</span><span class="sxs-lookup"><span data-stu-id="c64b0-222">**Upper Grid**</span></span>  
 <span data-ttu-id="c64b0-223">Contient un ou plusieurs éléments pour lesquels des autorisations peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="c64b0-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="c64b0-224">Les colonnes affichées dans la grille supérieure varient selon le principal ou l'élément sécurisable.</span><span class="sxs-lookup"><span data-stu-id="c64b0-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="c64b0-225">Pour ajouter des éléments à la grille supérieure :</span><span class="sxs-lookup"><span data-stu-id="c64b0-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="c64b0-226">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="c64b0-227">Dans la boîte de dialogue **Ajouter des objets** , sélectionnez l’une des options suivantes : **objets spécifiques...**, **tous les objets des types...** ou **le serveur**_SERVER_NAME_.</span><span class="sxs-lookup"><span data-stu-id="c64b0-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64b0-228">La sélection de l’option **Le serveur**_nom_serveur_ remplit automatiquement la grille supérieure avec tous les objets sécurisables de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="c64b0-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="c64b0-229">Si vous sélectionnez **Objets spécifiques…**  :</span><span class="sxs-lookup"><span data-stu-id="c64b0-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="c64b0-230">Dans la boîte de dialogue **Sélectionner les objets**, sous **Sélectionnez ces types d’objets**, cliquez sur **Types d’objets…** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="c64b0-231">Dans la boîte de dialogue **Sélectionner les types d’objets**, sélectionnez tout ou partie des types d’objets suivants : **Points de terminaison**, **Connexions**, **Serveurs**, **Groupes de disponibilité** et **Rôles serveur**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="c64b0-232">Sous **Entrez les noms d’objets à sélectionner (exemples)** , cliquez sur **Parcourir…** .</span><span class="sxs-lookup"><span data-stu-id="c64b0-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="c64b0-233">Dans la boîte de dialogue **Rechercher des objets** , sélectionnez les objets disponibles du type sélectionné dans la boîte de dialogue **Sélectionner les types d'objets** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="c64b0-234">Dans la boîte de dialogue **Sélectionner des objets** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="c64b0-235">Si vous sélectionnez **Tous les objets des types...** , dans la boîte de dialogue **Sélectionner les types d’objets**, sélectionnez tout ou partie des types d’objets suivants : **Points de terminaison**, **Connexions**, **Serveurs**, **Groupes de disponibilité** et **Rôles serveur**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="c64b0-236">**Nom**</span><span class="sxs-lookup"><span data-stu-id="c64b0-236">**Name**</span></span>  
 <span data-ttu-id="c64b0-237">Nom de chaque principal ou élément sécurisable ajouté à la grille.</span><span class="sxs-lookup"><span data-stu-id="c64b0-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="c64b0-238">**Type**</span><span class="sxs-lookup"><span data-stu-id="c64b0-238">**Type**</span></span>  
 <span data-ttu-id="c64b0-239">Décrit le type de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="c64b0-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="c64b0-240">**Onglet Autorisations explicites**</span><span class="sxs-lookup"><span data-stu-id="c64b0-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="c64b0-241">Énumère les autorisations possibles pour les éléments sécurisables sélectionnés dans la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="c64b0-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="c64b0-242">Toutes les options ne sont pas disponibles pour toutes les autorisations explicites.</span><span class="sxs-lookup"><span data-stu-id="c64b0-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="c64b0-243">**autorisations**</span><span class="sxs-lookup"><span data-stu-id="c64b0-243">**Permissions**</span></span>  
 <span data-ttu-id="c64b0-244">Nom de l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="c64b0-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="c64b0-245">**Fournisseur d'autorisations**</span><span class="sxs-lookup"><span data-stu-id="c64b0-245">**Grantor**</span></span>  
 <span data-ttu-id="c64b0-246">Principal ayant accordé l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="c64b0-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="c64b0-247">**Octroyer**</span><span class="sxs-lookup"><span data-stu-id="c64b0-247">**Grant**</span></span>  
 <span data-ttu-id="c64b0-248">Sélectionnez cette option pour octroyer cette autorisation à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="c64b0-249">Désactivez-la pour révoquer cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="c64b0-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="c64b0-250">**Avec autorisation**</span><span class="sxs-lookup"><span data-stu-id="c64b0-250">**With Grant**</span></span>  
 <span data-ttu-id="c64b0-251">Reflète l'état de l'option WITH GRANT pour l'autorisation indiquée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c64b0-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="c64b0-252">Cette zone est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="c64b0-252">This box is read-only.</span></span> <span data-ttu-id="c64b0-253">Pour appliquer cette autorisation, utilisez l'instruction [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c64b0-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="c64b0-254">**Deny**</span><span class="sxs-lookup"><span data-stu-id="c64b0-254">**Deny**</span></span>  
 <span data-ttu-id="c64b0-255">Sélectionnez cette option pour refuser cette autorisation à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="c64b0-256">Désactivez-la pour révoquer cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="c64b0-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="c64b0-257">Statut</span><span class="sxs-lookup"><span data-stu-id="c64b0-257">Status</span></span>  
 <span data-ttu-id="c64b0-258">La page **État** répertorie certaines des options d'authentification et d'autorisation qui peuvent être configurées sur la connexion sélectionnée de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c64b0-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="c64b0-259">Les options suivantes sont disponibles sur cette page :</span><span class="sxs-lookup"><span data-stu-id="c64b0-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="c64b0-260">**Autorisation de se connecter au moteur de base de données**</span><span class="sxs-lookup"><span data-stu-id="c64b0-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="c64b0-261">Lorsque vous travaillez avec ce paramètre, vous devez considérer la connexion sélectionnée comme un principal auquel une autorisation sur un élément sécurisable peut être accordée ou refusée.</span><span class="sxs-lookup"><span data-stu-id="c64b0-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="c64b0-262">Sélectionnez **Octroyer** pour accorder l'autorisation CONNECT SQL à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="c64b0-263">Sélectionnez **Refuser** pour refuser l'autorisation CONNECT SQL à la connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="c64b0-264">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="c64b0-264">**Login**</span></span>  
 <span data-ttu-id="c64b0-265">Lorsque vous travaillez avec ce paramètre, vous devez considérer la connexion sélectionnée comme un enregistrement d'une table.</span><span class="sxs-lookup"><span data-stu-id="c64b0-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="c64b0-266">Les modifications apportées aux valeurs répertoriées ici seront appliquées à l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c64b0-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="c64b0-267">Une connexion qui a été désactivée continue d'exister en tant qu'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c64b0-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="c64b0-268">Mais si elle tente de se connecter à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], elle ne sera pas authentifiée.</span><span class="sxs-lookup"><span data-stu-id="c64b0-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="c64b0-269">Sélectionnez cette option pour activer ou désactiver cette connexion.</span><span class="sxs-lookup"><span data-stu-id="c64b0-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="c64b0-270">Cette option utilise l'instruction ALTER LOGIN avec l'option ENABLE ou DISABLE.</span><span class="sxs-lookup"><span data-stu-id="c64b0-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="c64b0-271">**Authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c64b0-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="c64b0-272">La case à cocher **La connexion est verrouillée** est disponible uniquement si la connexion sélectionnée se connecte à l’aide de l’authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et qu’elle a été verrouillée. Ce paramètre est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="c64b0-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="c64b0-273">Pour déverrouiller une connexion verrouillée, exécutez ALTER LOGIN avec l'option UNLOCK.</span><span class="sxs-lookup"><span data-stu-id="c64b0-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c64b0-274">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c64b0-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="c64b0-275">Pour créer une connexion à l'aide de l'authentification Windows</span><span class="sxs-lookup"><span data-stu-id="c64b0-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="c64b0-276">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c64b0-277">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c64b0-278">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="c64b0-279">Pour créer une connexion via l'authentification SQL Server</span><span class="sxs-lookup"><span data-stu-id="c64b0-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="c64b0-280">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64b0-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c64b0-281">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c64b0-282">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c64b0-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="c64b0-283">Pour plus d’informations, consultez [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c64b0-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a> <span data-ttu-id="c64b0-284">Suivi : Mesures à prendre après avoir créé un compte de connexion</span><span class="sxs-lookup"><span data-stu-id="c64b0-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="c64b0-285">Une fois le compte de connexion créé, celui-ci peut se connecter à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], mais il ne dispose pas nécessairement des autorisations suffisantes pour effectuer des tâches utiles.</span><span class="sxs-lookup"><span data-stu-id="c64b0-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="c64b0-286">La liste suivante fournit des liens vers des actions de compte de connexion courantes.</span><span class="sxs-lookup"><span data-stu-id="c64b0-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="c64b0-287">Pour effectuer une jointure entre le compte de connexion et un rôle de base de données, consultez [Attacher un rôle](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="c64b0-288">Pour autoriser un compte de connexion à utiliser une base de données, consultez [Créer un utilisateur de base de données](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="c64b0-289">Pour accorder une autorisation à un compte de connexion, consultez [Accorder une autorisation à un principal](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c64b0-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
