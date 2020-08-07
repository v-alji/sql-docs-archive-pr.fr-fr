---
title: Agent XPs (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Agent XPs option
- extended stored procedures [SQL Server], SQL Server Agent
ms.assetid: 2e1c6c64-5ce7-4357-98c7-ac7763a9f9de
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 541c81ea8d9f782a9c1ea391824b90a6fee772d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611303"
---
# <a name="agent-xps-server-configuration-option"></a><span data-ttu-id="99702-102">Agent XPs (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="99702-102">Agent XPs Server Configuration Option</span></span>
  <span data-ttu-id="99702-103">Utilisez l’option **Agent XPs** pour activer les procédures stockées étendues de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="99702-103">Use the **Agent XPs** option to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures on this server.</span></span> <span data-ttu-id="99702-104">Si cette option n'est pas activée, le nœud de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas disponible dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99702-104">When this option is not enabled, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer.</span></span>  
  
 <span data-ttu-id="99702-105">Quand vous utilisez l’outil [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour démarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, ces procédures stockées étendues sont activées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="99702-105">When you use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tool to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, these extended stored procedures are enabled automatically.</span></span> <span data-ttu-id="99702-106">Pour plus d'informations, consultez [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="99702-106">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="99702-107">L’Explorateur d’objets n’affiche pas le contenu du nœud [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent, sauf si ces procédures stockées étendues sont activées, quel que soit l’état du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="99702-107">Object Explorer does not display the contents of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent node unless these extended stored procedures are enabled regardless of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service state.</span></span>  
  
 <span data-ttu-id="99702-108">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="99702-108">The possible values are:</span></span>  
  
-   <span data-ttu-id="99702-109">**0**, qui indique que les procédures stockées étendues de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne sont pas disponibles (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="99702-109">**0**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are not available (the default).</span></span>  
  
-   <span data-ttu-id="99702-110">**1**, qui indique que les procédures stockées étendues de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="99702-110">**1**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are available.</span></span>  
  
 <span data-ttu-id="99702-111">Le paramètre prend effet immédiatement, sans arrêt et redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="99702-111">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="99702-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="99702-112">Examples</span></span>  
 <span data-ttu-id="99702-113">L'exemple suivant active les procédures stockées étendues de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99702-113">The following example enables the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Agent XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="99702-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99702-114">See Also</span></span>  
 <span data-ttu-id="99702-115">[Tâches d’administration automatisée &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="99702-115">[Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="99702-116">Démarrer, arrêter ou suspendre le service SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="99702-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
