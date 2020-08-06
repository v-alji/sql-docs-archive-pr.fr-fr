---
title: Joindre un rôle | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602015"
---
# <a name="join-a-role"></a><span data-ttu-id="249d1-102">joindre un rôle</span><span class="sxs-lookup"><span data-stu-id="249d1-102">Join a Role</span></span>
  <span data-ttu-id="249d1-103">Cette rubrique décrit comment affecter des rôles aux utilisateurs des connexions et des bases de données dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="249d1-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="249d1-104">Utilisez les rôles dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour gérer efficacement les autorisations.</span><span class="sxs-lookup"><span data-stu-id="249d1-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="249d1-105">Affectez des autorisations aux rôles, puis ajoutez et supprimez des utilisateurs et des connexions aux rôles.</span><span class="sxs-lookup"><span data-stu-id="249d1-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="249d1-106">L'utilisation de rôles évite de devoir maintenir individuellement les autorisations pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="249d1-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="249d1-107">prend en charge quatre types de rôle :</span><span class="sxs-lookup"><span data-stu-id="249d1-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="249d1-108">Rôles serveur fixes</span><span class="sxs-lookup"><span data-stu-id="249d1-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="249d1-109">Rôles de serveur définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="249d1-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="249d1-110">Rôles de base de données fixes</span><span class="sxs-lookup"><span data-stu-id="249d1-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="249d1-111">Rôles de base de données définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="249d1-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="249d1-112">Les rôles fixes sont automatiquement disponibles dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="249d1-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="249d1-113">Les rôles fixes ont les autorisations nécessaires pour accomplir des tâches courantes.</span><span class="sxs-lookup"><span data-stu-id="249d1-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="249d1-114">Pour plus d'informations sur les rôles fixes, consultez les liens suivants.</span><span class="sxs-lookup"><span data-stu-id="249d1-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="249d1-115">Les rôles définis par l'utilisateur sont créés par vous-même et peuvent être personnalisés à l'aide des autorisations que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="249d1-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="249d1-116">Pour plus d'informations sur les rôles définis par l'utilisateur, consultez les liens suivants.</span><span class="sxs-lookup"><span data-stu-id="249d1-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="249d1-117">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="249d1-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="249d1-118">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="249d1-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="249d1-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="249d1-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="249d1-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="249d1-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="249d1-121">**Pour assigner des rôles aux utilisateurs des connexions et des bases de données, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="249d1-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="249d1-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="249d1-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="249d1-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="249d1-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="249d1-124">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="249d1-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="249d1-125">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="249d1-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="249d1-126">La modification du nom d'un rôle de base de données ne modifie pas le numéro d'identification, le propriétaire ou les autorisations du rôle.</span><span class="sxs-lookup"><span data-stu-id="249d1-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="249d1-127">Les rôles de base de données sont visibles dans les vues de catalogue sys.database_role_members et sys.database_principals.</span><span class="sxs-lookup"><span data-stu-id="249d1-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="249d1-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="249d1-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="249d1-129">Autorisations</span><span class="sxs-lookup"><span data-stu-id="249d1-129">Permissions</span></span>  
 <span data-ttu-id="249d1-130">Nécessite l' `ALTER ANY ROLE` autorisation sur la base de données, `ALTER` l’autorisation sur le rôle ou l’appartenance à **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="249d1-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="249d1-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="249d1-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="249d1-132">Pour ajouter un membre à un rôle serveur fixe</span><span class="sxs-lookup"><span data-stu-id="249d1-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="249d1-133">Dans l'Explorateur d'objets, développez le serveur sur lequel vous souhaitez modifier un rôle serveur fixe.</span><span class="sxs-lookup"><span data-stu-id="249d1-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="249d1-134">Développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="249d1-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="249d1-135">Développez le dossier **Rôles serveur** .</span><span class="sxs-lookup"><span data-stu-id="249d1-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="249d1-136">Cliquez avec le bouton droit sur le rôle à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="249d1-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="249d1-137">Dans la boîte de dialogue **Propriétés du rôle de serveur-**_server_role_name_ , dans la page **membres** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="249d1-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="249d1-138">Dans la boîte de dialogue **Sélectionner la connexion au serveur ou le rôle de serveur** , sous **Entrez les noms des objets à sélectionner (exemples)** , entrez la connexion ou le rôle serveur à ajouter à ce rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="249d1-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="249d1-139">Vous pouvez également cliquer sur **Parcourir…** et sélectionner l’ensemble ou certains des objets disponibles dans la boîte de dialogue **Rechercher des objets**.</span><span class="sxs-lookup"><span data-stu-id="249d1-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="249d1-140">Cliquez sur **OK** pour revenir à la boîte de dialogue **Propriétés du rôle de serveur-**_server_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="249d1-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="249d1-141">Pour ajouter un membre à un rôle de base de données défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="249d1-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="249d1-142">Dans l'Explorateur d'objets, développez le serveur sur lequel vous souhaitez modifier un rôle de base de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="249d1-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="249d1-143">Développez le dossier **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="249d1-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="249d1-144">Développez la base de données dans laquelle vous souhaitez modifier un rôle de base de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="249d1-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="249d1-145">Développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="249d1-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="249d1-146">Développez le dossier **Rôles** .</span><span class="sxs-lookup"><span data-stu-id="249d1-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="249d1-147">Développez le dossier **Rôles serveur** .</span><span class="sxs-lookup"><span data-stu-id="249d1-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="249d1-148">Cliquez avec le bouton droit sur le rôle à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="249d1-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="249d1-149">Dans la boîte **de dialogue Propriétés du rôle de base de données-**_database_role_name_ , dans la page **général** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="249d1-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="249d1-150">Dans la boîte de dialogue **Sélectionner l’utilisateur ou le rôle de la base de données** , sous **Entrez les noms des objets à sélectionner (exemples)** , entrez la connexion ou le rôle de base de données à ajouter à ce rôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="249d1-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="249d1-151">Vous pouvez également cliquer sur **Parcourir…** et sélectionner l’ensemble ou certains des objets disponibles dans la boîte de dialogue **Rechercher des objets**.</span><span class="sxs-lookup"><span data-stu-id="249d1-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="249d1-152">Cliquez sur **OK** pour revenir à la boîte **de dialogue Propriétés du rôle de base de données-**_database_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="249d1-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="249d1-153">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="249d1-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="249d1-154">Pour ajouter un membre à un rôle serveur fixe</span><span class="sxs-lookup"><span data-stu-id="249d1-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="249d1-155">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="249d1-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="249d1-156">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="249d1-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="249d1-157">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="249d1-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="249d1-158">Pour plus d’informations, consultez [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="249d1-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="249d1-159">Pour ajouter un membre à un rôle de base de données défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="249d1-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="249d1-160">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="249d1-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="249d1-161">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="249d1-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="249d1-162">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="249d1-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="249d1-163">Pour plus d’informations, consultez [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="249d1-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249d1-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="249d1-164">See Also</span></span>  
 <span data-ttu-id="249d1-165">[Rôles de niveau serveur](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="249d1-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="249d1-166">[Rôles au niveau de la base de données](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="249d1-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="249d1-167">Rôles d’application</span><span class="sxs-lookup"><span data-stu-id="249d1-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
