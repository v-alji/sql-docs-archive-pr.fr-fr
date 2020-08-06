---
title: Destination d’apprentissage du modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610785"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="e287b-102">Destination d’apprentissage du modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="e287b-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="e287b-103">La destination d'apprentissage du modèle d'exploration de données exerce les modèles d'exploration de données en transmettant les données que la destination reçoit par le biais des algorithmes de modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e287b-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="e287b-104">Plusieurs modèles d'exploration de données peuvent faire l'objet d'un apprentissage par une même destination si les modèles sont construits sur la même structure d'exploration des données.</span><span class="sxs-lookup"><span data-stu-id="e287b-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="e287b-105">Pour plus d’informations, consultez [Colonnes de structure d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) et [Colonnes d’un modèle d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="e287b-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="e287b-106">Configuration de la destination d'apprentissage du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="e287b-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="e287b-107">Si une colonne de niveau de cas de la structure cible et les modèles créés sur cette structure ont un contenu de type KEY TIME ou KEY SEQUENCE, les données d'entrée doivent être triées sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="e287b-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="e287b-108">Par exemple, les modèles créés à l'aide de l'algorithme Microsoft Time Series utilisent le type de contenu KEY TIME.</span><span class="sxs-lookup"><span data-stu-id="e287b-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="e287b-109">Si les données d'entrée ne sont pas triées, le traitement du modèle risque d'échouer.</span><span class="sxs-lookup"><span data-stu-id="e287b-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="e287b-110">Si les données doivent être triées, vous pouvez utiliser une transformation de tri plus haut dans le flux de données afin de trier les données.</span><span class="sxs-lookup"><span data-stu-id="e287b-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="e287b-111">Ceci ne s'applique pas aux colonnes dont le type de contenu est KEY.</span><span class="sxs-lookup"><span data-stu-id="e287b-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="e287b-112">Pour plus d’informations, consultez [Types de contenu &#40;exploration de données&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) et [Transformation de tri](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e287b-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e287b-113">L'entrée de la destination d'apprentissage du modèle d'exploration de données doit être triée.</span><span class="sxs-lookup"><span data-stu-id="e287b-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="e287b-114">Pour trier les données, vous pouvez inclure une destination de tri en amont de la destination d'apprentissage du modèle d'exploration de données dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="e287b-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="e287b-115">Pour plus d’informations, voir [Sort Transformation](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e287b-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="e287b-116">La destination comporte une entrée et aucune sortie.</span><span class="sxs-lookup"><span data-stu-id="e287b-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="e287b-117">La destination d’apprentissage du modèle d’exploration de données utilise un gestionnaire de connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter au projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à l’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient la structure et les modèles d’exploration de données dont la destination assure l’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="e287b-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="e287b-118">Pour plus d'informations, consultez [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e287b-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e287b-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="e287b-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e287b-120">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur d’apprentissage du modèle d’exploration de données**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e287b-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e287b-121">Éditeur d’apprentissage du modèle d’exploration de données &#40;onglet Connexion&#41;</span><span class="sxs-lookup"><span data-stu-id="e287b-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="e287b-122">Éditeur d’apprentissage du modèle d’exploration de données &#40;onglet Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="e287b-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="e287b-123">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="e287b-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e287b-124">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e287b-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e287b-125">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="e287b-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e287b-126">Propriétés personnalisées de la destination d'apprentissage du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="e287b-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="e287b-127">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e287b-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
