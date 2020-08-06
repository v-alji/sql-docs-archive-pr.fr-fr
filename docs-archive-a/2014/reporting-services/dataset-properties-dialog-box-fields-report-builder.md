---
title: Boîte de dialogue Propriétés du DataSet, champs (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601986"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="3208b-102">Boîte de dialogue Propriétés du dataset, Champs (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="3208b-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="3208b-103">Sélectionnez **Champs** dans la boîte de dialogue **Propriétés du dataset** pour modifier la collection de champs pour le dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="3208b-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="3208b-104">La liste des champs est automatiquement remplie, mais vous pouvez utiliser **Champs** pour ajouter, modifier, et supprimer les champs de requête et les champs calculés.</span><span class="sxs-lookup"><span data-stu-id="3208b-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="3208b-105">Les champs calculés sont pris en charge uniquement sur les datasets incorporés.</span><span class="sxs-lookup"><span data-stu-id="3208b-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="3208b-106">Pour plus d’informations, consultez [Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3208b-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3208b-107">Options</span><span class="sxs-lookup"><span data-stu-id="3208b-107">Options</span></span>  
 <span data-ttu-id="3208b-108">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="3208b-108">**Add**</span></span>  
 <span data-ttu-id="3208b-109">Ajoutez un nouveau champ de requête ou calculé au dataset.</span><span class="sxs-lookup"><span data-stu-id="3208b-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="3208b-110">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="3208b-110">**Delete**</span></span>  
 <span data-ttu-id="3208b-111">Supprimez le champ sélectionné du dataset.</span><span class="sxs-lookup"><span data-stu-id="3208b-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="3208b-112">**Nom du champ**</span><span class="sxs-lookup"><span data-stu-id="3208b-112">**Field Name**</span></span>  
 <span data-ttu-id="3208b-113">Tapez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="3208b-113">Type a name for the field.</span></span> <span data-ttu-id="3208b-114">Ce champ doit être unique dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="3208b-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="3208b-115">Pour chaque champ existant dans le dataset, le nom est prérempli.</span><span class="sxs-lookup"><span data-stu-id="3208b-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="3208b-116">**Champ source**</span><span class="sxs-lookup"><span data-stu-id="3208b-116">**Field Source**</span></span>  
 <span data-ttu-id="3208b-117">Entrez une valeur pour le champ.</span><span class="sxs-lookup"><span data-stu-id="3208b-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="3208b-118">Pour un champ calculé, la source du champ doit être le nom d'un champ existant récupéré par la requête de dataset ou une expression que vous créez.</span><span class="sxs-lookup"><span data-stu-id="3208b-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="3208b-119">Par exemple, pour créer un champ qui représente 10 fois la valeur du champ de requête Sales, utilisez l'expression `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="3208b-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="3208b-120">Pour un champ de requête, la source du champ doit être le nom d'un champ existant récupéré par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="3208b-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="3208b-121">**Expression (fx)**</span><span class="sxs-lookup"><span data-stu-id="3208b-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="3208b-122">Ajoutez ou modifiez une expression pour le nouveau champ calculé.</span><span class="sxs-lookup"><span data-stu-id="3208b-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="3208b-123">Ce bouton apparaît uniquement lorsque vous cliquez sur **Ajouter** et sélectionnez **Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="3208b-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3208b-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3208b-124">See Also</span></span>  
 <span data-ttu-id="3208b-125">[Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3208b-126">[Créer un dataset partagé ou incorporé &#40;Générateur de rapports et SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3208b-127">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="3208b-128">[Boîte de dialogue Propriétés du DataSet, options &#40;Générateur de rapports&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="3208b-129">[Boîte de dialogue Propriétés du DataSet, filtres &#40;Générateur de rapports&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="3208b-130">[Boîte de dialogue Propriétés du DataSet, paramètres &#40;Générateur de rapports&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="3208b-131">[Boîte de dialogue Propriétés du DataSet, requête &#40;Générateur de rapports&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="3208b-132">[Expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3208b-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3208b-133">Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="3208b-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
