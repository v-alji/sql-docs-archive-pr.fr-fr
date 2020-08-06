---
title: Développement d’un gestionnaire de connexions personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709764"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="23ccf-102">Développement d'un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-102">Developing a Custom Connection Manager</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="23ccf-103">utilise des gestionnaires de connexions pour encapsuler les informations nécessaires pour se connecter à une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="23ccf-103">uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="23ccf-104">inclut divers gestionnaires de connexions qui prennent en charge les connexions aux sources de données les plus couramment utilisées, allant des bases de données d'entreprise aux fichiers texte et feuilles de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="23ccf-104">includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="23ccf-105">Si les gestionnaires de connexions et les sources de données externes pris en charge par [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] ne répondent pas totalement à vos besoins, vous pouvez créer un gestionnaire de connexions personnalisé.</span><span class="sxs-lookup"><span data-stu-id="23ccf-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="23ccf-106">Pour créer un gestionnaire de connexions personnalisé, vous devez créer une classe qui hérite de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, appliquer l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> à votre nouvelle classe et remplacer les méthodes et propriétés importantes de la classe de base, notamment la propriété <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> et la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="23ccf-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="23ccf-107">Une grande partie des tâches, sources et destinations intégrées à [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilisent uniquement des types spécifiques de gestionnaires de connexions intégrés.</span><span class="sxs-lookup"><span data-stu-id="23ccf-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="23ccf-108">Avant de développer un gestionnaire de connexions personnalisé afin de l'utiliser avec des tâches et composants intégrés, vérifiez si ces composants limitent la liste des gestionnaires de connexions disponibles à un type spécifique.</span><span class="sxs-lookup"><span data-stu-id="23ccf-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="23ccf-109">Si votre solution requiert un gestionnaire de connexions personnalisé, vous devrez peut-être développer également une tâche personnalisée ou une source/destination personnalisée à utiliser avec le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="23ccf-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23ccf-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="23ccf-110">In This Section</span></span>  
 <span data-ttu-id="23ccf-111">Cette section décrit comment créer, configurer et coder un gestionnaire de connexions personnalisé et son interface utilisateur personnalisée facultative.</span><span class="sxs-lookup"><span data-stu-id="23ccf-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="23ccf-112">Les extraits de code présentés dans cette section sont tirés de l'exemple de gestionnaire de connexions personnalisé SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23ccf-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="23ccf-113">Création d’un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="23ccf-114">Explique comment créer les classes d'un projet de gestionnaire de connexions personnalisé.</span><span class="sxs-lookup"><span data-stu-id="23ccf-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="23ccf-115">Codage d’un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="23ccf-116">Décrit comment implémenter un gestionnaire de connexions personnalisé en remplaçant les méthodes et propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="23ccf-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="23ccf-117">Développement d’une interface utilisateur pour un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="23ccf-118">Explique comment implémenter la classe d'interface utilisateur et le formulaire servant à configurer le gestionnaire de connexions personnalisé.</span><span class="sxs-lookup"><span data-stu-id="23ccf-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23ccf-119">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="23ccf-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="23ccf-120">Informations communes à tous les objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="23ccf-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="23ccf-121">Pour obtenir les informations communes à tous les types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="23ccf-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="23ccf-122">Développement d’objets personnalisés pour Integration Services</span><span class="sxs-lookup"><span data-stu-id="23ccf-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="23ccf-123">Décrit les étapes de base permettant d’implémenter tous les types d’objets personnalisés pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23ccf-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="23ccf-124">Persistance des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="23ccf-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="23ccf-125">Décrit la persistance personnalisée et explique les situations dans lesquelles elle est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="23ccf-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="23ccf-126">Génération, déploiement et débogage d’objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="23ccf-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="23ccf-127">Décrit les techniques permettant de générer, signer, déployer et déboguer des objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="23ccf-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="23ccf-128">Informations sur les autres objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="23ccf-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="23ccf-129">Pour plus d’informations sur les autres types d’objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="23ccf-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="23ccf-130">Développement d’une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="23ccf-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="23ccf-131">Explique comment programmer des tâches personnalisées.</span><span class="sxs-lookup"><span data-stu-id="23ccf-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="23ccf-132">Développement d’un module fournisseur d’informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="23ccf-133">Explique comment programmer des modules fournisseurs d'informations personnalisés.</span><span class="sxs-lookup"><span data-stu-id="23ccf-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="23ccf-134">Développement d’un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="23ccf-135">Décrit comment programmer des énumérateurs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="23ccf-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="23ccf-136">Développement d’un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="23ccf-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="23ccf-137">Explique comment programmer des sources, des transformations et des destinations de flux de données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="23ccf-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="23ccf-138">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="23ccf-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="23ccf-139">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="23ccf-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="23ccf-140">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="23ccf-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="23ccf-141">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="23ccf-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
