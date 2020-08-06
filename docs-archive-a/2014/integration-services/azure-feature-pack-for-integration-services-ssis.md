---
title: Feature Pack Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696015"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="174e5-102">Feature Pack Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-102">Azure Feature Pack</span></span>
<span data-ttu-id="174e5-103">Le Feature Pack SQL Server Integration Services (SSIS) pour Azure est une extension qui fournit les composants répertoriés dans cette page afin de permettre à SSIS de se connecter aux services Azure, de transférer des données entre des sources de données Azure et locales, et de traiter des données stockées dans Azure.</span><span class="sxs-lookup"><span data-stu-id="174e5-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="174e5-104">Composants du Feature Pack</span><span class="sxs-lookup"><span data-stu-id="174e5-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="174e5-105">Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="174e5-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="174e5-106">Gestionnaire de connexions Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="174e5-107">Gestionnaire de connexions d’abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="174e5-108">Gestionnaire de connexions Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="174e5-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="174e5-109">Gestionnaire de connexions Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="174e5-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="174e5-110">Gestionnaire de connexions Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="174e5-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="174e5-111">Tâches</span><span class="sxs-lookup"><span data-stu-id="174e5-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="174e5-112">Tâche de chargement d’objets blob Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="174e5-113">Tâche de téléchargement d’objets blob Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="174e5-114">Tâche Hive d’Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="174e5-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="174e5-115">[Tâche Pig Azure HDInsight](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="174e5-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="174e5-116">Tâche de création d’un cluster Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="174e5-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="174e5-117">Tâche de suppression d’un cluster Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="174e5-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="174e5-118">Tâche de chargement Azure SQL Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="174e5-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="174e5-119">Tâche du système de fichiers Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="174e5-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="174e5-120">Composants de flux de données</span><span class="sxs-lookup"><span data-stu-id="174e5-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="174e5-121">[Source des objets blob Azure](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="174e5-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="174e5-122">Destination des objets blob Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="174e5-123">Source Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="174e5-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="174e5-124">Destination Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="174e5-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="174e5-125">Énumérateur d’objets BLOB Azure & énumérateur de fichier ADLS.</span><span class="sxs-lookup"><span data-stu-id="174e5-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="174e5-126">Consultez [conteneur de boucles Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="174e5-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="174e5-127">Télécharger le Feature Pack</span><span class="sxs-lookup"><span data-stu-id="174e5-127">Download the Feature Pack</span></span>  
<span data-ttu-id="174e5-128">Téléchargez le Feature Pack SQL Server Integration Services (SSIS) pour Azure.</span><span class="sxs-lookup"><span data-stu-id="174e5-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="174e5-129">Feature Pack Microsoft SQL Server 2014 Integration Services pour Azure</span><span class="sxs-lookup"><span data-stu-id="174e5-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="174e5-130">Prérequis</span><span class="sxs-lookup"><span data-stu-id="174e5-130">Prerequisites</span></span>  
<span data-ttu-id="174e5-131">Avant d’installer le Feature Pack, vous devez vérifier que les conditions préalables suivantes sont remplies.</span><span class="sxs-lookup"><span data-stu-id="174e5-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="174e5-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="174e5-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="174e5-133">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="174e5-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="174e5-134">Scénarios</span><span class="sxs-lookup"><span data-stu-id="174e5-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="174e5-135">Traitement de données volumineuses</span><span class="sxs-lookup"><span data-stu-id="174e5-135">Big Data Processing</span></span>  
 <span data-ttu-id="174e5-136">Utilisez le connecteur Azure pour accomplir le travail suivant de traitement de données volumineuses :</span><span class="sxs-lookup"><span data-stu-id="174e5-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="174e5-137">Utilisez la tâche de téléchargement d'objet blob Azure pour charger des données d'entrée dans le stockage d'objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="174e5-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="174e5-138">Utilisez la tâche de création de cluster Azure HDInsight pour créer un cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="174e5-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="174e5-139">Cette étape est facultative si vous souhaitez utiliser votre propre cluster.</span><span class="sxs-lookup"><span data-stu-id="174e5-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="174e5-140">Utilisez la tâche Hive ou Pig Azure HDInsight pour invoquer un travail Pig ou Hive sur le cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="174e5-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="174e5-141">Utilisez la tâche de suppression de cluster Azure HDInsight pour supprimer le cluster HDInsight après utilisation, si vous avez créé un cluster HDInsight à la demande à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="174e5-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="174e5-142">Utilisez la tâche de téléchargement d'objet blob Azure HDInsight pour télécharger les données de sortie des travaux Pig/Hive à partir du stockage d'objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="174e5-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="174e5-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="174e5-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="174e5-144">Archivage de données de cloud</span><span class="sxs-lookup"><span data-stu-id="174e5-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="174e5-145">Utilisez la destination d'objets blob Azure dans un package SSIS pour écrire des données de sortie dans un stockage d'objets blob Azure, ou la source d'objets blob Azure pour lire des données à partir d'un stockage d'objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="174e5-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="174e5-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="174e5-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="174e5-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="174e5-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="174e5-148">Et utilisez le conteneur de boucles Foreach avec l'énumérateur d'objet blob Azure pour traiter des données dans plusieurs fichiers bob.</span><span class="sxs-lookup"><span data-stu-id="174e5-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="174e5-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="174e5-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  
