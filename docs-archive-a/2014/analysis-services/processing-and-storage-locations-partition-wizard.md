---
title: Emplacements de traitement et de stockage (Assistant Partition) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708712"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="4edc9-102">Emplacements pour le traitement et le stockage (Assistant Partition)</span><span class="sxs-lookup"><span data-stu-id="4edc9-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="4edc9-103">Utilisez la page **Emplacements pour le traitement et le stockage** pour spécifier l’instance [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] du cube qui possède la partition, ainsi que l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui stocke les données de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="4edc9-104">Vous pouvez définir une partition distante en spécifiant une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] distante ou un emplacement de stockage différent de l'emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="4edc9-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="4edc9-105">Pour plus d’informations sur les partitions distantes, consultez [Partitions distantes](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="4edc9-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="4edc9-106">Options d'emplacement du traitement</span><span class="sxs-lookup"><span data-stu-id="4edc9-106">Processing location Options</span></span>  
 <span data-ttu-id="4edc9-107">**Instance de serveur actuelle**</span><span class="sxs-lookup"><span data-stu-id="4edc9-107">**Current server instance**</span></span>  
 <span data-ttu-id="4edc9-108">Rend l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] active responsable du traitement de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="4edc9-109">**Source de données Analysis Services distante**</span><span class="sxs-lookup"><span data-stu-id="4edc9-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="4edc9-110">Rend une instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] distante responsable du traitement de cette partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="4edc9-111">Dans la liste déroulante, sélectionnez la source de données qui représente l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] distante qui sera responsable du traitement de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4edc9-112">Une erreur se produit si vous sélectionnez une source de données dans laquelle la propriété de la chaîne de connexion `Initial Catalog` ne définit pas une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] valide ou si la base de données spécifiée dans la chaîne de connexion `Initial Catalog` ne prend pas en charge les partitions distantes (autrement dit, si la propriété `MasterDatasourceID` de la base de données n'est pas configurée avec une valeur valide).</span><span class="sxs-lookup"><span data-stu-id="4edc9-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="4edc9-113">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="4edc9-113">**New**</span></span>  
 <span data-ttu-id="4edc9-114">Crée une nouvelle source de données qui représente l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] distante responsable du traitement de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="4edc9-115">Options de l'emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="4edc9-115">Storage location Options</span></span>  
 <span data-ttu-id="4edc9-116">**Emplacement du serveur par défaut**</span><span class="sxs-lookup"><span data-stu-id="4edc9-116">**Default server location**</span></span>  
 <span data-ttu-id="4edc9-117">Le dossier de données de l'instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] active est l'emplacement de stockage des données d'agrégation et d'indexation de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="4edc9-118">**Dossier spécifié**</span><span class="sxs-lookup"><span data-stu-id="4edc9-118">**Specified folder**</span></span>  
 <span data-ttu-id="4edc9-119">Emplacement de stockage des données d'agrégation et d'indexation de la partition.</span><span class="sxs-lookup"><span data-stu-id="4edc9-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="4edc9-120">**...**</span><span class="sxs-lookup"><span data-stu-id="4edc9-120">**...**</span></span>  
 <span data-ttu-id="4edc9-121">Affiche la boîte de dialogue **Rechercher un dossier distant** dans laquelle vous sélectionnez un dossier pour l’option **Dossier spécifié**.</span><span class="sxs-lookup"><span data-stu-id="4edc9-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edc9-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4edc9-122">See Also</span></span>  
 <span data-ttu-id="4edc9-123">[Aide (F1) de l’Assistant partition &#40;Analysis Services-données multidimensionnelles&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4edc9-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="4edc9-124">[Partitions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4edc9-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4edc9-125">Boîte de dialogue Rechercher un dossier distant &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="4edc9-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  
