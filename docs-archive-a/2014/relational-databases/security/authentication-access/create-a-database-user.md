---
title: Créer un utilisateur de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697763"
---
# <a name="create-a-database-user"></a><span data-ttu-id="8c721-102">Créer un utilisateur de base de données</span><span class="sxs-lookup"><span data-stu-id="8c721-102">Create a Database User</span></span>
  <span data-ttu-id="8c721-103">Cette rubrique indique comment créer un utilisateur de base de données mappé à un compte de connexion dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c721-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8c721-104">L'utilisateur de base de données est l'identité du compte de connexion lorsqu'il est connecté à la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="8c721-105">Il peut utiliser le même nom que celui du compte de connexion, mais cela n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="8c721-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="8c721-106">Cette rubrique part du principe qu'il existe déjà un compte de connexion dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c721-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8c721-107">Pour plus d’informations sur la création d’une connexion, consultez [créer une connexion](create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="8c721-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="8c721-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8c721-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c721-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8c721-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c721-110">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="8c721-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8c721-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c721-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c721-112">**Pour créer un utilisateur de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8c721-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="8c721-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c721-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c721-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c721-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c721-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8c721-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="8c721-116">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="8c721-116">Background</span></span>  
 <span data-ttu-id="8c721-117">Un utilisateur est un principal de sécurité au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-117">A user is a database level security principal.</span></span> <span data-ttu-id="8c721-118">Les comptes de connexion doivent être mappés à un utilisateur de base de données pour permettre la connexion à une base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="8c721-119">Un compte de connexion peut être mappé à différentes bases de données en tant qu'utilisateurs différents, mais il ne peut être mappé que comme utilisateur unique dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="8c721-120">Dans une base de données partiellement autonome, il est possible de créer un utilisateur qui ne dispose pas de compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="8c721-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="8c721-121">Pour plus d’informations sur les utilisateurs de base de données autonome, consultez [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c721-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="8c721-122">Lorsque l'utilisateur invité d'une base de données est activé, un compte de connexion non mappé à un utilisateur de base de données peut accéder à la base de données en tant qu'utilisateur invité.</span><span class="sxs-lookup"><span data-stu-id="8c721-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8c721-123">L'utilisateur invité est habituellement désactivé.</span><span class="sxs-lookup"><span data-stu-id="8c721-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="8c721-124">Ne l'activez que lorsque cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8c721-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="8c721-125">En tant que principal de sécurité, il est possible d'accorder des autorisations à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8c721-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="8c721-126">L'étendue d'un utilisateur est la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-126">The scope of a user is the database.</span></span> <span data-ttu-id="8c721-127">Pour se connecter à une base de données spécifique sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un compte de connexion doit être mappé à un utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="8c721-128">Les autorisations dans la base de données sont accordées et refusées à l'utilisateur de la base de données, pas au compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="8c721-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c721-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c721-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c721-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8c721-130">Permissions</span></span>  
 <span data-ttu-id="8c721-131">Requiert l'autorisation `ALTER ANY USER` sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c721-132">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c721-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="8c721-133">Pour créer un utilisateur de base de données</span><span class="sxs-lookup"><span data-stu-id="8c721-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="8c721-134">Dans l'Explorateur d'objets, développez le dossier **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="8c721-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="8c721-135">Développez la base de données où créer le nouvel utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="8c721-136">Cliquez avec le bouton droit sur le dossier **Sécurité**, pointez sur **Nouveau**, puis sélectionnez **Utilisateur...** .</span><span class="sxs-lookup"><span data-stu-id="8c721-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="8c721-137">Dans la **boîte de dialogue utilisateur de base de données-nouveau** , dans la page **général** , sélectionnez l’un des types d’utilisateur suivants dans la liste **type d’utilisateur** : **utilisateur SQL avec connexion**, **utilisateur SQL sans connexion**, **utilisateur mappé à un certificat**, **utilisateur mappé à une clé asymétrique**ou **utilisateur Windows**.</span><span class="sxs-lookup"><span data-stu-id="8c721-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="8c721-138">Dans la zone **Nom d'utilisateur** , entrez un nom pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c721-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="8c721-139">Si vous avez choisi **Utilisateur Windows** dans la liste **Type d’utilisateur**, vous pouvez également cliquer sur les points de suspension **(...)** pour ouvrir la boîte de dialogue **Sélectionner un utilisateur ou un groupe**.</span><span class="sxs-lookup"><span data-stu-id="8c721-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="8c721-140">Dans la zone **Nom de connexion** , entrez l'identifiant de connexion de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c721-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="8c721-141">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner la connexion**.</span><span class="sxs-lookup"><span data-stu-id="8c721-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="8c721-142">**Nom de connexion** est disponible si vous sélectionnez **Utilisateur SQL avec connexion** ou **Utilisateur Windows** dans la liste **Type d'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="8c721-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="8c721-143">Dans la zone **Schéma par défaut** , spécifie le schéma qui possédera les objets créés par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c721-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="8c721-144">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner le schéma**.</span><span class="sxs-lookup"><span data-stu-id="8c721-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="8c721-145">**Schéma par défaut** est disponible si vous sélectionnez **Utilisateur SQL avec connexion**, **Utilisateur SQL sans connexion**ou **Utilisateur Windows** dans la liste **Type d'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="8c721-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="8c721-146">Dans la zone **Nom du certificat** , entrez le certificat à utiliser pour l'utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="8c721-147">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner le certificat**.</span><span class="sxs-lookup"><span data-stu-id="8c721-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="8c721-148">**Nom du certificat** est disponible si vous sélectionnez **Utilisateur mappé à un certificat** dans la liste **Type d'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="8c721-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="8c721-149">Dans la zone **Nom de la clé asymétrique**  , entrez la clé à utiliser pour l'utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="8c721-150">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner la clé asymétrique**.</span><span class="sxs-lookup"><span data-stu-id="8c721-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="8c721-151">**Nom de la clé asymétrique** est disponible si vous sélectionnez **Utilisateur mappé à une clé asymétrique** dans la liste **Type d'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="8c721-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="8c721-152">Options supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8c721-152">Additional Options</span></span>  
 <span data-ttu-id="8c721-153">La boîte de dialogue **Utilisateur de base de données - Nouveau** offre également des options sur quatre pages supplémentaires : **schémas détenus**, **appartenance**, **éléments sécurisables** et **propriétés étendues**.</span><span class="sxs-lookup"><span data-stu-id="8c721-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="8c721-154">La page **Schémas appartenant à un rôle** répertorie tous les schémas possibles qui peuvent être détenus par le nouvel utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="8c721-155">Pour ajouter des schémas à un utilisateur de base de données ou lui en supprimer, sous **Schémas appartenant à cet utilisateur**, activez ou désactivez les cases à cocher en regard de ces schémas.</span><span class="sxs-lookup"><span data-stu-id="8c721-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="8c721-156">La page **Appartenance** répertorie tous les rôles possibles d'appartenance de base de données qui peuvent être détenus par le nouvel utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="8c721-157">Pour ajouter des rôles à un utilisateur de base de données ou lui en supprimer, sous **Appartenance au rôle de base de données**, activez ou désactivez les cases à cocher en regard de ces rôles.</span><span class="sxs-lookup"><span data-stu-id="8c721-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="8c721-158">La page **Éléments sécurisables** répertorie tous les éléments sécurisables possibles et les autorisations sur ces éléments sécurisables qui peuvent être accordées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="8c721-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="8c721-159">La page **Propriétés étendues** vous permet d'ajouter des propriétés personnalisées aux utilisateurs de base de données.</span><span class="sxs-lookup"><span data-stu-id="8c721-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="8c721-160">Les options supplémentaires suivantes sont disponibles sur cette page.</span><span class="sxs-lookup"><span data-stu-id="8c721-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="8c721-161">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="8c721-161">**Database**</span></span>  
     <span data-ttu-id="8c721-162">Affiche le nom de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8c721-162">Displays the name of the selected database.</span></span> <span data-ttu-id="8c721-163">Ce champ est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="8c721-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="8c721-164">**Classement**</span><span class="sxs-lookup"><span data-stu-id="8c721-164">**Collation**</span></span>  
     <span data-ttu-id="8c721-165">Affiche le classement utilisé pour la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8c721-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="8c721-166">Ce champ est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="8c721-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="8c721-167">**Propriétés**</span><span class="sxs-lookup"><span data-stu-id="8c721-167">**Properties**</span></span>  
     <span data-ttu-id="8c721-168">Affiche ou spécifie les propriétés étendues de l'objet.</span><span class="sxs-lookup"><span data-stu-id="8c721-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="8c721-169">Chaque propriété étendue est constituée d'une paire nom/valeur de métadonnées associées à l'objet.</span><span class="sxs-lookup"><span data-stu-id="8c721-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="8c721-170">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="8c721-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="8c721-171">Cliquez sur les points de suspension **(…)** figurant après **Valeur** pour ouvrir la boîte de dialogue **Valeur de la propriété étendue**.</span><span class="sxs-lookup"><span data-stu-id="8c721-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="8c721-172">Tapez ou affichez la valeur de la propriété étendue dans cet emplacement de plus grande taille.</span><span class="sxs-lookup"><span data-stu-id="8c721-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="8c721-173">Pour plus d'informations, consultez [Boîte de dialogue Valeur de la propriété étendue](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="8c721-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="8c721-174">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="8c721-174">**Delete**</span></span>  
     <span data-ttu-id="8c721-175">Supprime la propriété étendue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8c721-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c721-176">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c721-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="8c721-177">Pour créer un utilisateur de base de données</span><span class="sxs-lookup"><span data-stu-id="8c721-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="8c721-178">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c721-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c721-179">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8c721-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c721-180">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8c721-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="8c721-181">Pour plus d’informations, consultez [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c721-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c721-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c721-182">See Also</span></span>  
 [<span data-ttu-id="8c721-183">Principaux &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8c721-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
