---
title: Recycler les journaux d’erreurs de l’Agent SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.recyclesqlagenterrorlogs.f1
ms.assetid: 10bc2dd1-0505-4527-8ec7-d3b4e5d6352b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b30f0a2ba9a2d861d4a36a86489757cde512fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614315"
---
# <a name="recycle-sql-server-agent-error-logs"></a><span data-ttu-id="4aafa-102">Recycler les journaux d'erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="4aafa-102">Recycle SQL Server Agent Error Logs</span></span>
  <span data-ttu-id="4aafa-103">Utilisez cette page pour recycler les journaux d’erreurs de l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent.</span><span class="sxs-lookup"><span data-stu-id="4aafa-103">Use this page to recycle the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Error Logs.</span></span> <span data-ttu-id="4aafa-104">Le recyclage du journal ferme le journal des erreurs actuel de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent et crée un nouveau journal des erreurs sans redémarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4aafa-104">Recycling the log closes the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="4aafa-105">Notez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent conserve les neuf derniers journaux d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="4aafa-105">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs.</span></span> <span data-ttu-id="4aafa-106">S'il y a déjà neuf journaux d'erreurs et que vous recyclez un autre journal d'erreurs, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supprime le journal d'erreurs le plus ancien.</span><span class="sxs-lookup"><span data-stu-id="4aafa-106">If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to remove the oldest error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aafa-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4aafa-107">See Also</span></span>  
 [<span data-ttu-id="4aafa-108">Journal des erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="4aafa-108">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
