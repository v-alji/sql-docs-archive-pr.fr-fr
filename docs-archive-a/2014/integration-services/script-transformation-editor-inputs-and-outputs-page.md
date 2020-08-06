---
title: Éditeur de transformation de script (page entrées et sorties) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695820"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="eb1ec-102">Éditeur de transformation de script (page Entrées et sorties)</span><span class="sxs-lookup"><span data-stu-id="eb1ec-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="eb1ec-103">Utilisez la page **Entrées et sorties** de la boîte de dialogue **Éditeur de transformation de script** pour ajouter, supprimer et configurer les entrées et les sorties destinées à la transformation de script.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb1ec-104">Les composants source disposent de sorties mais d'aucune entrée ; à l'inverse, les composants de destination possèdent des entrées mais aucune sortie.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="eb1ec-105">Les transformations, elles, ont les deux.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="eb1ec-106">Pour en savoir plus sur le composant de script, consultez [Script Component](data-flow/transformations/script-component.md) et [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="eb1ec-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="eb1ec-107">Pour en savoir plus sur la programmation du composant de script, consultez [Extension du flux de données avec le composant Script](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="eb1ec-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb1ec-108">Options</span><span class="sxs-lookup"><span data-stu-id="eb1ec-108">Options</span></span>  
 <span data-ttu-id="eb1ec-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="eb1ec-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="eb1ec-110">Permet de sélectionner une entrée ou une sortie à gauche pour en voir les propriétés dans le tableau de droite.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="eb1ec-111">Les propriétés pouvant être modifiées varient en fonction de la sélection faite.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="eb1ec-112">La plupart des propriétés affichées sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="eb1ec-113">Pour plus d'informations sur chacune de ces propriétés, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="eb1ec-114">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="eb1ec-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="eb1ec-115">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="eb1ec-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="eb1ec-116">**Ajouter une sortie**</span><span class="sxs-lookup"><span data-stu-id="eb1ec-116">**Add Output**</span></span>  
 <span data-ttu-id="eb1ec-117">Ajoute une sortie à la liste.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="eb1ec-118">**Ajouter une colonne**</span><span class="sxs-lookup"><span data-stu-id="eb1ec-118">**Add Column**</span></span>  
 <span data-ttu-id="eb1ec-119">Sélectionnez un dossier dans lequel placer la nouvelle colonne de sortie, puis ajoutez la colonne en cliquant sur **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="eb1ec-120">**Supprimer une sortie**</span><span class="sxs-lookup"><span data-stu-id="eb1ec-120">**Remove Output**</span></span>  
 <span data-ttu-id="eb1ec-121">Sélectionnez une sortie, puis supprimez-la en cliquant sur **Supprimer une sortie**.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="eb1ec-122">**Supprimer une colonne**</span><span class="sxs-lookup"><span data-stu-id="eb1ec-122">**Remove Column**</span></span>  
 <span data-ttu-id="eb1ec-123">Sélectionnez une colonne, puis cliquez sur le bouton **Supprimer une colonne**pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="eb1ec-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1ec-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb1ec-124">See Also</span></span>  
 <span data-ttu-id="eb1ec-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="eb1ec-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="eb1ec-126">[Sélectionner un type de composant de script](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="eb1ec-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="eb1ec-127">[Éditeur de transformation de script &#40;page colonnes d’entrée&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb1ec-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="eb1ec-128">[Éditeur de transformation de script &#40;page de script&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb1ec-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="eb1ec-129">[Éditeur de transformation de script &#40;page gestionnaires de connexions&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb1ec-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="eb1ec-130">Exemples supplémentaires du composant Script</span><span class="sxs-lookup"><span data-stu-id="eb1ec-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
