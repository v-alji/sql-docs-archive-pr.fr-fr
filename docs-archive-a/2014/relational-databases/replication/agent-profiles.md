---
title: Profils de l’Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofiles.f1
helpviewer_keywords:
- Agent Profiles dialog box
ms.assetid: 0422e99c-e688-419b-bb4c-c7bebeef1d8d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7584670088da1ac7a9c81f1f8f0cbdce8b040c7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603410"
---
# <a name="agent-profiles"></a><span data-ttu-id="95cec-102">Profils de l'Agent</span><span class="sxs-lookup"><span data-stu-id="95cec-102">Agent Profiles</span></span>
  <span data-ttu-id="95cec-103">Utilisez la boîte de dialogue **Profils de l'Agent** pour gérer les profils de l'agent.</span><span class="sxs-lookup"><span data-stu-id="95cec-103">Use the **Agent Profiles** dialog box to manage agent profiles.</span></span> <span data-ttu-id="95cec-104">Les profils d'agent permettent de gérer aisément les paramètres d'exécution de chaque agent.</span><span class="sxs-lookup"><span data-stu-id="95cec-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="95cec-105">Chaque agent possède un profil par défaut tandis que certains ont des profils prédéfinis supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="95cec-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="95cec-106">Par exemple, l'Agent de fusion possède un profil « liaison lente » conçu pour les connexions à faible bande passante.</span><span class="sxs-lookup"><span data-stu-id="95cec-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="95cec-107">Les profils prédéfinis suffisent pour la plupart des applications, mais vous pouvez également créer des profils définis par l'utilisateur, qui vous permettent de personnaliser le comportement de l'agent.</span><span class="sxs-lookup"><span data-stu-id="95cec-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="95cec-108">Options</span><span class="sxs-lookup"><span data-stu-id="95cec-108">Options</span></span>  
 <span data-ttu-id="95cec-109">**Sélectionner une page**</span><span class="sxs-lookup"><span data-stu-id="95cec-109">**Select a page**</span></span>  
 <span data-ttu-id="95cec-110">Sélectionnez un agent dans le volet de gauche et les profils pour cet agent s'affichent dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="95cec-110">Select an agent in the left pane, and the profiles for the agent are displayed in the right pane.</span></span>  
  
 <span data-ttu-id="95cec-111">**Valeur par défaut pour nouveau**</span><span class="sxs-lookup"><span data-stu-id="95cec-111">**Default for New**</span></span>  
 <span data-ttu-id="95cec-112">Sélectionnez le profil à utiliser lorsque des travaux sont créés pour un agent d'un type donné.</span><span class="sxs-lookup"><span data-stu-id="95cec-112">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="95cec-113">Par exemple, si vous créez plusieurs abonnements à une publication de fusion, le travail de l'Agent de fusion pour chaque abonnement utilisera le profil sélectionné.</span><span class="sxs-lookup"><span data-stu-id="95cec-113">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="95cec-114">Si vous souhaitez modifier le profil de travaux existants, sélectionnez un profil, puis cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="95cec-114">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="95cec-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="95cec-115">**Name**</span></span>  
 <span data-ttu-id="95cec-116">Nom du profil.</span><span class="sxs-lookup"><span data-stu-id="95cec-116">The name of the profile.</span></span>  
  
 <span data-ttu-id="95cec-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="95cec-117">**Type**</span></span>  
 <span data-ttu-id="95cec-118">Type de profil : **Utilisateur** (défini par l'utilisateur) ou **Système** (prédéfini).</span><span class="sxs-lookup"><span data-stu-id="95cec-118">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="95cec-119">**Propriétés (...)**</span><span class="sxs-lookup"><span data-stu-id="95cec-119">**Properties (...)**</span></span>  
 <span data-ttu-id="95cec-120">Cliquez sur cette option pour voir les valeurs utilisées pour chaque paramètre dans le profil de l'agent.</span><span class="sxs-lookup"><span data-stu-id="95cec-120">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="95cec-121">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="95cec-121">**New**</span></span>  
 <span data-ttu-id="95cec-122">Cliquez sur ce bouton pour créer un profil.</span><span class="sxs-lookup"><span data-stu-id="95cec-122">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="95cec-123">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="95cec-123">**Delete**</span></span>  
 <span data-ttu-id="95cec-124">Sélectionnez un profil défini par l'utilisateur, puis cliquez sur **Supprimer** pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="95cec-124">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="95cec-125">Les profils prédéfinis ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="95cec-125">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="95cec-126">**Modifier les Agents existants**</span><span class="sxs-lookup"><span data-stu-id="95cec-126">**Change Existing Agents**</span></span>  
 <span data-ttu-id="95cec-127">Sélectionnez un profil, puis cliquez sur **Modifier les Agents existants** afin d'indiquer que tous les travaux existants d'un agent d'un type donné doivent utiliser le profil sélectionné.</span><span class="sxs-lookup"><span data-stu-id="95cec-127">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="95cec-128">Par exemple, si vous avez créé plusieurs abonnements à une publication de fusion et que vous souhaitez modifier le profil afin de spécifier que le travail d'Agent de fusion de chaque abonnement doit utiliser le **Profil de liaison lente de l'agent**, sélectionnez ce profil, puis cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="95cec-128">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cec-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95cec-129">See Also</span></span>  
 <span data-ttu-id="95cec-130">[Utiliser des profils d’Agent de réplication](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="95cec-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="95cec-131">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="95cec-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="95cec-132">Profils de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="95cec-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
