---
title: Nouveau profil de l’Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705036"
---
# <a name="new-agent-profile"></a><span data-ttu-id="d834f-102">Nouveau profil de l'Agent</span><span class="sxs-lookup"><span data-stu-id="d834f-102">New Agent Profile</span></span>
  <span data-ttu-id="d834f-103">Utilisez la boîte de dialogue **Nouveau profil de l'Agent** pour créer un profil.</span><span class="sxs-lookup"><span data-stu-id="d834f-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="d834f-104">Les nouveaux profils sont toujours dérivés de profils existants, mais il n'est pas possible de les modifier pour répondre aux besoins des applications.</span><span class="sxs-lookup"><span data-stu-id="d834f-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="d834f-105">Lorsqu'un profil est créé, vous pouvez l'appliquer à des travaux de l'agent existants ou à venir dans la boîte de dialogue **Profils de l'Agent** .</span><span class="sxs-lookup"><span data-stu-id="d834f-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="d834f-106">Vous pouvez modifier les valeurs de paramètre de l’agent dans la boîte de dialogue \<**AgentProfileName>Propriétés\*\*.</span><span class="sxs-lookup"><span data-stu-id="d834f-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d834f-107">Options</span><span class="sxs-lookup"><span data-stu-id="d834f-107">Options</span></span>  
 <span data-ttu-id="d834f-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="d834f-108">**Name**</span></span>  
 <span data-ttu-id="d834f-109">Entrez le nom du profil.</span><span class="sxs-lookup"><span data-stu-id="d834f-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="d834f-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="d834f-110">**Description**</span></span>  
 <span data-ttu-id="d834f-111">Entrez la description du profil</span><span class="sxs-lookup"><span data-stu-id="d834f-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="d834f-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="d834f-112">**Parameter**</span></span>  
 <span data-ttu-id="d834f-113">Paramètres de l'agent contenus dans le profil.</span><span class="sxs-lookup"><span data-stu-id="d834f-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="d834f-114">Le profil de base dont est dérivé le nouveau profil ne nécessite pas obligatoirement une valeur pour chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="d834f-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="d834f-115">Pour connaître tous les paramètres valides pour un agent donné, désactivez la case à cocher **Afficher uniquement les paramètres utilisés dans ce profil** .</span><span class="sxs-lookup"><span data-stu-id="d834f-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="d834f-116">Pour la description de chaque paramètre, consultez :</span><span class="sxs-lookup"><span data-stu-id="d834f-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="d834f-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="d834f-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="d834f-118">Agent de lecture du journal des réplications</span><span class="sxs-lookup"><span data-stu-id="d834f-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="d834f-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="d834f-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="d834f-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="d834f-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="d834f-121">Agent de lecture de la file d’attente de réplication</span><span class="sxs-lookup"><span data-stu-id="d834f-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="d834f-122">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="d834f-122">**Default Value**</span></span>  
 <span data-ttu-id="d834f-123">Valeur par défaut de chaque paramètre de l'agent.</span><span class="sxs-lookup"><span data-stu-id="d834f-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="d834f-124">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="d834f-124">**Value**</span></span>  
 <span data-ttu-id="d834f-125">Valeur du paramètre spécifié dans le profil de base du nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="d834f-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="d834f-126">Modifiez les paramètres voulus.</span><span class="sxs-lookup"><span data-stu-id="d834f-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="d834f-127">**Afficher uniquement les paramètres utilisés dans ce profil**</span><span class="sxs-lookup"><span data-stu-id="d834f-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="d834f-128">Désactivez cette case pour afficher tous les paramètres valides d'un agent donné.</span><span class="sxs-lookup"><span data-stu-id="d834f-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d834f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d834f-129">See Also</span></span>  
 <span data-ttu-id="d834f-130">[Utiliser des profils d’Agent de réplication](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="d834f-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="d834f-131">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d834f-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="d834f-132">Profils de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="d834f-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
