---
title: Fractionnement conditionnel, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611197"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="8e61b-102">transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8e61b-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="8e61b-103">La transformation de fractionnement conditionnel peut aiguiller les lignes de données vers différentes sorties, suivant le contenu des données.</span><span class="sxs-lookup"><span data-stu-id="8e61b-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="8e61b-104">L’implémentation de la transformation du fractionnement conditionnel est similaire à une structure de décision CASE dans un langage de programmation.</span><span class="sxs-lookup"><span data-stu-id="8e61b-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="8e61b-105">La transformation évalue les expressions puis, sur la base des résultats, dirige la ligne de données vers la sortie spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8e61b-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="8e61b-106">Cette transformation offre également une sortie par défaut. Ainsi, si une ligne ne correspond à aucune expression, elle est dirigée vers la sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="8e61b-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="8e61b-107">Configuration de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8e61b-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="8e61b-108">Vous pouvez configurer la transformation de fractionnement conditionnel comme suit :</span><span class="sxs-lookup"><span data-stu-id="8e61b-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="8e61b-109">Indiquez une expression renvoyant une valeur booléenne pour chaque condition que la transformation doit tester.</span><span class="sxs-lookup"><span data-stu-id="8e61b-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="8e61b-110">Spécifiez l'ordre dans lequel les conditions sont évaluées.</span><span class="sxs-lookup"><span data-stu-id="8e61b-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="8e61b-111">L'ordre est significatif car une ligne est envoyée à la sortie correspondant à la première condition qui renvoie True.</span><span class="sxs-lookup"><span data-stu-id="8e61b-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="8e61b-112">Spécifiez la sortie par défaut de la transformation.</span><span class="sxs-lookup"><span data-stu-id="8e61b-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="8e61b-113">Il est nécessaire de spécifier une sortie par défaut pour la transformation.</span><span class="sxs-lookup"><span data-stu-id="8e61b-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="8e61b-114">Chaque ligne d'entrée ne peut être envoyée qu'à une sortie, en l'occurrence celle correspondant à la première condition qui renvoie True.</span><span class="sxs-lookup"><span data-stu-id="8e61b-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="8e61b-115">Par exemple, les conditions suivantes dirigent toutes les lignes de la colonne **FirstName** commençant par la lettre *A* vers une sortie, celles commençant par la lettre *B* vers une autre sortie et toutes les autres vers la sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="8e61b-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="8e61b-116">Sortie 1</span><span class="sxs-lookup"><span data-stu-id="8e61b-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="8e61b-117">Sortie 2</span><span class="sxs-lookup"><span data-stu-id="8e61b-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="8e61b-118">comprend des fonctions et des opérateurs permettant de créer les expressions qui évaluent les données d’entrée et dirigent les données de sortie.</span><span class="sxs-lookup"><span data-stu-id="8e61b-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="8e61b-119">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8e61b-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="8e61b-120">La transformation de fractionnement conditionnel inclut la propriété personnalisée `FriendlyExpression`.</span><span class="sxs-lookup"><span data-stu-id="8e61b-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="8e61b-121">La propriété peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="8e61b-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="8e61b-122">Pour plus d’informations, consultez [Expressions de propriété dans des packages](../../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées des transformation](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8e61b-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="8e61b-123">Cette transformation possède une entrée, une ou plusieurs sorties et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8e61b-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="8e61b-124">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="8e61b-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8e61b-125">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation de fractionnement conditionnel** , consultez [Éditeur de transformation de fractionnement conditionnel](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8e61b-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="8e61b-126">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="8e61b-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="8e61b-127">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8e61b-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8e61b-128">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="8e61b-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="8e61b-129">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="8e61b-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="8e61b-130">Pour plus d'informations sur la définition des propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8e61b-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8e61b-131">Fractionner un dataset à l'aide de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8e61b-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="8e61b-132">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="8e61b-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="8e61b-133">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8e61b-133">Related Tasks</span></span>  
 [<span data-ttu-id="8e61b-134">Fractionner un dataset à l'aide de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8e61b-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e61b-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e61b-135">See Also</span></span>  
 <span data-ttu-id="8e61b-136">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8e61b-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="8e61b-137">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="8e61b-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
