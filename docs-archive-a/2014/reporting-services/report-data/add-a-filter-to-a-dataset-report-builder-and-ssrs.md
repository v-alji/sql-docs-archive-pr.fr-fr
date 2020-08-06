---
title: Ajouter un filtre à un dataset (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600591"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="aa207-102">Ajouter un filtre à un dataset (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="aa207-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="aa207-103">Ajoutez un filtre à un dataset pour limiter les données dans un rapport après que les données ont été récupérées d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="aa207-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="aa207-104">Lorsque vous ajoutez un filtre à un dataset, toutes les parties de rapport ou régions de données utilisent uniquement les données qui correspondent aux conditions de filtre.</span><span class="sxs-lookup"><span data-stu-id="aa207-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="aa207-105">Pour un dataset partagé, un filtre qui s'applique à tous les éléments dépendants doit faire partie de la définition de dataset partagé sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="aa207-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="aa207-106">Un rapport ou une partie de rapport qui contient une instance d'un dataset partagé peut créer un filtre supplémentaire qui s'applique uniquement à l'instance.</span><span class="sxs-lookup"><span data-stu-id="aa207-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="aa207-107">Pour ajouter un filtre, vous devez spécifier une ou plusieurs conditions qui sont les équations de filtre.</span><span class="sxs-lookup"><span data-stu-id="aa207-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="aa207-108">Une équation de filtre est composée d'une expression qui identifie les données que vous souhaitez filtrer, d'un opérateur et de la valeur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="aa207-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="aa207-109">Les types de données des données filtrées et de la valeur doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="aa207-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="aa207-110">Le filtrage sur des valeurs d'agrégation n'est pas pris en charge pour les datasets.</span><span class="sxs-lookup"><span data-stu-id="aa207-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="aa207-111">Pour ajouter un filtre à un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="aa207-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="aa207-112">Ouvrez un dataset partagé en mode de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="aa207-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="aa207-113">Sous l'onglet **Accueil** , dans le groupe **Datasets partagés** , cliquez sur Datasets.</span><span class="sxs-lookup"><span data-stu-id="aa207-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="aa207-114">La boîte de dialogue **Propriétés du dataset** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="aa207-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="aa207-115">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="aa207-115">Click **Filters**.</span></span> <span data-ttu-id="aa207-116">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="aa207-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="aa207-117">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="aa207-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="aa207-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="aa207-118">Click **Add**.</span></span> <span data-ttu-id="aa207-119">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="aa207-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="aa207-120">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="aa207-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="aa207-121">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="aa207-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="aa207-122">Dans la zone de liste, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="aa207-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="aa207-123">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="aa207-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="aa207-124">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="aa207-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="aa207-125">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="aa207-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="aa207-126">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="aa207-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="aa207-127">Pour ajouter un filtre à un dataset incorporé ou une instance de dataset partagé</span><span class="sxs-lookup"><span data-stu-id="aa207-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="aa207-128">Ouvrez un rapport en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="aa207-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="aa207-129">Dans le volet **Données du rapport** , cliquez avec le bouton droit sur un dataset, puis cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="aa207-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="aa207-130">La boîte de dialogue **Propriétés du dataset** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="aa207-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="aa207-131">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="aa207-131">Click **Filters**.</span></span> <span data-ttu-id="aa207-132">La liste actuelle des équations de filtre s'affiche.</span><span class="sxs-lookup"><span data-stu-id="aa207-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="aa207-133">Par défaut, elle est vide.</span><span class="sxs-lookup"><span data-stu-id="aa207-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="aa207-134">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="aa207-134">Click **Add**.</span></span> <span data-ttu-id="aa207-135">Une nouvelle équation de filtre vierge apparaît.</span><span class="sxs-lookup"><span data-stu-id="aa207-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="aa207-136">Dans **Expression**, tapez ou sélectionnez l'expression pour le champ à filtrer.</span><span class="sxs-lookup"><span data-stu-id="aa207-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="aa207-137">Pour modifier l’expression, cliquez sur le bouton d’expression (*fx*).</span><span class="sxs-lookup"><span data-stu-id="aa207-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="aa207-138">Dans la liste déroulante, sélectionnez le type de données correspondant au type de données de l'expression que vous avez créée à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="aa207-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="aa207-139">Dans la zone **Opérateur** , sélectionnez l'opérateur que le filtre doit utiliser pour comparer les valeurs des zones **Expression** et **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="aa207-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="aa207-140">L'opérateur sélectionné détermine le nombre de valeurs utilisées pour l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="aa207-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="aa207-141">Dans la zone **Valeur** , tapez l'expression ou la valeur en fonction de laquelle le filtre doit évaluer la valeur indiquée dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="aa207-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="aa207-142">Pour obtenir des exemples d’équations de filtre, consultez [Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="aa207-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa207-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aa207-143">See Also</span></span>  
 <span data-ttu-id="aa207-144">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="aa207-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="aa207-145">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa207-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="aa207-146">Ajouter un filtre &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa207-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
