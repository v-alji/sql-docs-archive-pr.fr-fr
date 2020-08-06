---
title: Spécifier le type de contenu et de données des colonnes (Assistant Exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604169"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="49de2-102">Spécifier type de contenu et de données des colonnes (Assistant Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="49de2-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="49de2-103">Utilisez la page **Spécifier type de contenu et de données des colonnes** pour spécifier l’utilisation et le type de données de chaque colonne que vous avez sélectionnée dans la page précédente de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="49de2-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="49de2-104">Si vous voulez ignorer la colonne, cliquez sur **Précédent** pour revenir à la page **Spécifier les données d’apprentissage**, puis décochez toutes les cases.</span><span class="sxs-lookup"><span data-stu-id="49de2-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="49de2-105">L'utilisation d'une colonne indique la manière dont les données seront utilisées dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="49de2-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="49de2-106">Une colonne peut être utilisée en tant que clé d'identification d'une série, en tant que valeur d'entrée à utiliser dans l'analyse ou en tant que valeur à prédire.</span><span class="sxs-lookup"><span data-stu-id="49de2-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="49de2-107">Les colonnes peuvent à la fois être utilisées à des fins de prédiction et de saisie.</span><span class="sxs-lookup"><span data-stu-id="49de2-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="49de2-108">Le type de données spécifie des détails supplémentaires sur le type des données contenues dans la colonne, ainsi que la manière dont les données seront utilisées pendant l'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="49de2-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="49de2-109">Certains types de contenu requièrent un type de données spécifique, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="49de2-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="49de2-110">Vous pouvez également avoir besoin de spécifier un type de données particulier selon l'algorithme que vous utilisez lorsque vous créez un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="49de2-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="49de2-111">Pour plus d’informations sur les types de contenu et les types de données dans les modèles et structures d’exploration de données, consultez [Types de contenu &#40;Exploration de données&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="49de2-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="49de2-112">**Pour plus d’informations :** [Structures d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colonnes d’un modèle d’exploration de données](data-mining/mining-model-columns.md), [Assistant Exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Créer une structure d’exploration de données relationnelle](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="49de2-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="49de2-113">Options</span><span class="sxs-lookup"><span data-stu-id="49de2-113">Options</span></span>  
 <span data-ttu-id="49de2-114">**Structure du modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="49de2-114">**Mining model structure**</span></span>  
 <span data-ttu-id="49de2-115">Affiche les colonnes des vues et des tables imbriquées que vous avez sélectionnées dans la page précédente de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="49de2-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="49de2-116">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="49de2-116">**Columns**</span></span>  
 <span data-ttu-id="49de2-117">Répertorie les colonnes.</span><span class="sxs-lookup"><span data-stu-id="49de2-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="49de2-118">**Type de contenu**</span><span class="sxs-lookup"><span data-stu-id="49de2-118">**Content type**</span></span>  
 <span data-ttu-id="49de2-119">Spécifiez le type de contenu de la colonne.</span><span class="sxs-lookup"><span data-stu-id="49de2-119">Specify the content type for the column.</span></span> <span data-ttu-id="49de2-120">Si vous avez spécifié que la colonne est une clé dans la page précédente de l'Assistant, les valeurs suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="49de2-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="49de2-121">Option</span><span class="sxs-lookup"><span data-stu-id="49de2-121">Option</span></span>|<span data-ttu-id="49de2-122">Description</span><span class="sxs-lookup"><span data-stu-id="49de2-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="49de2-123">Clé</span><span class="sxs-lookup"><span data-stu-id="49de2-123">Key</span></span>|<span data-ttu-id="49de2-124">Spécifiez que la colonne contient un identificateur unique pour la série de cas.</span><span class="sxs-lookup"><span data-stu-id="49de2-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="49de2-125">Séquence clé</span><span class="sxs-lookup"><span data-stu-id="49de2-125">Key Sequence</span></span>|<span data-ttu-id="49de2-126">Spécifiez que la colonne contient un identificateur de séquence.</span><span class="sxs-lookup"><span data-stu-id="49de2-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="49de2-127">Temps clé</span><span class="sxs-lookup"><span data-stu-id="49de2-127">Key Time</span></span>|<span data-ttu-id="49de2-128">Spécifiez que la colonne contient une date ou un autre nombre continu unique utilisé pour identifier une date ou une série chronologique.</span><span class="sxs-lookup"><span data-stu-id="49de2-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="49de2-129">Si vous avez sélectionné la colonne en tant que colonne non-clé, les valeurs suivantes sont disponibles, selon le type de données :</span><span class="sxs-lookup"><span data-stu-id="49de2-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="49de2-130">Option</span><span class="sxs-lookup"><span data-stu-id="49de2-130">Option</span></span>|<span data-ttu-id="49de2-131">Description</span><span class="sxs-lookup"><span data-stu-id="49de2-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="49de2-132">Continue</span><span class="sxs-lookup"><span data-stu-id="49de2-132">Continuous</span></span>|<span data-ttu-id="49de2-133">Spécifiez que la colonne contient des valeurs numériques continues.</span><span class="sxs-lookup"><span data-stu-id="49de2-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="49de2-134">Discrétisé</span><span class="sxs-lookup"><span data-stu-id="49de2-134">Discretized</span></span>|<span data-ttu-id="49de2-135">Spécifiez que la colonne contient des valeurs numériques qui ont été discrétisées ou qui peut être traitées comme des valeurs discrètes.</span><span class="sxs-lookup"><span data-stu-id="49de2-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="49de2-136">Discret</span><span class="sxs-lookup"><span data-stu-id="49de2-136">Discrete</span></span>|<span data-ttu-id="49de2-137">Spécifiez que la colonne contient des valeurs de texte ou d'autres valeurs non numériques.</span><span class="sxs-lookup"><span data-stu-id="49de2-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="49de2-138">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="49de2-138">**Data type**</span></span>  
 <span data-ttu-id="49de2-139">Spécifiez le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="49de2-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="49de2-140">Les valeurs suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="49de2-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="49de2-141">**Detect**</span><span class="sxs-lookup"><span data-stu-id="49de2-141">**Detect**</span></span>  
 <span data-ttu-id="49de2-142">Analysez un exemple de données dans toutes les colonnes numériques.</span><span class="sxs-lookup"><span data-stu-id="49de2-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="49de2-143">Remplace les valeurs **Type de contenu** spécifiées par un type de contenu recommandé.</span><span class="sxs-lookup"><span data-stu-id="49de2-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49de2-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49de2-144">See Also</span></span>  
 <span data-ttu-id="49de2-145">[Aide (F1) de l’Assistant Exploration de données &#40;Analysis Services-exploration de données&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="49de2-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="49de2-146">[Suggérer des colonnes associées &#40;l’Assistant Exploration de données&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="49de2-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="49de2-147">[Spécifier les types de tables &#40;l’Assistant Exploration de données&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="49de2-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="49de2-148">Spécifiez le contenu et le type de données de la colonne &#40;l’Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="49de2-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
