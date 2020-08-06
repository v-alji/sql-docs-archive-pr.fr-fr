---
title: Création de cluster Azure HDInsight, tâche | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697071"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="d24d8-102">Tâche de création d’un cluster Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="d24d8-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="d24d8-103">La **tâche de création de cluster Azure HDInsight** permet à un package SSIS de créer un cluster Azure HDInsight dans le groupe de ressources et l’abonnement Azure spécifiés.</span><span class="sxs-lookup"><span data-stu-id="d24d8-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="d24d8-104">La création d’un cluster HDInsight peut prendre 10 à 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="d24d8-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="d24d8-105">Il existe un coût associé à la création et à l’exécution d’un cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="d24d8-106">Pour plus d’informations, consultez [Tarification HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/).</span><span class="sxs-lookup"><span data-stu-id="d24d8-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="d24d8-107">Pour ajouter une **tâche de création de cluster Azure HDInsight**, faites-la glisser sur le concepteur SSIS, double-cliquez dessus ou cliquez dessus avec le bouton droit, puis cliquez sur **Modifier** pour afficher la boîte de dialogue **Éditeur de la tâche de création de cluster Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="d24d8-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="d24d8-108">Le tableau suivant décrit les champs de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d24d8-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d24d8-109">**Champ**</span><span class="sxs-lookup"><span data-stu-id="d24d8-109">**Field**</span></span>|<span data-ttu-id="d24d8-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="d24d8-110">**Description**</span></span>|  
|<span data-ttu-id="d24d8-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="d24d8-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="d24d8-112">Sélectionnez un gestionnaire de connexions Azure Resource Manager existant ou créez-en un qui sera utilisé pour créer le cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d24d8-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="d24d8-113">AzureStorageConnection</span></span>|<span data-ttu-id="d24d8-114">Sélectionnez un gestionnaire de connexions Azure Storage existant ou créez-en un nouveau qui fait référence à un compte Azure Storage qui sera associé au cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="d24d8-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="d24d8-115">SubscriptionId</span></span>|<span data-ttu-id="d24d8-116">Spécifiez l’ID de l’abonnement dans lequel le cluster HDInsight sera créé.</span><span class="sxs-lookup"><span data-stu-id="d24d8-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="d24d8-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="d24d8-117">ResourceGroup</span></span>|<span data-ttu-id="d24d8-118">Spécifiez le groupe de ressources Azure dans lequel le cluster HDInsight sera créé.</span><span class="sxs-lookup"><span data-stu-id="d24d8-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="d24d8-119">Emplacement</span><span class="sxs-lookup"><span data-stu-id="d24d8-119">Location</span></span>|<span data-ttu-id="d24d8-120">Spécifiez l’emplacement du cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="d24d8-121">Le cluster doit être créé au même emplacement que le compte de stockage Azure spécifié.</span><span class="sxs-lookup"><span data-stu-id="d24d8-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="d24d8-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="d24d8-122">ClusterName</span></span>|<span data-ttu-id="d24d8-123">Spécifiez un nom pour le cluster HDInsight à créer.</span><span class="sxs-lookup"><span data-stu-id="d24d8-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="d24d8-124">clusterSize</span><span class="sxs-lookup"><span data-stu-id="d24d8-124">ClusterSize</span></span>|<span data-ttu-id="d24d8-125">Spécifiez le nombre de nœuds à créer dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="d24d8-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="d24d8-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="d24d8-126">BlobContainer</span></span>|<span data-ttu-id="d24d8-127">Spécifiez le nom du conteneur de stockage par défaut à associer au cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d24d8-128">UserName</span><span class="sxs-lookup"><span data-stu-id="d24d8-128">UserName</span></span>|<span data-ttu-id="d24d8-129">Spécifiez le nom d’utilisateur à utiliser pour la connexion au cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d24d8-130">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="d24d8-130">Password</span></span>|<span data-ttu-id="d24d8-131">Spécifiez le mot de passe à utiliser pour la connexion au cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d24d8-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="d24d8-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="d24d8-132">SshUserName</span></span>|<span data-ttu-id="d24d8-133">Spécifiez le nom d’utilisateur utilisé pour accéder à distance au cluster HDInsight à l’aide de SSH.</span><span class="sxs-lookup"><span data-stu-id="d24d8-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="d24d8-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="d24d8-134">SshPassword</span></span>|<span data-ttu-id="d24d8-135">Spécifiez le mot de passe utilisé pour accéder à distance au cluster HDInsight à l’aide de SSH.</span><span class="sxs-lookup"><span data-stu-id="d24d8-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="d24d8-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="d24d8-136">FailIfExists</span></span>|<span data-ttu-id="d24d8-137">Spécifiez si la tâche doit échouer si le cluster existe déjà.</span><span class="sxs-lookup"><span data-stu-id="d24d8-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="d24d8-138">L’emplacement du cluster HDInsight et celui du compte de stockage Azure doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="d24d8-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>
