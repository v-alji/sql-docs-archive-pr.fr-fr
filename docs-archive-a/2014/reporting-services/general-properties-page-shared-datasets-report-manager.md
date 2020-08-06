---
title: Page Propriétés générales, datasets partagés (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10798e41-24c3-4e69-893b-7ee6af7fc958
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 31825e61cb40505e9167cc2b930a5b79e5aaa013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615018"
---
# <a name="general-properties-page-shared-datasets-report-manager"></a><span data-ttu-id="2213c-102">Page Propriétés générales, Datasets partagés (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="2213c-102">General Properties Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="2213c-103">La page Dataset partagé permet d'afficher et de gérer les propriétés d'un élément de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="2213c-103">Use the Shared Dataset page to view and manage properties for a shared dataset item.</span></span>  
  
 <span data-ttu-id="2213c-104">Dans le Gestionnaire de rapports, vous ne pouvez pas afficher ou modifier la définition du dataset partagé, y compris la requête.</span><span class="sxs-lookup"><span data-stu-id="2213c-104">From Report Manager, you cannot view or change the shared dataset definition, including the query.</span></span> <span data-ttu-id="2213c-105">Pour modifier la définition, vous devez utiliser un outil de création permettant d'ouvrir et de modifier la définition, puis l'enregistrer sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-105">To change the definition, you must use an authoring tool to open and modify the definition and then save it to the report server.</span></span>  
  
 <span data-ttu-id="2213c-106">Avec un dataset partagé, vous pouvez gérer les paramètres d'un dataset séparément des rapports, des composants et des autres éléments de catalogue qui l'utilisent.</span><span class="sxs-lookup"><span data-stu-id="2213c-106">With a shared dataset, you can manage the settings for a dataset separately from reports, components, and other catalog items that use it.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2213c-107">Navigation</span><span class="sxs-lookup"><span data-stu-id="2213c-107">Navigation</span></span>  
 <span data-ttu-id="2213c-108">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2213c-108">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-shared-dataset-properties-page-for-a-shared-dataset"></a><span data-ttu-id="2213c-109">Pour ouvrir la page des propriétés de dataset partagé d'un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="2213c-109">To open the Shared Dataset properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="2213c-110">Ouvrez le Gestionnaire de rapports et recherchez le dataset partagé dont vous souhaitez configurer les propriétés.</span><span class="sxs-lookup"><span data-stu-id="2213c-110">Open Report Manager, and locate shared dataset for which you want to configure properties.</span></span>  
  
2.  <span data-ttu-id="2213c-111">Pointez sur le dataset partagé, puis cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="2213c-111">Hover over the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2213c-112">Dans la liste déroulante, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="2213c-112">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="2213c-113">La page des propriétés générales s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2213c-113">The General properties page opens.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2213c-114">Options</span><span class="sxs-lookup"><span data-stu-id="2213c-114">Options</span></span>  
 <span data-ttu-id="2213c-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="2213c-115">**Name**</span></span>  
 <span data-ttu-id="2213c-116">Permet de taper le nom du dataset partagé afin d'identifier l'élément dans l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-116">Type a name for the shared dataset that is used to identify the item within the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="2213c-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="2213c-117">**Description**</span></span>  
 <span data-ttu-id="2213c-118">Permet de fournir des informations sur le dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="2213c-118">Provide information about the shared dataset.</span></span> <span data-ttu-id="2213c-119">Cette description apparaît dans la page Contenu.</span><span class="sxs-lookup"><span data-stu-id="2213c-119">This description appears on the Contents page.</span></span>  
  
 <span data-ttu-id="2213c-120">**Masquer en mode Liste**</span><span class="sxs-lookup"><span data-stu-id="2213c-120">**Hide in list view**</span></span>  
 <span data-ttu-id="2213c-121">Permet de masquer le dataset partagé pour les utilisateurs qui recourent au mode Liste dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-121">Hide the shared dataset from users who are using list view mode in Report Manager.</span></span> <span data-ttu-id="2213c-122">Le mode Liste est le format d'affichage par défaut lorsque vous parcourez l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-122">List view mode is the default view format when browsing the report server folder hierarchy.</span></span> <span data-ttu-id="2213c-123">En mode Liste, les noms et les descriptions des éléments sont affichés sur la largeur de la page.</span><span class="sxs-lookup"><span data-stu-id="2213c-123">In list view, item names and descriptions flow across the page.</span></span> <span data-ttu-id="2213c-124">Un autre format d'affichage, le mode Détails, est également disponible.</span><span class="sxs-lookup"><span data-stu-id="2213c-124">The alternative format is details view.</span></span> <span data-ttu-id="2213c-125">En mode Détails, les descriptions ne sont pas affichées, mais cette vue fournit d'autres informations sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="2213c-125">Details view omits descriptions, but includes other information about the item.</span></span> <span data-ttu-id="2213c-126">Vous pouvez masquer un élément en mode Liste, mais pas en mode Détails.</span><span class="sxs-lookup"><span data-stu-id="2213c-126">Although you can hide an item in list view, you cannot hide an item in details view.</span></span> <span data-ttu-id="2213c-127">Pour restreindre l'accès à un élément, vous devez créer une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="2213c-127">If you want to restrict access to an item, you must create a role assignment.</span></span>  
  
 <span data-ttu-id="2213c-128">**Délai de requête**</span><span class="sxs-lookup"><span data-stu-id="2213c-128">**Query execution timeout**</span></span>  
 <span data-ttu-id="2213c-129">Tapez le nombre de secondes avant l’expiration de la requête. Si la valeur est égale à 0, la requête n’expire pas.</span><span class="sxs-lookup"><span data-stu-id="2213c-129">Type the number of seconds until the query times out. If it is 0, the query does not time out.</span></span>  
  
 <span data-ttu-id="2213c-130">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="2213c-130">**Apply**</span></span>  
 <span data-ttu-id="2213c-131">Enregistrez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="2213c-131">Save your changes.</span></span>  
  
 <span data-ttu-id="2213c-132">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="2213c-132">**Delete**</span></span>  
 <span data-ttu-id="2213c-133">Permet de supprimer le dataset partagé de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-133">Remove the shared dataset from the report server database.</span></span> <span data-ttu-id="2213c-134">La suppression d'un dataset partagé désactive les rapports ou les versions mises en cache.</span><span class="sxs-lookup"><span data-stu-id="2213c-134">Deleting a shared dataset deactivates any reports or cached versions.</span></span> <span data-ttu-id="2213c-135">Pour réactiver un rapport, vous devez l'ouvrir dans un outil de création de rapports et spécifier un dataset portant le même nom et utilisant la même collection de champs.</span><span class="sxs-lookup"><span data-stu-id="2213c-135">To reactivate a report, you must open each one in a report authoring tool, and specify a dataset with the same name and the same field collection.</span></span> <span data-ttu-id="2213c-136">Vous pouvez également mettre à jour chaque référence de région de données pour qu'elle utilise un dataset différent avec la même collection de champs.</span><span class="sxs-lookup"><span data-stu-id="2213c-136">Alternatively, you can update each data region reference to use a different dataset with the same field collection.</span></span>  
  
 <span data-ttu-id="2213c-137">**Déplacer**</span><span class="sxs-lookup"><span data-stu-id="2213c-137">**Move**</span></span>  
 <span data-ttu-id="2213c-138">Permet de déplacer un dataset partagé dans l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2213c-138">Relocate a shared dataset within the report server folder hierarchy.</span></span> <span data-ttu-id="2213c-139">Un clic sur ce bouton permet d'ouvrir la page Déplacer les éléments dans laquelle vous pouvez parcourir les dossiers pour sélectionner un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="2213c-139">Clicking this button opens the Move Items page, on which you can browse through folders for a new folder location.</span></span> <span data-ttu-id="2213c-140">Pour plus d’informations, consultez [page déplacer des éléments &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2213c-140">For more information, see [Move Items Page &#40;Report Manager&#41;](../../2014/reporting-services/move-items-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="2213c-141">**Télécharger**</span><span class="sxs-lookup"><span data-stu-id="2213c-141">**Download**</span></span>  
 <span data-ttu-id="2213c-142">Permet d'extraire une copie de la définition du dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="2213c-142">Extract a copy of the shared dataset definition.</span></span> <span data-ttu-id="2213c-143">Selon les associations de fichiers définies sur votre ordinateur, le fichier s'ouvre dans Visual Studio ou une autre application.</span><span class="sxs-lookup"><span data-stu-id="2213c-143">Depending on the file associations defined on your computer, the file will open in Visual Studio or a different application.</span></span> <span data-ttu-id="2213c-144">Dans la plupart des cas, le dataset partagé s'ouvre dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="2213c-144">In most cases, the shared dataset opens as an XML file.</span></span>  
  
 <span data-ttu-id="2213c-145">**Replace**</span><span class="sxs-lookup"><span data-stu-id="2213c-145">**Replace**</span></span>  
 <span data-ttu-id="2213c-146">Permet de remplacer la définition du dataset partagé par une définition différente d'un fichier .rds situé dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="2213c-146">Replace the shared dataset definition with a different one from an .rsd file located on the file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2213c-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2213c-147">See Also</span></span>  
 <span data-ttu-id="2213c-148">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-148">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="2213c-149">[Page contenu &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-149">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="2213c-150">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-150">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="2213c-151">[Options d’actualisation du cache &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-151">[Cache Refresh Options &#40;Report Manager&#41;](../../2014/reporting-services/cache-refresh-options-report-manager.md) </span></span>  
 <span data-ttu-id="2213c-152">[Page mise en cache, datasets partagés &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-152">[Caching Page, Shared Datasets &#40;Report Manager&#41;](../../2014/reporting-services/caching-page-shared-datasets-report-manager.md) </span></span>  
 <span data-ttu-id="2213c-153">[Gérer des datasets partagés](report-data/manage-shared-datasets.md) </span><span class="sxs-lookup"><span data-stu-id="2213c-153">[Manage Shared Datasets](report-data/manage-shared-datasets.md) </span></span>  
 [<span data-ttu-id="2213c-154">Mettre en cache les datasets partagés &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2213c-154">Cache Shared Datasets &#40;SSRS&#41;</span></span>](report-server/cache-shared-datasets-ssrs.md)  
  
  
