---
title: Ajouter, modifier ou supprimer les valeurs par défaut d’un paramètre de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605211"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="7acc0-102">Ajouter, modifier ou supprimer les valeurs par défaut d'un paramètre de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="7acc0-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7acc0-103">Après avoir créé un paramètre de rapport, vous pouvez fournir une liste de valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="7acc0-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="7acc0-104">Si tous les paramètres ont une valeur par défaut valide, le rapport s'exécute automatiquement lorsque vous l'affichez pour la première fois ou en affichez un aperçu.</span><span class="sxs-lookup"><span data-stu-id="7acc0-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="7acc0-105">Les paramètres de rapport peuvent représenter une ou plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="7acc0-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="7acc0-106">Pour les valeurs uniques, vous pouvez fournir un littéral ou une expression.</span><span class="sxs-lookup"><span data-stu-id="7acc0-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="7acc0-107">Pour les valeurs multiples, vous pouvez fournir une liste statique ou une liste provenant d'un dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="7acc0-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="7acc0-108">Après la publication d'un rapport, vous pouvez remplacer les valeurs par défaut définies dans l'outil de création de rapports en définissant les valeurs de propriété de paramètre sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="7acc0-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="7acc0-109">Vous pouvez également fournir plusieurs jeux de valeurs de paramètre par défaut en créant des rapports liés.</span><span class="sxs-lookup"><span data-stu-id="7acc0-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="7acc0-110">Pour plus d’informations, consultez  [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="7acc0-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="7acc0-111">Pour ajouter ou modifier les valeurs par défaut d'un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="7acc0-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="7acc0-112">Dans le volet Données du rapport, développez le nœud **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="7acc0-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="7acc0-113">Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="7acc0-114">La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="7acc0-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7acc0-115">Si le volet Données du rapport n’est pas visible, cliquez sur **Affichage** , puis sur **Données du rapport**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="7acc0-116">Cliquez sur **Valeurs par défaut**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="7acc0-117">Sélectionnez une option par défaut :</span><span class="sxs-lookup"><span data-stu-id="7acc0-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="7acc0-118">Pour fournir manuellement une valeur ou une liste de valeurs, cliquez sur **Spécifier les valeurs**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="7acc0-119">Cliquez sur **Ajouter** , puis entrez la valeur dans la zone de texte **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="7acc0-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="7acc0-120">Vous pouvez écrire une expression pour une valeur.</span><span class="sxs-lookup"><span data-stu-id="7acc0-120">You can write an expression for a value.</span></span> <span data-ttu-id="7acc0-121">Le type de données doit correspondre au type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="7acc0-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="7acc0-122">Les noms de champs ne peuvent pas être utilisés dans une expression pour un paramètre.</span><span class="sxs-lookup"><span data-stu-id="7acc0-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="7acc0-123">Pour les paramètres à valeurs multiples, répétez cette étape pour toutes les valeurs que vous souhaitez fournir.</span><span class="sxs-lookup"><span data-stu-id="7acc0-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="7acc0-124">L'ordre des éléments que vous voyez dans cette liste détermine l'ordre dans lequel l'utilisateur les voit dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7acc0-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="7acc0-125">Pour modifier l’ordre d’un élément dans la liste, cliquez sur la zone de texte **Valeur** pour sélectionner l’élément, puis utilisez les flèches haut et bas pour déplacer l’élément dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7acc0-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="7acc0-126">Pour fournir le nom d’un dataset existant qui récupère les valeurs, cliquez sur **Obtenir les valeurs à partir d’une requête**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="7acc0-127">Dans **Dataset**, choisissez le nom du dataset.</span><span class="sxs-lookup"><span data-stu-id="7acc0-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="7acc0-128">Dans **Champ de valeur**, choisissez le nom du champ qui fournit les valeurs de paramètre.</span><span class="sxs-lookup"><span data-stu-id="7acc0-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="7acc0-129">Pour supprimer les valeurs par défaut d'un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="7acc0-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="7acc0-130">Dans le volet Données du rapport, développez le nœud **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="7acc0-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="7acc0-131">Cliquez avec le bouton droit sur le paramètre, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="7acc0-132">La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="7acc0-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7acc0-133">Cliquez sur **Valeurs par défaut**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="7acc0-134">Dans **Sélectionnez l’une des options suivantes**, cliquez sur **Aucune valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="7acc0-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7acc0-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7acc0-135">See Also</span></span>  
 <span data-ttu-id="7acc0-136">[Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="7acc0-137">[Ajouter des paramètres en cascade à un rapport &#40;Générateur de rapports et SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7acc0-138">[Didacticiel : ajouter un paramètre à un rapport &#40;Générateur de rapports&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="7acc0-139">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="7acc0-140">[Références à la collection Parameters&#40;Générateur de rapports et SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="7acc0-141">[Modifier l’ordre d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7acc0-142">[Ajouter, modifier ou supprimer un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7acc0-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7acc0-143">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7acc0-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
