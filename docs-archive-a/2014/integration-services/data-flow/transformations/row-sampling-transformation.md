---
title: Échantillonnage de lignes, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710776"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="4213f-102">transformation d'échantillonnage de lignes</span><span class="sxs-lookup"><span data-stu-id="4213f-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="4213f-103">La transformation d'échantillonnage de lignes permet d'obtenir un sous-ensemble sélectionné aléatoirement d'un ensemble de données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4213f-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="4213f-104">Vous pouvez spécifier la taille exacte de l'échantillon de sortie ainsi que la valeur de départ du générateur de nombres aléatoires.</span><span class="sxs-lookup"><span data-stu-id="4213f-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="4213f-105">Il existe de nombreuses applications de l'échantillonnage aléatoire.</span><span class="sxs-lookup"><span data-stu-id="4213f-105">There are many applications for random sampling.</span></span> <span data-ttu-id="4213f-106">Par exemple, une entreprise souhaitant sélectionner aléatoirement 50 employés pour l'attribution de prix dans une loterie peut utiliser la transformation d'échantillonnage de lignes dans la base de données des employés afin de générer le nombre exact de gagnants.</span><span class="sxs-lookup"><span data-stu-id="4213f-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="4213f-107">La transformation d'échantillonnage de lignes permet également de créer, lors du développement des packages, un ensemble de données réduit mais représentatif.</span><span class="sxs-lookup"><span data-stu-id="4213f-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="4213f-108">Vous pouvez tester l'exécution des packages et la transformation des données avec des données très représentatives, mais plus rapidement car c'est un échantillon aléatoire qui est utilisé, au lieu de l'ensemble complet des données.</span><span class="sxs-lookup"><span data-stu-id="4213f-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="4213f-109">Étant donné que l'échantillon de dataset utilisé par le package de test a toujours la même taille, le recours à l'échantillon de sous-ensemble facilite également l'identification des problèmes de performances dans le package.</span><span class="sxs-lookup"><span data-stu-id="4213f-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="4213f-110">Cette transformation est similaire à la transformation de l'échantillonnage par pourcentage, qui crée un échantillon de dataset en sélectionnant un pourcentage de lignes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4213f-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="4213f-111">Consultez [Transformation de l’échantillonnage du pourcentage](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4213f-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="4213f-112">Configuration de la transformation d'échantillonnage de lignes</span><span class="sxs-lookup"><span data-stu-id="4213f-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="4213f-113">La transformation d'échantillonnage de lignes crée un échantillon de dataset en sélectionnant un nombre spécifié de lignes de l'entrée de transformation.</span><span class="sxs-lookup"><span data-stu-id="4213f-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="4213f-114">La sélection de lignes de l'entrée de transformation étant aléatoire, l'échantillon obtenu est représentatif de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="4213f-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="4213f-115">Vous pouvez également spécifier la valeur de départ utilisée par le générateur de nombres aléatoires afin de définir la façon dont la transformation sélectionne les lignes.</span><span class="sxs-lookup"><span data-stu-id="4213f-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="4213f-116">L'utilisation de la même valeur aléatoire de départ sur la même entrée de transformation crée toujours le même échantillon en sortie.</span><span class="sxs-lookup"><span data-stu-id="4213f-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="4213f-117">Si aucune valeur de départ n'est spécifiée, la transformation utilise le nombre de cycles du système d'exploitation pour créer le nombre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="4213f-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="4213f-118">Par conséquent, vous pouvez utiliser la même valeur de départ pendant le test, pour vérifier les résultats de la transformation durant le développement et le test du package, puis adopter une valeur aléatoire de départ lorsque le package passe en production.</span><span class="sxs-lookup"><span data-stu-id="4213f-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="4213f-119">La transformation d'échantillonnage de lignes inclut la propriété personnalisée `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="4213f-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="4213f-120">La propriété peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="4213f-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="4213f-121">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41; ](../../expressions/integration-services-ssis-expressions.md), [Expressions de propriété dans des packages](../../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées des transformations](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4213f-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="4213f-122">Cette transformation a une entrée et deux sorties.</span><span class="sxs-lookup"><span data-stu-id="4213f-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="4213f-123">Elle ne possède aucune sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="4213f-123">It has no error output.</span></span>  
  
 <span data-ttu-id="4213f-124">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="4213f-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4213f-125">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation d’échantillonnage de ligne**, consultez [Éditeur de transformation d’échantillonnage de ligne &#40;page Échantillonnage&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="4213f-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="4213f-126">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="4213f-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="4213f-127">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4213f-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4213f-128">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="4213f-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="4213f-129">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="4213f-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="4213f-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="4213f-130">Related Tasks</span></span>  
 [<span data-ttu-id="4213f-131">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="4213f-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
