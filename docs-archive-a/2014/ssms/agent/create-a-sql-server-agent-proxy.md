---
title: Créer un proxy de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612069"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="1c34c-102">Create a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="1c34c-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="1c34c-103">Cette rubrique explique comment créer un proxy de SQL Server Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c34c-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1c34c-104">Un compte proxy de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] définit un contexte de sécurité dans lequel une étape de travail peut être exécutée.</span><span class="sxs-lookup"><span data-stu-id="1c34c-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="1c34c-105">Chaque proxy correspond à des informations d'identification de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1c34c-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="1c34c-106">Pour définir des autorisations pour une étape de travail particulière, créez un proxy possédant les autorisations requises pour un sous-système de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puis assignez ce proxy à l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="1c34c-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="1c34c-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="1c34c-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1c34c-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="1c34c-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1c34c-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="1c34c-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1c34c-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1c34c-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1c34c-111">**Pour créer un proxy de SQL Server Agent, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="1c34c-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="1c34c-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c34c-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1c34c-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c34c-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c34c-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1c34c-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1c34c-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="1c34c-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1c34c-116">Vous devez créer des informations d'identification avant de créer un proxy si elles ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="1c34c-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="1c34c-117">Les proxys de l'Agent[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent les informations d'identification pour stocker les informations relatives aux comptes d'utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="1c34c-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="1c34c-118">L'utilisateur spécifié dans l'information d'identification doit être habilité à ouvrir une session en tant que programme de traitement par lots sur l'ordinateur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1c34c-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1c34c-119">vérifie l'accès au sous-système pour un proxy et donne accès au proxy à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="1c34c-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="1c34c-120">Si le proxy n'a plus accès au sous-système, l'étape de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="1c34c-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="1c34c-121">Sinon, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emprunte l'identité de l'utilisateur spécifié dans le proxy et exécute l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="1c34c-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="1c34c-122">La création d'un proxy ne modifie pas les autorisations de l'utilisateur spécifié dans l'information d'identification du proxy.</span><span class="sxs-lookup"><span data-stu-id="1c34c-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="1c34c-123">Par exemple, vous pouvez créer un proxy pour un utilisateur qui n'est pas autorisé à se connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c34c-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1c34c-124">Dans ce cas, les étapes de travail qui utilisent ce proxy ne sont pas en mesure de se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c34c-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1c34c-125">Si la connexion de l'utilisateur a accès au proxy ou que l'utilisateur appartient à un rôle qui y a accès, l'utilisateur peut recourir au proxy dans une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="1c34c-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1c34c-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1c34c-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c34c-127">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1c34c-127">Permissions</span></span>  
  
-   <span data-ttu-id="1c34c-128">Seuls les membres du rôle de serveur fixe **sysadmin** ont l'autorisation de créer, modifier ou supprimer des comptes proxy.</span><span class="sxs-lookup"><span data-stu-id="1c34c-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="1c34c-129">Les utilisateurs qui ne sont pas des membres du rôle serveur fixe **sysadmin** doivent être ajoutés à l'un des rôles de bases de données fixes Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suivants dans la base de données **msdb** pour utiliser des proxys : **SQLAgentUserRole**, **SQLAgentReaderRole**ou **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="1c34c-130">Requiert l'autorisation `ALTER ANY CREDENTIAL` lors de la création des informations d'identification en plus du proxy.</span><span class="sxs-lookup"><span data-stu-id="1c34c-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1c34c-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c34c-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="1c34c-132">Pour créer un proxy de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="1c34c-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="1c34c-133">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un proxy sur SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="1c34c-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="1c34c-134">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1c34c-135">Cliquez avec le bouton droit sur le dossier **Proxys** et sélectionnez **Nouveau proxy**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="1c34c-136">Dans la boîte de dialogue **Nouveau compte proxy** , sur la page **Général** , entrez le nom du compte proxy dans la zone **Nom du proxy** .</span><span class="sxs-lookup"><span data-stu-id="1c34c-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="1c34c-137">Dans la zone **Nom d'identification** , entrez le nom des informations d'identification de sécurité que le compte proxy utilisera.</span><span class="sxs-lookup"><span data-stu-id="1c34c-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="1c34c-138">Dans la zone **Description** , entrez une description du compte proxy</span><span class="sxs-lookup"><span data-stu-id="1c34c-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="1c34c-139">Sous **Actif pour les sous-systèmes suivants**, sélectionnez le ou les sous-systèmes appropriés pour ce proxy.</span><span class="sxs-lookup"><span data-stu-id="1c34c-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="1c34c-140">Sur la page **Principaux** , ajoutez ou supprimez des connexions ou des rôles pour accorder ou refuser un accès au compte proxy.</span><span class="sxs-lookup"><span data-stu-id="1c34c-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="1c34c-141">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1c34c-142">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c34c-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="1c34c-143">Pour créer un proxy de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="1c34c-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="1c34c-144">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c34c-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c34c-145">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c34c-146">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1c34c-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="1c34c-147">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c34c-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1c34c-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c34c-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="1c34c-149">sp_add_proxy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c34c-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="1c34c-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c34c-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
