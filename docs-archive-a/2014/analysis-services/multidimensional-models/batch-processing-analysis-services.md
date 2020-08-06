---
title: Traitement par lots (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601151"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="b283b-102">Traitement par lots (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b283b-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="b283b-103">Dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous pouvez utiliser la commande batch pour envoyer plusieurs commandes de traitement au serveur dans une demande unique.</span><span class="sxs-lookup"><span data-stu-id="b283b-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="b283b-104">Le traitement par lots vous offre une méthode pour contrôler les objets qui doivent être traités, et dans quel ordre.</span><span class="sxs-lookup"><span data-stu-id="b283b-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="b283b-105">De plus, un traitement par lots peut s'exécuter en tant que série de travaux autonomes ou en tant que transaction dans laquelle l'échec d'un processus entraîne une annulation de l'ensemble du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b283b-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="b283b-106">Le traitement par lots optimise la disponibilité des données en consolidant et en réduisant la durée nécessaire à la validation des modifications.</span><span class="sxs-lookup"><span data-stu-id="b283b-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="b283b-107">Lorsque vous traitez entièrement une dimension, toute partition qui utilise cette dimension est marquée comme non traitée.</span><span class="sxs-lookup"><span data-stu-id="b283b-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="b283b-108">En conséquence, les cubes qui contiennent les partitions non traitées sont indisponibles pour l'exploration.</span><span class="sxs-lookup"><span data-stu-id="b283b-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="b283b-109">Vous pouvez résoudre ce problème à l'aide d'un travail de traitement par lots en traitant les dimensions avec les partitions affectées.</span><span class="sxs-lookup"><span data-stu-id="b283b-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="b283b-110">L'exécution du travail de traitement par lots en tant que transaction permet de s'assurer que tous les objets inclus dans la transaction demeurent disponibles pour les requêtes jusqu'à ce que tout le traitement soit terminé.</span><span class="sxs-lookup"><span data-stu-id="b283b-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="b283b-111">Lorsque la transaction valide les modifications, des verrous sont placés sur les objets affectés, ce qui les rend temporairement indisponibles, mais globalement, la durée nécessaire pour valider les modifications est moindre que si vous traitiez des objets individuellement.</span><span class="sxs-lookup"><span data-stu-id="b283b-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="b283b-112">Les procédures de cette rubrique décrivent les étapes de traitement complet de dimensions et de partitions.</span><span class="sxs-lookup"><span data-stu-id="b283b-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="b283b-113">Le traitement par lots peut également inclure d'autres options de traitement, telles que le traitement incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="b283b-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="b283b-114">Pour que ces procédures fonctionnent correctement, vous devez utiliser une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existante qui contient au moins deux dimensions et une partition.</span><span class="sxs-lookup"><span data-stu-id="b283b-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="b283b-115">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="b283b-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="b283b-116">Traitement par lots dans SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="b283b-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="b283b-117">Traitement par lots à l'aide de XMLA dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="b283b-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a> <span data-ttu-id="b283b-118">Traitement par lots dans SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="b283b-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="b283b-119">Pour que des objets puissent être traités dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], le projet contenant les objets doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="b283b-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="b283b-120">Pour plus d’informations, consultez [Déployer des projets Analysis Services &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="b283b-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="b283b-121">Ouvrez [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b283b-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="b283b-122">Ouvrez un projet qui a été déployé.</span><span class="sxs-lookup"><span data-stu-id="b283b-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="b283b-123">Dans l'Explorateur de solutions, sous le projet déployé, développez le dossier **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="b283b-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="b283b-124">En maintenant la touche Ctrl enfoncée, cliquez sur chaque dimension répertoriée dans le dossier **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="b283b-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="b283b-125">Cliquez avec le bouton droit sur les dimensions sélectionnées, puis cliquez sur **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="b283b-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="b283b-126">En maintenant la touche Ctrl enfoncée, cliquez sur chaque dimension répertoriée dans **Liste d'objets**.</span><span class="sxs-lookup"><span data-stu-id="b283b-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="b283b-127">Cliquez avec le bouton droit sur les dimensions sélectionnées et cliquez sur **Traiter entièrement**.</span><span class="sxs-lookup"><span data-stu-id="b283b-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="b283b-128">Pour personnaliser le travail de traitement par lots, cliquez sur **Modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b283b-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="b283b-129">Sous **Options de traitement**, marquez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="b283b-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="b283b-130">**Ordre de traitement** a la valeur **Séquentiel**et **Mode de transaction** a la valeur **Une seule transaction**.</span><span class="sxs-lookup"><span data-stu-id="b283b-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="b283b-131">**Option de la table d'écriture différée** a la valeur **Utiliser l'existante**.</span><span class="sxs-lookup"><span data-stu-id="b283b-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="b283b-132">Sous **Objets affectés**, activez la case à cocher **Traiter les objets affectés** .</span><span class="sxs-lookup"><span data-stu-id="b283b-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="b283b-133">Cliquez sur l’onglet **Erreurs de clé de dimension** . Vérifiez que l’option utiliser la configuration d' **erreur par défaut** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b283b-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="b283b-134">Cliquez sur **OK** pour fermer l'écran **Modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="b283b-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="b283b-135">Cliquez sur **Exécuter** sur l'écran **Traiter les objets** pour démarrer le travail de traitement.</span><span class="sxs-lookup"><span data-stu-id="b283b-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="b283b-136">Lorsque la zone **État** indique **Traitement réussi**, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b283b-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="b283b-137">Cliquez sur **Fermer** sur l'écran **Traiter les objets** .</span><span class="sxs-lookup"><span data-stu-id="b283b-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="b283b-138">Traitement par lots à l’aide de XMLA dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="b283b-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="b283b-139">Vous pouvez créer un script XMLA qui exécute le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b283b-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="b283b-140">Commencez en générant un script XMLA dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour chaque objet, puis associez-les dans une seule requête XMLA que vous exécutez de façon interactive ou dans une tâche planifiée.</span><span class="sxs-lookup"><span data-stu-id="b283b-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="b283b-141">Pour obtenir des instructions pas à pas, consultez l' **exemple 2** dans [planifier des tâches d’administration SSAS avec SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span><span class="sxs-lookup"><span data-stu-id="b283b-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b283b-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b283b-142">See Also</span></span>  
 [<span data-ttu-id="b283b-143">Traitement des objets de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="b283b-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
