---
title: Afficher des objets de packages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611853"
---
# <a name="view-package-objects"></a><span data-ttu-id="ff202-102">Afficher des objets de packages</span><span class="sxs-lookup"><span data-stu-id="ff202-102">View Package Objects</span></span>
  <span data-ttu-id="ff202-103">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , l'onglet **Explorateur de package** fournit un aperçu du package.</span><span class="sxs-lookup"><span data-stu-id="ff202-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="ff202-104">Cet affichage reflète la hiérarchie de conteneur de l'architecture [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff202-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="ff202-105">Le conteneur de packages est situé en haut de la hiérarchie et vous pouvez développer le package pour afficher les connexions, les exécutables, les gestionnaires d'événements, les fournisseurs d'informations, les contraintes de précédence et les variables du package.</span><span class="sxs-lookup"><span data-stu-id="ff202-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="ff202-106">Les exécutables, qui sont les conteneurs et les tâches du package, peuvent inclure des gestionnaires d'événements, des contraintes de précédence et des variables.</span><span class="sxs-lookup"><span data-stu-id="ff202-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ff202-107">prend en charge une hiérarchie imbriquée de conteneurs, et les conteneurs de boucles For, de boucles Foreach et de séquences peuvent inclure d'autres exécutables.</span><span class="sxs-lookup"><span data-stu-id="ff202-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="ff202-108">Si un package contient un flux de données, l' **Explorateur de package** répertorie la tâche de flux de données et inclut un dossier **Composants** qui répertorie les composants du flux de données.</span><span class="sxs-lookup"><span data-stu-id="ff202-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="ff202-109">À partir de l'onglet **Explorateur de package** , vous pouvez supprimer des objets d'un package et accéder à la fenêtre **Propriétés** afin d'afficher les propriétés des objets.</span><span class="sxs-lookup"><span data-stu-id="ff202-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="ff202-110">Le schéma suivant illustre l'arborescence d'un package simple.</span><span class="sxs-lookup"><span data-stu-id="ff202-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="ff202-111">![Capture d’écran de l'onglet Explorateur de package](media/packageexplorer.gif "Capture d’écran de l'onglet Explorateur de package")</span><span class="sxs-lookup"><span data-stu-id="ff202-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="ff202-112">Pour afficher le contenu d'un package</span><span class="sxs-lookup"><span data-stu-id="ff202-112">To view package content</span></span>

-   [<span data-ttu-id="ff202-113">Afficher les objets de package dans l'Explorateur de package</span><span class="sxs-lookup"><span data-stu-id="ff202-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="ff202-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff202-114">See Also</span></span>
 <span data-ttu-id="ff202-115">[Integration Services tâches](control-flow/integration-services-tasks.md) [Integration Services](control-flow/integration-services-containers.md) [les contraintes de priorité](control-flow/precedence-constraints.md) des conteneurs [Integration Services &#40;les variables de&#41;](integration-services-ssis-variables.md) SSIS Integration Services &#40;les gestionnaires d’événements&#41; [SSIS](integration-services-ssis-event-handlers.md) Integration Services &#40;la [journalisation SSIS&#41;](performance/integration-services-ssis-logging.md)</span><span class="sxs-lookup"><span data-stu-id="ff202-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>


