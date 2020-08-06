---
title: Créer, supprimer ou modifier un rôle (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704848"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="59fca-102">Créer, supprimer ou modifier un rôle (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="59fca-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="59fca-103">Reporting Services fournit des rôles prédéfinis qui établissent un niveau d'accès à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="59fca-104">Chaque utilisateur ou groupe qui requiert l'accès au serveur de rapports se voit attribuer un rôle qui décrit les tâches pouvant être effectuées.</span><span class="sxs-lookup"><span data-stu-id="59fca-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="59fca-105">Les rôles sont définis pour l'ensemble du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="59fca-106">Vous ne pouvez pas modifier une définition de rôle pour des parties spécifiques du serveur de rapports, ni spécifier qu'un rôle soit utilisé différemment selon les circonstances.</span><span class="sxs-lookup"><span data-stu-id="59fca-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="59fca-107">Pour créer, modifier ou supprimer des rôles, utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59fca-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="59fca-108">Vous ne pouvez supprimer que les rôles qui ne sont pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="59fca-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="59fca-109">Pour attribuer les rôles que vous créez à des utilisateurs et des groupes, utilisez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="59fca-110">Pour plus d’informations, consultez [Accorder à un utilisateur l’accès à un serveur de rapports &#40;Gestionnaire de rapports&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="59fca-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59fca-111">Si le serveur de rapports est configuré en mode intégré SharePoint, et si vous vous êtes connecté au site SharePoint auquel le serveur de rapports est intégré, vous pouvez afficher et modifier les niveaux d'autorisation qui contrôlent l'accès au contenu et aux opérations du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="59fca-112">Pour créer une définition de rôle</span><span class="sxs-lookup"><span data-stu-id="59fca-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="59fca-113">Dans l'Explorateur d'objets, développez un nœud du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="59fca-114">Développez le dossier Sécurité.</span><span class="sxs-lookup"><span data-stu-id="59fca-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="59fca-115">Si vous créez une définition de rôle au niveau d’un élément, cliquez avec le bouton droit sur **Rôles**, puis pointez sur **Nouveau rôle**.</span><span class="sxs-lookup"><span data-stu-id="59fca-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="59fca-116">Ou si vous créez une définition de rôle au niveau système, cliquez avec le bouton droit sur **Rôles système**, puis pointez sur **Nouveau rôle système**.</span><span class="sxs-lookup"><span data-stu-id="59fca-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="59fca-117">Tapez un nom unique pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="59fca-117">Type a unique name for the role.</span></span> <span data-ttu-id="59fca-118">Il doit contenir au moins un caractère.</span><span class="sxs-lookup"><span data-stu-id="59fca-118">A name must contain at least one character.</span></span> <span data-ttu-id="59fca-119">Il peut également comprendre des espaces et certains symboles, à l'exception des caractères ; ?</span><span class="sxs-lookup"><span data-stu-id="59fca-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="59fca-120">: \@ & = +, $/\* \< > | "ou/.</span><span class="sxs-lookup"><span data-stu-id="59fca-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="59fca-121">Tapez éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="59fca-121">Optionally type a description.</span></span> <span data-ttu-id="59fca-122">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , cette description n’est visible que dans cette page.</span><span class="sxs-lookup"><span data-stu-id="59fca-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="59fca-123">Les utilisateurs qui affichent cet élément via le Gestionnaire de rapports peuvent voir la description dans cet outil.</span><span class="sxs-lookup"><span data-stu-id="59fca-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="59fca-124">Sélectionnez les tâches pouvant être effectuées par les membres de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="59fca-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="59fca-125">Pour supprimer ou modifier une définition de rôle</span><span class="sxs-lookup"><span data-stu-id="59fca-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="59fca-126">Dans l'Explorateur d'objets, développez un nœud du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="59fca-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="59fca-127">Développez le dossier Sécurité.</span><span class="sxs-lookup"><span data-stu-id="59fca-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="59fca-128">Pour supprimer ou modifier une définition de rôle au niveau d'un élément, développez le dossier Rôles.</span><span class="sxs-lookup"><span data-stu-id="59fca-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="59fca-129">Effectuez une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="59fca-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="59fca-130">Pour supprimer une définition de rôle, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="59fca-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="59fca-131">La boîte de dialogue **Supprimer un objet** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="59fca-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="59fca-132">Pour modifier une définition de rôle, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="59fca-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="59fca-133">La page Général de la boîte de dialogue **Propriétés de rôle d’utilisateur** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="59fca-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="59fca-134">Sélectionnez les tâches pouvant être effectuées par les membres de ce rôle, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="59fca-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="59fca-135">Pour supprimer ou modifier une définition de rôle au niveau d’un système, développez le dossier **Rôles système** .</span><span class="sxs-lookup"><span data-stu-id="59fca-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="59fca-136">Effectuez une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="59fca-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="59fca-137">Pour supprimer une définition de rôle système, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="59fca-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="59fca-138">La boîte de dialogue **Supprimer un objet** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="59fca-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="59fca-139">Pour modifier une définition de rôle système, cliquez avec le bouton droit sur l’élément, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="59fca-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="59fca-140">La page Général de la boîte de dialogue **Propriétés de rôle système** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="59fca-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="59fca-141">Sélectionnez les tâches pouvant être effectuées par les membres de ce rôle, puis cliquez sur **OK** pour appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="59fca-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fca-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59fca-142">See Also</span></span>  
 <span data-ttu-id="59fca-143">[Se connecter à un serveur de rapports dans Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="59fca-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="59fca-144">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="59fca-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="59fca-145">Reporting Services pour SQL Server Management Studio &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="59fca-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
