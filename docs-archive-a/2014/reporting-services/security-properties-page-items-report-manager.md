---
title: Page Propriétés de sécurité, éléments (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 351b8503-354f-4b1b-a7ac-f1245d978da0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 297ae2ceefad89d64c59b5da25d51d541917c894
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603819"
---
# <a name="security-properties-page-items-report-manager"></a><span data-ttu-id="ee991-102">Page Propriétés de sécurité, Éléments (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="ee991-102">Security Properties Page, Items (Report Manager)</span></span>
  <span data-ttu-id="ee991-103">La page Propriétés de sécurité vous permet d'afficher ou de modifier les paramètres de sécurité qui déterminent l'accès aux dossiers, aux rapports, aux modèles, aux ressources et aux sources de données partagées.</span><span class="sxs-lookup"><span data-stu-id="ee991-103">Use the Security properties page to view or modify the security settings that determine access to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="ee991-104">Cette page est disponible pour les éléments que vous êtes autorisé à sécuriser.</span><span class="sxs-lookup"><span data-stu-id="ee991-104">This page is available for items that you have permission to secure.</span></span>  
  
 <span data-ttu-id="ee991-105">L'accès aux éléments est défini par l'intermédiaire des attributions de rôle qui spécifient les tâches que peuvent effectuer un groupe ou un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee991-105">Access to items is defined through role assignments that specify the tasks that a group or user can perform.</span></span> <span data-ttu-id="ee991-106">Une attribution de rôle est composée d'un nom d'utilisateur ou de groupe et d'une ou plusieurs définitions de rôles qui spécifient une collection de tâches.</span><span class="sxs-lookup"><span data-stu-id="ee991-106">A role assignment consists of one user or group name and one or more role definitions that specify a collection of tasks.</span></span>  
  
 <span data-ttu-id="ee991-107">Les paramètres de sécurité sont transmis du dossier racine aux sous-dossiers et aux éléments contenus dans ces dossiers.</span><span class="sxs-lookup"><span data-stu-id="ee991-107">Security settings are inherited from the root folder down to subfolders and items within those folders.</span></span> <span data-ttu-id="ee991-108">Si vous n'arrêtez pas de façon explicite la sécurité héritée, les sous-dossiers et les éléments héritent du contexte de sécurité d'un élément parent.</span><span class="sxs-lookup"><span data-stu-id="ee991-108">Unless you explicitly break inherited security, subfolders and items inherit the security context of a parent item.</span></span> <span data-ttu-id="ee991-109">Si vous redéfinissez une stratégie de sécurité pour un dossier situé au milieu de la hiérarchie, tous ses éléments enfants (y compris les sous-dossiers) utiliseront les nouveaux paramètres de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ee991-109">If you redefine a security policy for a folder in the middle of the hierarchy, all its child items, including subfolders, assume the new security settings.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="ee991-110">Navigation</span><span class="sxs-lookup"><span data-stu-id="ee991-110">Navigation</span></span>  
 <span data-ttu-id="ee991-111">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee991-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-security-page-for-an-item"></a><span data-ttu-id="ee991-112">Pour ouvrir la page Sécurité pour un élément</span><span class="sxs-lookup"><span data-stu-id="ee991-112">To open the Security page for an item</span></span>  
  
1.  <span data-ttu-id="ee991-113">Ouvrez le Gestionnaire de rapports et recherchez l'élément pour lequel vous souhaitez configurer des paramètres de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ee991-113">Open Report Manager, and locate the item for which you want to configure security settings.</span></span>  
  
2.  <span data-ttu-id="ee991-114">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="ee991-114">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="ee991-115">Dans le menu déroulant, effectuez l'une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee991-115">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="ee991-116">Cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="ee991-116">Click **Security**.</span></span> <span data-ttu-id="ee991-117">La page de propriétés de sécurité s'ouvre pour l'élément.</span><span class="sxs-lookup"><span data-stu-id="ee991-117">This opens the Security properties page for the item.</span></span>  
  
    -   <span data-ttu-id="ee991-118">Cliquez sur **Gérer** pour ouvrir la page des propriétés générales pour l'élément.</span><span class="sxs-lookup"><span data-stu-id="ee991-118">Click **Manage** to open the General properties page for the item.</span></span> <span data-ttu-id="ee991-119">Sélectionnez ensuite l'onglet **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="ee991-119">Then select the **Security** tab.</span></span>  
  
 <span data-ttu-id="ee991-120">**Modifier la sécurité de l'élément**</span><span class="sxs-lookup"><span data-stu-id="ee991-120">**Edit Item Security**</span></span>  
 <span data-ttu-id="ee991-121">Cliquez pour modifier la définition de la sécurité pour l'élément actif.</span><span class="sxs-lookup"><span data-stu-id="ee991-121">Click to change how security is defined for the current item.</span></span> <span data-ttu-id="ee991-122">Si vous modifiez la sécurité d'un dossier, vos modifications s'appliquent au contenu du dossier actif et des sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="ee991-122">If you are editing security for a folder, your changes apply to the contents of the current folder and any subfolders.</span></span>  
  
 <span data-ttu-id="ee991-123">Ce bouton n'est pas disponible pour le dossier racine.</span><span class="sxs-lookup"><span data-stu-id="ee991-123">This button is not available for the Home folder.</span></span>  
  
 <span data-ttu-id="ee991-124">Les boutons ci-dessous deviennent disponibles lorsque vous modifiez la sécurité d'un élément.</span><span class="sxs-lookup"><span data-stu-id="ee991-124">The following buttons become available when you edit item security.</span></span>  
  
 <span data-ttu-id="ee991-125">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="ee991-125">**Delete**</span></span>  
 <span data-ttu-id="ee991-126">Activez la case à cocher en regard du nom d'utilisateur ou de groupe à supprimer et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ee991-126">Select the check box next to the group or user name that you want to delete and click **Delete**.</span></span> <span data-ttu-id="ee991-127">Vous ne pouvez pas supprimer une attribution de rôle s'il s'agit de la dernière ou s'il s'agit d'une attribution de rôle intégrée (par exemple « Built-in\Administrateurs ») qui définit la ligne de base de la sécurité du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee991-127">You cannot delete a role assignment if it is the only one remaining, or if it is a built-in role assignment (for example, "Built-in\Administrators") that defines the security baseline for the report server.</span></span> <span data-ttu-id="ee991-128">La suppression d'une attribution de rôle n'entraîne pas celle d'un compte d'utilisateur ou de groupe ou des définitions de rôles.</span><span class="sxs-lookup"><span data-stu-id="ee991-128">Deleting a role assignment does not delete a group or user account or role definitions.</span></span>  
  
 <span data-ttu-id="ee991-129">**Nouvelle attribution de rôle**</span><span class="sxs-lookup"><span data-stu-id="ee991-129">**New Role Assignment**</span></span>  
 <span data-ttu-id="ee991-130">Cliquez pour ouvrir la page Nouvelle attribution de rôle qui permet de créer des attributions de rôles supplémentaires pour l'élément actif.</span><span class="sxs-lookup"><span data-stu-id="ee991-130">Click to open the New Role Assignment page, which is used to create additional role assignments for the current item.</span></span> <span data-ttu-id="ee991-131">Pour plus d’informations, consultez la [page nouvelle attribution de rôle : modifier l’attribution de rôle &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ee991-131">For more information, see [New Role Assignment: Edit Role Assignment Page &#40;Report Manager&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="ee991-132">**Rétablir la sécurité parente**</span><span class="sxs-lookup"><span data-stu-id="ee991-132">**Revert to Parent Security**</span></span>  
 <span data-ttu-id="ee991-133">Cliquez pour rétablir les paramètres de sécurité en fonction de ceux du dossier immédiatement parent.</span><span class="sxs-lookup"><span data-stu-id="ee991-133">Click to reset the security settings to that of the immediate parent folder.</span></span> <span data-ttu-id="ee991-134">Si l'héritage est arrêté dans toute l'arborescence des dossiers du serveur de rapports, les paramètres de sécurité du dossier de niveau supérieur (Dossier racine) sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="ee991-134">If inheritance is unbroken throughout the report server folder hierarchy, the security settings of the top-level folder, Home, are used.</span></span>  
  
 <span data-ttu-id="ee991-135">**Groupe ou utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ee991-135">**Group or User**</span></span>  
 <span data-ttu-id="ee991-136">Répertorie les groupes et les utilisateurs qui font partie de l'attribution de rôle existante pour l'élément actuel.</span><span class="sxs-lookup"><span data-stu-id="ee991-136">Lists the groups and users that are part of an existing role assignment for the current item.</span></span> <span data-ttu-id="ee991-137">Les attributions de rôle existantes pour le dossier actif sont définies pour les groupes et les utilisateurs qui apparaissent dans cette colonne.</span><span class="sxs-lookup"><span data-stu-id="ee991-137">Existing role assignments for the current folder are defined for the groups and users that appear in this column.</span></span> <span data-ttu-id="ee991-138">Vous pouvez cliquer sur un nom d'utilisateur ou de groupe pour afficher ou modifier les détails d'une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="ee991-138">You can click a group or user name to view or edit role assignment details.</span></span>  
  
 <span data-ttu-id="ee991-139">**Rôles**</span><span class="sxs-lookup"><span data-stu-id="ee991-139">**Roles**</span></span>  
 <span data-ttu-id="ee991-140">Répertorie une ou plusieurs définitions de rôles qui font partie d'une attribution de rôle existante.</span><span class="sxs-lookup"><span data-stu-id="ee991-140">Lists one or more role definitions that are part of an existing role assignment.</span></span> <span data-ttu-id="ee991-141">Si plusieurs rôles sont attribués à un compte d'utilisateur ou de groupe, ce groupe ou cet utilisateur peut effectuer toutes les tâches qui appartiennent à ces rôles.</span><span class="sxs-lookup"><span data-stu-id="ee991-141">If multiple roles are assigned to a group or user account, that group or user can perform all tasks that belong to those roles.</span></span> <span data-ttu-id="ee991-142">Pour afficher les tâches associées à un rôle, utilisez SQL Server Management Studio pour consulter les tâches dans chaque définition de rôle.</span><span class="sxs-lookup"><span data-stu-id="ee991-142">To view the tasks that are associated with a role, use SQL Server Management Studio to view the tasks in each role definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee991-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee991-143">See Also</span></span>  
 <span data-ttu-id="ee991-144">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="ee991-144">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="ee991-145">[Rôles prédéfinis](security/role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="ee991-145">[Predefined Roles](security/role-definitions-predefined-roles.md) </span></span>  
 <span data-ttu-id="ee991-146">[Octroi d'autorisations sur un serveur de rapports en mode natif](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="ee991-146">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="ee991-147">[Attributions de rôles](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="ee991-147">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="ee991-148">Définitions de rôles</span><span class="sxs-lookup"><span data-stu-id="ee991-148">Role Definitions</span></span>](security/role-definitions.md)  
  
  
