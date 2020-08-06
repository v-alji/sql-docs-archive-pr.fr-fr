---
title: MSSQL_ENG021075 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612243"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="a31c1-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="a31c1-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a31c1-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="a31c1-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a31c1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a31c1-104">Product Name</span></span>|<span data-ttu-id="a31c1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a31c1-105">SQL Server</span></span>|  
|<span data-ttu-id="a31c1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a31c1-106">Event ID</span></span>|<span data-ttu-id="a31c1-107">21075</span><span class="sxs-lookup"><span data-stu-id="a31c1-107">21075</span></span>|  
|<span data-ttu-id="a31c1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a31c1-108">Event Source</span></span>|<span data-ttu-id="a31c1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a31c1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a31c1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a31c1-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a31c1-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a31c1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a31c1-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a31c1-112">Message Text</span></span>|<span data-ttu-id="a31c1-113">L'instantané initial de la publication '%1!' n'est pas encore disponible.</span><span class="sxs-lookup"><span data-stu-id="a31c1-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a31c1-114">Explication</span><span class="sxs-lookup"><span data-stu-id="a31c1-114">Explanation</span></span>  
 <span data-ttu-id="a31c1-115">L'erreur MSSQL_ENG021075 est signalée si l'Agent de Distribution ou l'Agent de fusion est démarré avant que l'Agent d'instantané ait terminé la génération de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="a31c1-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a31c1-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a31c1-116">User Action</span></span>  
 <span data-ttu-id="a31c1-117">Si l'Agent d'instantané pour la publication n'a pas été démarré depuis que l'abonnement a été créé, ou s'il n'a pas été démarré depuis la dernière fois que vous avez choisi de réinitialiser l'abonnement, démarrez l'Agent d'instantané et laissez-le terminer avant de démarrer l'Agent de distribution ou l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="a31c1-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="a31c1-118">Pour plus d’informations, consultez [Créer et appliquer un instantané](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="a31c1-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="a31c1-119">Si l'Agent d'instantané ne se termine pas, recherchez les erreurs dans son historique et résolvez-les.</span><span class="sxs-lookup"><span data-stu-id="a31c1-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="a31c1-120">Pour obtenir des informations sur l’affichage de l’état de l’agent et des détails de l’erreur dans le moniteur de réplication, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a31c1-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="a31c1-121">Si l'erreur continue de se produire, augmentez le facteur de journalisation de l'agent et spécifiez un fichier de sortie pour le journal.</span><span class="sxs-lookup"><span data-stu-id="a31c1-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="a31c1-122">En fonction du contexte de l'erreur, cette action peut fournir des pistes conduisant à l'erreur et/ou à d'autres messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a31c1-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31c1-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a31c1-123">See Also</span></span>  
 [<span data-ttu-id="a31c1-124">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="a31c1-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
