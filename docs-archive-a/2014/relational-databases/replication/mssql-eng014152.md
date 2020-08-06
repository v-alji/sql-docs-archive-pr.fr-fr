---
title: MSSQL_ENG014152 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603949"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="f6523-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="f6523-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f6523-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="f6523-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6523-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f6523-104">Product Name</span></span>|<span data-ttu-id="f6523-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6523-105">SQL Server</span></span>|  
|<span data-ttu-id="f6523-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f6523-106">Event ID</span></span>|<span data-ttu-id="f6523-107">14152</span><span class="sxs-lookup"><span data-stu-id="f6523-107">14152</span></span>|  
|<span data-ttu-id="f6523-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f6523-108">Event Source</span></span>|<span data-ttu-id="f6523-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f6523-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f6523-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f6523-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f6523-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f6523-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f6523-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f6523-112">Message Text</span></span>|<span data-ttu-id="f6523-113">Réplication-%s : agent %s programmé pour réessayer.</span><span class="sxs-lookup"><span data-stu-id="f6523-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="f6523-114">%s</span><span class="sxs-lookup"><span data-stu-id="f6523-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6523-115">Explication</span><span class="sxs-lookup"><span data-stu-id="f6523-115">Explanation</span></span>  
 <span data-ttu-id="f6523-116">L'agent de réplication spécifié a été programmé pour retenter l'opération demandée.</span><span class="sxs-lookup"><span data-stu-id="f6523-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="f6523-117">Le processus continue à réessayer jusqu'à ce qu'il atteigne le nombre maximal de tentatives de reprise configuré pour l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="f6523-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="f6523-118">Une nouvelle tentative est effectuée généralement pour l'une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6523-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="f6523-119">La valeur **QueryTimeout** est dépassée.</span><span class="sxs-lookup"><span data-stu-id="f6523-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="f6523-120">La valeur **LoginTimeout** est dépassée.</span><span class="sxs-lookup"><span data-stu-id="f6523-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="f6523-121">Le processus de réplication a été choisi comme victime du blocage.</span><span class="sxs-lookup"><span data-stu-id="f6523-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6523-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f6523-122">User Action</span></span>  
 <span data-ttu-id="f6523-123">Si ce message est occasionnel, aucune action de l'utilisateur n'est requise.</span><span class="sxs-lookup"><span data-stu-id="f6523-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="f6523-124">Utilisez [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) pour afficher le paramétrage actuel du nombre maximal de tentatives défini pour l'étape **Exécution de l'Agent** pour l'agent de réplication spécifié.</span><span class="sxs-lookup"><span data-stu-id="f6523-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="f6523-125">Vous pouvez utiliser le **@retry_attempts** paramètre de la procédure stockée [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) pour ajuster le nombre de tentatives d’exécution d’une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="f6523-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="f6523-126">Si ce message est récurrent, résolvez le problème en fonction du message qui est à l'origine de la nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="f6523-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="f6523-127">Vérifiez si l'historique de l'agent contient des messages indiquant pourquoi la reprise a dû être planifiée.</span><span class="sxs-lookup"><span data-stu-id="f6523-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="f6523-128">Dans certains cas, vous devrez peut-être activer une journalisation plus détaillée pour votre agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="f6523-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="f6523-129">Pour plus d'informations sur la configuration de la journalisation pour la réplication, consultez l'article [312292](https://support.microsoft.com/kb/312292)de la Base de connaissances Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6523-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6523-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6523-130">See Also</span></span>  
 [<span data-ttu-id="f6523-131">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="f6523-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
