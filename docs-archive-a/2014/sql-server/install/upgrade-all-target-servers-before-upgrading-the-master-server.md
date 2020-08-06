---
title: Mettre à niveau tous les serveurs cibles avant de mettre à niveau le serveur maître | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601268"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="17804-102">Mettre à niveau tous les serveurs cibles avant de mettre à niveau le serveur maître</span><span class="sxs-lookup"><span data-stu-id="17804-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="17804-103">Avant de mettre à niveau le serveur maître, mettez à niveau tous les ordinateurs exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et configurés comme serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="17804-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="17804-104">Composant</span><span class="sxs-lookup"><span data-stu-id="17804-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="17804-105">Agent</span><span class="sxs-lookup"><span data-stu-id="17804-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="17804-106">Description</span><span class="sxs-lookup"><span data-stu-id="17804-106">Description</span></span>  
 <span data-ttu-id="17804-107">Pour automatiser l'administration dans des environnements multiserveurs, vous devez disposer, au minimum, d'un serveur maître et d'un serveur cible.</span><span class="sxs-lookup"><span data-stu-id="17804-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="17804-108">Un serveur maître distribue les travaux aux serveurs cibles et reçoit les événements de ces derniers.</span><span class="sxs-lookup"><span data-stu-id="17804-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="17804-109">Un serveur maître stocke également la copie centrale des définitions de travaux pour les travaux exécutés sur des serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="17804-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="17804-110">Si le serveur actif est configuré en tant que serveur maître, mettez à niveau tous les serveurs cibles avant de mettre à niveau le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="17804-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="17804-111">Action corrective</span><span class="sxs-lookup"><span data-stu-id="17804-111">Corrective Action</span></span>  
 <span data-ttu-id="17804-112">Si vous ne pouvez pas mettre à niveau tous les serveurs cibles avant de mettre à niveau le serveur maître, vous devez désinscrire tous les serveurs cibles et les réinscrire après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="17804-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="17804-113">Pour plus d'informations, consultez les rubriques « Automatisation de l'administration à l'échelle d'une entreprise », « Procédure : désinscrire un serveur cible d'un serveur maître » et « Procédure : inscrire un serveur cible sur un serveur maître » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17804-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17804-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17804-114">See Also</span></span>  
 <span data-ttu-id="17804-115">[Problèmes de mise à niveau SQL Server Agent](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="17804-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="17804-116">Problèmes de mise à niveau de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="17804-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
