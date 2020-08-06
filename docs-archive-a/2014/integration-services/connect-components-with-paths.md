---
title: Connecter des composants avec des chemins d’accès | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706656"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="74608-102">Connecter des composants avec des chemins d’accès</span><span class="sxs-lookup"><span data-stu-id="74608-102">Connect Components with Paths</span></span>
  <span data-ttu-id="74608-103">Le flux de données d’un package est construit sur la surface de conception de l’onglet **Flux de données** du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74608-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="74608-104">Si un flux de données contient deux composants de flux de données, vous pouvez les relier en connectant la sortie d'une source ou d'une transformation à l'entrée d'une transformation ou d'une destination.</span><span class="sxs-lookup"><span data-stu-id="74608-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="74608-105">Le connecteur entre ces deux composants de flux de données porte le nom de chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="74608-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="74608-106">Le diagramme qui suit montre un flux de données simple formé d'un composant source, de deux transformations, d'un composant de destination et des chemins d'accès les connectant.</span><span class="sxs-lookup"><span data-stu-id="74608-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="74608-107">![Data flow](media/mw-dts-08.gif "Flux de données") (Flux de données)</span><span class="sxs-lookup"><span data-stu-id="74608-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="74608-108">Une fois deux composants connectés, vous pouvez afficher les métadonnées des données empruntant le chemin et les propriétés du chemin dans **l’Éditeur du chemin d’accès au flux de données**.</span><span class="sxs-lookup"><span data-stu-id="74608-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="74608-109">Pour plus d’informations, consultez [Chemins d’accès d’Integration Services](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="74608-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="74608-110">Vous pouvez également ajouter des visionneuses de données aux chemins d'accès.</span><span class="sxs-lookup"><span data-stu-id="74608-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="74608-111">Une visionneuse de données permet d'afficher les données circulant entre les composants du flux de données lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="74608-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="74608-112">Pour connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="74608-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="74608-113">Connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="74608-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="74608-114">Pour définir les propriétés d'un chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="74608-114">To set path properties</span></span>

-   [<span data-ttu-id="74608-115">Définir les propriétés d’un chemin à l’aide de l’Éditeur du chemin d’accès au flux de données</span><span class="sxs-lookup"><span data-stu-id="74608-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="74608-116">Pour afficher les métadonnées d'un chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="74608-116">To view path metadata</span></span>

-   [<span data-ttu-id="74608-117">Afficher les métadonnées d'un chemin d'accès dans l'Éditeur du chemin d'accès au flux de données</span><span class="sxs-lookup"><span data-stu-id="74608-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="74608-118">Pour afficher les métadonnées d'un chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="74608-118">To view path metadata</span></span>

-   [<span data-ttu-id="74608-119">Ajouter une visionneuse de données à un flux de données</span><span class="sxs-lookup"><span data-stu-id="74608-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="74608-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74608-120">See Also</span></span>
 <span data-ttu-id="74608-121">Traitement des données de la [tâche](control-flow/data-flow-task.md) [de Data](data-flow/data-flow.md) Flow [transformer des données avec des transformations](data-flow/transformations/transform-data-with-transformations.md) [gestion des erreurs dans les données](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="74608-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


