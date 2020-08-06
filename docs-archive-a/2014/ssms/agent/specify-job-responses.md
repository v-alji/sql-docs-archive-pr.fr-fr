---
title: Spécifier des réponses à un travail| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695255"
---
# <a name="specify-job-responses"></a><span data-ttu-id="85d2d-102">Spécifier des réponses à un travail</span><span class="sxs-lookup"><span data-stu-id="85d2d-102">Specify Job Responses</span></span>
  <span data-ttu-id="85d2d-103">Les réponses à un travail spécifient les actions que le service Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] réalisera après l'achèvement d'un travail.</span><span class="sxs-lookup"><span data-stu-id="85d2d-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="85d2d-104">Les réponses à un travail garantissent que les administrateurs de base de données ont connaissance de l'achèvement des travaux et de leur fréquence d'exécution.</span><span class="sxs-lookup"><span data-stu-id="85d2d-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="85d2d-105">Les réponses classiques à un travail peuvent être :</span><span class="sxs-lookup"><span data-stu-id="85d2d-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="85d2d-106">Une notification de l’opérateur, à l’aide de l’e-mail, de la radiomessagerie ou d’un message **net send** .</span><span class="sxs-lookup"><span data-stu-id="85d2d-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="85d2d-107">Utilisez une de ces réponses à un travail si l'opérateur doit exécuter une action en conséquence.</span><span class="sxs-lookup"><span data-stu-id="85d2d-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="85d2d-108">Par exemple, si un travail de sauvegarde se termine avec succès, l'opérateur doit être averti afin qu'il enlève la bande de sauvegarde et qu'il la mette en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="85d2d-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="85d2d-109">L'écriture d'un message d'événement dans le journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="85d2d-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="85d2d-110">Vous pouvez choisir d'utiliser cette réponse uniquement en cas d'échec des travaux.</span><span class="sxs-lookup"><span data-stu-id="85d2d-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="85d2d-111">La suppression automatique du travail.</span><span class="sxs-lookup"><span data-stu-id="85d2d-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="85d2d-112">Utilisez cette réponse à un travail si vous êtes certain de ne plus avoir besoin d'exécuter ce travail à nouveau.</span><span class="sxs-lookup"><span data-stu-id="85d2d-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="85d2d-113">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="85d2d-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85d2d-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="85d2d-114">**Description**</span></span>|<span data-ttu-id="85d2d-115">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="85d2d-115">**Topic**</span></span>|  
|<span data-ttu-id="85d2d-116">Explique comment avertir un opérateur de l'état d'un travail.</span><span class="sxs-lookup"><span data-stu-id="85d2d-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="85d2d-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="85d2d-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="85d2d-118">Explique comment écrire l'état du travail dans le journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="85d2d-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="85d2d-119">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="85d2d-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="85d2d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85d2d-120">See Also</span></span>  
 [<span data-ttu-id="85d2d-121">Surveiller et répondre aux événements</span><span class="sxs-lookup"><span data-stu-id="85d2d-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
