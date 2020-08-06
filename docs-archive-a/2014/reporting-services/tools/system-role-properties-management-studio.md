---
title: Propriétés de rôle système (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602708"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="77307-102">Propriétés de rôle système (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="77307-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="77307-103">La page Rôles système vous permet d'afficher les définitions de rôles système qui sont actuellement définies pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="77307-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="77307-104">Une définition de rôle système contient une collection nommée de tâches effectuées sur tout le site plutôt que sur un élément individuel.</span><span class="sxs-lookup"><span data-stu-id="77307-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="77307-105">Les définitions de rôles sont attribuées à un utilisateur ou à des groupes pour créer une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="77307-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="77307-106">Les tâches contenues dans la définition de rôle spécifient les opérations que peuvent effectuer l'utilisateur ou le groupe.</span><span class="sxs-lookup"><span data-stu-id="77307-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="77307-107">a deux définitions de rôles système prédéfinies : **Administrateur système** et **Utilisateur système**.</span><span class="sxs-lookup"><span data-stu-id="77307-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="77307-108">Vous pouvez les modifier en changeant la liste des tâches de chacune d'elles, ou vous pouvez créer un rôle système qui prend en charge une autre combinaison de tâches.</span><span class="sxs-lookup"><span data-stu-id="77307-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="77307-109">La modification d'une définition de rôle affecte toutes les attributions de rôles qui contiennent la définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="77307-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77307-110">Les attributions de rôles système sont utilisées uniquement sur un serveur de rapports qui s'exécute en mode natif.</span><span class="sxs-lookup"><span data-stu-id="77307-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="77307-111">Si le serveur de rapports est configuré pour l'intégration SharePoint, cette page n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="77307-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="77307-112">Options</span><span class="sxs-lookup"><span data-stu-id="77307-112">Options</span></span>  
 <span data-ttu-id="77307-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="77307-113">**Name**</span></span>  
 <span data-ttu-id="77307-114">Spécifie le nom de la définition du rôle système.</span><span class="sxs-lookup"><span data-stu-id="77307-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="77307-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="77307-115">**Description**</span></span>  
 <span data-ttu-id="77307-116">Affiche une description de la définition du rôle système.</span><span class="sxs-lookup"><span data-stu-id="77307-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="77307-117">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], cette description n'est visible que sur cette page.</span><span class="sxs-lookup"><span data-stu-id="77307-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="77307-118">Les utilisateurs qui consultent cet élément par le biais du Gestionnaire de rapports peuvent afficher cette description en parcourant l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="77307-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="77307-119">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="77307-119">**Task**</span></span>  
 <span data-ttu-id="77307-120">Répertorie toutes les tâches au niveau système qui peuvent être sélectionnées pour la définition de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="77307-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="77307-121">Vous pouvez ajouter ou supprimer des éléments dans la liste des tâches prédéfinies pour spécifier comment les utilisateurs accèdent à un élément donné par le biais de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="77307-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="77307-122">Vous ne pouvez ni créer de nouvelles tâches, ni modifier les tâches existantes.</span><span class="sxs-lookup"><span data-stu-id="77307-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="77307-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="77307-123">**Description**</span></span>  
 <span data-ttu-id="77307-124">Donne des informations sur chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="77307-124">Provides information about each task.</span></span> <span data-ttu-id="77307-125">Vous ne pouvez pas modifier la description des tâches.</span><span class="sxs-lookup"><span data-stu-id="77307-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77307-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77307-126">See Also</span></span>  
 <span data-ttu-id="77307-127">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="77307-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="77307-128">[Tâches au niveau système](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="77307-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="77307-129">[Tâches et autorisations](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="77307-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="77307-130">Rôles prédéfinis</span><span class="sxs-lookup"><span data-stu-id="77307-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
