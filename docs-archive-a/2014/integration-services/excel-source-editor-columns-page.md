---
title: Éditeur de source Excel (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.columns.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 50024686-a18d-4824-b20e-c84123f89d0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0713d8d3d0c1f56bf322684a924a286e8b81af55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610751"
---
# <a name="excel-source-editor-columns-page"></a><span data-ttu-id="f751d-102">Éditeur de source Excel (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="f751d-102">Excel Source Editor (Columns Page)</span></span>
  <span data-ttu-id="f751d-103">La page **Colonnes** de la boîte de dialogue **Éditeur de source Excel** vous permet de mapper une colonne de sortie à chaque colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="f751d-103">Use the **Columns** page of the **Excel Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="f751d-104">Pour en savoir plus sur la source Excel, consultez [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="f751d-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f751d-105">Options</span><span class="sxs-lookup"><span data-stu-id="f751d-105">Options</span></span>  
 <span data-ttu-id="f751d-106">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="f751d-106">**Available External Columns**</span></span>  
 <span data-ttu-id="f751d-107">Affiche la liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="f751d-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="f751d-108">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="f751d-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="f751d-109">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="f751d-109">**External Column**</span></span>  
 <span data-ttu-id="f751d-110">Affiche les colonnes externes (sources) dans l'ordre de lecture de la tâche.</span><span class="sxs-lookup"><span data-stu-id="f751d-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="f751d-111">Vous pouvez modifier cet ordre en désactivant les colonnes sélectionnées dans la table mentionnée ci-dessus, puis en sélectionnant les colonnes externes dans la liste, dans un ordre différent.</span><span class="sxs-lookup"><span data-stu-id="f751d-111">You can change this order by first clearing the selected columns in the table discussed above, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="f751d-112">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="f751d-112">**Output Column**</span></span>  
 <span data-ttu-id="f751d-113">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="f751d-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="f751d-114">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; vous pouvez néanmoins choisir n'importe quel nom unique et significatif.</span><span class="sxs-lookup"><span data-stu-id="f751d-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="f751d-115">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f751d-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f751d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f751d-116">See Also</span></span>  
 <span data-ttu-id="f751d-117">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f751d-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f751d-118">[Éditeur de source Excel &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="f751d-118">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="f751d-119">[Éditeur de source Excel &#40;page sortie d’erreur&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f751d-119">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="f751d-120">[Gestionnaire de connexions Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f751d-120">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="f751d-121">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="f751d-121">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
