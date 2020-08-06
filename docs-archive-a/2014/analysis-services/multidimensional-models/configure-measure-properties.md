---
title: Configurer les propriétés de mesure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705648"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="65119-102">Configurer des propriétés de mesure</span><span class="sxs-lookup"><span data-stu-id="65119-102">Configure Measure Properties</span></span>
  <span data-ttu-id="65119-103">Les propriétés des mesures vous permettent de définir le fonctionnement des mesures et de contrôler l'affichage des mesures pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="65119-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="65119-104">Vous pouvez définir les propriétés dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] au moment de la création ou modification d'un cube ou d'une mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="65119-105">Vous pouvez également le faire par programmation, en utilisant MDX ou AMO.</span><span class="sxs-lookup"><span data-stu-id="65119-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="65119-106">Pour plus d’informations, consultez [Création de mesures et de groupes de mesures dans les modèles multidimensionnels](create-measures-and-measure-groups-in-multidimensional-models.md), [Instruction CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) ou [Programmation d’objets de base OLAP AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="65119-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="65119-107">Propriétés des mesures</span><span class="sxs-lookup"><span data-stu-id="65119-107">Measure Properties</span></span>  
 <span data-ttu-id="65119-108">Les mesures héritent certaines propriétés du groupe de mesures dont elles sont membres, sauf si ces propriétés sont remplacées à l'échelle de la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="65119-109">Les propriétés d'une mesure déterminent la manière dont la mesure est agrégée, son type de données, le nom qui s'affiche pour l'utilisateur, le dossier d'affichage dans lequel elle apparaît, sa chaîne de format, l'expression de mesure (le cas échéant), la colonne source sous-jacente et sa visibilité par rapport aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="65119-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="65119-110">Propriété</span><span class="sxs-lookup"><span data-stu-id="65119-110">Property</span></span>|<span data-ttu-id="65119-111">Définition</span><span class="sxs-lookup"><span data-stu-id="65119-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="65119-112">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="65119-112">Required.</span></span> <span data-ttu-id="65119-113">Détermine la manière dont les mesures sont agrégées.</span><span class="sxs-lookup"><span data-stu-id="65119-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="65119-114">`Sum` est l'agrégation par défaut.</span><span class="sxs-lookup"><span data-stu-id="65119-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="65119-115">Pour plus d’informations et obtenir une description de chaque fonction, consultez [Utiliser des fonctions d’agrégation](use-aggregate-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="65119-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="65119-116">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="65119-116">Required.</span></span> <span data-ttu-id="65119-117">Spécifie le type de données de la colonne dans la table de faits sous-jacente à laquelle est liée la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="65119-118">Par défaut, cette valeur est héritée de la colonne source.</span><span class="sxs-lookup"><span data-stu-id="65119-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="65119-119">Fournit une description de la mesure qui peut être exposée dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="65119-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="65119-120">Spécifie le dossier dans lequel apparaît la mesure lorsque les utilisateurs se connectent au cube.</span><span class="sxs-lookup"><span data-stu-id="65119-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="65119-121">Si un cube possède plusieurs mesures, vous pouvez utiliser les dossiers d'affichage pour classer les mesures par catégories et faciliter la navigation pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="65119-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="65119-122">Vous pouvez choisir le format dans lequel les utilisateurs voient les valeurs de mesure à l'aide de la propriété `FormatString` de la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="65119-123">Une liste de formats d'affichage est fournie dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], mais vous pouvez spécifier de nombreux autres formats qui ne figurent pas dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="65119-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="65119-124">Vous pouvez spécifier n'importe quel format nommé ou défini par l'utilisateur, à condition qu'il soit valide dans Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="65119-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="65119-125">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="65119-125">Required.</span></span> <span data-ttu-id="65119-126">Affiche l'identificateur (ID) unique de la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="65119-127">Cette propriété est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="65119-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="65119-128">Spécifie une expression MDX contrainte définissant la valeur de la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="65119-129">L'expression est évaluée au niveau feuille avant d'être agrégée et permet d'effectuer la pondération d'une valeur.</span><span class="sxs-lookup"><span data-stu-id="65119-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="65119-130">C'est le cas, par exemple, dans une conversion monétaire où un montant des ventes est pondéré en fonction du taux de change.</span><span class="sxs-lookup"><span data-stu-id="65119-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="65119-131">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="65119-131">Required.</span></span> <span data-ttu-id="65119-132">Spécifie le nom de la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="65119-133">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="65119-133">Required.</span></span> <span data-ttu-id="65119-134">Spécifie la colonne de la vue de source de données à laquelle est liée la mesure.</span><span class="sxs-lookup"><span data-stu-id="65119-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="65119-135">Consultez [Sources de données et liaisons &#40;SSAS Multidimensionnel&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="65119-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="65119-136">Détermine la visibilité de la mesure dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="65119-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65119-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65119-137">See Also</span></span>  
 <span data-ttu-id="65119-138">[Configurer les propriétés d’un groupe de mesures](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="65119-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="65119-139">Modification des mesures</span><span class="sxs-lookup"><span data-stu-id="65119-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
