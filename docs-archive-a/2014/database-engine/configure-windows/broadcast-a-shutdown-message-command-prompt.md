---
title: Diffuser un message d’arrêt (invite de commandes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701880"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="492ba-102">Diffuser un message d'arrêt (invite de commandes)</span><span class="sxs-lookup"><span data-stu-id="492ba-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="492ba-103">Cette rubrique décrit comment diffuser un message d’arrêt dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de la commande **net send** .</span><span class="sxs-lookup"><span data-stu-id="492ba-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="492ba-104">Dans ce message, incluez l'heure d'arrêt de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour permettre aux utilisateurs de terminer leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="492ba-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="492ba-105">Pour diffuser un message d'arrêt</span><span class="sxs-lookup"><span data-stu-id="492ba-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="492ba-106">À partir d'une invite de commandes, entrez :</span><span class="sxs-lookup"><span data-stu-id="492ba-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="492ba-107">**net send /users "message"**</span><span class="sxs-lookup"><span data-stu-id="492ba-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="492ba-108">L’option **/users** spécifie que le message doit être envoyé à tous les utilisateurs connectés au serveur.</span><span class="sxs-lookup"><span data-stu-id="492ba-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="492ba-109">Pour que la commande **net send** fonctionne, le service Affichage des messages doit être exécuté sur l’ordinateur émetteur et sur les ordinateurs récepteurs.</span><span class="sxs-lookup"><span data-stu-id="492ba-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="492ba-110">Le service Affichage des messages est désactivé par défaut dans Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="492ba-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="492ba-111">Pour plus d’informations sur **net send**, consultez la documentation de Windows.</span><span class="sxs-lookup"><span data-stu-id="492ba-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="492ba-112">Sur votre réseau, il peut être préférable de contacter les utilisateurs par courrier électronique ou par téléphone.</span><span class="sxs-lookup"><span data-stu-id="492ba-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="492ba-113">Pour savoir quels sont les utilisateurs actuellement connectés à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], utilisez le Moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="492ba-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="492ba-114">Pour plus d’informations sur le moniteur d’activité, consultez [Moniteur d’activité](../../relational-databases/performance-monitor/activity-monitor.md) et [Ouvrir le Moniteur d’activité &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="492ba-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492ba-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="492ba-115">See Also</span></span>  
 [<span data-ttu-id="492ba-116">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="492ba-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
