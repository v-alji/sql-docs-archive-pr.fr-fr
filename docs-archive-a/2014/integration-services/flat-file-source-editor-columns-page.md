---
title: Éditeur de source de fichier plat (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601597"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="ae1dd-102">Éditeur de source de fichier plat (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="ae1dd-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="ae1dd-103">Utilisez le nœud **Colonnes** de la boîte de dialogue **Éditeur de source de fichier plat** pour mapper une colonne de sortie à chaque colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="ae1dd-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae1dd-104">La `FileNameColumnName` propriété de la source de fichier plat et la `FastParse` propriété de ses colonnes de sortie ne sont pas disponibles dans l' **éditeur de source de fichier plat**, mais elles peuvent être définies à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="ae1dd-105">Pour plus d'informations sur ces propriétés, consultez la section sur la source de fichier plat de [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ae1dd-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="ae1dd-106">Pour en savoir plus sur la source de fichier plat, consultez [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="ae1dd-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae1dd-107">Options</span><span class="sxs-lookup"><span data-stu-id="ae1dd-107">Options</span></span>  
 <span data-ttu-id="ae1dd-108">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="ae1dd-108">**Available External Columns**</span></span>  
 <span data-ttu-id="ae1dd-109">Affiche la liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="ae1dd-110">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="ae1dd-111">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="ae1dd-111">**External Column**</span></span>  
 <span data-ttu-id="ae1dd-112">Affiche les colonnes externes (sources) dans l'ordre de lecture de la tâche.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="ae1dd-113">Vous pouvez modifier cet ordre en supprimant d'abord les colonnes sélectionnées dans la table, puis en choisissant des colonnes externes dans la liste selon un ordre différent.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="ae1dd-114">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="ae1dd-114">**Output Column**</span></span>  
 <span data-ttu-id="ae1dd-115">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="ae1dd-116">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; vous pouvez néanmoins choisir n'importe quel nom unique et significatif.</span><span class="sxs-lookup"><span data-stu-id="ae1dd-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="ae1dd-117">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae1dd-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1dd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae1dd-118">See Also</span></span>  
 <span data-ttu-id="ae1dd-119">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ae1dd-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ae1dd-120">[Éditeur de source de fichier plat &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae1dd-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ae1dd-121">[Éditeur de source de fichier plat &#40;page sortie d’erreur&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae1dd-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="ae1dd-122">Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="ae1dd-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
