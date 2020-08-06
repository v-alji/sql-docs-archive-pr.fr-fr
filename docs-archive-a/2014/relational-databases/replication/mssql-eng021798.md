---
title: MSSQL_ENG021798 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697925"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="92b27-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="92b27-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="92b27-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="92b27-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92b27-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="92b27-104">Product Name</span></span>|<span data-ttu-id="92b27-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="92b27-105">SQL Server</span></span>|  
|<span data-ttu-id="92b27-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="92b27-106">Event ID</span></span>|<span data-ttu-id="92b27-107">21798</span><span class="sxs-lookup"><span data-stu-id="92b27-107">21798</span></span>|  
|<span data-ttu-id="92b27-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="92b27-108">Event Source</span></span>|<span data-ttu-id="92b27-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="92b27-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="92b27-110">Composant</span><span class="sxs-lookup"><span data-stu-id="92b27-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="92b27-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="92b27-111">Symbolic Name</span></span>||  
|<span data-ttu-id="92b27-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="92b27-112">Message Text</span></span>|<span data-ttu-id="92b27-113">Le travail de l'Agent « %1!s! » doit être ajouté à l'aide de « %2!s! » avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="92b27-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="92b27-114">Consultez la documentation de '%s'.</span><span class="sxs-lookup"><span data-stu-id="92b27-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92b27-115">Explication</span><span class="sxs-lookup"><span data-stu-id="92b27-115">Explanation</span></span>  
 <span data-ttu-id="92b27-116">Pour créer une publication, vous devez être membre du rôle de serveur fixe **sysadmin** sur le serveur de publication, ou membre du rôle de base de données fixe **db_owner** dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="92b27-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="92b27-117">Si vous êtes membre du rôle **db_owner** , cette erreur est émise si :</span><span class="sxs-lookup"><span data-stu-id="92b27-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="92b27-118">Vous exécutez des scripts à partir de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92b27-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="92b27-119">Le modèle de sécurité a changé dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]et ces scripts doivent être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="92b27-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="92b27-120">La procédure stockée **sp_addpublication** est exécutée avant l’exécution de [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92b27-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="92b27-121">Ceci s'applique à toutes les publications transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="92b27-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="92b27-122">La procédure stockée **sp_addpublication** est exécutée avant l’exécution de [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92b27-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="92b27-123">Cela s’applique aux publications transactionnelles qui sont activées pour les abonnements de mise à jour en attente (valeur TRUE pour le **@allow_queued_tran** paramètre de **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="92b27-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="92b27-124">Les procédures stockées **sp_addlogreader_agent** et **sp_addqreader_agent** créent chacune un travail d'Agent et vous permettent de spécifier le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sous lequel l'Agent s'exécute.</span><span class="sxs-lookup"><span data-stu-id="92b27-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="92b27-125">Pour les utilisateurs membres du rôle **sysadmin** , les travaux d'Agents sont créés implicitement si **sp_addlogreader_agent** et **sp_addqreader_agent** ne sont pas exécutées ; les Agents s'exécutent dans le contexte du compte de service de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="92b27-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="92b27-126">Bien que **sp_addlogreader_agent** et **sp_addqreader_agent** ne soient pas nécessaires pour les utilisateurs membres du rôle **sysadmin** , il est recommandé par mesure de sécurité de spécifier un compte distinct pour les Agents.</span><span class="sxs-lookup"><span data-stu-id="92b27-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="92b27-127">Pour plus d’informations, voir [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="92b27-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92b27-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="92b27-128">User Action</span></span>  
 <span data-ttu-id="92b27-129">Veillez à exécuter les procédures dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="92b27-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="92b27-130">Pour plus d’informations, consultez [créer une publication](publish/create-a-publication.md), mettre à jour ces scripts pour inclure les procédures stockées et les paramètres requis par [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="92b27-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="92b27-131">Pour plus d’informations, consultez [Mettre à niveau les scripts de réplication &#40;programmation Transact-SQL de la réplication&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="92b27-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b27-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92b27-132">See Also</span></span>  
 [<span data-ttu-id="92b27-133">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="92b27-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
