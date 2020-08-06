---
title: Éditeur de tâche de traitement de Analysis Services (page Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602973"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="d3f6f-102">Éditeur de tâche de traitement d'Analysis Services (page Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="d3f6f-103">Utilisez la page **Analysis Services** de la boîte de dialogue **Éditeur de tâche de traitement d’Analysis Services** pour définir un gestionnaire de connexions Analysis Services, sélectionner les objets analytiques à traiter et définir les options de traitement et de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="d3f6f-104">Lors du traitement des modèles tabulaires, gardez à l'esprit les points suivants :</span><span class="sxs-lookup"><span data-stu-id="d3f6f-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="d3f6f-105">Vous ne pouvez pas effectuer d'analyse d'impact sur les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="d3f6f-106">Certaines options de traitement du mode tabulaire ne sont pas exposées, par exemple Traiter la défragmentation et Traiter le recalcul.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="d3f6f-107">Vous pouvez exécuter ces fonctions à l'aide de la tâche DDL d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="d3f6f-108">Certaines options de traitement fournies, par exemple le traitement des index, ne conviennent pas aux modèles tabulaires et ne doivent pas être utilisées.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="d3f6f-109">Les paramètres de lot sont ignorés pour les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="d3f6f-110">Pour en savoir plus sur cette tâche, consultez [Tâche de traitement d’Analysis Services](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="d3f6f-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3f6f-111">Options</span><span class="sxs-lookup"><span data-stu-id="d3f6f-111">Options</span></span>  
 <span data-ttu-id="d3f6f-112">**Gestionnaire de connexions Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="d3f6f-113">Sélectionnez un gestionnaire de connexions Analysis Services existant dans la liste ou cliquez sur **Nouveau** pour créer un nouveau gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="d3f6f-114">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-114">**New**</span></span>  
 <span data-ttu-id="d3f6f-115">Créez un nouveau gestionnaire de connexions Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="d3f6f-116">**Rubriques connexes :** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Référence de l’interface utilisateur de la boîte de dialogue Ajout d’un gestionnaire de connexions Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="d3f6f-117">**Liste d’objets**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-117">**Object list**</span></span>  
 |<span data-ttu-id="d3f6f-118">Propriété</span><span class="sxs-lookup"><span data-stu-id="d3f6f-118">Property</span></span>|<span data-ttu-id="d3f6f-119">Description</span><span class="sxs-lookup"><span data-stu-id="d3f6f-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d3f6f-120">**Nom de l’objet**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-120">**Object Name**</span></span>|<span data-ttu-id="d3f6f-121">Affiche la liste des noms d'objets définis.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="d3f6f-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-122">**Type**</span></span>|<span data-ttu-id="d3f6f-123">Affiche la liste des types des objets définis.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="d3f6f-124">**Options de traitement**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-124">**Process Options**</span></span>|<span data-ttu-id="d3f6f-125">Sélectionnez une option de traitement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="d3f6f-126">**Rubriques connexes**: [traitement d’objets de modèle multidimensionnel](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="d3f6f-127">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-127">**Settings**</span></span>|<span data-ttu-id="d3f6f-128">Affiche la liste des paramètres de traitement des objets définis.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="d3f6f-129">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-129">**Add**</span></span>  
 <span data-ttu-id="d3f6f-130">Ajoutez un objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à la liste.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="d3f6f-131">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-131">**Remove**</span></span>  
 <span data-ttu-id="d3f6f-132">Sélectionnez un objet et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="d3f6f-133">**Analyse d'impact**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="d3f6f-134">Analyse l'impact sur l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="d3f6f-135">**Rubriques connexes :** [Boîte de dialogue Analyse d’impact &#40;Analysis Services - Données multidimensionnelles&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="d3f6f-136">**Résumé des paramètres du traitement**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="d3f6f-137">Propriété</span><span class="sxs-lookup"><span data-stu-id="d3f6f-137">Property</span></span>|<span data-ttu-id="d3f6f-138">Description</span><span class="sxs-lookup"><span data-stu-id="d3f6f-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d3f6f-139">**Ordre de traitement**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-139">**Processing order**</span></span>|<span data-ttu-id="d3f6f-140">Indique si les objets sont traités séquentiellement ou dans un traitement. Si le traitement parallèle est utilisé, indique le nombre d'objets à traiter simultanément.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="d3f6f-141">**Mode de transaction**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-141">**Transaction mode**</span></span>|<span data-ttu-id="d3f6f-142">Indique le mode de transaction du traitement séquentiel.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="d3f6f-143">**Erreurs de la dimension**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-143">**Dimension errors**</span></span>|<span data-ttu-id="d3f6f-144">Indique le comportement de la tâche lorsqu'une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="d3f6f-145">**Chemin d'accès du journal des erreurs de clé de dimension**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-145">**Dimension key error log path**</span></span>|<span data-ttu-id="d3f6f-146">Définit le chemin d'accès du fichier de consignation des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="d3f6f-147">**Traiter les objets affectés**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-147">**Process affected objects**</span></span>|<span data-ttu-id="d3f6f-148">Indique si les objets dépendants ou affectés sont également traités.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="d3f6f-149">**Modifier les paramètres**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-149">**Change Settings**</span></span>  
 <span data-ttu-id="d3f6f-150">Change les options de traitement et la gestion des erreurs dans les clés de dimension.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="d3f6f-151">**Rubriques connexes :** [Boîte de dialogue Modifier les paramètres &#40;Analysis Services - Données multidimensionnelles&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f6f-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3f6f-152">See Also</span></span>  
 <span data-ttu-id="d3f6f-153">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d3f6f-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d3f6f-154">[Éditeur de tâche de traitement de Analysis Services &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d3f6f-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="d3f6f-155">Tâche DDL d’exécution de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d3f6f-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
