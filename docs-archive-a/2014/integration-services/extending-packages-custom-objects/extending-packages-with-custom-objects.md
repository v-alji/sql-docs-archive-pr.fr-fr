---
title: Extension de packages avec des objets personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694648"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="2d9e6-102">Extension de packages avec des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="2d9e6-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="2d9e6-103">Si vous constatez que les composants fournis dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ne satisfont pas vos besoins, vous pouvez étendre la puissance d'[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en codant vos propres extensions.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="2d9e6-104">Vous disposez de deux options distinctes pour étendre vos packages : vous pouvez écrire du code dans les puissants wrappers fournis par la tâche de script et le composant Script, ou vous pouvez entièrement créer des extensions [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisées, dérivées des classes de base fournies par le modèle objet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d9e6-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="2d9e6-105">Cette section explore l’option la plus avancée des deux : l’extension de packages à l’aide d’objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="2d9e6-106">Lorsque votre solution [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisée exige davantage de flexibilité que celle fournie par la tâche de script ou le composant Script, ou lorsque vous avez besoin d'un composant réutilisable dans plusieurs packages, le modèle objet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] vous permet de créer des tâches personnalisées, des composants de flux de données et d'autres objets de package en code managé.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d9e6-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2d9e6-107">In This Section</span></span>  
 [<span data-ttu-id="2d9e6-108">Développement d’objets personnalisés pour Integration Services</span><span class="sxs-lookup"><span data-stu-id="2d9e6-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="2d9e6-109">Présente les objets personnalisés qui peuvent être créés pour [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et résume les étapes et les paramètres essentiels.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="2d9e6-110">Persistance des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="2d9e6-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="2d9e6-111">Examine la persistance par défaut des objets personnalisés et le processus d'implémentation de la persistance personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="2d9e6-112">Génération, déploiement et débogage d’objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="2d9e6-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="2d9e6-113">Présente les méthodes les plus usuelles pour créer, déployer et tester les différents types d'objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="2d9e6-114">Développement d’une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="2d9e6-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="2d9e6-115">Décrit le processus de codage d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="2d9e6-116">Développement d’un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="2d9e6-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="2d9e6-117">Décrit le processus de codage d'un gestionnaire de connexions personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="2d9e6-118">Développement d’un module fournisseur d’informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="2d9e6-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="2d9e6-119">Décrit le processus du codage d'un module fournisseur d'informations personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="2d9e6-120">Développement d’un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="2d9e6-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="2d9e6-121">Décrit le processus de codage d'un énumérateur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="2d9e6-122">Développement d’un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="2d9e6-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="2d9e6-123">Explique comment programmer des sources, des transformations et des destinations de flux de données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2d9e6-124">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="2d9e6-124">Reference</span></span>  
 [<span data-ttu-id="2d9e6-125">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="2d9e6-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="2d9e6-126">Répertorie les codes d'erreur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prédéfinis avec leur nom symbolique et leur description.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2d9e6-127">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="2d9e6-127">Related Sections</span></span>  
 [<span data-ttu-id="2d9e6-128">Extension de packages avec des scripts</span><span class="sxs-lookup"><span data-stu-id="2d9e6-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="2d9e6-129">Explique comment étendre le flux de contrôle à l'aide de la tâche de script, ou comment étendre le flux de données à l'aide du composant Script.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="2d9e6-130">Génération de packages par programmation</span><span class="sxs-lookup"><span data-stu-id="2d9e6-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="2d9e6-131">Décrit comment créer, configurer, exécuter, charger, enregistrer et gérer des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] par programme.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="2d9e6-132">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2d9e6-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2d9e6-133">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="2d9e6-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2d9e6-134">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="2d9e6-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2d9e6-135">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="2d9e6-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9e6-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d9e6-136">See Also</span></span>  
 <span data-ttu-id="2d9e6-137">[Comparaison des solutions de script et des objets personnalisés](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2d9e6-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="2d9e6-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="2d9e6-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
