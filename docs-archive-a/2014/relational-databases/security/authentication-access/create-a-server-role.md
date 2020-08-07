---
title: Créer un rôle serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612739"
---
# <a name="create-a-server-role"></a><span data-ttu-id="84ea6-102">Créer un rôle serveur</span><span class="sxs-lookup"><span data-stu-id="84ea6-102">Create a Server Role</span></span>
  <span data-ttu-id="84ea6-103">Cette rubrique explique comment créer un rôle de serveur dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84ea6-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="84ea6-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="84ea6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="84ea6-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="84ea6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="84ea6-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="84ea6-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="84ea6-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="84ea6-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="84ea6-108">**Pour créer un nouveau rôle serveur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="84ea6-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="84ea6-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84ea6-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="84ea6-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84ea6-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84ea6-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="84ea6-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="84ea6-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="84ea6-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="84ea6-113">L'autorisation sur les éléments sécurisables au niveau de la base de données ne peut pas être accordée aux rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="84ea6-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="84ea6-114">Pour créer des rôles de base de données, consultez [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84ea6-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84ea6-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="84ea6-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="84ea6-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="84ea6-116">Permissions</span></span>  
  
-   <span data-ttu-id="84ea6-117">Requiert l’autorisation CREATE SERVER ROLE ou l’appartenance au rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="84ea6-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="84ea6-118">Requiert également IMPERSONATE sur *server_principal* pour les connexions, l’autorisation ALTER pour les rôles serveur utilisés comme *server_principal*ou l’appartenance à un groupe Windows utilisé comme server_principal.</span><span class="sxs-lookup"><span data-stu-id="84ea6-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="84ea6-119">Lorsque vous utilisez l'option AUTHORIZATION pour affecter la propriété de rôle de serveur, les autorisations suivantes sont également requises :</span><span class="sxs-lookup"><span data-stu-id="84ea6-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="84ea6-120">Pour affecter la propriété d'un rôle de serveur à un autre compte de connexion, l'autorisation IMPERSONATE est requise pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="84ea6-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="84ea6-121">Pour affecter la propriété d'un rôle de serveur à un autre rôle de serveur, l'appartenance au rôle de serveur destinataire ou l'autorisation ALTER est requise sur ce rôle.</span><span class="sxs-lookup"><span data-stu-id="84ea6-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="84ea6-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="84ea6-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="84ea6-123">Pour créer un rôle serveur</span><span class="sxs-lookup"><span data-stu-id="84ea6-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="84ea6-124">Dans l'Explorateur d'objets, développez le serveur sur lequel vous souhaitez créer le rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="84ea6-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="84ea6-125">Développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="84ea6-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="84ea6-126">Cliquez avec le bouton droit sur le dossier **Rôles de serveur**, puis sélectionnez **Nouveau rôle de serveur...** .</span><span class="sxs-lookup"><span data-stu-id="84ea6-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="84ea6-127">Dans la boîte de dialogue **nouveau rôle serveur-**_server_role_name_ , dans la page **général** , entrez un nom pour le nouveau rôle serveur dans la zone **nom du rôle de serveur** .</span><span class="sxs-lookup"><span data-stu-id="84ea6-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="84ea6-128">Dans la zone **Propriétaire** , entrez le nom du principal de serveur qui détiendra le nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="84ea6-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="84ea6-129">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner la connexion au serveur ou le rôle de serveur**.</span><span class="sxs-lookup"><span data-stu-id="84ea6-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="84ea6-130">Sous **Éléments sécurisables**, sélectionnez un ou plusieurs éléments sécurisables au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="84ea6-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="84ea6-131">Lorsqu'un élément sécurisable est sélectionné, ce rôle de serveur peut se voir accorder ou refuser des autorisations sur cet élément sécurisable.</span><span class="sxs-lookup"><span data-stu-id="84ea6-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="84ea6-132">Dans la zone **Autorisations : explicite**, cochez la case pour accorder, accorder avec transmission des droits, ou refuser une autorisation d’accès à ce rôle serveur pour les éléments sécurisables sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="84ea6-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="84ea6-133">Si une autorisation ne peut pas être accordée ou refusée à tous les éléments sécurisables sélectionnés, l'autorisation est représentée sous forme de sélection partielle.</span><span class="sxs-lookup"><span data-stu-id="84ea6-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="84ea6-134">Dans la page **Membres** , utilisez le bouton **Ajouter** pour ajouter des connexions qui représentent des individus ou des groupes au nouveau rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="84ea6-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="84ea6-135">Un rôle du serveur défini par l'utilisateur peut être membre d'un autre rôle du serveur.</span><span class="sxs-lookup"><span data-stu-id="84ea6-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="84ea6-136">Dans la page **Appartenances** , cochez une case pour rendre le rôle serveur défini par l’utilisateur actuel membre d’un rôle serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="84ea6-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="84ea6-137">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="84ea6-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="84ea6-138">Pour créer un rôle serveur</span><span class="sxs-lookup"><span data-stu-id="84ea6-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="84ea6-139">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84ea6-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="84ea6-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="84ea6-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="84ea6-141">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="84ea6-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="84ea6-142">Pour plus d’informations, consultez [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84ea6-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
