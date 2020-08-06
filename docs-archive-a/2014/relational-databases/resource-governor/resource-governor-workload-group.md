---
title: Groupe de charge de travail du gouverneur de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699377"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="fa0b8-102">Groupe de charge de travail de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="fa0b8-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="fa0b8-103">Dans le gouverneur de ressources [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un groupe de charge de travail sert de conteneur aux demandes de session qui ont des critères de classification similaires.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="fa0b8-104">Une charge de travail autorise l'analyse globale des sessions et définit les stratégies pour les sessions.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="fa0b8-105">Chaque groupe de charge de travail figure dans un pool de ressources, qui représente un sous-ensemble des ressources physiques d'une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa0b8-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="fa0b8-106">Lorsqu'une session est démarrée, le classifieur du gouverneur de ressources affecte la session à un groupe de charge de travail spécifique, et la session doit s'exécuter à l'aide des stratégies assignées au groupe de charge de travail et aux ressources définies pour le pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="fa0b8-107">Concepts autour des groupes de charge de travail</span><span class="sxs-lookup"><span data-stu-id="fa0b8-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="fa0b8-108">Un groupe de charge de travail sert de conteneur pour les demandes de session qui sont semblables selon les critères de classification appliqués à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="fa0b8-109">Un groupe de charges de travail permet l'analyse globale de la consommation des ressources et l'application d'une stratégie uniforme à toutes les demandes dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="fa0b8-110">Un groupe définit les stratégies pour ses membres.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa0b8-111">Les groupes de charges de travail définis par l'utilisateur peuvent être déplacés d'un pool de ressources à un autre.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="fa0b8-112">Le gouverneur de ressources prédéfinit deux groupes de charges de travail : le groupe interne et le groupe par défaut.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="fa0b8-113">Un utilisateur ne peut pas modifier des éléments classés comme un groupe interne, mais il peut les surveiller.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="fa0b8-114">Les demandes sont classées dans le groupe par défaut si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="fa0b8-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="fa0b8-115">il n'existe pas de critères pour classer une demande ;</span><span class="sxs-lookup"><span data-stu-id="fa0b8-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="fa0b8-116">une tentative pour classer la demande dans un groupe inexistant a été effectuée ;</span><span class="sxs-lookup"><span data-stu-id="fa0b8-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="fa0b8-117">un échec de classification général s'est produit.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="fa0b8-118">Le gouverneur de ressources fournit aussi des instructions DDL pour créer, changer et supprimer des groupes de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="fa0b8-119">Tâches de groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="fa0b8-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="fa0b8-120">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="fa0b8-120">Task Description</span></span>|<span data-ttu-id="fa0b8-121">Rubrique</span><span class="sxs-lookup"><span data-stu-id="fa0b8-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="fa0b8-122">Décrit comment créer un groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="fa0b8-123">Créer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="fa0b8-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="fa0b8-124">Décrit comment modifier les paramètres de groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="fa0b8-125">Modifier les paramètres de groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="fa0b8-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="fa0b8-126">Décrit comment supprimer un groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fa0b8-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="fa0b8-127">Supprimer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="fa0b8-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="fa0b8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa0b8-128">See Also</span></span>  
 <span data-ttu-id="fa0b8-129">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="fa0b8-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="fa0b8-130">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="fa0b8-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="fa0b8-131">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="fa0b8-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="fa0b8-132">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="fa0b8-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="fa0b8-133">[Configurer le gouverneur de ressources à l'aide d'un modèle](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="fa0b8-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="fa0b8-134">Afficher les propriétés du gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="fa0b8-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
