---
title: Éditeur de destination de traitement de partition (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604611"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="23c34-102">Éditeur de destination de traitement de partition (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="23c34-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="23c34-103">La page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination de traitement de partition** vous permet de spécifier une connexion à un projet [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23c34-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="23c34-104">Pour en savoir plus sur la destination de traitement de partition, consultez [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="23c34-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23c34-105">Les tâches décrites ici ne s’appliquent pas aux modèles tabulaires Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="23c34-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="23c34-106">Vous ne pouvez pas mapper des colonnes d’entrée aux colonnes de partition pour les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="23c34-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="23c34-107">Vous pouvez en revanche utiliser la tâche DDL d'exécution [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) d'Analysis Services pour traiter la partition.</span><span class="sxs-lookup"><span data-stu-id="23c34-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="23c34-108">Options</span><span class="sxs-lookup"><span data-stu-id="23c34-108">Options</span></span>  
 <span data-ttu-id="23c34-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="23c34-109">**Connection manager**</span></span>  
 <span data-ttu-id="23c34-110">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="23c34-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="23c34-111">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="23c34-111">**New**</span></span>  
 <span data-ttu-id="23c34-112">Créez une connexion à l’aide de la boîte de dialogue **Ajout d’un gestionnaire de connexions Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="23c34-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="23c34-113">**Liste des partitions disponibles**</span><span class="sxs-lookup"><span data-stu-id="23c34-113">**List of available partitions**</span></span>  
 <span data-ttu-id="23c34-114">Sélectionnez la partition à traiter.</span><span class="sxs-lookup"><span data-stu-id="23c34-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="23c34-115">**Méthode de traitement**</span><span class="sxs-lookup"><span data-stu-id="23c34-115">**Processing method**</span></span>  
 <span data-ttu-id="23c34-116">Sélectionnez la méthode de traitement.</span><span class="sxs-lookup"><span data-stu-id="23c34-116">Select the processing method.</span></span> <span data-ttu-id="23c34-117">La valeur par défaut de cette option est **Complète**.</span><span class="sxs-lookup"><span data-stu-id="23c34-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="23c34-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="23c34-118">Value</span></span>|<span data-ttu-id="23c34-119">Description</span><span class="sxs-lookup"><span data-stu-id="23c34-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23c34-120">Ajouter (incrémentiel)</span><span class="sxs-lookup"><span data-stu-id="23c34-120">Add (incremental)</span></span>|<span data-ttu-id="23c34-121">Permet d'effectuer un traitement incrémentiel de la partition.</span><span class="sxs-lookup"><span data-stu-id="23c34-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="23c34-122">Complète</span><span class="sxs-lookup"><span data-stu-id="23c34-122">Full</span></span>|<span data-ttu-id="23c34-123">Permet d'effectuer un traitement complet de la partition.</span><span class="sxs-lookup"><span data-stu-id="23c34-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="23c34-124">Données seulement</span><span class="sxs-lookup"><span data-stu-id="23c34-124">Data only</span></span>|<span data-ttu-id="23c34-125">Permet d'effectuer un traitement de mise à jour de la partition.</span><span class="sxs-lookup"><span data-stu-id="23c34-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23c34-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23c34-126">See Also</span></span>  
 <span data-ttu-id="23c34-127">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="23c34-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="23c34-128">[Éditeur de destination de traitement de partition &#40;page Mappages&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="23c34-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="23c34-129">Éditeur de destination de traitement de partition &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="23c34-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
