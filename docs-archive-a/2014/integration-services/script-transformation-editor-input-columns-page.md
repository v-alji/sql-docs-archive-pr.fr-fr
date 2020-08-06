---
title: Éditeur de transformation de script (page colonnes d’entrée) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695824"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="2211a-102">Éditeur de transformation de script (page Colonnes d'entrée)</span><span class="sxs-lookup"><span data-stu-id="2211a-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="2211a-103">Utilisez la page **Colonnes d’entrée** de la boîte de dialogue **Éditeur de transformation de script** pour définir les propriétés des colonnes d’entrée.</span><span class="sxs-lookup"><span data-stu-id="2211a-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2211a-104">La page **Colonnes d’entrée** ne s’affiche pas pour les composants source qui ont des sorties, mais pas d’entrées.</span><span class="sxs-lookup"><span data-stu-id="2211a-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="2211a-105">Pour en savoir plus sur le composant de script, consultez [Script Component](data-flow/transformations/script-component.md) et [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2211a-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="2211a-106">Pour en savoir plus sur la programmation du composant de script, consultez [Extension du flux de données avec le composant Script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="2211a-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2211a-107">Options</span><span class="sxs-lookup"><span data-stu-id="2211a-107">Options</span></span>  
 <span data-ttu-id="2211a-108">**Nom de l'entrée**</span><span class="sxs-lookup"><span data-stu-id="2211a-108">**Input name**</span></span>  
 <span data-ttu-id="2211a-109">Sélectionnez le nom d'une entrée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2211a-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="2211a-110">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="2211a-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="2211a-111">Utilisez les cases à cocher pour spécifier les colonnes que la transformation de script utilisera.</span><span class="sxs-lookup"><span data-stu-id="2211a-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="2211a-112">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="2211a-112">**Input Column**</span></span>  
 <span data-ttu-id="2211a-113">Sélectionnez dans la liste le nom d'une colonne d'entrée pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="2211a-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="2211a-114">Vos sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes d’entrée disponibles**.</span><span class="sxs-lookup"><span data-stu-id="2211a-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="2211a-115">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="2211a-115">**Output Alias**</span></span>  
 <span data-ttu-id="2211a-116">Permet de saisir un alias pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="2211a-116">Type an alias for each output column.</span></span> <span data-ttu-id="2211a-117">Par défaut, il s'agit du nom de la colonne d'entrée ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="2211a-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="2211a-118">**Type d'utilisation**</span><span class="sxs-lookup"><span data-stu-id="2211a-118">**Usage Type**</span></span>  
 <span data-ttu-id="2211a-119">Spécifiez si la transformation de script traite chaque colonne en `ReadOnly` ou en `ReadWrite`.</span><span class="sxs-lookup"><span data-stu-id="2211a-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2211a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2211a-120">See Also</span></span>  
 <span data-ttu-id="2211a-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2211a-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2211a-122">[Sélectionner un type de composant de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="2211a-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="2211a-123">[Éditeur de transformation de script &#40;page entrées et sorties&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="2211a-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="2211a-124">[Éditeur de transformation de script &#40;page de script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="2211a-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="2211a-125">[Éditeur de transformation de script &#40;page gestionnaires de connexions&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="2211a-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="2211a-126">Exemples supplémentaires du composant Script</span><span class="sxs-lookup"><span data-stu-id="2211a-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
