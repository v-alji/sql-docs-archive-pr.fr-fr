---
title: Page déplacer les éléments (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707260"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="f707f-102">Page Déplacer les éléments (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="f707f-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="f707f-103">La page Déplacer les éléments vous permet de déplacer un rapport, un dossier ou un autre élément vers un nouvel emplacement sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f707f-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="f707f-104">Vous pouvez taper le chemin d'accès au nouvel emplacement ou utiliser l'arborescence pour naviguer jusqu'à un nouvel emplacement dans l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f707f-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="f707f-105">Vous pouvez déplacer uniquement les éléments que vous êtes autorisé à déplacer et qui sont stockés sur le serveur de rapports actuel.</span><span class="sxs-lookup"><span data-stu-id="f707f-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="f707f-106">Lorsque vous déplacez un élément qui est référencé par un autre (par exemple, une source de données partagée ou un modèle qui est référencé par de nombreux rapports), les informations de chemin d'accès relatives à cet élément sont automatiquement mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f707f-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="f707f-107">Vous pouvez déplacer une source de données partagée sans interrompre la connexion d'une source de données aux rapports et aux modèles qui l'utilisent.</span><span class="sxs-lookup"><span data-stu-id="f707f-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="f707f-108">Si vous déplacez une source de données partagée ou un modèle vers un dossier pour lequel les utilisateurs n'ont pas d'autorisation, ils seront encore en mesure d'exécuter tout rapport qui référence la source de données ou le modèle, mais ils ne verront pas l'élément dans l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="f707f-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="f707f-109">Pour l' **Emplacement**, spécifiez le chemin d'accès complet au dossier, en commençant par le nom du dossier racine.</span><span class="sxs-lookup"><span data-stu-id="f707f-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="f707f-110">Vous pouvez taper le nom du chemin d'accès ou utiliser l'arborescence pour naviguer jusqu'au dossier désiré.</span><span class="sxs-lookup"><span data-stu-id="f707f-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f707f-111">Il n'est pas possible de déplacer tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="f707f-111">Not all items are movable.</span></span> <span data-ttu-id="f707f-112">Vous ne pouvez pas déplacer des dossiers réservés tels que Dossier de base, Mes Rapports ou Dossiers des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f707f-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="f707f-113">En outre, vous ne pouvez pas déplacer un historique de rapport ou des instantanés vers d'autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="f707f-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="f707f-114">L'historique et les instantanés sont toujours situés au même endroit que le rapport sur lequel ils sont basés et vous ne pouvez y accéder que par l'intermédiaire du rapport.</span><span class="sxs-lookup"><span data-stu-id="f707f-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="f707f-115">Navigation</span><span class="sxs-lookup"><span data-stu-id="f707f-115">Navigation</span></span>  
 <span data-ttu-id="f707f-116">Utilisez les procédures suivantes pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f707f-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="f707f-117">Pour ouvrir la page Déplacer des éléments dans la page Contenu en Mode Détails</span><span class="sxs-lookup"><span data-stu-id="f707f-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="f707f-118">Ouvrez le Gestionnaire de rapports et parcourez l'arborescence jusqu'au dossier qui contient un élément à déplacer.</span><span class="sxs-lookup"><span data-stu-id="f707f-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="f707f-119">Vous pouvez également déplacer des éléments à partir de la page d'accueil du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="f707f-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="f707f-120">Dans la barre d'outils, cliquez sur **Mode Détails**.</span><span class="sxs-lookup"><span data-stu-id="f707f-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f707f-121">Si vous voyez uniquement **Mode Mosaïques**, c'est que le **Mode Détails**est déjà activé.</span><span class="sxs-lookup"><span data-stu-id="f707f-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="f707f-122">Activez la case à cocher située en regard d'un élément, puis cliquez sur **Déplacer** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="f707f-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="f707f-123">Vous pouvez sélectionner plusieurs cases si vous souhaitez déplacer plusieurs éléments vers le même nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="f707f-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="f707f-124">Pour ouvrir la page Déplacer les éléments dans la page Contenu en Mode Mosaïques</span><span class="sxs-lookup"><span data-stu-id="f707f-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="f707f-125">Ouvrez le Gestionnaire de rapports et parcourez l'arborescence jusqu'au dossier qui contient un élément à déplacer.</span><span class="sxs-lookup"><span data-stu-id="f707f-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="f707f-126">Vous pouvez également déplacer des éléments à partir de la page d'accueil du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="f707f-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="f707f-127">Dans la barre d'outils, cliquez sur **Mode Mosaïques**.</span><span class="sxs-lookup"><span data-stu-id="f707f-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f707f-128">Si vous voyez uniquement **Mode Détails**, c'est que le **Mode Mosaïques**est déjà activé.</span><span class="sxs-lookup"><span data-stu-id="f707f-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="f707f-129">Pointez sur un élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="f707f-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="f707f-130">Dans le menu déroulant, cliquez sur **Déplacer**.</span><span class="sxs-lookup"><span data-stu-id="f707f-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="f707f-131">Pour ouvrir la page Déplacer les éléments dans la page des propriétés générales d'un élément</span><span class="sxs-lookup"><span data-stu-id="f707f-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="f707f-132">Ouvrez le Gestionnaire de rapports et parcourez l'arborescence jusqu'au dossier qui contient un élément à déplacer.</span><span class="sxs-lookup"><span data-stu-id="f707f-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="f707f-133">Vous pouvez également déplacer des éléments à partir de la page d'accueil du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="f707f-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="f707f-134">Pointez sur un élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="f707f-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="f707f-135">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="f707f-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="f707f-136">La page des propriétés générales pour un élément s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="f707f-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="f707f-137">Dans la barre d'outils de l'élément, cliquez sur **Déplacer**.</span><span class="sxs-lookup"><span data-stu-id="f707f-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f707f-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f707f-138">See Also</span></span>  
 <span data-ttu-id="f707f-139">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="f707f-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="f707f-140">[Page Propriétés générales, dossiers &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f707f-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="f707f-141">[Page Propriétés générales, rapports &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f707f-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="f707f-142">[Page Propriétés générales, ressources &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f707f-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="f707f-143">[Page Propriétés générales, sources de données partagées &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f707f-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="f707f-144">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="f707f-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
