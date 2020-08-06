---
title: Propriétés de SQL Server Agent (page Système de travaux) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613259"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="4c36a-102">Propriétés de l'Agent SQL Server (page Système de travaux)</span><span class="sxs-lookup"><span data-stu-id="4c36a-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="4c36a-103">Utilisez cette page pour afficher et modifier la manière dont le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service agent gère les travaux.</span><span class="sxs-lookup"><span data-stu-id="4c36a-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c36a-104">Options</span><span class="sxs-lookup"><span data-stu-id="4c36a-104">Options</span></span>  
 <span data-ttu-id="4c36a-105">**Intervalle du délai d'arrêt (secondes)**</span><span class="sxs-lookup"><span data-stu-id="4c36a-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="4c36a-106">Spécifie le nombre de secondes que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attend pour considérer que les travaux sont terminés et pour forcer l'arrêt.</span><span class="sxs-lookup"><span data-stu-id="4c36a-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="4c36a-107">Si le travail est toujours en cours d'exécution après l'intervalle spécifié, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] force l'arrêt du travail.</span><span class="sxs-lookup"><span data-stu-id="4c36a-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="4c36a-108">**Utiliser un compte proxy non-administrateur**</span><span class="sxs-lookup"><span data-stu-id="4c36a-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="4c36a-109">Définit un compte proxy non-administrateur pour l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c36a-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="4c36a-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]et les versions ultérieures prennent en charge plusieurs proxies, c’est pourquoi cette option est applicable uniquement lors de la gestion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versions de l’agent antérieures à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c36a-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="4c36a-111">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="4c36a-111">**User name**</span></span>  
 <span data-ttu-id="4c36a-112">Entrez le nom de l'utilisateur du compte proxy non-administrateur.</span><span class="sxs-lookup"><span data-stu-id="4c36a-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c36a-113">prend en charge plusieurs serveurs proxy, c'est pourquoi cette option est applicable uniquement à la gestion des versions de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui précèdent [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c36a-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="4c36a-114">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="4c36a-114">**Password**</span></span>  
 <span data-ttu-id="4c36a-115">Entrez le mot de passe de l'utilisateur du compte proxy non-administrateur.</span><span class="sxs-lookup"><span data-stu-id="4c36a-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="4c36a-116">et les versions ultérieures prennent en charge plusieurs serveurs proxy, c'est pourquoi cette option est applicable uniquement à la gestion des versions de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui précèdent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c36a-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="4c36a-117">**Domaine**</span><span class="sxs-lookup"><span data-stu-id="4c36a-117">**Domain**</span></span>  
 <span data-ttu-id="4c36a-118">Entrez le domaine de l'utilisateur du compte proxy non-administrateur.</span><span class="sxs-lookup"><span data-stu-id="4c36a-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c36a-119">prend en charge plusieurs serveurs proxy, c'est pourquoi cette option est applicable uniquement à la gestion des versions de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui précèdent [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c36a-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c36a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c36a-120">See Also</span></span>  
 [<span data-ttu-id="4c36a-121">Implémenter des travaux</span><span class="sxs-lookup"><span data-stu-id="4c36a-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
