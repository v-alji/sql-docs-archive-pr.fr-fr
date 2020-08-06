---
title: Guide des&#39;pour les développeurs (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613011"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="273f5-102">Guide des&#39;pour les développeurs (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="273f5-102">Developer&#39;s Guide (Integration Services)</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="273f5-103">inclut un modèle objet entièrement réécrit, auquel ont été ajoutées de nombreuses fonctionnalités, afin d'offrir un outil convivial, souple et puissant pour étendre et programmer des packages.</span><span class="sxs-lookup"><span data-stu-id="273f5-103">includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="273f5-104">Les développeurs peuvent étendre et programmer pratiquement tous les aspects des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="273f5-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="273f5-105">En tant que développeur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], vous disposez de deux méthodes de programmation [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fondamentales :</span><span class="sxs-lookup"><span data-stu-id="273f5-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="273f5-106">Vous pouvez étendre des packages en écrivant des composants qui deviennent disponibles dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] pour fournir des fonctionnalités personnalisées dans un package.</span><span class="sxs-lookup"><span data-stu-id="273f5-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="273f5-107">Vous pouvez créer, configurer et exécuter des packages par programme à partir de vos propres applications.</span><span class="sxs-lookup"><span data-stu-id="273f5-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="273f5-108">Si vous constatez que les composants intégrés dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ne satisfont pas vos besoins, vous pouvez étendre la puissance d'[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en codant vos propres extensions.</span><span class="sxs-lookup"><span data-stu-id="273f5-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="273f5-109">Cette méthode propose deux options distinctes :</span><span class="sxs-lookup"><span data-stu-id="273f5-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="273f5-110">Pour une utilisation ad hoc dans un seul package, vous pouvez créer une tâche personnalisée en écrivant du code dans la tâche de script, ou un composant de flux de données personnalisé en écrivant du code dans le composant Script, que vous pouvez configurer en tant que source, transformation ou destination.</span><span class="sxs-lookup"><span data-stu-id="273f5-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="273f5-111">Ces wrappers puissants se chargent d'écrire le code d'infrastructure et vous permettent ainsi de vous consacrer exclusivement au développement de vos fonctionnalités personnalisées ; toutefois, ils sont difficilement réutilisables dans un contexte différent.</span><span class="sxs-lookup"><span data-stu-id="273f5-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="273f5-112">Pour une utilisation dans plusieurs packages, vous pouvez créer des extensions [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] personnalisées, telles que des gestionnaires de connexions, des tâches, des énumérateurs, des modules fournisseurs d'informations et des composants de flux.</span><span class="sxs-lookup"><span data-stu-id="273f5-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="273f5-113">Le modèle objet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] managé contient des classes de base qui fournissent un point de départ et facilitent considérablement le développement d'extensions personnalisées.</span><span class="sxs-lookup"><span data-stu-id="273f5-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="273f5-114">Si vous souhaitez créer des packages de manière dynamique, ou gérer et exécuter des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] à l'extérieur de l'environnement de développement, vous pouvez manipuler les packages par programme.</span><span class="sxs-lookup"><span data-stu-id="273f5-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="273f5-115">Vous pouvez charger, modifier et exécuter des packages existants, ou créer et exécuter par programme des packages entièrement nouveaux.</span><span class="sxs-lookup"><span data-stu-id="273f5-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="273f5-116">Cette méthode vous offre une gamme continue d'options :</span><span class="sxs-lookup"><span data-stu-id="273f5-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="273f5-117">Charger et exécuter un package existant sans modification.</span><span class="sxs-lookup"><span data-stu-id="273f5-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="273f5-118">Charger un package existant, le reconfigurer (par exemple, spécifier une source de données différente) et l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="273f5-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="273f5-119">Créer un package, ajouter et configurer des composants, apporter des modifications objet par objet et propriété par propriété, l’enregistrer, puis l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="273f5-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="273f5-120">Ces méthodes de programmation [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sont décrites dans cette section et illustrées par des exemples.</span><span class="sxs-lookup"><span data-stu-id="273f5-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="273f5-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="273f5-121">In This Section</span></span>  
 [<span data-ttu-id="273f5-122">Vue d’ensemble de la programmation Integration Services</span><span class="sxs-lookup"><span data-stu-id="273f5-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="273f5-123">Décrit les rôles de flux de contrôle et de flux dans le développement [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="273f5-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="273f5-124">Présentation des transformations synchrones et asynchrones</span><span class="sxs-lookup"><span data-stu-id="273f5-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="273f5-125">Décrit la distinction importante entre les sorties synchrones et les sorties asynchrones, ainsi que les composants qui les utilisent dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="273f5-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="273f5-126">Utilisation de gestionnaires de connexions par programmation</span><span class="sxs-lookup"><span data-stu-id="273f5-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="273f5-127">Répertorie les gestionnaires de connexions que vous pouvez utiliser à partir du code managé, ainsi que les valeurs que les gestionnaires de connexions retournent lorsque le code appelle la méthode `AcquireConnection`.</span><span class="sxs-lookup"><span data-stu-id="273f5-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="273f5-128">Extension de packages avec des scripts</span><span class="sxs-lookup"><span data-stu-id="273f5-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="273f5-129">Décrit comment étendre le flux de contrôle à l’aide de la tâche de script, ou le flux de données à l’aide du composant Script.</span><span class="sxs-lookup"><span data-stu-id="273f5-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="273f5-130">Extension de packages avec des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="273f5-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="273f5-131">Décrit comment créer et programmer des tâches personnalisées, des composants de flux de données et d'autres objets de package à utiliser dans plusieurs packages.</span><span class="sxs-lookup"><span data-stu-id="273f5-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="273f5-132">Génération de packages par programmation</span><span class="sxs-lookup"><span data-stu-id="273f5-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="273f5-133">Décrit comment créer, configurer et enregistrer des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] par programme.</span><span class="sxs-lookup"><span data-stu-id="273f5-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="273f5-134">Exécution et gestion de packages par programmation</span><span class="sxs-lookup"><span data-stu-id="273f5-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="273f5-135">Décrit comment énumérer, exécuter et gérer des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] par programme.</span><span class="sxs-lookup"><span data-stu-id="273f5-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="273f5-136">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="273f5-136">Reference</span></span>  
 [<span data-ttu-id="273f5-137">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="273f5-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="273f5-138">Répertorie les codes d'erreur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] prédéfinis, avec leur nom symbolique et leur description.</span><span class="sxs-lookup"><span data-stu-id="273f5-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="273f5-139">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="273f5-139">Related Sections</span></span>  
 [<span data-ttu-id="273f5-140">Outils de dépannage pour le développement des packages</span><span class="sxs-lookup"><span data-stu-id="273f5-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="273f5-141">Décrit les fonctionnalités et les outils fournis par [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour le dépannage des packages lors du développement.</span><span class="sxs-lookup"><span data-stu-id="273f5-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="273f5-142">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="273f5-142">External Resources</span></span>  
  
-   <span data-ttu-id="273f5-143">Exemples de code CodePlex, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), sur www.codeplex.com/MSFTISProdSamples</span><span class="sxs-lookup"><span data-stu-id="273f5-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273f5-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="273f5-144">See Also</span></span>  
 [<span data-ttu-id="273f5-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="273f5-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
