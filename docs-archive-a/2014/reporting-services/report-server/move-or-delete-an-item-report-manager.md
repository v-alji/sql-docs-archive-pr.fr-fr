---
title: Déplacer ou supprimer un élément (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695284"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="ee159-102">Déplacer ou supprimer un élément (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="ee159-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="ee159-103">Les rapports et les éléments connexes que vous publiez sur un serveur de rapports sont stockés dans des dossiers.</span><span class="sxs-lookup"><span data-stu-id="ee159-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="ee159-104">Vous pouvez déplacer ces éléments dans un dossier différent de sorte que les références à ces éléments soient gérées automatiquement par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee159-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="ee159-105">Avant de supprimer un élément, demandez-vous si d'autres éléments en dépendent.</span><span class="sxs-lookup"><span data-stu-id="ee159-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="ee159-106">Déplacer un élément</span><span class="sxs-lookup"><span data-stu-id="ee159-106">Move an Item</span></span>  
 <span data-ttu-id="ee159-107">Vous pouvez déplacer des éléments de serveur de rapports vers des emplacements de dossiers dans l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee159-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="ee159-108">Lorsque vous déplacez un élément, toutes les propriétés (y compris les paramètres de sécurité) accompagnent l'élément vers son nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="ee159-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="ee159-109">Lorsque vous déplacez un dossier, tous les éléments qu'il contient l'accompagnent.</span><span class="sxs-lookup"><span data-stu-id="ee159-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="ee159-110">Dans le Gestionnaire de rapports, les éléments que vous pouvez déplacer sont indiqués dans l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="ee159-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="ee159-111">Le tableau suivant indique l'icône associée à chaque élément pouvant être déplacé.</span><span class="sxs-lookup"><span data-stu-id="ee159-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="ee159-112">Icône</span><span class="sxs-lookup"><span data-stu-id="ee159-112">Icon</span></span>|<span data-ttu-id="ee159-113">Élément pouvant être déplacé</span><span class="sxs-lookup"><span data-stu-id="ee159-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="ee159-114">![Report icon](../media/hlp-16doc.gif "Icône de rapport")</span><span class="sxs-lookup"><span data-stu-id="ee159-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="ee159-115">Rapport</span><span class="sxs-lookup"><span data-stu-id="ee159-115">Report</span></span>|  
|<span data-ttu-id="ee159-116">![Icône Rapport lié](../media/hlp-16linked.gif "Icône Rapport lié")</span><span class="sxs-lookup"><span data-stu-id="ee159-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="ee159-117">Rapport lié</span><span class="sxs-lookup"><span data-stu-id="ee159-117">Linked report</span></span>|  
|<span data-ttu-id="ee159-118">![Icône de dossier](../media/hlp-16folder.gif "Icône de dossier")</span><span class="sxs-lookup"><span data-stu-id="ee159-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="ee159-119">Dossier</span><span class="sxs-lookup"><span data-stu-id="ee159-119">Folder</span></span>|  
|<span data-ttu-id="ee159-120">![icône de ressource générique](../media/hlp-16file.gif "icône de ressource générique")</span><span class="sxs-lookup"><span data-stu-id="ee159-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="ee159-121">Ressource générique</span><span class="sxs-lookup"><span data-stu-id="ee159-121">Generic resource</span></span>|  
|<span data-ttu-id="ee159-122">![Shared data source icon](../media/hlp-16datasource.png "Icône de source de données partagée")</span><span class="sxs-lookup"><span data-stu-id="ee159-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="ee159-123">Source de données partagée</span><span class="sxs-lookup"><span data-stu-id="ee159-123">Shared data source</span></span>|  
||<span data-ttu-id="ee159-124">Dataset partagé</span><span class="sxs-lookup"><span data-stu-id="ee159-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="ee159-125">Les éléments avec lesquels vous travaillez ne peuvent pas tous être déplacés.</span><span class="sxs-lookup"><span data-stu-id="ee159-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="ee159-126">Par exemple, il n'est pas possible de déplacer les éléments qui sont associés à un rapport, comme les abonnements ou l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="ee159-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="ee159-127">Ces éléments se déplacent avec leurs rapports associés.</span><span class="sxs-lookup"><span data-stu-id="ee159-127">Those items move with their associated reports.</span></span> <span data-ttu-id="ee159-128">Il n'est pas non plus possible de déplacer des éléments, comme les planifications partagées, qui existent à l'extérieur de l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="ee159-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="ee159-129">Vous ne pouvez pas déplacer des éléments si vous n'avez pas l'autorisation de le faire.</span><span class="sxs-lookup"><span data-stu-id="ee159-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="ee159-130">L'autorisation pour déplacer un élément est transmise lorsque les tâches suivantes sont sélectionnées dans votre attribution de rôle pour l'élément considéré : « Gérer les rapports », « Gérer les modèles », « Gérer les dossiers » et « Gérer les sources de données ».</span><span class="sxs-lookup"><span data-stu-id="ee159-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="ee159-131">Pour déplacer un élément à partir de la page Contenu</span><span class="sxs-lookup"><span data-stu-id="ee159-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="ee159-132">Démarrer [Gestionnaire de rapports &#40;le mode natif SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ee159-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="ee159-133">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis recherchez l’élément à déplacer.</span><span class="sxs-lookup"><span data-stu-id="ee159-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="ee159-134">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="ee159-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="ee159-135">Dans le menu déroulant, cliquez sur **Déplacer**.</span><span class="sxs-lookup"><span data-stu-id="ee159-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="ee159-136">Dans **Emplacement**, spécifiez le dossier dans lequel placer l’élément.</span><span class="sxs-lookup"><span data-stu-id="ee159-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="ee159-137">Vous pouvez taper le nom de dossier complet ou utiliser l'option de navigation dans l'arborescence pour accéder au dossier.</span><span class="sxs-lookup"><span data-stu-id="ee159-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="ee159-138">Vous pouvez aussi accéder à l’objet à déplacer, cliquer sur **Propriétés**, puis sur **Déplacer** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="ee159-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="ee159-139">Supprimer un élément</span><span class="sxs-lookup"><span data-stu-id="ee159-139">Delete an item</span></span>  
 <span data-ttu-id="ee159-140">Avant de supprimer un élément, déterminez s'il est utilisé par d'autres éléments.</span><span class="sxs-lookup"><span data-stu-id="ee159-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="ee159-141">Par exemple, si vous supprimez une source de données partagée, les rapports et les modèles qui l'utilisent ne pourront plus s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="ee159-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="ee159-142">Si vous supprimez un rapport, les abonnements et l'historique de rapport associés sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="ee159-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="ee159-143">Pour rechercher des éléments dépendants pour un élément, consultez la page [éléments dépendants &#40;Gestionnaire de rapports&#41;]. /dependent-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ee159-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="ee159-144">Pour supprimer un rapport ou un élément</span><span class="sxs-lookup"><span data-stu-id="ee159-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="ee159-145">Démarrer [Gestionnaire de rapports &#40;le mode natif SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ee159-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="ee159-146">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis recherchez l’élément à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ee159-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="ee159-147">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="ee159-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="ee159-148">Dans le menu déroulant, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ee159-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee159-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee159-149">See Also</span></span>  
 <span data-ttu-id="ee159-150">[Page contenu &#40;Gestionnaire de rapports&#41;]. /contents-page-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="ee159-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="ee159-151">Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee159-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
