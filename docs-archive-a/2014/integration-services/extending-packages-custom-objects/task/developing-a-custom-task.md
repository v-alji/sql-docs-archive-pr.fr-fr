---
title: Développement d’une tâche personnalisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611912"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="5c794-102">Développement d'une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-102">Developing a Custom Task</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="5c794-103">utilise des tâches pour effectuer des unités de travail en soutien à l'extraction, la transformation et le chargement de données.</span><span class="sxs-lookup"><span data-stu-id="5c794-103">uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="5c794-104">inclut une variété de tâches qui effectuent les actions les plus fréquemment utilisées, allant de l'exécution d'une instruction SQL au téléchargement d'un fichier à partir d'un site FTP.</span><span class="sxs-lookup"><span data-stu-id="5c794-104">includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="5c794-105">Si les tâches incluses et les actions prises en charge ne répondent pas complètement à vos besoins, vous pouvez créer une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="5c794-106">Pour créer une tâche personnalisée, vous devez créer une classe qui hérite de la classe de base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), appliquer l’attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> à votre nouvelle classe et remplacer les méthodes et propriétés importantes de la classe de base, notamment la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c794-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c794-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5c794-107">In This Section</span></span>  
 <span data-ttu-id="5c794-108">Cette section explique comment créer, configurer et coder une tâche personnalisée et son interface utilisateur personnalisée facultative.</span><span class="sxs-lookup"><span data-stu-id="5c794-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="5c794-109">Création d’une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="5c794-110">Décrit la première étape, à savoir la création de la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="5c794-111">Codage d’une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="5c794-112">Décrit comment coder les méthodes principales d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="5c794-113">Connexion à des sources de données dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="5c794-114">Décrit comment connecter une tâche personnalisée à une source de données.</span><span class="sxs-lookup"><span data-stu-id="5c794-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="5c794-115">Déclenchement et définition d’événements dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="5c794-116">Décrit comment déclencher des événements et définir des événements personnalisés à partir de la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="5c794-117">Ajout de la prise en charge du débogage dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="5c794-118">Décrit comment créer des cibles de points d'arrêt dans la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="5c794-119">Développement d’une interface utilisateur pour une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5c794-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="5c794-120">Explique comment créer une interface utilisateur qui s'affiche dans le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] pour configurer des propriétés sur la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5c794-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c794-121">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="5c794-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="5c794-122">Informations communes à tous les objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="5c794-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="5c794-123">Pour obtenir les informations communes à tous les types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c794-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="5c794-124">Développement d’objets personnalisés pour Integration Services</span><span class="sxs-lookup"><span data-stu-id="5c794-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="5c794-125">Décrit les étapes de base pour implémenter tous les types d'objets personnalisés pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c794-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="5c794-126">Persistance des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="5c794-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="5c794-127">Décrit la persistance personnalisée et explique les situations dans lesquelles elle est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5c794-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="5c794-128">Génération, déploiement et débogage d’objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="5c794-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="5c794-129">Décrit les techniques permettant de générer, signer, déployer et déboguer des objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5c794-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="5c794-130">Informations sur les autres objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="5c794-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="5c794-131">Pour plus d'informations sur les autres types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c794-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="5c794-132">Développement d’un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="5c794-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="5c794-133">Explique comment programmer des gestionnaires de connexions personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5c794-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="5c794-134">Développement d’un module fournisseur d’informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="5c794-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="5c794-135">Explique comment programmer des modules fournisseurs d'informations personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5c794-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="5c794-136">Développement d’un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="5c794-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="5c794-137">Décrit comment programmer des énumérateurs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5c794-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="5c794-138">Développement d’un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="5c794-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="5c794-139">Explique comment programmer des sources, des transformations et des destinations de flux de données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="5c794-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="5c794-140">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5c794-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5c794-141">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5c794-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5c794-142">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5c794-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5c794-143">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5c794-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c794-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c794-144">See Also</span></span>  
 <span data-ttu-id="5c794-145">[Extension du package à l’aide de la tâche de script](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="5c794-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="5c794-146">Comparaison des solutions de script et des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="5c794-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
