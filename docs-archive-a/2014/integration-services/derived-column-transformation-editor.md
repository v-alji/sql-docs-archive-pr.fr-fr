---
title: Éditeur de transformation de colonne dérivée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613563"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="5ff99-102">Éditeur de transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="5ff99-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="5ff99-103">Utilisez la boîte de dialogue **Éditeur de transformation de colonne dérivée** pour créer des expressions qui remplissent de nouvelles colonnes ou des colonnes de remplacement.</span><span class="sxs-lookup"><span data-stu-id="5ff99-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="5ff99-104">Pour en savoir plus sur la transformation de colonne dérivée, consultez [Transformation de colonne dérivée](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5ff99-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ff99-105">Options</span><span class="sxs-lookup"><span data-stu-id="5ff99-105">Options</span></span>  
 <span data-ttu-id="5ff99-106">**Variables et colonnes**</span><span class="sxs-lookup"><span data-stu-id="5ff99-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="5ff99-107">Pour créer une expression qui utilise une variable ou une colonne d'entrée, faites glisser la variable ou la colonne à partir de la liste des variables et colonnes disponibles vers une ligne d'une table existante dans le volet inférieur ou vers une nouvelle ligne au bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="5ff99-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="5ff99-108">**Fonctions et opérateurs**</span><span class="sxs-lookup"><span data-stu-id="5ff99-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="5ff99-109">Pour créer une expression qui utilise une fonction ou un opérateur dans le but d'évaluer des données d'entrée ou de diriger des données de sortie, faites-les glisser à partir de la liste dans le volet inférieur.</span><span class="sxs-lookup"><span data-stu-id="5ff99-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="5ff99-110">**Nom de la colonne dérivée**</span><span class="sxs-lookup"><span data-stu-id="5ff99-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="5ff99-111">Fournissez un nom pour la colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="5ff99-111">Provide a derived column name.</span></span> <span data-ttu-id="5ff99-112">Par défaut, il s'agit d'une liste numérotée de colonnes dérivées ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="5ff99-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="5ff99-113">**Colonne dérivée**</span><span class="sxs-lookup"><span data-stu-id="5ff99-113">**Derived Column**</span></span>  
 <span data-ttu-id="5ff99-114">Sélectionnez une colonne dérivée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5ff99-114">Select a derived column from the list.</span></span> <span data-ttu-id="5ff99-115">Choisissez d'ajouter la colonne dérivée comme nouvelle colonne de sortie ou de remplacer les données d'une colonne existante.</span><span class="sxs-lookup"><span data-stu-id="5ff99-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="5ff99-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="5ff99-116">**Expression**</span></span>  
 <span data-ttu-id="5ff99-117">Tapez une expression ou créez-en une en faisant glisser la liste précédente des colonnes, variables et fonctions disponibles.</span><span class="sxs-lookup"><span data-stu-id="5ff99-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="5ff99-118">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="5ff99-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="5ff99-119">**Rubriques connexes :**[Expressions Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Opérateurs &#40;expression SSIS&#41;](expressions/operators-ssis-expression.md) et [Fonctions &#40;expression SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="5ff99-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="5ff99-120">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="5ff99-120">**Data Type**</span></span>  
 <span data-ttu-id="5ff99-121">Si vous ajoutez des données à une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** évalue automatiquement l’expression et définit correctement le type de données.</span><span class="sxs-lookup"><span data-stu-id="5ff99-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="5ff99-122">La valeur de cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5ff99-122">The value of this column is read-only.</span></span> <span data-ttu-id="5ff99-123">Pour plus d’informations, consultez [Types de données Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5ff99-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="5ff99-124">**Longueur**</span><span class="sxs-lookup"><span data-stu-id="5ff99-124">**Length**</span></span>  
 <span data-ttu-id="5ff99-125">Si vous ajoutez des données à une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** évalue automatiquement l’expression et définit la longueur de colonne des données de chaînes.</span><span class="sxs-lookup"><span data-stu-id="5ff99-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="5ff99-126">La valeur de cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5ff99-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="5ff99-127">**Précision**</span><span class="sxs-lookup"><span data-stu-id="5ff99-127">**Precision**</span></span>  
 <span data-ttu-id="5ff99-128">Si vous ajoutez des données à une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** définit automatiquement la précision des données numériques en fonction du type de données.</span><span class="sxs-lookup"><span data-stu-id="5ff99-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="5ff99-129">La valeur de cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5ff99-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="5ff99-130">**Mise à l’échelle**</span><span class="sxs-lookup"><span data-stu-id="5ff99-130">**Scale**</span></span>  
 <span data-ttu-id="5ff99-131">Si vous ajoutez des données à une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** définit automatiquement l’échelle des données numériques en fonction du type de données.</span><span class="sxs-lookup"><span data-stu-id="5ff99-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="5ff99-132">La valeur de cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5ff99-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="5ff99-133">**Page de codes**</span><span class="sxs-lookup"><span data-stu-id="5ff99-133">**Code Page**</span></span>  
 <span data-ttu-id="5ff99-134">Si vous ajoutez des données à une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** définit automatiquement la page de codes pour le type de données DT_STR.</span><span class="sxs-lookup"><span data-stu-id="5ff99-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="5ff99-135">Vous pouvez mettre à jour **Page de codes**.</span><span class="sxs-lookup"><span data-stu-id="5ff99-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="5ff99-136">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="5ff99-136">**Configure error output**</span></span>  
 <span data-ttu-id="5ff99-137">Spécifiez comment gérer les erreurs dans la boîte de dialogue [Configurer la sortie d’erreur](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="5ff99-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff99-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ff99-138">See Also</span></span>  
 <span data-ttu-id="5ff99-139">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5ff99-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="5ff99-140">Dériver les valeurs de colonnes à l'aide de la transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="5ff99-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
