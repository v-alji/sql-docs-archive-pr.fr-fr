---
title: Boîte de dialogue Propriétés du DataSet, filtres (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10025"
ms.assetid: 933a6f44-4eb7-4e73-9c40-ac0fd17b23d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7bc13b0eeff1eaf27fb0ec0c4279ff00d0809e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601984"
---
# <a name="dataset-properties-dialog-box-filters-report-builder"></a><span data-ttu-id="ab428-102">Boîte de dialogue Propriétés du dataset, Filtres (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="ab428-102">Dataset Properties Dialog Box, Filters (Report Builder)</span></span>
  <span data-ttu-id="ab428-103">Sélectionnez **Filtres** dans la boîte de dialogue **Propriétés du dataset** pour créer des filtres pour le dataset.</span><span class="sxs-lookup"><span data-stu-id="ab428-103">Select **Filters** on the **Dataset Properties** dialog box to create filters for the dataset.</span></span>  
  
 <span data-ttu-id="ab428-104">Les filtres qui font partie d'une définition de dataset partagé sur le serveur de rapports affectent tous les rapports qui utilisent le dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="ab428-104">Filters that are part of a shared dataset definition on the report server affect all reports that use the shared dataset.</span></span> <span data-ttu-id="ab428-105">Des filtres supplémentaires pour le dataset partagé peuvent être spécifiés après que celui-ci a été ajouté à un rapport.</span><span class="sxs-lookup"><span data-stu-id="ab428-105">Additional filters for the shared dataset can be specified after it is added to a report.</span></span> <span data-ttu-id="ab428-106">Ces filtres affectent uniquement le rapport dans lequel ils sont définis.</span><span class="sxs-lookup"><span data-stu-id="ab428-106">These filters affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="ab428-107">Les filtres d'un dataset incorporé affectent uniquement le rapport dans lequel ils sont définis.</span><span class="sxs-lookup"><span data-stu-id="ab428-107">Filters for an embedded dataset affect only the report in which they are defined.</span></span>  
  
 <span data-ttu-id="ab428-108">Pour plus d’informations, consultez [Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab428-108">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab428-109">Options</span><span class="sxs-lookup"><span data-stu-id="ab428-109">Options</span></span>  
 <span data-ttu-id="ab428-110">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="ab428-110">**Add**</span></span>  
 <span data-ttu-id="ab428-111">Ajoutez une nouvelle clause de filtre à la liste.</span><span class="sxs-lookup"><span data-stu-id="ab428-111">Add a new filter clause to the list.</span></span>  
  
 <span data-ttu-id="ab428-112">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="ab428-112">**Delete**</span></span>  
 <span data-ttu-id="ab428-113">Supprimez la clause de filtre sélectionnée de la liste.</span><span class="sxs-lookup"><span data-stu-id="ab428-113">Delete the selected filter clause from the list.</span></span>  
  
 <span data-ttu-id="ab428-114">**Flèche haut**</span><span class="sxs-lookup"><span data-stu-id="ab428-114">**Up arrow**</span></span>  
 <span data-ttu-id="ab428-115">Déplacez le filtre sélectionné vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="ab428-115">Move the selected filter up in the list.</span></span>  
  
 <span data-ttu-id="ab428-116">**Flèche bas**</span><span class="sxs-lookup"><span data-stu-id="ab428-116">**Down arrow**</span></span>  
 <span data-ttu-id="ab428-117">Déplacez le filtre sélectionné vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="ab428-117">Move the selected filter down in the list</span></span>  
  
 <span data-ttu-id="ab428-118">**Expression**</span><span class="sxs-lookup"><span data-stu-id="ab428-118">**Expression**</span></span>  
 <span data-ttu-id="ab428-119">Tapez ou choisissez l'expression à laquelle vous souhaitez appliquer un filtre.</span><span class="sxs-lookup"><span data-stu-id="ab428-119">Type or choose the expression to which you want to apply a filter.</span></span> <span data-ttu-id="ab428-120">Cliquez sur le bouton Expression (**fx**) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="ab428-120">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="ab428-121">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ab428-121">**Data type**</span></span>  
 <span data-ttu-id="ab428-122">Sélectionnez le type de données du champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="ab428-122">Choose the data type for **Value**.</span></span> <span data-ttu-id="ab428-123">Lorsque cela est possible, sélectionnez un type de données correspondant à celui du champ **Expression**.</span><span class="sxs-lookup"><span data-stu-id="ab428-123">When possible, choose a data type that matches the data type for **Expression**.</span></span>  
  
 <span data-ttu-id="ab428-124">Les valeurs dans **Expression** et **Valeur** doivent s’évaluer au même type de données.</span><span class="sxs-lookup"><span data-stu-id="ab428-124">The values in **Expression** and **Value** must evaluate to the same data type.</span></span> <span data-ttu-id="ab428-125">Par exemple, si **Expression** a pour valeur un champ du type de données System.Int32 et que **Valeur** a pour valeur 7, sélectionnez **Entier**dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="ab428-125">For example, if **Expression** is set to a field that has the data type System.Int32 and **Value** is set to 7, from the drop-down list, choose **Integer**.</span></span>  
  
 <span data-ttu-id="ab428-126">Si le type de données recherché ne figure pas dans la liste déroulante, écrivez une expression permettant de convertir la valeur en type de données correct.</span><span class="sxs-lookup"><span data-stu-id="ab428-126">If the data type option you need is not in the drop-down list, write an expression to convert the value to the correct data type.</span></span> <span data-ttu-id="ab428-127">Pour plus d’informations, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab428-127">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ab428-128">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="ab428-128">**Operator**</span></span>  
 <span data-ttu-id="ab428-129">Choisissez l'opérateur à utiliser pour comparer l'expression et la valeur.</span><span class="sxs-lookup"><span data-stu-id="ab428-129">Choose the operator to use to compare the expression and the value.</span></span>  
  
 <span data-ttu-id="ab428-130">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="ab428-130">**Value**</span></span>  
 <span data-ttu-id="ab428-131">Tapez l’expression ou la valeur à utiliser lors de l’évaluation de l’expression spécifiée dans la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="ab428-131">Type the expression or value to use when evaluating the expression specified in the **Expression** box.</span></span> <span data-ttu-id="ab428-132">Cliquez sur le bouton Expression (**fx**) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="ab428-132">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab428-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab428-133">See Also</span></span>  
 <span data-ttu-id="ab428-134">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ab428-134">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ab428-135">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ab428-135">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="ab428-136">[Ajouter un filtre à un jeu de données &#40;Générateur de rapports et SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ab428-136">[Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ab428-137">Utilisation d’expressions dans les rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ab428-137">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
