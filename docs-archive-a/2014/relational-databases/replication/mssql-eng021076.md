---
title: MSSQL_ENG021076 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697944"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="907b5-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="907b5-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="907b5-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="907b5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="907b5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="907b5-104">Product Name</span></span>|<span data-ttu-id="907b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="907b5-105">SQL Server</span></span>|  
|<span data-ttu-id="907b5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="907b5-106">Event ID</span></span>|<span data-ttu-id="907b5-107">21076</span><span class="sxs-lookup"><span data-stu-id="907b5-107">21076</span></span>|  
|<span data-ttu-id="907b5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="907b5-108">Event Source</span></span>|<span data-ttu-id="907b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="907b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="907b5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="907b5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="907b5-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="907b5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="907b5-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="907b5-112">Message Text</span></span>|<span data-ttu-id="907b5-113">L'instantané initial de l'article '%1!' n'est pas encore disponible.</span><span class="sxs-lookup"><span data-stu-id="907b5-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="907b5-114">Explication</span><span class="sxs-lookup"><span data-stu-id="907b5-114">Explanation</span></span>  
 <span data-ttu-id="907b5-115">L'erreur MSSQL_ENG021076 peut se déclencher si l'Agent de distribution est démarré avant que l'Agent d'instantané ait terminé de générer l'instantané.</span><span class="sxs-lookup"><span data-stu-id="907b5-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="907b5-116">Cette erreur n'est déclenchée que si la publication ne contient qu'un seul article.</span><span class="sxs-lookup"><span data-stu-id="907b5-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="907b5-117">Si la publication contient plus d'un article, c'est l'erreur MSSQL_ENG021075 qui est déclenchée à la place.</span><span class="sxs-lookup"><span data-stu-id="907b5-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="907b5-118">Pour plus d’informations, voir [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="907b5-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="907b5-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="907b5-119">User Action</span></span>  
 <span data-ttu-id="907b5-120">Si l'Agent d'instantané pour la publication n'a pas été démarré depuis la création de l'abonnement, ou depuis la dernière fois que vous avez réinitialisé l'abonnement, démarrez l'Agent d'instantané et laissez-le se terminer avant de démarrer l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="907b5-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="907b5-121">Pour plus d’informations, consultez [Créer et appliquer un instantané](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="907b5-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="907b5-122">Si l'Agent d'instantané ne se termine pas, recherchez les erreurs dans son historique et résolvez-les.</span><span class="sxs-lookup"><span data-stu-id="907b5-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="907b5-123">Pour obtenir des informations sur l’affichage de l’état de l’agent et des détails de l’erreur dans le moniteur de réplication, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="907b5-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="907b5-124">Si l'erreur continue de se produire, augmentez le facteur de journalisation de l'agent et spécifiez un fichier de sortie pour le journal.</span><span class="sxs-lookup"><span data-stu-id="907b5-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="907b5-125">En fonction du contexte de l'erreur, cette action peut fournir des pistes conduisant à l'erreur et/ou à d'autres messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="907b5-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907b5-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="907b5-126">See Also</span></span>  
 [<span data-ttu-id="907b5-127">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="907b5-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
