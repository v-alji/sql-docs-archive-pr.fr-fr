---
title: MSSQL_ENG024070 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697919"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="fb890-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="fb890-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="fb890-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="fb890-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb890-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="fb890-104">Product Name</span></span>|<span data-ttu-id="fb890-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb890-105">SQL Server</span></span>|  
|<span data-ttu-id="fb890-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="fb890-106">Event ID</span></span>|<span data-ttu-id="fb890-107">24070</span><span class="sxs-lookup"><span data-stu-id="fb890-107">24070</span></span>|  
|<span data-ttu-id="fb890-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="fb890-108">Event Source</span></span>|<span data-ttu-id="fb890-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb890-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb890-110">Composant</span><span class="sxs-lookup"><span data-stu-id="fb890-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="fb890-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="fb890-111">Symbolic Name</span></span>||  
|<span data-ttu-id="fb890-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="fb890-112">Message Text</span></span>|<span data-ttu-id="fb890-113">Le client ne dispose pas d'un privilège qui est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="fb890-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb890-114">Explication</span><span class="sxs-lookup"><span data-stu-id="fb890-114">Explanation</span></span>  
 <span data-ttu-id="fb890-115">C'est une erreur générale qui peut être déclenchée qu'une réplication soit utilisée ou non.</span><span class="sxs-lookup"><span data-stu-id="fb890-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="fb890-116">Dans le cas d'un serveur appartenant à une topologie de réplication, l'erreur est généralement déclenchée car le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent est modifié à l'aide du Gestionnaire de contrôle des services [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows et non du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb890-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="fb890-117">Lorsque vous essayez d'exécuter un travail d'agent après avoir modifié le compte de service, le travail peut échouer avec un message d'erreur similaire au message suivant :</span><span class="sxs-lookup"><span data-stu-id="fb890-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="fb890-118">«Exécuté en tant qu’utilisateur : \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="fb890-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="fb890-119">Réplication-sous-système d’instantané de réplication : échec de l’agent \<AgentName> .</span><span class="sxs-lookup"><span data-stu-id="fb890-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="fb890-120">Exécuté en tant qu’utilisateur : \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="fb890-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="fb890-121">Le client ne dispose pas d'un privilège qui est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="fb890-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="fb890-122">L'étape a échoué.</span><span class="sxs-lookup"><span data-stu-id="fb890-122">The step failed.</span></span> <span data-ttu-id="fb890-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="fb890-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="fb890-124">L'étape a échoué. »</span><span class="sxs-lookup"><span data-stu-id="fb890-124">The step failed."</span></span>  
  
 <span data-ttu-id="fb890-125">Ce problème est dû au fait que le Gestionnaire de contrôle des services Windows ne peut pas accorder les autorisations requises au nouveau compte de service pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb890-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb890-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fb890-126">User Action</span></span>  
 <span data-ttu-id="fb890-127">Pour éviter ce problème à l'avenir, utilisez toujours le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à la place du Gestionnaire de contrôle des services Windows pour modifier les comptes de service et les mots de passe.</span><span class="sxs-lookup"><span data-stu-id="fb890-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="fb890-128">Pour résoudre ce problème, à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , rétablissez le compte d'origine.</span><span class="sxs-lookup"><span data-stu-id="fb890-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="fb890-129">Ensuite, à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , passez au nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="fb890-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="fb890-130">Lors de cette opération, le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajoute le nouveau compte au groupe de sécurité suivant :</span><span class="sxs-lookup"><span data-stu-id="fb890-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="fb890-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="fb890-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="fb890-132">En tant que membre de ce groupe de sécurité, le nouveau compte est habilité à exécuter le travail de l'agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="fb890-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb890-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb890-133">See Also</span></span>  
 <span data-ttu-id="fb890-134">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fb890-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="fb890-135">[Gérer les comptes de connexion et les mots de passe dans la réplication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="fb890-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="fb890-136">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb890-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
