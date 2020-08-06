---
title: MSSQL_ENG014151 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600806"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="1f72e-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="1f72e-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="1f72e-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="1f72e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f72e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1f72e-104">Product Name</span></span>|<span data-ttu-id="1f72e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f72e-105">SQL Server</span></span>|  
|<span data-ttu-id="1f72e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1f72e-106">Event ID</span></span>|<span data-ttu-id="1f72e-107">14151</span><span class="sxs-lookup"><span data-stu-id="1f72e-107">14151</span></span>|  
|<span data-ttu-id="1f72e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1f72e-108">Event Source</span></span>|<span data-ttu-id="1f72e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1f72e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1f72e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="1f72e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="1f72e-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="1f72e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="1f72e-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1f72e-112">Message Text</span></span>|<span data-ttu-id="1f72e-113">Réplication-%s : échec de l'agent %s.</span><span class="sxs-lookup"><span data-stu-id="1f72e-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="1f72e-114">%s</span><span class="sxs-lookup"><span data-stu-id="1f72e-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1f72e-115">Explication</span><span class="sxs-lookup"><span data-stu-id="1f72e-115">Explanation</span></span>  
 <span data-ttu-id="1f72e-116">Cette erreur est émise pour tout échec d'un Agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="1f72e-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="1f72e-117">Le texte de la fin du message dépend du contexte de l'échec.</span><span class="sxs-lookup"><span data-stu-id="1f72e-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1f72e-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1f72e-118">User Action</span></span>  
 <span data-ttu-id="1f72e-119">Cette erreur peut se produire dans un certain nombre de situations ; utilisez l'une des approches ci-dessous selon le cas :</span><span class="sxs-lookup"><span data-stu-id="1f72e-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="1f72e-120">Redémarrez l'Agent en échec pour voir s'il s'exécutera sans erreur.</span><span class="sxs-lookup"><span data-stu-id="1f72e-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="1f72e-121">Pour plus d’informations, consultez [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) et [Concepts des exécutables de l’agent de réplication](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="1f72e-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="1f72e-122">Vérifiez dans l'historique de l'Agent et des travaux si d'autres erreurs se sont produites vers la même heure.</span><span class="sxs-lookup"><span data-stu-id="1f72e-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="1f72e-123">Pour obtenir des informations sur l’affichage de l’état de l’agent et des détails de l’erreur dans le moniteur de réplication, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="1f72e-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="1f72e-124">Vérifiez que la connectivité de base fonctionne entre les ordinateurs auxquels accède l'Agent, puis connectez-vous à chaque ordinateur avec un utilitaire tel que [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1f72e-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="1f72e-125">Lors de la connexion, utilisez le même compte que celui qu'utilise l'Agent pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="1f72e-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="1f72e-126">Pour plus d'informations sur les autorisations requises pour chaque compte d'Agent, consultez [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="1f72e-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="1f72e-127">Si l'erreur se produit lors de la création ou de l'application d'un instantané, vérifiez si les fichiers du répertoire d'instantané ne comportent pas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="1f72e-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="1f72e-128">Si l'erreur continue de se produire, augmentez le facteur de journalisation de l'agent et spécifiez un fichier de sortie pour le journal.</span><span class="sxs-lookup"><span data-stu-id="1f72e-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="1f72e-129">En fonction du contexte de l'erreur, cette action peut fournir des pistes conduisant à l'erreur et/ou à d'autres messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1f72e-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f72e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f72e-130">See Also</span></span>  
 <span data-ttu-id="1f72e-131">[Administration de l’Agent de réplication](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="1f72e-132">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="1f72e-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="1f72e-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="1f72e-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="1f72e-136">[Agent de lecture de la file d'attente de réplication](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1f72e-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="1f72e-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="1f72e-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
