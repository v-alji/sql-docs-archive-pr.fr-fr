---
title: MSSQL_ENG020557 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614547"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="7e5aa-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="7e5aa-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7e5aa-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="7e5aa-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e5aa-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7e5aa-104">Product Name</span></span>|<span data-ttu-id="7e5aa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e5aa-105">SQL Server</span></span>|  
|<span data-ttu-id="7e5aa-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7e5aa-106">Event ID</span></span>|<span data-ttu-id="7e5aa-107">20557</span><span class="sxs-lookup"><span data-stu-id="7e5aa-107">20557</span></span>|  
|<span data-ttu-id="7e5aa-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7e5aa-108">Event Source</span></span>|<span data-ttu-id="7e5aa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7e5aa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7e5aa-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7e5aa-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7e5aa-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7e5aa-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7e5aa-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7e5aa-112">Message Text</span></span>|<span data-ttu-id="7e5aa-113">Arrêt de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-113">Agent shutdown.</span></span> <span data-ttu-id="7e5aa-114">Pour plus d'informations, reportez-vous à l'historique des travaux de l'Agent SQL Server pour le travail « %s ».</span><span class="sxs-lookup"><span data-stu-id="7e5aa-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e5aa-115">Explication</span><span class="sxs-lookup"><span data-stu-id="7e5aa-115">Explanation</span></span>  
 <span data-ttu-id="7e5aa-116">Un agent de réplication a été arrêté sans qu'aucune explication n'ait été écrite dans la table d'historique appropriée ou l'agent a été arrêté au milieu d'un processus.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e5aa-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7e5aa-117">User Action</span></span>  
  
-   <span data-ttu-id="7e5aa-118">Redémarrez l'Agent pour voir s'il va s'exécuter sans erreur.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="7e5aa-119">Pour plus d’informations, consultez [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) et [Concepts des exécutables de l’agent de réplication](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="7e5aa-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="7e5aa-120">Vérifiez dans l'historique de l'Agent et des travaux si d'autres erreurs se sont produites vers la même heure.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="7e5aa-121">Pour obtenir des informations sur l’affichage de l’état de l’agent et des détails de l’erreur dans le moniteur de réplication, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="7e5aa-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="7e5aa-122">Vérifiez que la connectivité de base fonctionne entre les ordinateurs auxquels l’Agent accède, puis connectez-vous à chaque ordinateur à l’aide d’un utilitaire tel que **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="7e5aa-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="7e5aa-123">Lors de la connexion, utilisez le même compte que celui qu'utilise l'Agent pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="7e5aa-124">Pour plus d'informations sur les autorisations requises pour chaque compte d'agent, consultez [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="7e5aa-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="7e5aa-125">Si l'erreur se produit lors de la création ou de l'application d'un instantané, vérifiez si les fichiers du répertoire d'instantanés comportent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="7e5aa-126">Si l'erreur continue de se produire, augmentez le facteur de journalisation de l'agent et spécifiez un fichier de sortie pour le journal.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="7e5aa-127">En fonction du contexte de l'erreur, cette action peut révéler les étapes qui conduisent à l'erreur et fournir d'autres messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="7e5aa-128">Pour plus d'informations sur la configuration de la journalisation pour la réplication, consultez l'article [312292](https://support.microsoft.com/kb/312292)de la Base de connaissances Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e5aa-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5aa-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e5aa-129">See Also</span></span>  
 [<span data-ttu-id="7e5aa-130">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="7e5aa-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
