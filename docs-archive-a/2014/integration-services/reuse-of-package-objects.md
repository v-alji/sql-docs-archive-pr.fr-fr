---
title: Réutiliser des objets de packages | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696947"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="79870-102">Réutiliser des objets de packages</span><span class="sxs-lookup"><span data-stu-id="79870-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="79870-103">Fonctionnalités usuelles de packages que vous souhaitez réutiliser.</span><span class="sxs-lookup"><span data-stu-id="79870-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="79870-104">Si vous avez par exemple créé un ensemble de tâches, il peut être utile de réutiliser des éléments rassemblés en groupe, ou un élément unique, tel qu'un gestionnaire de connexions créé dans un autre projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79870-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="79870-105">Copier et coller</span><span class="sxs-lookup"><span data-stu-id="79870-105">Copy and Paste</span></span>  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="79870-106">et le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] prennent en charge la copie et le collage d'objets de packages, tels que des éléments de flux de contrôle, des éléments de flux de données et des gestionnaires de connexions.</span><span class="sxs-lookup"><span data-stu-id="79870-106">and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="79870-107">Vous pouvez effectuer la copie et le collage entre des projets et entre des packages.</span><span class="sxs-lookup"><span data-stu-id="79870-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="79870-108">Si la solution contient plusieurs projets, vous pouvez effectuer la copie entre des projets, lesquels peuvent être de types différents.</span><span class="sxs-lookup"><span data-stu-id="79870-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="79870-109">Si une solution contient plusieurs packages, vous pouvez effectuer la copie et le collage entre eux.</span><span class="sxs-lookup"><span data-stu-id="79870-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="79870-110">Les packages peuvent se trouver dans des projets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] différents ou de même nature.</span><span class="sxs-lookup"><span data-stu-id="79870-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="79870-111">Les objets de packages peuvent toutefois avoir des dépendances avec d'autres objets sans lesquels ils ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="79870-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="79870-112">Par exemple, une tâche d'exécution SQL utilise un gestionnaire de connexions que vous devez également copier pour faire fonctionner la tâche.</span><span class="sxs-lookup"><span data-stu-id="79870-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="79870-113">Certains objets de packages nécessitent également que le package contienne déjà un objet particulier, sans lequel il n'est pas possible de coller convenablement les objets copiés dans un package.</span><span class="sxs-lookup"><span data-stu-id="79870-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="79870-114">Par exemple, il n'est pas possible de coller un flux de données dans un package qui ne possède pas au moins une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="79870-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="79870-115">Il peut arriver que vous deviez copier les mêmes packages plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="79870-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="79870-116">Pour éviter le processus de copie, vous pouvez désigner ces packages en tant que modèles et vous en servir pour créer des packages.</span><span class="sxs-lookup"><span data-stu-id="79870-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="79870-117">Lorsque vous copiez un objet de package, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] attribue automatiquement un nouveau GUID à la propriété `ID` du nouvel objet et met à jour la propriété `Name`.</span><span class="sxs-lookup"><span data-stu-id="79870-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="79870-118">Vous ne pouvez pas copier de variables.</span><span class="sxs-lookup"><span data-stu-id="79870-118">You cannot copy variables.</span></span> <span data-ttu-id="79870-119">Si un objet, une tâche par exemple, utilise des variables, vous devez recréer les variables dans le package de destination.</span><span class="sxs-lookup"><span data-stu-id="79870-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="79870-120">À l'inverse, si vous copiez le package complet, les variables du package sont également copiées.</span><span class="sxs-lookup"><span data-stu-id="79870-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="79870-121">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="79870-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="79870-122">Copier des objets de packages</span><span class="sxs-lookup"><span data-stu-id="79870-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="79870-123">Copier des éléments de projet</span><span class="sxs-lookup"><span data-stu-id="79870-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="79870-124">Enregistrer un package en tant que modèle de package</span><span class="sxs-lookup"><span data-stu-id="79870-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
