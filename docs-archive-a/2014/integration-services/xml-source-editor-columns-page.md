---
title: Éditeur de source XML (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.columns.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: 5162c400-b2fc-4711-af0f-609132fbaaad
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0b9433b7a2c4f08f9e0c70d568f8fc037ceb7c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705244"
---
# <a name="xml-source-editor-columns-page"></a><span data-ttu-id="d50d5-102">Éditeur de source XML (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="d50d5-102">XML Source Editor (Columns Page)</span></span>
  <span data-ttu-id="d50d5-103">Le nœud **Colonnes** de la boîte de dialogue **Éditeur de source XML** vous permet de mapper une colonne de sortie à une colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="d50d5-103">Use the **Columns** node of the **XML Source Editor** dialog box to map an output column to an external (source) column.</span></span>  
  
 <span data-ttu-id="d50d5-104">Pour plus d'informations sur la source XML, consultez [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="d50d5-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d50d5-105">Options</span><span class="sxs-lookup"><span data-stu-id="d50d5-105">Options</span></span>  
 <span data-ttu-id="d50d5-106">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="d50d5-106">**Available External Columns**</span></span>  
 <span data-ttu-id="d50d5-107">Affiche la liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="d50d5-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="d50d5-108">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="d50d5-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="d50d5-109">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="d50d5-109">**External Column**</span></span>  
 <span data-ttu-id="d50d5-110">Affiche les colonnes externes (sources) dans l'ordre de lecture de la tâche.</span><span class="sxs-lookup"><span data-stu-id="d50d5-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="d50d5-111">Vous pouvez modifier cet ordre en désactivant les colonnes sélectionnées dans la table affichée dans l'éditeur, puis en sélectionnant les colonnes externes dans la liste, dans un ordre différent.</span><span class="sxs-lookup"><span data-stu-id="d50d5-111">You can change this order by first clearing the selected columns in the table displayed in the editor, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="d50d5-112">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="d50d5-112">**Output Column**</span></span>  
 <span data-ttu-id="d50d5-113">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="d50d5-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="d50d5-114">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; vous pouvez néanmoins choisir n'importe quel nom unique et significatif.</span><span class="sxs-lookup"><span data-stu-id="d50d5-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="d50d5-115">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d50d5-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50d5-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d50d5-116">See Also</span></span>  
 <span data-ttu-id="d50d5-117">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d50d5-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d50d5-118">[Éditeur de source XML &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d50d5-118">[XML Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d50d5-119">[Éditeur de source XML &#40;page sortie d’erreur&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d50d5-119">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d50d5-120">Extraire des données à l'aide de la source XML</span><span class="sxs-lookup"><span data-stu-id="d50d5-120">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
