---
title: Éditeur de transformation de jointure de fusion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611159"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="ba362-102">Éditeur de transformation de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="ba362-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="ba362-103">La boîte de dialogue **Éditeur de transformation de jointure de fusion** permet de préciser le type de jointure, les colonnes qui composent cette dernière et les colonnes de sortie, afin de pouvoir fusionner deux entrées combinées par une opération de jointure.</span><span class="sxs-lookup"><span data-stu-id="ba362-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba362-104">La transformation de jointure de fusion requiert des données triées pour ses entrées.</span><span class="sxs-lookup"><span data-stu-id="ba362-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="ba362-105">Pour plus d’informations sur cette spécification importante, consultez [Trier des données pour les transformations de fusion et de jointure de fusion](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="ba362-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="ba362-106">Pour en savoir plus sur la transformation de jointure de fusion, consultez [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ba362-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba362-107">Options</span><span class="sxs-lookup"><span data-stu-id="ba362-107">Options</span></span>  
 <span data-ttu-id="ba362-108">**Type de jointure**</span><span class="sxs-lookup"><span data-stu-id="ba362-108">**Join type**</span></span>  
 <span data-ttu-id="ba362-109">Permet de préciser l'utilisation d'une jointure interne, externe gauche ou entière.</span><span class="sxs-lookup"><span data-stu-id="ba362-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="ba362-110">**Échanger les entrées**</span><span class="sxs-lookup"><span data-stu-id="ba362-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="ba362-111">Permet d’intervertir l’ordre des entrées par le bouton **Échanger les entrées** .</span><span class="sxs-lookup"><span data-stu-id="ba362-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="ba362-112">Ceci peut s'avérer utile dans le cas de jointure externe gauche.</span><span class="sxs-lookup"><span data-stu-id="ba362-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="ba362-113">**Entrée**</span><span class="sxs-lookup"><span data-stu-id="ba362-113">**Input**</span></span>  
 <span data-ttu-id="ba362-114">Permet de sélectionner, dans la liste des entrées disponibles, chaque colonne à inclure à la sortie fusionnée.</span><span class="sxs-lookup"><span data-stu-id="ba362-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="ba362-115">Les entrées se présentent sous forme de deux tables distinctes.</span><span class="sxs-lookup"><span data-stu-id="ba362-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="ba362-116">Permet de choisir les colonnes à inclure dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="ba362-116">Select columns to include in the output.</span></span> <span data-ttu-id="ba362-117">Pour créer une jointure entre tables, faites glisser les colonnes.</span><span class="sxs-lookup"><span data-stu-id="ba362-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="ba362-118">Pour supprimer une jointure, sélectionnez-la et appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="ba362-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="ba362-119">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="ba362-119">**Input Column**</span></span>  
 <span data-ttu-id="ba362-120">Permet de choisir une colonne à inclure à la sortie fusionnée d'après la liste de colonnes disponibles dans l'entrée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba362-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="ba362-121">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="ba362-121">**Output Alias**</span></span>  
 <span data-ttu-id="ba362-122">Permet de saisir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="ba362-122">Type an alias for each output column.</span></span> <span data-ttu-id="ba362-123">Par défaut, il s'agit du nom de la colonne d'entrée ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="ba362-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba362-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba362-124">See Also</span></span>  
 <span data-ttu-id="ba362-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ba362-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ba362-126">[Trier des données pour les transformations de fusion et de jointure de fusion](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="ba362-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="ba362-127">[Étendre un DataSet à l’aide de la transformation de jointure de fusion](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ba362-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="ba362-128">[Transformation de fusion](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ba362-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="ba362-129">Transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="ba362-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
