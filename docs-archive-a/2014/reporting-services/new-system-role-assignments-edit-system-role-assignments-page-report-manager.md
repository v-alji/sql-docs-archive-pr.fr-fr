---
title: 'Nouvelle attribution de rôle système : page modifier les attributions de rôles système (Gestionnaire de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601950"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="bb372-102">Page Nouvelle attribution de rôle système : Modifier les attributions de rôles système (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="bb372-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="bb372-103">La page Nouvelle attribution de rôle système ou Modifier les attributions de rôle système vous permet de définir la sécurité pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bb372-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="bb372-104">La sécurité est définie par l'intermédiaire des attributions de rôle qui mappent des groupes ou des utilisateurs spécifiques aux tâches qu'ils peuvent effectuer.</span><span class="sxs-lookup"><span data-stu-id="bb372-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="bb372-105">La liste des tâches est représentée sous la forme d'une définition de rôle que vous sélectionnez lors de l'attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="bb372-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="bb372-106">Au niveau système, les attributions de rôle que vous créez ou modifiez s'appliquent à l'ensemble du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bb372-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="bb372-107">Par exemple, la possibilité de créer des planifications partagées est spécifiée au niveau système, car celles-ci sont utilisées par tout le système.</span><span class="sxs-lookup"><span data-stu-id="bb372-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="bb372-108">Par défaut, Reporting Services fournit deux rôles de niveau système prédéfinis :</span><span class="sxs-lookup"><span data-stu-id="bb372-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="bb372-109">L'utilisateur système inclut des tâches qui permettent aux utilisateurs de consulter des propriétés de serveur de rapports et des planifications partagées, ainsi que d'exécuter des définitions de rapport, qui permettent aux utilisateurs de consulter des rapports générés interactifs publiés sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bb372-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="bb372-110">La plupart des utilisateurs doivent être assignés à ce rôle.</span><span class="sxs-lookup"><span data-stu-id="bb372-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="bb372-111">Administrateur système inclut des tâches pour créer et gérer des planifications partagées, définir des propriétés de serveur et créer des attributions de rôles au niveau du système pour d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bb372-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="bb372-112">Peu d'utilisateurs ont besoin d'autorisations à ce niveau.</span><span class="sxs-lookup"><span data-stu-id="bb372-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="bb372-113">Navigation</span><span class="sxs-lookup"><span data-stu-id="bb372-113">Navigation</span></span>  
 <span data-ttu-id="bb372-114">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb372-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="bb372-115">Pour ouvrir la page Nouvelle attribution de rôle système ou Modifier les attributions de rôles système</span><span class="sxs-lookup"><span data-stu-id="bb372-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="bb372-116">Ouvrez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="bb372-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="bb372-117">En haut de la page, dans l'angle droit, cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="bb372-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="bb372-118">La page des propriétés générales du site s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="bb372-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="bb372-119">Sélectionnez l’onglet **sécurité** . Vous devez disposer des autorisations de gestionnaire de contenu et d’administrateur système pour accéder à cette page.</span><span class="sxs-lookup"><span data-stu-id="bb372-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="bb372-120">Pour créer une attribution de rôle, cliquez sur **Nouvelle attribution de rôle** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="bb372-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="bb372-121">Pour modifier une attribution de rôle existante, cliquez sur **Modifier** en regard d'un groupe ou utilisateur dans la page de propriétés Sécurité.</span><span class="sxs-lookup"><span data-stu-id="bb372-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb372-122">Options</span><span class="sxs-lookup"><span data-stu-id="bb372-122">Options</span></span>  
 <span data-ttu-id="bb372-123">**Groupe ou utilisateur**</span><span class="sxs-lookup"><span data-stu-id="bb372-123">**Group or User**</span></span>  
 <span data-ttu-id="bb372-124">Tapez le nom d'un compte d'utilisateur ou de groupe dans votre domaine.</span><span class="sxs-lookup"><span data-stu-id="bb372-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="bb372-125">Si le serveur de rapports s'exécute sous un compte local, vous devez spécifier les utilisateurs ou les groupes locaux.</span><span class="sxs-lookup"><span data-stu-id="bb372-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="bb372-126">S'il s'exécute sous un compte de domaine, vous devez spécifier les utilisateurs ou les groupes de domaine.</span><span class="sxs-lookup"><span data-stu-id="bb372-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="bb372-127">Entrez le compte au format suivant : \<domain> \\<compte \> .</span><span class="sxs-lookup"><span data-stu-id="bb372-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb372-128">Cette case est disponible uniquement dans la page Nouvelle attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="bb372-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="bb372-129">**Rôles**</span><span class="sxs-lookup"><span data-stu-id="bb372-129">**Roles**</span></span>  
 <span data-ttu-id="bb372-130">Fournit une liste de rôles au niveau du système que vous pouvez attribuer à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bb372-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="bb372-131">Vous pouvez spécifier plusieurs rôles pour une attribution de rôle unique.</span><span class="sxs-lookup"><span data-stu-id="bb372-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="bb372-132">Le Gestionnaire de rapports n'affiche pas les tâches dans chaque rôle ni ne propose de façon d'ajouter ou de modifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="bb372-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="bb372-133">Vous devez utiliser les rôles comme ils sont définis.</span><span class="sxs-lookup"><span data-stu-id="bb372-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="bb372-134">Pour créer, modifier ou supprimer des rôles, utilisez [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb372-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="bb372-135">Pour plus d’informations, consultez [Créer, supprimer ou modifier un rôle &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="bb372-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="bb372-136">Notez que, si vous utilisez [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, vous devez utiliser les rôles par défaut fournis.</span><span class="sxs-lookup"><span data-stu-id="bb372-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="bb372-137">**Descriptions**</span><span class="sxs-lookup"><span data-stu-id="bb372-137">**Descriptions**</span></span>  
 <span data-ttu-id="bb372-138">Affiche des informations supplémentaires sur le rôle.</span><span class="sxs-lookup"><span data-stu-id="bb372-138">Shows additional information about the role.</span></span> <span data-ttu-id="bb372-139">Pour les rôles prédéfinis, tels que Utilisateur système ou Administrateur système, la description résume les tâches que chaque rôle prend en charge.</span><span class="sxs-lookup"><span data-stu-id="bb372-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="bb372-140">**Supprimer l’attribution de rôle**</span><span class="sxs-lookup"><span data-stu-id="bb372-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="bb372-141">Cliquez pour supprimer une attribution de rôle existante pour un utilisateur ou un groupe.</span><span class="sxs-lookup"><span data-stu-id="bb372-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="bb372-142">Vous ne pouvez pas supprimer une attribution de rôle s'il s'agit de la dernière (chaque élément doit posséder une attribution de rôle au minimum).</span><span class="sxs-lookup"><span data-stu-id="bb372-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb372-143">Ce bouton est disponible uniquement dans la page Modifier l'attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="bb372-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb372-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb372-144">See Also</span></span>  
 <span data-ttu-id="bb372-145">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bb372-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="bb372-146">[Attributions de rôles](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="bb372-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="bb372-147">Définitions de rôles</span><span class="sxs-lookup"><span data-stu-id="bb372-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
