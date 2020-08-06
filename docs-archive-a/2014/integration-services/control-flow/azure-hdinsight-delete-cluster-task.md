---
title: Supprimer un cluster Azure HDInsight, tâche | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613088"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="7cc41-102">Tâche Supprimer un cluster Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="7cc41-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="7cc41-103">La tâche **Supprimer un cluster Azure HDInsight** permet à un package SSIS de supprimer un cluster Azure HDInsight dans l’abonnement et le groupe de ressources Azure spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7cc41-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cc41-104">La suppression d’un cluster HDInsight peut prendre 10 à 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="7cc41-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="7cc41-105">Pour ajouter une **tâche de suppression de cluster Azure HDInsight**, faites-la glisser sur le concepteur SSIS, double-cliquez dessus ou cliquez dessus avec le bouton droit, puis cliquez sur **Modifier** pour afficher la boîte de dialogue **Éditeur de la tâche de suppression de cluster Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="7cc41-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="7cc41-106">Le tableau suivant décrit les champs de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7cc41-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cc41-107">**Champ**</span><span class="sxs-lookup"><span data-stu-id="7cc41-107">**Field**</span></span>|<span data-ttu-id="7cc41-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="7cc41-108">**Description**</span></span>|  
|<span data-ttu-id="7cc41-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="7cc41-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="7cc41-110">Sélectionnez un gestionnaire de connexions Azure Resource Manager existant ou créez-en un qui sera utilisé pour supprimer le cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7cc41-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="7cc41-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="7cc41-111">SubscriptionId</span></span>|<span data-ttu-id="7cc41-112">Spécifiez l’ID de l’abonnement du cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7cc41-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="7cc41-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="7cc41-113">ResourceGroup</span></span>|<span data-ttu-id="7cc41-114">Spécifiez le groupe de ressources Azure du cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="7cc41-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="7cc41-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="7cc41-115">ClusterName</span></span>|<span data-ttu-id="7cc41-116">Spécifiez le nom du cluster à supprimer.</span><span class="sxs-lookup"><span data-stu-id="7cc41-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="7cc41-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="7cc41-117">FailIfNotExists</span></span>|<span data-ttu-id="7cc41-118">Spécifiez si la tâche doit échouer si le cluster n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="7cc41-118">Specify whether the task should fail if the cluster does not exist.</span></span>|
