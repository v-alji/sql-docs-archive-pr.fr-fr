---
title: Fusion, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707695"
---
# <a name="merge-transformation"></a><span data-ttu-id="ced82-102">transformation de fusion</span><span class="sxs-lookup"><span data-stu-id="ced82-102">Merge Transformation</span></span>
  <span data-ttu-id="ced82-103">La transformation de fusion combine deux datasets triés en un seul datasets.</span><span class="sxs-lookup"><span data-stu-id="ced82-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="ced82-104">Les lignes de chaque ensemble de données sont insérées dans la sortie en fonction des valeurs de leurs colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="ced82-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="ced82-105">L'intégration de la transformation de fusion dans un flux de données permet de réaliser les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ced82-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ced82-106">Fusionner des données de deux sources de données, telles que des tables et des fichiers.</span><span class="sxs-lookup"><span data-stu-id="ced82-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="ced82-107">Créer des ensembles de données complexes en imbriquant des transformations de fusion.</span><span class="sxs-lookup"><span data-stu-id="ced82-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="ced82-108">Fusionner des lignes à nouveau après avoir corrigé les erreurs affectant les données.</span><span class="sxs-lookup"><span data-stu-id="ced82-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="ced82-109">La transformation de fusion est similaire aux transformations d'union totale.</span><span class="sxs-lookup"><span data-stu-id="ced82-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="ced82-110">Utilisez la transformation d'union totale au lieu de la transformation de fusion dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ced82-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="ced82-111">Les entrées de transformation ne sont pas triées.</span><span class="sxs-lookup"><span data-stu-id="ced82-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="ced82-112">La sortie combinée n'a pas besoin d'être triée.</span><span class="sxs-lookup"><span data-stu-id="ced82-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="ced82-113">La transformation a au moins trois entrées.</span><span class="sxs-lookup"><span data-stu-id="ced82-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="ced82-114">Spécifications relatives aux entrées</span><span class="sxs-lookup"><span data-stu-id="ced82-114">Input Requirements</span></span>  
 <span data-ttu-id="ced82-115">La transformation de fusion requiert des données triées pour ses entrées.</span><span class="sxs-lookup"><span data-stu-id="ced82-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="ced82-116">Pour plus d’informations sur cette spécification importante, consultez [Trier des données pour les transformations de fusion et de jointure de fusion](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="ced82-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="ced82-117">La transformation de fusion requiert également que les colonnes fusionnées dans ses entrées aient des métadonnées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="ced82-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="ced82-118">Par exemple, vous ne pouvez pas fusionner une colonne de type de données numérique avec une colonne de type de données caractère.</span><span class="sxs-lookup"><span data-stu-id="ced82-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="ced82-119">Si les données sont du type de données chaîne, la colonne de la deuxième entrée doit avoir une longueur inférieure ou égale à celle de la colonne de la première entrée avec laquelle elle est fusionnée.</span><span class="sxs-lookup"><span data-stu-id="ced82-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="ced82-120">Dans le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , l’interface utilisateur de la transformation de fusion mappe automatiquement les colonnes qui ont les mêmes métadonnées.</span><span class="sxs-lookup"><span data-stu-id="ced82-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="ced82-121">Vous pouvez ensuite mapper manuellement les colonnes ayant des types de données compatibles.</span><span class="sxs-lookup"><span data-stu-id="ced82-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="ced82-122">Cette transformation a deux entrées et une sortie.</span><span class="sxs-lookup"><span data-stu-id="ced82-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="ced82-123">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="ced82-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="ced82-124">Configuration de la transformation de fusion</span><span class="sxs-lookup"><span data-stu-id="ced82-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="ced82-125">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programme.</span><span class="sxs-lookup"><span data-stu-id="ced82-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ced82-126">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur de transformation de fusion** , consultez [Éditeur de transformation de fusion](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ced82-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="ced82-127">Pour plus d'informations sur les propriétés définissables par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ced82-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ced82-128">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="ced82-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="ced82-129">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="ced82-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="ced82-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ced82-130">Related Tasks</span></span>  
 <span data-ttu-id="ced82-131">Pour plus d'informations sur la définition des propriétés, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ced82-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="ced82-132">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="ced82-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="ced82-133">Trier des données pour les transformations de fusion et de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="ced82-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="ced82-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ced82-134">See Also</span></span>  
 <span data-ttu-id="ced82-135">[Transformation de jointure de fusion](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ced82-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="ced82-136">[Transformation d'union totale](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ced82-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="ced82-137">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="ced82-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="ced82-138">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="ced82-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
