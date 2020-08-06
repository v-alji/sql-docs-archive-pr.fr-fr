---
title: Propriétés du modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612609"
---
# <a name="mining-model-properties"></a><span data-ttu-id="15744-102">Propriétés du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="15744-102">Mining Model Properties</span></span>
  <span data-ttu-id="15744-103">Les modèles d'exploration de données ont les types de propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="15744-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="15744-104">les propriétés qui sont héritées de la structure d'exploration de données et qui définissent le type de données et le type de contenu des données utilisées par le modèle ;</span><span class="sxs-lookup"><span data-stu-id="15744-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="15744-105">les propriétés qui sont liées à l'algorithme utilisé pour créer le modèle d'exploration de données, y compris tout paramètre client ;</span><span class="sxs-lookup"><span data-stu-id="15744-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="15744-106">les propriétés qui définissent un filtre sur le modèle utilisé pour l'apprentissage du modèle.</span><span class="sxs-lookup"><span data-stu-id="15744-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="15744-107">Les propriétés d'un modèle d'exploration de données sont initialement définies lors de la création du modèle ; toutefois, vous pouvez modifier la plupart des propriétés ultérieurement, notamment les paramètres d'algorithme, les filtres et les propriétés d'utilisation des colonnes.</span><span class="sxs-lookup"><span data-stu-id="15744-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="15744-108">Vous modifiez ces propriétés à l’aide de l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, ou en utilisant AMO ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="15744-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="15744-109">Chaque fois que vous modifiez une propriété d'un modèle, vous devez traiter de nouveau le modèle pour que les modifications soient visibles dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="15744-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="15744-110">Un retraitement est requis même si la modification implique seulement des métadonnées, telles que l'ajout d'un alias ou d'une description de colonne.</span><span class="sxs-lookup"><span data-stu-id="15744-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="15744-111">Propriétés des modèles</span><span class="sxs-lookup"><span data-stu-id="15744-111">Properties of Models</span></span>  
 <span data-ttu-id="15744-112">Le tableau suivant décrit les propriétés spécifiques aux modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="15744-113">De plus, il existe des propriétés que vous pouvez définir sur des colonnes individuelles dans l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="15744-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="15744-114">Propriété</span><span class="sxs-lookup"><span data-stu-id="15744-114">Property</span></span>|<span data-ttu-id="15744-115">Description</span><span class="sxs-lookup"><span data-stu-id="15744-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="15744-116">**Algorithme**</span><span class="sxs-lookup"><span data-stu-id="15744-116">**Algorithm**</span></span>|<span data-ttu-id="15744-117">Définit le type d'algorithme pour le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="15744-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="15744-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="15744-119">Définit les valeurs pour les paramètres d'algorithme disponibles pour chaque type d'algorithme.</span><span class="sxs-lookup"><span data-stu-id="15744-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="15744-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="15744-120">**Filter**</span></span>|<span data-ttu-id="15744-121">Définit un filtre qui s'applique aux données utilisées pour former et tester le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="15744-122">La définition de filtre est stockée avec le modèle et peut être utilisée facultativement lorsque vous créez des requêtes de prédiction ou lorsque vous testez la précision du modèle.</span><span class="sxs-lookup"><span data-stu-id="15744-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="15744-123">Le filtre de modèle n'est pas facultatif lors de la formation du modèle.</span><span class="sxs-lookup"><span data-stu-id="15744-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="15744-124">**Nom**</span><span class="sxs-lookup"><span data-stu-id="15744-124">**Name**</span></span>|<span data-ttu-id="15744-125">Définit le nom du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="15744-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="15744-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="15744-127">Spécifie si l'extraction est activée sur le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="15744-128">Propriétés des colonnes d'un modèle</span><span class="sxs-lookup"><span data-stu-id="15744-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="15744-129">Vous pouvez définir les propriétés ci-dessous, spécifiques à l'exploration de données, pour chaque colonne dans un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="15744-130">Vous pouvez affecter à ces propriétés une valeur différente pour chaque modèle d'exploration de données d'une structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="15744-131">Propriété</span><span class="sxs-lookup"><span data-stu-id="15744-131">Property</span></span>|<span data-ttu-id="15744-132">Description</span><span class="sxs-lookup"><span data-stu-id="15744-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="15744-133">**Description**</span><span class="sxs-lookup"><span data-stu-id="15744-133">**Description**</span></span>|<span data-ttu-id="15744-134">Décrit la fonction de la colonne d'exploration des données.</span><span class="sxs-lookup"><span data-stu-id="15744-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="15744-135">**Nom**</span><span class="sxs-lookup"><span data-stu-id="15744-135">**Name**</span></span>|<span data-ttu-id="15744-136">Définit le nom de la colonne du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="15744-137">Vous pouvez taper un nouveau nom, pour fournir un alias pour la colonne du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="15744-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="15744-138">**ModelingFlags**</span></span>|<span data-ttu-id="15744-139">Définit tous les indicateurs spécifiques des algorithmes pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="15744-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="15744-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="15744-140">**SourceColumnID**</span></span>|<span data-ttu-id="15744-141">Indique le nom de la colonne de structure d'exploration de données sur laquelle la colonne du modèle est basée.</span><span class="sxs-lookup"><span data-stu-id="15744-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="15744-142">Cette propriété est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="15744-142">This property is read-only.</span></span>|  
|<span data-ttu-id="15744-143">**Utilisation**</span><span class="sxs-lookup"><span data-stu-id="15744-143">**Usage**</span></span>|<span data-ttu-id="15744-144">Définit comment la colonne sera utilisée par le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="15744-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15744-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15744-145">See Also</span></span>  
 <span data-ttu-id="15744-146">[Colonnes du modèle d’exploration de données](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="15744-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="15744-147">[Structures d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="15744-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="15744-148">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="15744-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="15744-149">[Modifier les propriétés d’un modèle d’exploration de données](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="15744-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="15744-150">[Outils d’exploration de données](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="15744-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="15744-151">[Créer une structure d’exploration de données relationnelle](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="15744-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="15744-152">Créer un alias pour une colonne du modèle</span><span class="sxs-lookup"><span data-stu-id="15744-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
