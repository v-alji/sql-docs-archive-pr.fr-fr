---
title: Résoudre les problèmes liés aux utilisateurs orphelins (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605028"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="3e72d-102">Dépanner des utilisateurs orphelins (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e72d-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="3e72d-103">Pour se connecter à une instance de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un principal doit posséder une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.</span><span class="sxs-lookup"><span data-stu-id="3e72d-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3e72d-104">Cette connexion est utilisée dans le processus d'authentification chargé de vérifier que le principal est autorisé à se connecter à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e72d-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e72d-105">Les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexions sur une instance de serveur sont visibles dans l’affichage catalogue **sys. server_principals** et l’affichage de compatibilité **sys.sysles connexions** .</span><span class="sxs-lookup"><span data-stu-id="3e72d-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 <span data-ttu-id="3e72d-106">Les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] accèdent aux bases de données à l'aide d'un utilisateur de base de données mappé à la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e72d-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3e72d-107">Il y a deux exceptions à cette règle :</span><span class="sxs-lookup"><span data-stu-id="3e72d-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="3e72d-108">Le compte invité.</span><span class="sxs-lookup"><span data-stu-id="3e72d-108">The guest account.</span></span>  
  
     <span data-ttu-id="3e72d-109">Lorsqu'il est activé dans la base de données, ce compte autorise les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non mappées à un utilisateur de base de données à accéder en tant qu'invité à la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="3e72d-110">Appartenance aux groupes Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3e72d-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="3e72d-111">Une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] créée à partir d'un utilisateur Windows peut accéder à la base de données si cet utilisateur est membre d'un groupe Windows lui-même utilisateur de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="3e72d-112">Les informations relatives au mappage d'une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à un utilisateur de base de données sont stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="3e72d-113">Elles incluent le nom de l'utilisateur de base de données et l'identificateur de sécurité de connexion (SID) de la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondante.</span><span class="sxs-lookup"><span data-stu-id="3e72d-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3e72d-114">Les autorisations de cet utilisateur de base de données sont utilisées comme autorisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="3e72d-115">Un utilisateur de base de données pour lequel la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondante n'est pas définie sur une instance serveur, ou l'est de façon incorrecte, ne peut pas se connecter à cette instance.</span><span class="sxs-lookup"><span data-stu-id="3e72d-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="3e72d-116">L'utilisateur devient donc un *utilisateur orphelin* de la base de données sur cette instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="3e72d-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="3e72d-117">Un utilisateur de base de données peut se retrouver orphelin si la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondante est supprimée.</span><span class="sxs-lookup"><span data-stu-id="3e72d-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="3e72d-118">De même, un utilisateur peut devenir orphelin après qu'une base de données a été restaurée ou attachée à une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e72d-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e72d-119">Le fait de se retrouver orphelin peut se produire si l'utilisateur de base de données est mappé à un SID absent dans la nouvelle instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="3e72d-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e72d-120">Une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexion ne peut pas accéder à une base de données dans laquelle elle n’a pas d’utilisateur de base de données correspondant, sauf si l' **invité** est activé dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="3e72d-121">Pour plus d’informations sur la création d’un compte d’utilisateur de base de données, consultez [Create user &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e72d-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="3e72d-122">Pour détecter des utilisateurs orphelins</span><span class="sxs-lookup"><span data-stu-id="3e72d-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="3e72d-123">Pour détecter des utilisateurs orphelins, exécutez les instructions Transact-SQL suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e72d-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="3e72d-124">Vous obtenez la liste des utilisateurs et de leurs identificateurs de sécurité (SID) qui, dans la base de données en cours, ne sont pas liés à une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e72d-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3e72d-125">Pour plus d’informations, consultez [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e72d-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e72d-126">**sp_change_users_login** ne peut pas être utilisé avec des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexions créées à partir de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e72d-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="3e72d-127">Pour résoudre le cas d'un utilisateur orphelin</span><span class="sxs-lookup"><span data-stu-id="3e72d-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="3e72d-128">Pour résoudre le cas d'un orphelin, utilisez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="3e72d-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="3e72d-129">La commande suivante relient le compte de connexion au serveur spécifié par *<login_name>* avec l’utilisateur de base de données spécifié par \*<Database_user \*>.</span><span class="sxs-lookup"><span data-stu-id="3e72d-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="3e72d-130">Pour plus d’informations, consultez [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e72d-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="3e72d-131">Dès l'exécution du code de l'étape ci-dessus, l'utilisateur peut accéder à la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e72d-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="3e72d-132">L’utilisateur peut ensuite modifier le mot de passe de l' *<login_name>* compte de connexion à l’aide de la procédure stockée **sp_password** , comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e72d-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3e72d-133">Seuls les comptes de connexion avec l'autorisation ALTER ANY LOGIN peuvent modifier le mot de passe du compte de connexion d'un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e72d-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="3e72d-134">Toutefois, seuls les membres du rôle **sysadmin** peuvent modifier les mots de passe des membres du rôle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3e72d-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e72d-135">**sp_password** ne peut pas être utilisé pour les [!INCLUDE[msCoName](../../includes/msconame-md.md)] comptes Windows.</span><span class="sxs-lookup"><span data-stu-id="3e72d-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="3e72d-136">Les utilisateurs se connectant à une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par l'intermédiaire de leur compte réseau Windows sont authentifiés par Windows ; par conséquent, leurs mots de passe ne peuvent être modifiés que dans Windows.</span><span class="sxs-lookup"><span data-stu-id="3e72d-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="3e72d-137">Pour plus d’informations, consultez [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e72d-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e72d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e72d-138">See Also</span></span>  
 <span data-ttu-id="3e72d-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="3e72d-145">[sys.sysles utilisateurs &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e72d-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="3e72d-146">Connexionssys.sys&#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e72d-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
