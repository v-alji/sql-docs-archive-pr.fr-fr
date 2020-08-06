---
title: Modifier ou supprimer une attribution de rôle (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700776"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="b9850-102">Modifier ou supprimer une attribution de rôle (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="b9850-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="b9850-103">Une attribution de rôle mappe un compte d'utilisateur ou de groupe à une définition de rôle prédéfinie qui inclut les tâches pouvant être effectuées.</span><span class="sxs-lookup"><span data-stu-id="b9850-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="b9850-104">Elle détermine les types d'opérations qu'un utilisateur peut effectuer sur un dossier, un rapport, un modèle ou tout autre type de contenu.</span><span class="sxs-lookup"><span data-stu-id="b9850-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="b9850-105">Pour créer, modifier ou supprimer des attributions de rôles, vous devez utiliser le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="b9850-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="b9850-106">Après avoir créé une attribution de rôle pour un utilisateur ou un groupe particulier, vous pouvez la modifier ultérieurement en sélectionnant un autre rôle.</span><span class="sxs-lookup"><span data-stu-id="b9850-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="b9850-107">Pour révoquer des autorisations d'accès à un serveur de rapports, vous pouvez supprimer une attribution de rôle du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b9850-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="b9850-108">Selon votre objectif, d'autres approches peuvent être plus appropriées.</span><span class="sxs-lookup"><span data-stu-id="b9850-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="b9850-109">Par exemple, vous pouvez personnaliser ou créer une définition de rôle, ou modifier l'appartenance (membership) d'un compte de groupe dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9850-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="b9850-110">Par exemple, un groupe d'utilisateurs doit gérer entièrement son contenu, mais il ne doit pas disposer du jeu complet d'autorisations associé au Gestionnaire de contenu.</span><span class="sxs-lookup"><span data-stu-id="b9850-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="b9850-111">Dans ce cas, vous pouvez créer une définition de rôle appelée Gestionnaire de contenu du service, qui inclut toutes les tâches du Gestionnaire de contenu à l’exception de la tâche **Définir des stratégies de sécurité pour les éléments**.</span><span class="sxs-lookup"><span data-stu-id="b9850-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="b9850-112">De même, si vous êtes un administrateur système ou réseau, et s'il est plus facile pour vous de gérer des comptes de groupes Active Directory plutôt que des attributions de rôles dans le Gestionnaire de rapports, vous pouvez réduire le temps de traitement lié à la gestion des attributions de rôles en créant une attribution de rôle unique pour un compte de groupe, puis en ajustant l'appartenance au groupe lorsque des utilisateurs n'ont plus besoin d'accéder aux rapports.</span><span class="sxs-lookup"><span data-stu-id="b9850-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="b9850-113">Si vous déterminez que la modification ou la suppression d'une attribution de rôle est la meilleure approche, n'oubliez pas de vérifier les attributions de rôles système et les attributions de rôles au niveau élément.</span><span class="sxs-lookup"><span data-stu-id="b9850-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="b9850-114">Chaque type d'attribution de rôle est configuré via des pages distinctes dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="b9850-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="b9850-115">Pour modifier ou supprimer une attribution de rôle système</span><span class="sxs-lookup"><span data-stu-id="b9850-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="b9850-116">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b9850-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b9850-117">Cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="b9850-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="b9850-118">Cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="b9850-118">Click **Security**.</span></span> <span data-ttu-id="b9850-119">Toutes les attributions de rôles de niveau système définies actuellement pour le serveur ou le déploiement avec montée en puissance parallèle sont répertoriées par nom de compte.</span><span class="sxs-lookup"><span data-stu-id="b9850-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="b9850-120">Recherchez l'attribution de rôle à modifier ou à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9850-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="b9850-121">Pour ajouter ou supprimer le rôle d’un utilisateur ou d’un groupe particulier, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b9850-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="b9850-122">Pour supprimer une attribution de rôle, cochez la case à côté du nom d’utilisateur ou de groupe, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b9850-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="b9850-123">Pour modifier ou supprimer une attribution de rôle au niveau élément</span><span class="sxs-lookup"><span data-stu-id="b9850-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="b9850-124">Démarrez le **Gestionnaire de rapports** et recherchez l’élément pour lequel vous souhaitez modifier ou supprimer une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="b9850-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="b9850-125">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="b9850-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b9850-126">Dans le menu déroulant, cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="b9850-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="b9850-127">Recherchez l'attribution de rôle à modifier ou à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9850-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="b9850-128">Pour ajouter ou supprimer le rôle d’un utilisateur ou d’un groupe particulier, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b9850-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="b9850-129">Pour supprimer une attribution de rôle, cochez la case à côté du nom d’utilisateur ou de groupe, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b9850-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9850-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9850-130">See Also</span></span>  
 <span data-ttu-id="b9850-131">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="b9850-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="b9850-132">[Attributions de rôles](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="b9850-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="b9850-133">[Page Paramètres du site &#40;Gestionnaire de rapports&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b9850-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="b9850-134">Page Nouvelle attribution de rôle système : Modifier les attributions de rôles système &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="b9850-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
