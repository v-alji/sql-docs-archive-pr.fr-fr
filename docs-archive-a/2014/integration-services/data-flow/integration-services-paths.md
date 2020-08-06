---
title: Chemins Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700121"
---
# <a name="integration-services-paths"></a><span data-ttu-id="94747-102">Chemins d'accès d'Integration Services</span><span class="sxs-lookup"><span data-stu-id="94747-102">Integration Services Paths</span></span>
  <span data-ttu-id="94747-103">Un chemin d'accès connecte deux composants d'un flux de données en reliant la sortie d'un composant à l'entrée d'un autre composant.</span><span class="sxs-lookup"><span data-stu-id="94747-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="94747-104">Un chemin d'accès comporte une source et une destination.</span><span class="sxs-lookup"><span data-stu-id="94747-104">A path has a source and a destination.</span></span> <span data-ttu-id="94747-105">Par exemple, si un chemin d'accès connecte une source OLE DB et une transformation de tri, la source OLE DB est la source du chemin d'accès, tandis que la transformation de tri est la destination du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="94747-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="94747-106">La source est le composant où débute le chemin d'accès et la destination, le composant où il se termine.</span><span class="sxs-lookup"><span data-stu-id="94747-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="94747-107">Si vous exécutez un package dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vous pouvez afficher les données d'un flux de données en attachant des visionneuses de données à un chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="94747-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="94747-108">Une visionneuse de données peut être configurée pour afficher des données dans une grille.</span><span class="sxs-lookup"><span data-stu-id="94747-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="94747-109">Une visionneuse de données est un outil de débogage très utile.</span><span class="sxs-lookup"><span data-stu-id="94747-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="94747-110">Pour plus d’informations, consultez [Débogage d’un flux de données](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="94747-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="94747-111">Configuration du chemin d’accès</span><span class="sxs-lookup"><span data-stu-id="94747-111">Configuration of the Path</span></span>  
 <span data-ttu-id="94747-112">Le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] contient la boîte de dialogue **Éditeur du chemin d’accès au flux de données** qui permet de définir les propriétés du chemin d’accès, d’afficher les métadonnées des colonnes de données qui empruntent le chemin d’accès et de configurer les visionneuses de données.</span><span class="sxs-lookup"><span data-stu-id="94747-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="94747-113">Le nom, la description et l'annotation du chemin d'accès sont des propriétés que vous pouvez configurer.</span><span class="sxs-lookup"><span data-stu-id="94747-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="94747-114">Vous pouvez également configurer les chemins d'accès par programme.</span><span class="sxs-lookup"><span data-stu-id="94747-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="94747-115">Pour plus d’informations, consultez [Connexion de composants de flux de données par programme](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="94747-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="94747-116">Une annotation de chemin d’accès affiche le nom de la source du chemin d’accès ou le nom du chemin d’accès sur l’aire de conception de l’onglet **Flux de données** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94747-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="94747-117">Les annotations de chemins d'accès sont similaires aux annotations ajoutées aux flux de données, aux flux de contrôles et aux gestionnaires d'événements.</span><span class="sxs-lookup"><span data-stu-id="94747-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="94747-118">La seule différence est qu’une annotation de chemin d’accès est attachée à un chemin d’accès, alors que les autres annotations apparaissent sous les onglets **Flux de données**, **Flux de contrôle**et **Gestionnaires d’événements**du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94747-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="94747-119">Les métadonnées indiquent le nom, le type de données, la précision, l'échelle, la longueur, la page de codes et le composant source de chaque colonne dans la sortie du composant précédent.</span><span class="sxs-lookup"><span data-stu-id="94747-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="94747-120">Le composant source est le composant du flux de données ayant créé la colonne.</span><span class="sxs-lookup"><span data-stu-id="94747-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="94747-121">Il peut ou non s'agir du premier composant du flux de données.</span><span class="sxs-lookup"><span data-stu-id="94747-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="94747-122">Par exemple, les transformations d'union totale et de tri créent leurs propres colonnes et sont les sources de leurs colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="94747-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="94747-123">À l'inverse, une transformation de copie de colonne peut transmettre des colonnes sans les modifier ou créer des colonnes en copiant les colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="94747-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="94747-124">La transformation de copie de colonne est le composant source des nouvelles colonnes uniquement.</span><span class="sxs-lookup"><span data-stu-id="94747-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="94747-125">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="94747-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="94747-126">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur du chemin d’accès au flux de données**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="94747-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="94747-127">Éditeur du chemin d’accès au Data Flow &#40;&#41;de page général</span><span class="sxs-lookup"><span data-stu-id="94747-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="94747-128">Éditeur du chemin d’accès de données &#40;page de métadonnées&#41;</span><span class="sxs-lookup"><span data-stu-id="94747-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="94747-129">Éditeur du chemin d’accès au workflow &#40;page des visionneuses de données&#41;</span><span class="sxs-lookup"><span data-stu-id="94747-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="94747-130">Pour plus d’informations sur les propriétés que vous pouvez définir par programmation, consultez [Propriétés du chemin d’accès](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="94747-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="94747-131">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="94747-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="94747-132">Afficher les métadonnées d'un chemin d'accès dans l'Éditeur du chemin d'accès au flux de données</span><span class="sxs-lookup"><span data-stu-id="94747-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="94747-133">Connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="94747-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="94747-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94747-134">See Also</span></span>  
 [<span data-ttu-id="94747-135">Flux de données</span><span class="sxs-lookup"><span data-stu-id="94747-135">Data Flow</span></span>](data-flow.md)  
  
  
