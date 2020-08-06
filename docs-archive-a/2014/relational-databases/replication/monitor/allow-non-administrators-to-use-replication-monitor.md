---
title: Autoriser des non-administrateurs à utiliser le moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603390"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="29b15-102">Autoriser des non-administrateurs à utiliser le Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="29b15-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="29b15-103">Cette rubrique explique comment autoriser des non-administrateurs à utiliser le Moniteur de réplication dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29b15-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="29b15-104">Le moniteur de réplication est utilisable par les membres des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="29b15-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="29b15-105">Rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="29b15-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="29b15-106">Ces utilisateurs peuvent surveiller la réplication et avoir un contrôle total sur la modification des propriétés de réplication telles que les planifications d'agents, les profils d'agents, etc.</span><span class="sxs-lookup"><span data-stu-id="29b15-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="29b15-107">`replmonitor`Rôle de base de données dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="29b15-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="29b15-108">Ces utilisateurs peuvent surveiller la réplication mais ne peuvent pas modifier les propriétés de réplication.</span><span class="sxs-lookup"><span data-stu-id="29b15-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="29b15-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="29b15-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29b15-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="29b15-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29b15-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="29b15-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29b15-112">**Pour autoriser des non-administrateurs à utiliser le Moniteur de réplication à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="29b15-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="29b15-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29b15-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29b15-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29b15-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29b15-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="29b15-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29b15-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="29b15-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29b15-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="29b15-117">Permissions</span></span>  
 <span data-ttu-id="29b15-118">Pour permettre aux non-administrateurs d’utiliser le moniteur de réplication, un membre du rôle serveur fixe **sysadmin** doit ajouter l’utilisateur à la base de données de distribution et affecter cet utilisateur au `replmonitor` rôle.</span><span class="sxs-lookup"><span data-stu-id="29b15-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29b15-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29b15-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="29b15-120">Pour autoriser des non-administrateurs à utiliser le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="29b15-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="29b15-121">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur de distribution, puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="29b15-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="29b15-122">Développez **Bases de données**, puis **Bases de données système**et enfin la base de données de distribution (nommée **distribution** par défaut).</span><span class="sxs-lookup"><span data-stu-id="29b15-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="29b15-123">Développez **Sécurité**, cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="29b15-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="29b15-124">Entrez un nom d'utilisateur et une connexion pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29b15-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="29b15-125">Sélectionnez un schéma par défaut de `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="29b15-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="29b15-126">Activez la `replmonitor` case à cocher dans la grille **appartenance au rôle de base de données** .</span><span class="sxs-lookup"><span data-stu-id="29b15-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29b15-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29b15-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="29b15-128">Pour ajouter un utilisateur au rôle de base de données fixe replmonitor</span><span class="sxs-lookup"><span data-stu-id="29b15-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="29b15-129">Dans la base de données de distribution sur le serveur de distribution, exécutez [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29b15-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="29b15-130">Si l’utilisateur n’est pas listé dans `UserName` dans le jeu de résultats, il doit se voir accorder l’accès à la base de données de distribution à l’aide de l’instruction [Create User &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="29b15-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="29b15-131">Sur le serveur de distribution de la base de données de distribution, exécutez [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), en spécifiant `replmonitor` la valeur pour le **@rolename** paramètre.</span><span class="sxs-lookup"><span data-stu-id="29b15-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="29b15-132">Si l’utilisateur est listé dans `MemberName` dans le jeu de résultats, l’utilisateur appartient déjà à ce rôle.</span><span class="sxs-lookup"><span data-stu-id="29b15-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="29b15-133">Si l’utilisateur n’appartient pas au `replmonitor` rôle, exécutez [Sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) sur le serveur de distribution de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="29b15-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="29b15-134">Spécifiez la valeur `replmonitor` pour **@rolename** et le nom de l’utilisateur de base de données ou la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] connexion Windows en cours d’ajout **@membername** .</span><span class="sxs-lookup"><span data-stu-id="29b15-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="29b15-135">Pour supprimer un utilisateur du rôle de base de données fixe replmonitor</span><span class="sxs-lookup"><span data-stu-id="29b15-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="29b15-136">Pour vérifier que l’utilisateur appartient au `replmonitor` rôle, exécutez [Sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) sur le serveur de distribution de la base de données de distribution et spécifiez la valeur `replmonitor` pour **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="29b15-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="29b15-137">Si l'utilisateur n'est pas répertorié dans `MemberName` dans le jeu de résultats, l'utilisateur n'appartient pas à ce rôle.</span><span class="sxs-lookup"><span data-stu-id="29b15-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="29b15-138">Si l’utilisateur appartient au `replmonitor` rôle, exécutez [sp_droprolemember &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) sur le serveur de distribution de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="29b15-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="29b15-139">Spécifiez la valeur `replmonitor` pour **@rolename** et le nom de l’utilisateur de la base de données ou la connexion Windows en cours de suppression **@membername** .</span><span class="sxs-lookup"><span data-stu-id="29b15-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
