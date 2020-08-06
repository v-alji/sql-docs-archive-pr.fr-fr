---
title: Éditeur du chemin d’accès au Data Flow (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697067"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="17f9d-102">Éditeur du chemin d'accès au flux de données (Page Général)</span><span class="sxs-lookup"><span data-stu-id="17f9d-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="17f9d-103">Utilisez la boîte de dialogue **Éditeur du chemin d'accès au flux de données** pour définir les propriétés du chemin d'accès, afficher les métadonnées de la colonne et gérer les visionneuses de données liées à ce chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="17f9d-104">Utilisez le nœud **Général** de la boîte de dialogue **Éditeur du chemin d'accès au flux de données** pour nommer et décrire le chemin d'accès et pour spécifier ses options d'annotation.</span><span class="sxs-lookup"><span data-stu-id="17f9d-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="17f9d-105">Options</span><span class="sxs-lookup"><span data-stu-id="17f9d-105">Options</span></span>  
 <span data-ttu-id="17f9d-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="17f9d-106">**Name**</span></span>  
 <span data-ttu-id="17f9d-107">Donnez un nom unique au chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="17f9d-108">**Identifiant**</span><span class="sxs-lookup"><span data-stu-id="17f9d-108">**ID**</span></span>  
 <span data-ttu-id="17f9d-109">Identificateur de lignage du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-109">The lineage identifier of the path.</span></span> <span data-ttu-id="17f9d-110">Cette propriété est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="17f9d-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="17f9d-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="17f9d-111">**IdentificationString**</span></span>  
 <span data-ttu-id="17f9d-112">Chaîne identifiant le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-112">The string that identifies the path.</span></span> <span data-ttu-id="17f9d-113">Généré automatiquement à partir du nom entré précédemment.</span><span class="sxs-lookup"><span data-stu-id="17f9d-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="17f9d-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="17f9d-114">**Description**</span></span>  
 <span data-ttu-id="17f9d-115">Décrivez le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-115">Describe the path.</span></span>  
  
 <span data-ttu-id="17f9d-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="17f9d-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="17f9d-117">Spécifiez le type d'annotation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="17f9d-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="17f9d-118">Choisissez **Never** pour désactiver les annotations, **AsNeeded** pour activer l'annotation à la demande, **SourceName** pour annoter automatiquement en utilisant la valeur de l'option **SourceName** et **PathName** pour annoter automatiquement en utilisant la valeur de la propriété **Nom** .</span><span class="sxs-lookup"><span data-stu-id="17f9d-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="17f9d-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="17f9d-119">**DestinationName**</span></span>  
 <span data-ttu-id="17f9d-120">Affiche l'entrée qui représente l'issue du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="17f9d-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="17f9d-121">**SourceName**</span></span>  
 <span data-ttu-id="17f9d-122">Affiche la sortie qui représente le début du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="17f9d-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f9d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17f9d-123">See Also</span></span>  
 <span data-ttu-id="17f9d-124">[Éditeur du chemin d’accès de données &#40;page de métadonnées&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="17f9d-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="17f9d-125">[Éditeur du chemin d’accès au workflow &#40;page des visionneuses de données&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="17f9d-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="17f9d-126">[Flux de données](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="17f9d-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="17f9d-127">Utiliser des annotations dans les packages</span><span class="sxs-lookup"><span data-stu-id="17f9d-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
