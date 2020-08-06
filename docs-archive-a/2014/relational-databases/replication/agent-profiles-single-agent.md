---
title: Profils de l’Agent (agent unique) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileagentname.f1
helpviewer_keywords:
- Agent Profile dialog box
ms.assetid: 22713555-c496-4ce1-8ec7-4ae75cfadca8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7def9a6fef4e7e66076ee18552705c6071dab134
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603411"
---
# <a name="agent-profiles-single-agent"></a><span data-ttu-id="f4103-102">Profils de l'Agent (agent unique)</span><span class="sxs-lookup"><span data-stu-id="f4103-102">Agent Profiles (single agent)</span></span>
  <span data-ttu-id="f4103-103">La boîte de dialogue **Profils de l'Agent** permet de gérer les profils d'un agent.</span><span class="sxs-lookup"><span data-stu-id="f4103-103">Use the **Agent Profiles** dialog box to manage profiles for an agent.</span></span> <span data-ttu-id="f4103-104">Les profils d'agent permettent de gérer aisément les paramètres d'exécution de chaque agent.</span><span class="sxs-lookup"><span data-stu-id="f4103-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="f4103-105">Chaque agent possède un profil par défaut tandis que certains ont des profils prédéfinis supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f4103-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="f4103-106">Par exemple, l'Agent de fusion possède un profil « liaison lente » conçu pour les connexions à faible bande passante.</span><span class="sxs-lookup"><span data-stu-id="f4103-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="f4103-107">Les profils prédéfinis suffisent pour la plupart des applications, mais vous pouvez également créer des profils définis par l'utilisateur, qui vous permettent de personnaliser le comportement de l'agent.</span><span class="sxs-lookup"><span data-stu-id="f4103-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4103-108">Options</span><span class="sxs-lookup"><span data-stu-id="f4103-108">Options</span></span>  
 <span data-ttu-id="f4103-109">**Valeur par défaut pour nouveau**</span><span class="sxs-lookup"><span data-stu-id="f4103-109">**Default for New**</span></span>  
 <span data-ttu-id="f4103-110">Sélectionnez le profil à utiliser lorsque des travaux sont créés pour un agent d'un type donné.</span><span class="sxs-lookup"><span data-stu-id="f4103-110">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="f4103-111">Par exemple, si vous créez plusieurs abonnements à une publication de fusion, le travail de l'Agent de fusion pour chaque abonnement utilisera le profil sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f4103-111">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="f4103-112">Si vous souhaitez modifier le profil de travaux existants, sélectionnez un profil, puis cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="f4103-112">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="f4103-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="f4103-113">**Name**</span></span>  
 <span data-ttu-id="f4103-114">Nom du profil.</span><span class="sxs-lookup"><span data-stu-id="f4103-114">The name of the profile.</span></span>  
  
 <span data-ttu-id="f4103-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="f4103-115">**Type**</span></span>  
 <span data-ttu-id="f4103-116">Type de profil : **Utilisateur** (défini par l'utilisateur) ou **Système** (prédéfini).</span><span class="sxs-lookup"><span data-stu-id="f4103-116">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="f4103-117">**Propriétés (...)**</span><span class="sxs-lookup"><span data-stu-id="f4103-117">**Properties (...)**</span></span>  
 <span data-ttu-id="f4103-118">Cliquez sur cette option pour voir les valeurs utilisées pour chaque paramètre dans le profil de l'agent.</span><span class="sxs-lookup"><span data-stu-id="f4103-118">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="f4103-119">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="f4103-119">**New**</span></span>  
 <span data-ttu-id="f4103-120">Cliquez sur ce bouton pour créer un profil.</span><span class="sxs-lookup"><span data-stu-id="f4103-120">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="f4103-121">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="f4103-121">**Delete**</span></span>  
 <span data-ttu-id="f4103-122">Sélectionnez un profil défini par l'utilisateur, puis cliquez sur **Supprimer** pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="f4103-122">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="f4103-123">Les profils prédéfinis ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="f4103-123">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="f4103-124">**Modifier les Agents existants**</span><span class="sxs-lookup"><span data-stu-id="f4103-124">**Change Existing Agents**</span></span>  
 <span data-ttu-id="f4103-125">Sélectionnez un profil, puis cliquez sur **Modifier les Agents existants** afin d'indiquer que tous les travaux existants d'un agent d'un type donné doivent utiliser le profil sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f4103-125">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="f4103-126">Par exemple, si vous avez créé plusieurs abonnements à une publication de fusion et que vous souhaitez modifier le profil afin de spécifier que le travail d'Agent de fusion de chaque abonnement doit utiliser le **Profil de liaison lente de l'agent**, sélectionnez ce profil, puis cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="f4103-126">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4103-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4103-127">See Also</span></span>  
 <span data-ttu-id="f4103-128">[Utiliser des profils d’Agent de réplication](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="f4103-128">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="f4103-129">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f4103-129">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="f4103-130">Profils de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="f4103-130">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
