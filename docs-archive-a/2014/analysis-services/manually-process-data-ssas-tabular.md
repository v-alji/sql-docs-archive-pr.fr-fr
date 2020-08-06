---
title: Traiter manuellement les données (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612581"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="3df36-102">Traiter manuellement les données (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="3df36-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="3df36-103">Cette rubrique décrit la procédure permettant de traiter manuellement des données d'espace de travail dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3df36-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3df36-104">Lorsque vous créez un modèle tabulaire qui utilise des données externes, vous pouvez actualiser manuellement les données à l'aide de la commande Traiter.</span><span class="sxs-lookup"><span data-stu-id="3df36-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="3df36-105">Vous pouvez traiter une table unique, toutes les tables du modèle, ou une ou plusieurs partitions.</span><span class="sxs-lookup"><span data-stu-id="3df36-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="3df36-106">Chaque fois que vous traitez des données, vous pouvez également être amené à recalculer les données.</span><span class="sxs-lookup"><span data-stu-id="3df36-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="3df36-107">Le traitement de données consiste à obtenir les données les plus récentes à partir des sources externes.</span><span class="sxs-lookup"><span data-stu-id="3df36-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="3df36-108">Recalculer implique mettre à jour le résultat de toute formule qui utilise les données.</span><span class="sxs-lookup"><span data-stu-id="3df36-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="3df36-109">Sections de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="3df36-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="3df36-110">Traiter manuellement les données</span><span class="sxs-lookup"><span data-stu-id="3df36-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="3df36-111">Progression du traitement des données</span><span class="sxs-lookup"><span data-stu-id="3df36-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="3df36-112">Traiter manuellement les données</span><span class="sxs-lookup"><span data-stu-id="3df36-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="3df36-113">Pour traiter des données pour une seule table ou toutes les tables d'un modèle</span><span class="sxs-lookup"><span data-stu-id="3df36-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="3df36-114">Dans le générateur de modèles, cliquez sur la table que vous souhaitez traiter.</span><span class="sxs-lookup"><span data-stu-id="3df36-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="3df36-115">Dans le menu **Modèle** , cliquez sur **Traiter**, puis sur **Traiter** ou **Traiter tout**.</span><span class="sxs-lookup"><span data-stu-id="3df36-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="3df36-116">Pour traiter les données de toutes les tables qui utilisent la même connexion</span><span class="sxs-lookup"><span data-stu-id="3df36-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="3df36-117">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Connexions existantes**.</span><span class="sxs-lookup"><span data-stu-id="3df36-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="3df36-118">Dans la boîte de dialogue **Connexions existantes** , sélectionnez une connexion, puis cliquez sur **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="3df36-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="3df36-119">Pour traiter des données pour une ou plusieurs partitions</span><span class="sxs-lookup"><span data-stu-id="3df36-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="3df36-120">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , pointez sur **Traiter**, puis cliquez sur **Traiter les partitions**.</span><span class="sxs-lookup"><span data-stu-id="3df36-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="3df36-121">Dans la boîte de dialogue **Traiter les partitions** , dans la zone **Mode**, sélectionnez l'un des modes de traitement suivants :</span><span class="sxs-lookup"><span data-stu-id="3df36-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="3df36-122">Mode</span><span class="sxs-lookup"><span data-stu-id="3df36-122">Mode</span></span>|<span data-ttu-id="3df36-123">Description</span><span class="sxs-lookup"><span data-stu-id="3df36-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="3df36-124">**Traiter par défaut**</span><span class="sxs-lookup"><span data-stu-id="3df36-124">**Process Default**</span></span>|<span data-ttu-id="3df36-125">Détecte l'état de traitement d'un objet de partition et effectue le traitement nécessaire pour faire passer les objets de partition non traités ou traités partiellement dans un état de traitement complet.</span><span class="sxs-lookup"><span data-stu-id="3df36-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="3df36-126">Les données des partitions et des tables vides sont chargées ; les hiérarchies, les colonnes calculées et les relations sont créées ou reconstruites.</span><span class="sxs-lookup"><span data-stu-id="3df36-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="3df36-127">**Traiter entièrement**</span><span class="sxs-lookup"><span data-stu-id="3df36-127">**Process Full**</span></span>|<span data-ttu-id="3df36-128">Traite un objet de partition et tous les objets qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="3df36-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="3df36-129">Lorsque la commande Traiter entièrement est exécutée pour un objet qui a déjà été traité, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] supprime toutes les données de l'objet, puis traite l'objet.</span><span class="sxs-lookup"><span data-stu-id="3df36-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="3df36-130">Ce type de traitement est obligatoire lorsqu'une modification structurelle a été apportée à un objet.</span><span class="sxs-lookup"><span data-stu-id="3df36-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="3df36-131">**Traiter des données**</span><span class="sxs-lookup"><span data-stu-id="3df36-131">**Process Data**</span></span>|<span data-ttu-id="3df36-132">Chargez les données dans une partition ou une table sans reconstruire les hiérarchies ou les relations ni recalculer les colonnes calculées et les mesures.</span><span class="sxs-lookup"><span data-stu-id="3df36-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="3df36-133">**Traiter l'effacement**</span><span class="sxs-lookup"><span data-stu-id="3df36-133">**Process Clear**</span></span>|<span data-ttu-id="3df36-134">Supprime toutes les données d'une partition.</span><span class="sxs-lookup"><span data-stu-id="3df36-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="3df36-135">**Traiter l'ajout**</span><span class="sxs-lookup"><span data-stu-id="3df36-135">**Process Add**</span></span>|<span data-ttu-id="3df36-136">Mise à jour incrémentielle de la partition avec de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="3df36-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="3df36-137">Dans la liste des partitions, sélectionnez les partitions à traiter, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3df36-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a><span data-ttu-id="3df36-138">Progression du traitement des données</span><span class="sxs-lookup"><span data-stu-id="3df36-138">Data Process Progress</span></span>  
 <span data-ttu-id="3df36-139">La boîte de dialogue **Progression du traitement des données** vous permet de surveiller le traitement des données que vous avez importées dans le modèle à partir d'une source externe.</span><span class="sxs-lookup"><span data-stu-id="3df36-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="3df36-140">Pour accéder à cette boîte de dialogue, cliquez sur le menu **Modèle** , puis sur **Traiter les partitions**, **Traiter la table** ou **Traiter tout**.</span><span class="sxs-lookup"><span data-stu-id="3df36-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="3df36-141">**État**</span><span class="sxs-lookup"><span data-stu-id="3df36-141">**Status**</span></span>  
 <span data-ttu-id="3df36-142">Indique si l'opération de traitement a abouti ou non.</span><span class="sxs-lookup"><span data-stu-id="3df36-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="3df36-143">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3df36-143">**Details**</span></span>  
 <span data-ttu-id="3df36-144">Répertorie les tables et les vues importées, le nombre des lignes importées, et fournit un lien vers un rapport concernant les éventuels problèmes.</span><span class="sxs-lookup"><span data-stu-id="3df36-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="3df36-145">**Arrêter l'actualisation**</span><span class="sxs-lookup"><span data-stu-id="3df36-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="3df36-146">Cliquez pour arrêter l'opération de traitement.</span><span class="sxs-lookup"><span data-stu-id="3df36-146">Click to halt the process operation.</span></span> <span data-ttu-id="3df36-147">Cette option est utile si l'opération prend trop de temps ou génère trop d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="3df36-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df36-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3df36-148">See Also</span></span>  
 <span data-ttu-id="3df36-149">[Traiter des données &#40;tabulaires SSAS&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="3df36-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="3df36-150">Dépanner le traitement des données &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="3df36-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
