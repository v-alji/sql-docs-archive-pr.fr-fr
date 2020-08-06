---
title: Principaux (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614465"
---
# <a name="principals-database-engine"></a><span data-ttu-id="32d38-102">Principaux (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="32d38-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="32d38-103">Les*principaux* sont des entités qui peuvent demander des ressources [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32d38-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="32d38-104">Comme les autres composants du modèle d'autorisation [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , les principaux peuvent être ordonnés de façon hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="32d38-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="32d38-105">La portée de l’influence d’un principal dépend de la portée de sa définition : Windows, serveur, base de données ; et du fait que le principal est indivisible ou qu'il s’agit d’une collection.</span><span class="sxs-lookup"><span data-stu-id="32d38-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="32d38-106">Une connexion Windows est un exemple de principal indivisible et un groupe Windows est un exemple de principal constituant une collection.</span><span class="sxs-lookup"><span data-stu-id="32d38-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="32d38-107">Chaque principal a un identificateur de sécurité (SID).</span><span class="sxs-lookup"><span data-stu-id="32d38-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="32d38-108">**Principaux au niveau de Windows**</span><span class="sxs-lookup"><span data-stu-id="32d38-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="32d38-109">Connexion à un domaine Windows</span><span class="sxs-lookup"><span data-stu-id="32d38-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="32d38-110">Connexion locale Windows</span><span class="sxs-lookup"><span data-stu-id="32d38-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="32d38-111">**SQL Server** - **level** **principaux** de niveau</span><span class="sxs-lookup"><span data-stu-id="32d38-111">**SQL Server**-**level** **principals**</span></span>  
  
-   <span data-ttu-id="32d38-112">Connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d38-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Login</span></span>  
  
-   <span data-ttu-id="32d38-113">Rôle serveur</span><span class="sxs-lookup"><span data-stu-id="32d38-113">Server Role</span></span>  
  
 <span data-ttu-id="32d38-114">**Principaux au niveau des bases de données**</span><span class="sxs-lookup"><span data-stu-id="32d38-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="32d38-115">Utilisateur de la base de données</span><span class="sxs-lookup"><span data-stu-id="32d38-115">Database User</span></span>  
  
-   <span data-ttu-id="32d38-116">Rôle de base de données</span><span class="sxs-lookup"><span data-stu-id="32d38-116">Database Role</span></span>  
  
-   <span data-ttu-id="32d38-117">Rôle d'application</span><span class="sxs-lookup"><span data-stu-id="32d38-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="32d38-118">La connexion SQL Server sa</span><span class="sxs-lookup"><span data-stu-id="32d38-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="32d38-119">La connexion sa [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est un principal au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="32d38-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="32d38-120">Par défaut, elle est créée lorsqu'une instance est installée.</span><span class="sxs-lookup"><span data-stu-id="32d38-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="32d38-121">À compter de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], la base de données par défaut de sa est MASTER.</span><span class="sxs-lookup"><span data-stu-id="32d38-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="32d38-122">Il s'agit là d'une différence par rapport aux versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d38-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="32d38-123">Rôle de base de données public</span><span class="sxs-lookup"><span data-stu-id="32d38-123">public Database Role</span></span>  
 <span data-ttu-id="32d38-124">Chaque utilisateur de base de données appartient au rôle de base de données public.</span><span class="sxs-lookup"><span data-stu-id="32d38-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="32d38-125">Quand des autorisations spécifiques sur un élément sécurisable n’ont pas été accordées ni refusées à un utilisateur, celui-ci hérite des autorisations accordées à public sur cet élément sécurisable.</span><span class="sxs-lookup"><span data-stu-id="32d38-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="32d38-126">INFORMATION_SCHEMA et sys</span><span class="sxs-lookup"><span data-stu-id="32d38-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="32d38-127">Chaque base de données inclut deux entités qui apparaissent comme des utilisateurs dans des affichages catalogue : INFORMATION_SCHEMA et sys.</span><span class="sxs-lookup"><span data-stu-id="32d38-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="32d38-128">Ces entités sont requises par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d38-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="32d38-129">Ce ne sont pas des principaux et ils ne peuvent être ni modifiés, ni supprimés.</span><span class="sxs-lookup"><span data-stu-id="32d38-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="32d38-130">Connexions SQL Server basées sur des certificats</span><span class="sxs-lookup"><span data-stu-id="32d38-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="32d38-131">Les principaux de serveur compris entre deux signes dièse (##) sont destinés uniquement à une utilisation système interne.</span><span class="sxs-lookup"><span data-stu-id="32d38-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="32d38-132">Les principaux suivants sont créés à partir de certificats lors de l'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; ils ne doivent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="32d38-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="32d38-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="32d38-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="32d38-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="32d38-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="32d38-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="32d38-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="32d38-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="32d38-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="32d38-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="32d38-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="32d38-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="32d38-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="32d38-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="32d38-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="32d38-140">Utilisateur invité</span><span class="sxs-lookup"><span data-stu-id="32d38-140">The guest User</span></span>  
 <span data-ttu-id="32d38-141">Chaque base de données inclut un **invité**.</span><span class="sxs-lookup"><span data-stu-id="32d38-141">Each database includes a **guest**.</span></span> <span data-ttu-id="32d38-142">Les autorisations accordées à l'utilisateur **invité** sont héritées par les utilisateurs qui ont accès à la base de données, mais n'ont pas de compte d'utilisateur dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="32d38-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="32d38-143">L’utilisateur **invité** ne peut pas être supprimé, mais il peut être désactivé en révoquant son `CONNECT` autorisation.</span><span class="sxs-lookup"><span data-stu-id="32d38-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="32d38-144">L' `CONNECT` autorisation peut être révoquée en exécutant `REVOKE CONNECT FROM GUEST` dans une base de données autre que Master ou tempdb.</span><span class="sxs-lookup"><span data-stu-id="32d38-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="32d38-145">Client et serveur de base de données</span><span class="sxs-lookup"><span data-stu-id="32d38-145">Client and Database Server</span></span>  
 <span data-ttu-id="32d38-146">Par définition, un client et un serveur de base de données sont des principaux de sécurité et peuvent être sécurisés.</span><span class="sxs-lookup"><span data-stu-id="32d38-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="32d38-147">Ces entités peuvent être authentifiées mutuellement avant qu'une connexion réseau sécurisée soit établie.</span><span class="sxs-lookup"><span data-stu-id="32d38-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="32d38-148">prend en charge le protocole d’authentification [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , qui définit la manière dont les clients interagissent avec un service d’authentification réseau.</span><span class="sxs-lookup"><span data-stu-id="32d38-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="32d38-149">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="32d38-149">Related Tasks</span></span>  
 <span data-ttu-id="32d38-150">Les rubriques suivantes sont incluses dans cette section de la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="32d38-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="32d38-151">Rubriques de procédures relatives à la gestion des connexions, des utilisateurs et des schémas</span><span class="sxs-lookup"><span data-stu-id="32d38-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="32d38-152">Rôles de niveau serveur</span><span class="sxs-lookup"><span data-stu-id="32d38-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="32d38-153">Rôles au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="32d38-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="32d38-154">Rôles d’application</span><span class="sxs-lookup"><span data-stu-id="32d38-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="32d38-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32d38-155">See Also</span></span>  
 <span data-ttu-id="32d38-156">[Sécurisation de SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32d38-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="32d38-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32d38-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="32d38-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32d38-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="32d38-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32d38-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="32d38-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32d38-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="32d38-161">[Rôles de niveau serveur](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="32d38-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="32d38-162">Rôles au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="32d38-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
