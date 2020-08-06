---
title: Boîte de dialogue fusionner une partition (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613195"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ebb43-102">Boîte de dialogue Partition de fusion (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="ebb43-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ebb43-103">La boîte de dialogue **Partition de fusion** de **SQL Server Management Studio** permet de fusionner des partitions pour un groupe de mesures d'un cube.</span><span class="sxs-lookup"><span data-stu-id="ebb43-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="ebb43-104">Vous pouvez afficher la boîte de dialogue **Partition de fusion** en cliquant avec le bouton droit sur le dossier Partitions ou sur une partition dans **Explorateur d’objets** et en sélectionnant **Fusionner des partitions** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="ebb43-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ebb43-105">Options</span><span class="sxs-lookup"><span data-stu-id="ebb43-105">Options</span></span>  
 <span data-ttu-id="ebb43-106">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="ebb43-106">**Server**</span></span>  
 <span data-ttu-id="ebb43-107">Sélectionnez le nom de l'instance Analysis Services qui contient la partition cible.</span><span class="sxs-lookup"><span data-stu-id="ebb43-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="ebb43-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ebb43-108">**Name**</span></span>  
 <span data-ttu-id="ebb43-109">Sélectionnez le nom d'une partition existante à utiliser comme cible.</span><span class="sxs-lookup"><span data-stu-id="ebb43-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="ebb43-110">**Folder**</span><span class="sxs-lookup"><span data-stu-id="ebb43-110">**Folder**</span></span>  
 <span data-ttu-id="ebb43-111">Affiche le nom du dossier qui contient la partition cible, si la partition indiquée dans le champ Nom n'utilise pas le dossier par défaut pour l'instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ebb43-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="ebb43-112">**Partitions sources**</span><span class="sxs-lookup"><span data-stu-id="ebb43-112">**Source Partitions**</span></span>  
 <span data-ttu-id="ebb43-113">Affiche une grille qui contient les partitions sources pouvant être fusionnées dans la partition cible.</span><span class="sxs-lookup"><span data-stu-id="ebb43-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebb43-114">Seules peuvent être fusionnées les partitions appartenant au même groupe de mesures qui partagent la même conception d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="ebb43-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="ebb43-115">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebb43-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="ebb43-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="ebb43-116">Column</span></span>|<span data-ttu-id="ebb43-117">Description</span><span class="sxs-lookup"><span data-stu-id="ebb43-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ebb43-118">**Fusionner**</span><span class="sxs-lookup"><span data-stu-id="ebb43-118">**Merge**</span></span>|<span data-ttu-id="ebb43-119">Permet de fusionner la partition source dans la partition cible.</span><span class="sxs-lookup"><span data-stu-id="ebb43-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="ebb43-120">**Nom de la partition**</span><span class="sxs-lookup"><span data-stu-id="ebb43-120">**Partition Name**</span></span>|<span data-ttu-id="ebb43-121">Affiche le nom de la partition source.</span><span class="sxs-lookup"><span data-stu-id="ebb43-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="ebb43-122">**Dernier traitement**</span><span class="sxs-lookup"><span data-stu-id="ebb43-122">**Last Processed**</span></span>|<span data-ttu-id="ebb43-123">Affiche la date et l'heure du dernier traitement de la partition source.</span><span class="sxs-lookup"><span data-stu-id="ebb43-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebb43-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebb43-124">See Also</span></span>  
 <span data-ttu-id="ebb43-125">[Partitions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ebb43-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ebb43-126">Fusionner des partitions dans Analysis Services &#40;SSAS - Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="ebb43-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
