---
title: MSSQL_ENG021797 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697931"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="40c44-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="40c44-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="40c44-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="40c44-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40c44-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="40c44-104">Product Name</span></span>|<span data-ttu-id="40c44-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="40c44-105">SQL Server</span></span>|  
|<span data-ttu-id="40c44-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="40c44-106">Event ID</span></span>|<span data-ttu-id="40c44-107">21797</span><span class="sxs-lookup"><span data-stu-id="40c44-107">21797</span></span>|  
|<span data-ttu-id="40c44-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="40c44-108">Event Source</span></span>|<span data-ttu-id="40c44-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="40c44-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="40c44-110">Composant</span><span class="sxs-lookup"><span data-stu-id="40c44-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="40c44-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="40c44-111">Symbolic Name</span></span>||  
|<span data-ttu-id="40c44-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="40c44-112">Message Text</span></span>|<span data-ttu-id="40c44-113">'%s' doit être une connexion Windows valide sous la forme : 'MACHINE\Connexion' ou 'DOMAIN\Connexion'.</span><span class="sxs-lookup"><span data-stu-id="40c44-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="40c44-114">Consultez la documentation de '%s'.</span><span class="sxs-lookup"><span data-stu-id="40c44-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="40c44-115">Explication</span><span class="sxs-lookup"><span data-stu-id="40c44-115">Explanation</span></span>  
 <span data-ttu-id="40c44-116">Cette erreur est générée par les procédures stockées de réplication suivantes si la valeur spécifiée pour le **@job_login** paramètre est null ou non valide.</span><span class="sxs-lookup"><span data-stu-id="40c44-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="40c44-117">Cette erreur peut se produire si un membre du rôle de base de données fixe **db_owner** exécute des scripts à partir d'anciennes versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40c44-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="40c44-118">Le modèle de sécurité a changé dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]et ces scripts doivent être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="40c44-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="40c44-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="40c44-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="40c44-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="40c44-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="40c44-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="40c44-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="40c44-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="40c44-126">Ces procédures stockées peuvent être exécutées par un membre du rôle de serveur fixe **sysadmin** sur le serveur approprié, ou par un membre du rôle de base de données fixe **db_owner** dans la base de données appropriée.</span><span class="sxs-lookup"><span data-stu-id="40c44-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="40c44-127">Les procédures stockées créent chacune un travail d'Agent et vous permettent de spécifier le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] sous lequel l'Agent s'exécute.</span><span class="sxs-lookup"><span data-stu-id="40c44-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="40c44-128">Pour les utilisateurs membres du rôle **sysadmin** , les travaux d'Agent sont créés implicitement même si aucun compte Windows n'est spécifié (si un compte est spécifié, il doit être valide) ; les Agents s'exécutent dans le contexte du compte du service de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sur le serveur approprié.</span><span class="sxs-lookup"><span data-stu-id="40c44-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="40c44-129">Bien que ce compte ne soit pas nécessaire, il est recommandé de spécifier un compte distinct pour les Agents.</span><span class="sxs-lookup"><span data-stu-id="40c44-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="40c44-130">Pour plus d’informations, voir [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="40c44-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40c44-131">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="40c44-131">User Action</span></span>  
 <span data-ttu-id="40c44-132">Veillez à spécifier un compte Windows valide pour le **@job_login** paramètre de chaque procédure.</span><span class="sxs-lookup"><span data-stu-id="40c44-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="40c44-133">Si vous avez des scritps de réplication provenant de versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mettez-les à jour pour qu'ils incluent les procédures stockées et les paramètres requis par [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40c44-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="40c44-134">Pour plus d’informations, consultez [Mettre à niveau les scripts de réplication &#40;programmation Transact-SQL de la réplication&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="40c44-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c44-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40c44-135">See Also</span></span>  
 [<span data-ttu-id="40c44-136">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="40c44-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
