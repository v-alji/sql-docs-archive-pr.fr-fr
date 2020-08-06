---
title: Propriétés de rôle d’utilisateur (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700662"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="b9866-102">Propriétés de rôle d'utilisateur (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b9866-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="b9866-103">Utilisez cette page pour afficher les tâches qui figurent dans une définition de rôle au niveau élément.</span><span class="sxs-lookup"><span data-stu-id="b9866-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="b9866-104">Vous pouvez également utiliser cette page pour modifier la liste des tâches ou la description d'un rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="b9866-105">Une définition de rôle au niveau élément est une collection nommée de tâches que les utilisateurs effectuent sur un élément spécifique (c'est-à-dire un dossier, un rapport, une ressource ou une source de données partagée).</span><span class="sxs-lookup"><span data-stu-id="b9866-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="b9866-106">Les définitions de rôles sont attribuées à un utilisateur ou à un groupe pour créer une attribution de rôle dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="b9866-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="b9866-107">Les tâches contenues dans la définition de rôle décrivent les opérations que peuvent effectuer l'utilisateur ou le groupe.</span><span class="sxs-lookup"><span data-stu-id="b9866-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b9866-108">contient plusieurs définitions de rôles au niveau élément prédéfinies que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="b9866-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="b9866-109">Vous pouvez changer les définitions de rôles en modifiant la liste des tâches de chacune.</span><span class="sxs-lookup"><span data-stu-id="b9866-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="b9866-110">La modification d'une définition de rôle affecte toutes les attributions de rôles qui contiennent la définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9866-111">Les attributions de rôles d'utilisateur sont utilisées uniquement sur un serveur de rapports qui s'exécute en mode natif.</span><span class="sxs-lookup"><span data-stu-id="b9866-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="b9866-112">Si le serveur de rapports est configuré pour l'intégration SharePoint, cette page affiche des informations en lecture seule sur les rôles et niveaux d'autorisation définis sur le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9866-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9866-113">Options</span><span class="sxs-lookup"><span data-stu-id="b9866-113">Options</span></span>  
 <span data-ttu-id="b9866-114">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b9866-114">**Name**</span></span>  
 <span data-ttu-id="b9866-115">Spécifie le nom de la définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="b9866-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="b9866-116">**Description**</span></span>  
 <span data-ttu-id="b9866-117">Affiche une description de la définition du rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-117">Shows a description of the role definition.</span></span> <span data-ttu-id="b9866-118">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cette description n'est visible que sur cette page.</span><span class="sxs-lookup"><span data-stu-id="b9866-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="b9866-119">Dans le Gestionnaire de rapports, cette description aide les utilisateurs à décider s'il convient d'utiliser le rôle dans une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="b9866-120">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="b9866-120">**Task**</span></span>  
 <span data-ttu-id="b9866-121">Répertorie toutes les tâches au niveau élément qui peuvent être sélectionnées pour la définition de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="b9866-122">Vous pouvez ajouter ou supprimer des éléments dans la liste des tâches prédéfinies pour spécifier comment les utilisateurs accèdent à un élément donné par le biais de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="b9866-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="b9866-123">Vous ne pouvez ni créer de nouvelles tâches, ni modifier les tâches existantes.</span><span class="sxs-lookup"><span data-stu-id="b9866-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="b9866-124">La liste des tâches d'une définition de rôle apparaît uniquement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9866-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b9866-125">**Description de la tâche**</span><span class="sxs-lookup"><span data-stu-id="b9866-125">**Task Description**</span></span>  
 <span data-ttu-id="b9866-126">Donne des informations sur chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="b9866-126">Provides information about each task.</span></span> <span data-ttu-id="b9866-127">Vous ne pouvez pas modifier la description des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9866-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9866-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9866-128">See Also</span></span>  
 <span data-ttu-id="b9866-129">[Tâches au niveau élément](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b9866-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="b9866-130">[Définitions de rôles](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="b9866-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="b9866-131">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b9866-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="b9866-132">[Tâches et autorisations](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="b9866-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="b9866-133">Rôles prédéfinis</span><span class="sxs-lookup"><span data-stu-id="b9866-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
