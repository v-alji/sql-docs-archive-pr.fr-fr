---
title: Tri, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611187"
---
# <a name="sort-transformation"></a><span data-ttu-id="5cdd7-102">transformation de tri</span><span class="sxs-lookup"><span data-stu-id="5cdd7-102">Sort Transformation</span></span>
  <span data-ttu-id="5cdd7-103">La transformation de tri trie les données d'entrée dans l'ordre croissant ou décroissant et copie les données triées dans sa sortie.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="5cdd7-104">Vous pouvez appliquer plusieurs tris à une entrée ; chaque tri est identifié par un chiffre qui détermine l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="5cdd7-105">La colonne qui possède le plus petit nombre est triée en premier, puis la colonne de tri ayant le deuxième plus petit nombre, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="5cdd7-106">Par exemple, si une colonne nommée **PaysRégion** a un ordre de tri égal à 1 et qu’une colonne nommée **Ville** a un ordre de tri égal à 2, la sortie est triée par pays/région puis par ville.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="5cdd7-107">Un nombre positif indique que le tri est croissant, tandis qu'un nombre négatif indique qu'il est décroissant.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="5cdd7-108">Les colonnes qui ne sont pas triées ont un ordre de tri égal à 0.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="5cdd7-109">Les colonnes qui ne sont pas sélectionnées pour le tri sont automatiquement copiées dans la sortie de la transformation avec les colonnes triées.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="5cdd7-110">La transformation de tri comprend un ensemble d'options de comparaison qui permettent de définir la façon dont la transformation gère les données de chaîne dans une colonne.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="5cdd7-111">Pour plus d'informations, voir [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="5cdd7-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cdd7-112">La transformation de tri ne trie pas les GUID dans le même ordre que la clause ORDER BY dans Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="5cdd7-113">Alors que la transformation de tri trie les GUID commençant par un numéro compris entre 0 et 9 avant les GUID commençant par une lettre comprise entre A et F, la clause ORDER BY, telle qu'elle est implémentée dans le [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], les trie différemment.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="5cdd7-114">Pour plus d’informations, consultez [Clause ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5cdd7-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="5cdd7-115">La transformation de tri peut également supprimer les doublons de lignes dans le cadre du tri.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="5cdd7-116">Les doublons de lignes sont des lignes possédant les mêmes valeurs de clé de tri.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="5cdd7-117">La valeur de clé de tri est générée en fonction des options de comparaison de chaînes en cours d'utilisation ; par conséquent, différentes chaînes littérales peuvent avoir les mêmes valeurs de clé de tri.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="5cdd7-118">Dans les colonnes d'entrée, la transformation identifie en tant que doublons les lignes qui ont des valeurs différentes mais la même clé de tri.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="5cdd7-119">La transformation de tri inclut la propriété personnalisée `MaximumThreads`, qui peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="5cdd7-120">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41; ](../../expressions/integration-services-ssis-expressions.md), [Expressions de propriété dans des packages](../../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées des transformations](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5cdd7-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="5cdd7-121">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-121">This transformation has one input and one output.</span></span> <span data-ttu-id="5cdd7-122">Elle ne prend pas en charge les sorties d'erreur.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="5cdd7-123">Configuration de la transformation de tri</span><span class="sxs-lookup"><span data-stu-id="5cdd7-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="5cdd7-124">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programme.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5cdd7-125">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur de transformation de tri** , consultez [Éditeur de transformation de tri](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5cdd7-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="5cdd7-126">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="5cdd7-127">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5cdd7-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5cdd7-128">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="5cdd7-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="5cdd7-129">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="5cdd7-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="5cdd7-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5cdd7-130">Related Tasks</span></span>  
 <span data-ttu-id="5cdd7-131">Pour plus d’informations sur la définition des propriétés du composant, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="5cdd7-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="5cdd7-132">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5cdd7-132">Related Content</span></span>  
 <span data-ttu-id="5cdd7-133">Exemple, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), sur codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="5cdd7-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cdd7-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5cdd7-134">See Also</span></span>  
 <span data-ttu-id="5cdd7-135">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="5cdd7-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="5cdd7-136">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="5cdd7-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
