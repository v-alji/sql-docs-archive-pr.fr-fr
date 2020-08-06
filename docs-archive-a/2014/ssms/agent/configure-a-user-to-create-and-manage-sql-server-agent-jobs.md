---
title: Configurer un utilisateur de manière à créer et à gérer des travaux de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614328"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="bb655-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="bb655-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="bb655-103">Cette rubrique explique comment configurer un utilisateur pour créer ou exécuter des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent.</span><span class="sxs-lookup"><span data-stu-id="bb655-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="bb655-104">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="bb655-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="bb655-105">**Pour configurer un utilisateur afin qu'il puisse créer et gérer des travaux de SQL Server Agent à l'aide de :**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="bb655-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb655-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bb655-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bb655-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bb655-107">Security</span></span>  
 <span data-ttu-id="bb655-108">Pour configurer un utilisateur pour créer ou exécuter [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des travaux de l’agent, vous devez d’abord ajouter un rôle de connexion SQL Server ou msdb existant à l’un des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rôles de base de données fixes de l’agent suivants dans la base de données msdb : SQLAgentUserRole, SQLAgentReaderRole ou SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="bb655-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="bb655-109">Par défaut, les membres de ces rôles de base de données peuvent créer leurs propres étapes de travail qui s'exécutent de façon autonome.</span><span class="sxs-lookup"><span data-stu-id="bb655-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="bb655-110">Si ces utilisateurs non-administrateurs souhaitent exécuter des travaux qui lancent d'autres types d'étapes de travail (par exemple, des packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), ils doivent disposer d'un accès à un compte proxy.</span><span class="sxs-lookup"><span data-stu-id="bb655-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="bb655-111">Tous les membres du rôle de serveur fixe sysadmin sont habilités à créer, à modifier et à supprimer des comptes proxy.</span><span class="sxs-lookup"><span data-stu-id="bb655-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="bb655-112">Pour plus d’informations sur les autorisations associées à ces rôles de base de données fixes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consultez [Rôles de base de données fixes de SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bb655-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bb655-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bb655-113">Permissions</span></span>  
 <span data-ttu-id="bb655-114">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="bb655-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="bb655-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb655-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="bb655-116">**Pour ajouter une connexion SQL ou un rôle msdb à un rôle de base de données fixe de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="bb655-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="bb655-117">Dans l' **Explorateur d'objets**, développez un serveur.</span><span class="sxs-lookup"><span data-stu-id="bb655-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="bb655-118">Développez **Sécurité**puis **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="bb655-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="bb655-119">Cliquez avec le bouton droit sur la connexion à ajouter au rôle de base de données fixe de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bb655-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="bb655-120">Dans la page mappage de l' **utilisateur** de la boîte de dialogue Propriétés de la **connexion** , sélectionnez la ligne contenant `msdb` .</span><span class="sxs-lookup"><span data-stu-id="bb655-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="bb655-121">Sous **Appartenance au rôle de base de données : msdb**, cochez le rôle de base de données fixe de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] approprié.</span><span class="sxs-lookup"><span data-stu-id="bb655-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="bb655-122">**Pour configurer un compte proxy de manière à créer et à gérer des étapes de travail de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="bb655-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="bb655-123">Dans l' **Explorateur d'objets**, développez un serveur.</span><span class="sxs-lookup"><span data-stu-id="bb655-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="bb655-124">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bb655-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="bb655-125">Cliquez avec le bouton droit de la souris sur **Proxies** , puis sélectionnez **Nouveau proxy**.</span><span class="sxs-lookup"><span data-stu-id="bb655-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="bb655-126">Dans la page **Général** de la boîte de dialogue **Nouveau compte de proxy** , indiquez le nom de proxy, le nom d'identification et la description du nouveau proxy.</span><span class="sxs-lookup"><span data-stu-id="bb655-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="bb655-127">Notez que vous devez créer une information d'identification avant de créer un proxy de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="bb655-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="bb655-128">Pour plus d’informations sur la création d’informations d’identification, consultez [créer des informations d'](../../relational-databases/security/authentication-access/create-a-credential.md) identification et [créer des informations d’identification &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb655-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="bb655-129">Activez les sous-systèmes appropriés pour ce proxy.</span><span class="sxs-lookup"><span data-stu-id="bb655-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="bb655-130">Sur la page **Principaux** , ajoutez ou supprimez des connexions ou des rôles pour accorder ou refuser un accès au compte proxy.</span><span class="sxs-lookup"><span data-stu-id="bb655-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb655-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb655-131">See Also</span></span>  
 [<span data-ttu-id="bb655-132">Implémenter la sécurité de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb655-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
