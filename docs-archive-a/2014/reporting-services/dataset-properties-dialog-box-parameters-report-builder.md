---
title: Boîte de dialogue Propriétés du DataSet, paramètres (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10023"
ms.assetid: 3a0672ad-c969-455b-b952-585164ce1dda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ef038e7cbf113556b11af9a0e6c59aa190b2400b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614397"
---
# <a name="dataset-properties-dialog-box-parameters-report-builder"></a><span data-ttu-id="4cfe1-102">Boîte de dialogue Propriétés du dataset, Paramètres (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="4cfe1-102">Dataset Properties Dialog Box, Parameters (Report Builder)</span></span>
  <span data-ttu-id="4cfe1-103">Sélectionnez **paramètres** dans la boîte de dialogue **Propriétés du DataSet** pour ajouter, modifier et supprimer des paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters.</span></span>  
  
 <span data-ttu-id="4cfe1-104">Pour un dataset incorporé, les options s'appliquent au dataset dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-104">For an embedded dataset, options apply to the dataset in the report definition.</span></span>  
  
 <span data-ttu-id="4cfe1-105">Pour un dataset partagé, les options s'appliquent à la définition de dataset partagé sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-105">For a shared dataset, options apply to the shared dataset definition on the report server.</span></span>  
  
 <span data-ttu-id="4cfe1-106">Pour plus d’informations, consultez [Datasets incorporés et partagés &#40;Générateur de rapports et SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4cfe1-106">For more information, see [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/embedded-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4cfe1-107">Options</span><span class="sxs-lookup"><span data-stu-id="4cfe1-107">Options</span></span>  
 <span data-ttu-id="4cfe1-108">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-108">**Add**</span></span>  
 <span data-ttu-id="4cfe1-109">Ajoutez un nouveau paramètre à la liste.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-109">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="4cfe1-110">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-110">**Delete**</span></span>  
 <span data-ttu-id="4cfe1-111">Supprimez le paramètre sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-111">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="4cfe1-112">**Flèche haut**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-112">**Up arrow**</span></span>  
 <span data-ttu-id="4cfe1-113">Déplacez le paramètre sélectionné vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-113">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="4cfe1-114">**Flèche bas**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-114">**Down arrow**</span></span>  
 <span data-ttu-id="4cfe1-115">Déplacez le paramètre sélectionné vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-115">Move the selected parameter down in the list.</span></span>  
  
 <span data-ttu-id="4cfe1-116">**Nom du paramètre**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-116">**Parameter name**</span></span>  
 <span data-ttu-id="4cfe1-117">Tapez le nom d’un paramètre de requête que vous avez ajouté au dataset sous l’onglet **Requête** de la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="4cfe1-117">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="4cfe1-118">**Valeur du paramètre**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-118">**Parameter value**</span></span>  
 <span data-ttu-id="4cfe1-119">Pour les datasets incorporés uniquement.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-119">For embedded datasets only.</span></span>  
  
 <span data-ttu-id="4cfe1-120">Entrez une valeur pour le paramètre de requête.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-120">Enter a value for the query parameter.</span></span> <span data-ttu-id="4cfe1-121">Il peut s'agir d'une valeur statique ou d'une expression faisant référence à un objet présent dans le rapport ; toutefois, elle ne peut pas faire référence à des éléments de rapport ou des champs.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-121">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="4cfe1-122">Par défaut, **Valeur** contient une expression qui pointe vers un paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-122">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="4cfe1-123">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-123">**Default value**</span></span>  
 <span data-ttu-id="4cfe1-124">Pour les datasets partagés uniquement.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-124">For shared datasets only.</span></span>  
  
 <span data-ttu-id="4cfe1-125">Activez la case à cocher pour spécifier une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-125">Select the check box to specify a default value.</span></span>  
  
 <span data-ttu-id="4cfe1-126">Entrez une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-126">Enter a default value.</span></span> <span data-ttu-id="4cfe1-127">Il peut s'agir d'une valeur statique ou d'une expression qui fait référence à un objet dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-127">This can be a static value or an expression that refers to an object within the report.</span></span> <span data-ttu-id="4cfe1-128">L'expression ne peut pas faire référence aux éléments de rapport, aux paramètres de rapport ni aux champs.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-128">The expression cannot refer to report items, report parameters, or fields.</span></span>  
  
 <span data-ttu-id="4cfe1-129">Pour spécifier une valeur vide, laissez la zone de texte vide.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-129">To specify a blank, leave the text box empty.</span></span>  
  
 <span data-ttu-id="4cfe1-130">Pour spécifier une valeur Null, sélectionnez l'option Nullable.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-130">To specify a null, select the Nullable option.</span></span>  
  
 <span data-ttu-id="4cfe1-131">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-131">**Read Only**</span></span>  
 <span data-ttu-id="4cfe1-132">Pour les datasets partagés uniquement.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-132">For shared datasets only.</span></span>  
  
 <span data-ttu-id="4cfe1-133">Sélectionnez cette option pour marquer ce paramètre comme étant en lecture seule dans la définition de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-133">Select this option to mark this parameter read only in the shared dataset definition.</span></span> <span data-ttu-id="4cfe1-134">Lorsque le dataset partagé est ajouté à un rapport, le paramètre ne s'affiche pas dans les propriétés.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-134">When the shared dataset is added to a report, the parameter does not appear in the properties.</span></span> <span data-ttu-id="4cfe1-135">Lorsque le dataset partagé est mis en cache sur le serveur de rapports, la valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-135">When the shared dataset is cached on the report server, the value cannot be changed.</span></span>  
  
 <span data-ttu-id="4cfe1-136">**Nullable**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-136">**Nullable**</span></span>  
 <span data-ttu-id="4cfe1-137">Pour les datasets partagés uniquement.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-137">For shared datasets only.</span></span>  
  
 <span data-ttu-id="4cfe1-138">Sélectionnez cette option pour autoriser une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-138">Select this option to allow a null value.</span></span>  
  
 <span data-ttu-id="4cfe1-139">**Omettre de la requête**</span><span class="sxs-lookup"><span data-stu-id="4cfe1-139">**Omit From Query**</span></span>  
 <span data-ttu-id="4cfe1-140">Pour les datasets partagés uniquement.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-140">For shared datasets only.</span></span>  
  
 <span data-ttu-id="4cfe1-141">Sélectionnez cette option lorsqu'une référence à un paramètre de rapport figure dans une expression dans le filtre de dataset partagé et pas dans la requête.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-141">Select this option when a reference to a report parameter is in an expression in the shared dataset filter and not in the query.</span></span> <span data-ttu-id="4cfe1-142">Lorsque vous sélectionnez cette option, vous n'avez pas besoin de spécifier une valeur par défaut pour ce paramètre lors de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="4cfe1-142">When you select this option, you do not need to specify a default value for this parameter when the query runs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfe1-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4cfe1-143">See Also</span></span>  
 <span data-ttu-id="4cfe1-144">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-144">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="4cfe1-145">[Boîte de dialogue Propriétés du DataSet, requête &#40;Générateur de rapports&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-145">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="4cfe1-146">[Expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-146">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4cfe1-147">[Didacticiel : ajouter un paramètre à votre rapport &#40;Générateur de rapports&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-147">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="4cfe1-148">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-148">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="4cfe1-149">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-149">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4cfe1-150">[Concepteurs de requêtes &#40;Générateur de rapports&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-150">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="4cfe1-151">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cfe1-151">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4cfe1-152">Créer un dataset partagé ou incorporé &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfe1-152">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
  
