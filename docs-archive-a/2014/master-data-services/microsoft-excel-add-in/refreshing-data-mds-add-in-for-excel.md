---
title: Actualisation des données (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708472"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="a593f-102">Actualisation des données (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="a593f-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="a593f-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], actualisez les données lorsque vous souhaitez obtenir les dernières informations du référentiel MDS sans ouvrir une nouvelle feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="a593f-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="a593f-104">Vous pouvez actualiser toutes les cellules ou uniquement une sélection de cellules.</span><span class="sxs-lookup"><span data-stu-id="a593f-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="a593f-105">Cela peut être utile lorsque vous avez inséré des colonnes avec des formules personnalisées ou d'autres données non managées par MDS et que vous souhaitez les conserver.</span><span class="sxs-lookup"><span data-stu-id="a593f-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="a593f-106">Actualisation des données managées MDS</span><span class="sxs-lookup"><span data-stu-id="a593f-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="a593f-107">Vous pouvez actualiser les données managées MDS dans une feuille de calcul active si la feuille de calcul contient déjà des données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="a593f-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="a593f-108">Si vous avez modifié les valeurs d'attribut ou ajouté des membres à la feuille de calcul, vous devez publier vos modifications avant de pouvoir actualiser.</span><span class="sxs-lookup"><span data-stu-id="a593f-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="a593f-109">Actualisation d'une sélection</span><span class="sxs-lookup"><span data-stu-id="a593f-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="a593f-110">Vous avez la possibilité d'actualiser toutes les cellules ou uniquement les cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a593f-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="a593f-111">Les cellules sélectionnées doivent être contigües.</span><span class="sxs-lookup"><span data-stu-id="a593f-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="a593f-112">Si un ensemble de cellules contiguës est sélectionné, toutes les cellules managées MDS appartenant à cet ensemble seront mises à jour pour afficher les valeurs actuellement stockées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="a593f-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="a593f-113">Les lignes et colonnes non modifiées qui ne sont pas managées par MDS ne sont pas affectées.</span><span class="sxs-lookup"><span data-stu-id="a593f-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="a593f-114">Que se produit-il lorsque vous actualisez les données managées MDS ?</span><span class="sxs-lookup"><span data-stu-id="a593f-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="a593f-115">Lorsque vous actualisez les données dans le [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], ce qui arrive aux données gérées par MDS dans la feuille dépend de ce qui a changé dans le référentiel MDS depuis le dernier chargement des données.</span><span class="sxs-lookup"><span data-stu-id="a593f-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="a593f-116">Si de nouveaux membres ont été ajoutés au référentiel, ils sont ajoutés à la fin de la feuille de calcul et sont mis en surbrillance en vert.</span><span class="sxs-lookup"><span data-stu-id="a593f-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="a593f-117">Si des membres ont été supprimés du référentiel, ils sont supprimés de la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="a593f-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="a593f-118">Si une valeur d'attribut a changé dans le référentiel MDS, la valeur dans la feuille de calcul est mise à jour avec la valeur du référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="a593f-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="a593f-119">La couleur de cellule ne change pas.</span><span class="sxs-lookup"><span data-stu-id="a593f-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="a593f-120">Dans la feuille de calcul active, si des données non managées MDS existent dans des lignes sous des données managées MDS, les données non managées peuvent être remplacées.</span><span class="sxs-lookup"><span data-stu-id="a593f-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="a593f-121">Cela se produit lorsque vous actualisez la feuille et de nouvelles lignes de données managées MDS sont ajoutées, se chevauchant avec des données non managées.</span><span class="sxs-lookup"><span data-stu-id="a593f-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="a593f-122">Lorsque vous actualisez, les commentaires sur les cellules managées MDS sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="a593f-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="a593f-123">Actualiser des données managées MDS</span><span class="sxs-lookup"><span data-stu-id="a593f-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="a593f-124">Dans le groupe **Se connecter et charger** du ruban, le bouton **Actualiser** propose deux options, **Actualiser tout** et **Actualiser la sélection**.</span><span class="sxs-lookup"><span data-stu-id="a593f-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="a593f-125">L’action par défaut du bouton du ruban est **Actualiser tout**.</span><span class="sxs-lookup"><span data-stu-id="a593f-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="a593f-126">Pour actualiser la feuille entière avec les valeurs du serveur, cliquez sur le bouton **Actualiser** ou choisissez l’option **Actualiser tout** .</span><span class="sxs-lookup"><span data-stu-id="a593f-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="a593f-127">Pour actualiser uniquement certaines cellules d’une feuille, sélectionnez les cellules (contiguës) et choisissez l’option **Actualiser la sélection** .</span><span class="sxs-lookup"><span data-stu-id="a593f-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a593f-128">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a593f-128">Related Tasks</span></span>  
  
|<span data-ttu-id="a593f-129">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="a593f-129">Task Description</span></span>|<span data-ttu-id="a593f-130">Rubrique</span><span class="sxs-lookup"><span data-stu-id="a593f-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="a593f-131">Créez une connexion à une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a593f-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="a593f-132">Se connecter à un référentiel MDS &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a593f-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="a593f-133">Chargez des données MDS dans Excel.</span><span class="sxs-lookup"><span data-stu-id="a593f-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="a593f-134">Charger des données MDS dans Excel</span><span class="sxs-lookup"><span data-stu-id="a593f-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="a593f-135">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="a593f-135">Related Content</span></span>  
  
-   [<span data-ttu-id="a593f-136">Connexions &#40;Complément MDS pour Excel#41;</span><span class="sxs-lookup"><span data-stu-id="a593f-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="a593f-137">Chargement de données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a593f-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="a593f-138">Complément Master Data Services pour Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a593f-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
