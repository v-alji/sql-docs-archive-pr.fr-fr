---
title: Propriétés de SQL Server Agent (page Historique) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613261"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="cfc53-102">Propriétés de l'Agent SQL Server (page Historique)</span><span class="sxs-lookup"><span data-stu-id="cfc53-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="cfc53-103">Utilisez cette page pour afficher et modifier les paramètres de gestion du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Journal d’historique des services de l’agent.</span><span class="sxs-lookup"><span data-stu-id="cfc53-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cfc53-104">Options</span><span class="sxs-lookup"><span data-stu-id="cfc53-104">Options</span></span>  
 <span data-ttu-id="cfc53-105">**Limiter la taille du journal d'historique des travaux.**</span><span class="sxs-lookup"><span data-stu-id="cfc53-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="cfc53-106">Limite la quantité d'informations d'historique des travaux que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve dans le journal.</span><span class="sxs-lookup"><span data-stu-id="cfc53-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="cfc53-107">**Taille maximale du journal d'historique des travaux (lignes)**</span><span class="sxs-lookup"><span data-stu-id="cfc53-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="cfc53-108">Spécifie le nombre maximal de lignes que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve.</span><span class="sxs-lookup"><span data-stu-id="cfc53-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="cfc53-109">Lorsque le journal a atteint le nombre de lignes indiqué, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supprime les lignes les plus anciennes à mesure que de nouvelles lignes sont insérées.</span><span class="sxs-lookup"><span data-stu-id="cfc53-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="cfc53-110">**Nombre  maximal de lignes d'historique des travaux par travail**</span><span class="sxs-lookup"><span data-stu-id="cfc53-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="cfc53-111">Spécifie le nombre maximal de lignes que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve par travail.</span><span class="sxs-lookup"><span data-stu-id="cfc53-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="cfc53-112">Lorsque l'historique d'un travail particulier a atteint le nombre de lignes indiqué, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supprime les lignes les plus anciennes à mesure que de nouvelles lignes sont insérées.</span><span class="sxs-lookup"><span data-stu-id="cfc53-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="cfc53-113">**Supprimer l'historique de l'agent**</span><span class="sxs-lookup"><span data-stu-id="cfc53-113">**Remove agent history**</span></span>  
 <span data-ttu-id="cfc53-114">Indique que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] va supprimer les entrées présentes dans le journal depuis plus longtemps que la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="cfc53-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="cfc53-115">Il s'agit d'une exécution ponctuelle pour supprimer l'historique.</span><span class="sxs-lookup"><span data-stu-id="cfc53-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="cfc53-116">Si vous préférez un travail récurrent, créez et planifiez un plan de maintenance avec un travail de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="cfc53-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="cfc53-117">**Antérieur à**</span><span class="sxs-lookup"><span data-stu-id="cfc53-117">**Older than**</span></span>  
 <span data-ttu-id="cfc53-118">Spécifie la période pendant laquelle l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve les entrées.</span><span class="sxs-lookup"><span data-stu-id="cfc53-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc53-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfc53-119">See Also</span></span>  
 [<span data-ttu-id="cfc53-120">Journal des erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfc53-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
