---
title: MSSQLSERVER_30089 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605481"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="40af9-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="40af9-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="40af9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="40af9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40af9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="40af9-104">Product Name</span></span>|<span data-ttu-id="40af9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="40af9-105">SQL Server</span></span>|  
|<span data-ttu-id="40af9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="40af9-106">Event ID</span></span>|<span data-ttu-id="40af9-107">30089</span><span class="sxs-lookup"><span data-stu-id="40af9-107">30089</span></span>|  
|<span data-ttu-id="40af9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="40af9-108">Event Source</span></span>|<span data-ttu-id="40af9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="40af9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="40af9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="40af9-110">Component</span></span>|<span data-ttu-id="40af9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="40af9-111">SQLEngine</span></span>|  
|<span data-ttu-id="40af9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="40af9-112">Symbolic Name</span></span>|<span data-ttu-id="40af9-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="40af9-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="40af9-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="40af9-114">Message Text</span></span>|<span data-ttu-id="40af9-115">Le processus hôte de démon de filtre de texte intégral (FDHost) s'est arrêté anormalement.</span><span class="sxs-lookup"><span data-stu-id="40af9-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="40af9-116">Cela peut se produire si un composant linguistique, tel qu'un analyseur lexical, un générateur de formes dérivées ou un filtre configuré de façon incorrecte ou présentant un dysfonctionnement a provoqué une erreur irrécupérable pendant l'indexation de texte intégral ou le traitement de requête.</span><span class="sxs-lookup"><span data-stu-id="40af9-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="40af9-117">Le processus sera redémarré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="40af9-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="40af9-118">Explication</span><span class="sxs-lookup"><span data-stu-id="40af9-118">Explanation</span></span>  
 <span data-ttu-id="40af9-119">Le processus hôte de démon de filtre de texte intégral a rencontré un problème qui l'a forcé à s'arrêter anormalement.</span><span class="sxs-lookup"><span data-stu-id="40af9-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="40af9-120">La cause du problème peut être un document mis en forme de manière incorrecte, un bogue dans le filtre ou l'analyseur lexical, ou un problème dans le démon de filtre.</span><span class="sxs-lookup"><span data-stu-id="40af9-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40af9-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="40af9-121">User Action</span></span>  
 <span data-ttu-id="40af9-122">En règle générale, le démon corrige l'erreur.</span><span class="sxs-lookup"><span data-stu-id="40af9-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="40af9-123">Si le problème persiste, une résolution définitive s'avère nécessaire.</span><span class="sxs-lookup"><span data-stu-id="40af9-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="40af9-124">Pour isoler le problème, essayez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="40af9-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="40af9-125">Si un nouveau composant linguistique a été installé récemment, supprimez-le du système.</span><span class="sxs-lookup"><span data-stu-id="40af9-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="40af9-126">Examinez le journal d'analyse pour identifier les nouveaux documents qui n'ont pas pu faire l'objet d'une indexation de texte intégral, puis supprimez-les.</span><span class="sxs-lookup"><span data-stu-id="40af9-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40af9-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40af9-127">See Also</span></span>  
 <span data-ttu-id="40af9-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40af9-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="40af9-129">[Configurer et gérer les analyseurs lexicaux et les générateurs de formes dérivées pour la recherche](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="40af9-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="40af9-130">Configurer et gérer des filtres pour la recherche</span><span class="sxs-lookup"><span data-stu-id="40af9-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
