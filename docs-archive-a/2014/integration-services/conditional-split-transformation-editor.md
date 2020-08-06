---
title: Éditeur de transformation de fractionnement conditionnel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601621"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="83e16-102">Éditeur de transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="83e16-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="83e16-103">Utilisez la boîte de dialogue **Éditeur de transformation de fractionnement conditionnel** pour créer des expressions, définir l'ordre dans lequel les expressions sont évaluées et nommer les sorties d'un fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="83e16-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="83e16-104">Cette boîte de dialogue comprend des fonctions mathématiques, de chaînes de caractères et de date/heure, ainsi que des opérateurs utilisés pour créer des expressions.</span><span class="sxs-lookup"><span data-stu-id="83e16-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="83e16-105">La première condition évaluée comme vraie détermine la sortie vers laquelle une ligne est dirigée.</span><span class="sxs-lookup"><span data-stu-id="83e16-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83e16-106">La transformation de fractionnement conditionnel dirige chaque ligne d'entrée vers une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="83e16-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="83e16-107">Si vous entrez plusieurs conditions, la transformation envoie chaque ligne à la première sortie pour laquelle la condition est remplie et ne tient pas compte des conditions suivantes pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="83e16-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="83e16-108">Si vous devez évaluer successivement plusieurs conditions, vous devrez peut-être enchaîner plusieurs transformations de fractionnement conditionnel dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="83e16-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="83e16-109">Pour en savoir plus sur la transformation de fractionnement conditionnel, consultez [Transformation de fractionnement conditionnel](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="83e16-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83e16-110">Options</span><span class="sxs-lookup"><span data-stu-id="83e16-110">Options</span></span>  
 <span data-ttu-id="83e16-111">**Commande**</span><span class="sxs-lookup"><span data-stu-id="83e16-111">**Order**</span></span>  
 <span data-ttu-id="83e16-112">Sélectionnez une ligne et utilisez les touches de direction à droite pour modifier l'ordre dans lequel les expressions sont évaluées.</span><span class="sxs-lookup"><span data-stu-id="83e16-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="83e16-113">**Nom de la sortie**</span><span class="sxs-lookup"><span data-stu-id="83e16-113">**Output Name**</span></span>  
 <span data-ttu-id="83e16-114">Donnez un nom à la sortie.</span><span class="sxs-lookup"><span data-stu-id="83e16-114">Provide an output name.</span></span> <span data-ttu-id="83e16-115">Par défaut, il s'agit d'une liste de cas numérotée ; vous pouvez néanmoins choisir un nom unique et illustratif.</span><span class="sxs-lookup"><span data-stu-id="83e16-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="83e16-116">**Condition**</span><span class="sxs-lookup"><span data-stu-id="83e16-116">**Condition**</span></span>  
 <span data-ttu-id="83e16-117">Tapez une expression ou créez-en une en faisant glisser les colonnes, variables et fonctions disponibles.</span><span class="sxs-lookup"><span data-stu-id="83e16-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="83e16-118">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="83e16-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="83e16-119">**Rubriques connexes :**  [Expressions Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Opérateurs &#40;Expression SSIS&#41;](expressions/operators-ssis-expression.md), et [Fonctions &#40;Expression SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="83e16-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="83e16-120">**Nom de sortie par défaut**</span><span class="sxs-lookup"><span data-stu-id="83e16-120">**Default output name**</span></span>  
 <span data-ttu-id="83e16-121">Tapez un nom pour la sortie par défaut ou utilisez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="83e16-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="83e16-122">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="83e16-122">**Configure error output**</span></span>  
 <span data-ttu-id="83e16-123">Spécifiez comment gérer les erreurs dans la boîte de dialogue [Configurer la sortie d’erreur](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="83e16-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e16-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83e16-124">See Also</span></span>  
 <span data-ttu-id="83e16-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="83e16-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="83e16-126">Fractionner un dataset à l'aide de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="83e16-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
