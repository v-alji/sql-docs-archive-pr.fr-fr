---
title: Union totale, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613040"
---
# <a name="union-all-transformation"></a><span data-ttu-id="03d4e-102">transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="03d4e-102">Union All Transformation</span></span>
  <span data-ttu-id="03d4e-103">La transformation d'union totale combine plusieurs entrées en une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="03d4e-104">Par exemple, les sorties de cinq sources de fichier plat peuvent être des entrées de la transformation d'union totale et être combinées en une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="03d4e-105">Entrées et sorties</span><span class="sxs-lookup"><span data-stu-id="03d4e-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="03d4e-106">Les entrées de transformation sont ajoutées à la sortie de transformation une par une ; aucune réorganisation de lignes n'intervient.</span><span class="sxs-lookup"><span data-stu-id="03d4e-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="03d4e-107">Si le package nécessite une sortie triée, vous devez utiliser la transformation de fusion au lieu de la transformation d'union totale.</span><span class="sxs-lookup"><span data-stu-id="03d4e-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="03d4e-108">La première entrée que vous connectez à la transformation d'union totale est l'entrée à partir de laquelle la transformation crée la sortie de transformation.</span><span class="sxs-lookup"><span data-stu-id="03d4e-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="03d4e-109">Les colonnes des entrées que vous connectez ensuite à la transformation sont mappées avec les colonnes de la sortie de transformation.</span><span class="sxs-lookup"><span data-stu-id="03d4e-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="03d4e-110">Pour fusionner les entrées, vous mappez les colonnes des entrées avec les colonnes de la sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="03d4e-111">Une colonne d'au moins une entrée doit être mappée avec chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="03d4e-112">Vous ne pouvez mapper deux colonnes que si leurs métadonnées correspondent.</span><span class="sxs-lookup"><span data-stu-id="03d4e-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="03d4e-113">Par exemple, les colonnes mappées doivent avoir le même type de données.</span><span class="sxs-lookup"><span data-stu-id="03d4e-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="03d4e-114">Si les colonnes mappées contiennent des données de chaîne et que la longueur de la colonne de sortie est plus courte que celle de la colonne d'entrée, la longueur de la colonne de sortie est automatiquement augmentée de manière à contenir la colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="03d4e-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="03d4e-115">Les colonnes d'entrée non mappées avec des colonnes de sortie ont la valeur NULL dans les colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="03d4e-116">Cette transformation a plusieurs entrées et une sortie.</span><span class="sxs-lookup"><span data-stu-id="03d4e-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="03d4e-117">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="03d4e-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="03d4e-118">Configuration de la transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="03d4e-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="03d4e-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="03d4e-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="03d4e-120">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur de transformation d’union totale** , consultez [Éditeur de transformation d’union totale](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="03d4e-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="03d4e-121">Pour plus d’informations sur les propriétés que vous pouvez définir par programmation, consultez [Propriétés communes](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="03d4e-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="03d4e-122">Pour plus d'informations sur la définition des propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="03d4e-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="03d4e-123">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="03d4e-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="03d4e-124">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="03d4e-124">Related Tasks</span></span>  
 [<span data-ttu-id="03d4e-125">Fusionner des données à l'aide de la transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="03d4e-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
