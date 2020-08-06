---
title: blocked process threshold (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705431"
---
# <a name="blocked-process-threshold-server-configuration-option"></a><span data-ttu-id="a73f3-102">blocked process threshold (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="a73f3-102">blocked process threshold Server Configuration Option</span></span>
  <span data-ttu-id="a73f3-103">L'option **blocked process threshold** permet de spécifier le seuil, en secondes, à partir duquel des rapports de processus bloqués sont générés.</span><span class="sxs-lookup"><span data-stu-id="a73f3-103">Use the **blocked process threshold** option to specify the threshold, in seconds, at which blocked process reports are generated.</span></span> <span data-ttu-id="a73f3-104">Le seuil peut être compris entre 0 et 86 400.</span><span class="sxs-lookup"><span data-stu-id="a73f3-104">The threshold can be set from 0 to 86,400.</span></span> <span data-ttu-id="a73f3-105">Par défaut, aucun rapport de processus bloqué n'est généré.</span><span class="sxs-lookup"><span data-stu-id="a73f3-105">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="a73f3-106">Cet événement n'est pas généré pour les tâches système ou les tâches en attente de ressources qui ne génèrent pas de blocages détectables.</span><span class="sxs-lookup"><span data-stu-id="a73f3-106">This event is not generated for system tasks or for tasks that are waiting on resources that do not generate detectable deadlocks.</span></span>  
  
 <span data-ttu-id="a73f3-107">Vous pouvez définir une [alerte](../../ssms/agent/alerts.md) à exécuter dès lorsque cet événement est généré.</span><span class="sxs-lookup"><span data-stu-id="a73f3-107">You can define an [alert](../../ssms/agent/alerts.md) to be executed when this event is generated.</span></span> <span data-ttu-id="a73f3-108">Ainsi, par exemple, vous pouvez choisir de contacter l'administrateur par récepteur de radiomessagerie afin de l'inviter à gérer la situation de blocage de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="a73f3-108">So for example, you can choose to page the administrator to take appropriate action to handle the blocking situation.</span></span>  
  
 <span data-ttu-id="a73f3-109">L'option « blocked process threshold » utilise le thread d'arrière-plan Moniteur de blocage pour parcourir la liste des tâches en attente depuis une durée supérieure ou multiple du seuil configuré.</span><span class="sxs-lookup"><span data-stu-id="a73f3-109">Blocked process threshold uses the deadlock monitor background thread to walk through the list of tasks waiting for a time greater than or multiples of the configured threshold.</span></span> <span data-ttu-id="a73f3-110">L'événement est généré une fois par intervalle de génération de rapports pour chaque tâche bloquée.</span><span class="sxs-lookup"><span data-stu-id="a73f3-110">The event is generated once per reporting interval for each of the blocked tasks.</span></span>  
  
 <span data-ttu-id="a73f3-111">Les rapports de processus bloqués sont générés le plus tôt possible.</span><span class="sxs-lookup"><span data-stu-id="a73f3-111">The blocked process report is done on a best effort basis.</span></span> <span data-ttu-id="a73f3-112">Toutefois, rien ne garantit qu'ils seront générés en temps réel ou quasiment en temps réel.</span><span class="sxs-lookup"><span data-stu-id="a73f3-112">There is no guarantee of any real-time or even close to real-time reporting.</span></span>  
  
 <span data-ttu-id="a73f3-113">Le paramètre prend effet immédiatement, sans arrêt et redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="a73f3-113">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a73f3-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="a73f3-114">Examples</span></span>  
 <span data-ttu-id="a73f3-115">Dans l'exemple suivant, l'option `blocked process threshold` est définie à `20` secondes, générant ainsi un rapport de processus bloqué pour chaque tâche bloquée.</span><span class="sxs-lookup"><span data-stu-id="a73f3-115">The following example sets the `blocked process threshold` to `20` seconds, generating a blocked process report for each task that is blocked.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a73f3-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a73f3-116">See Also</span></span>  
 <span data-ttu-id="a73f3-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a73f3-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="a73f3-118">Blocked Process Report, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="a73f3-118">Blocked Process Report Event Class</span></span>](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
