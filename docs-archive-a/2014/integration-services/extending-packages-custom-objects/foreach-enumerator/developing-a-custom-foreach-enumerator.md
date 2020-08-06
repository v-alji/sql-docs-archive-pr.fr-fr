---
title: Développement d’un énumérateur ForEach personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605659"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="6a8b8-102">Développement d'un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-102">Developing a Custom ForEach Enumerator</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="6a8b8-103">utilise des énumérateurs Foreach pour parcourir les éléments d'une collection et effectuer les mêmes tâches pour chaque élément.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-103">uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="6a8b8-104">inclut divers énumérateurs Foreach qui prennent en charge les collections les plus couramment utilisées, telles que tous les fichiers inclus dans un dossier, toutes les tables incluses dans une base de données ou tous les éléments d'une liste stockée dans une variable de package.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-104">includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="6a8b8-105">Si les énumérateurs foreach et les collections fournies ne répondent pas totalement à vos besoins, vous pouvez créer un énumérateur foreach personnalisé.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="6a8b8-106">Pour créer un énumérateur foreach personnalisé, vous devez créer une classe qui hérite de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, appliquer l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> à votre nouvelle classe et remplacer les méthodes et propriétés importantes de la classe de base, notamment la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a8b8-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6a8b8-107">In This Section</span></span>  
 <span data-ttu-id="6a8b8-108">Cette section explique comment créer, configurer et coder un énumérateur foreach personnalisé et son interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="6a8b8-109">Création d’un énumérateur Foreach personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="6a8b8-110">Explique comment créer les classes d'un projet d'énumérateur foreach personnalisé.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="6a8b8-111">Codage d’un énumérateur Foreach personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="6a8b8-112">Décrit comment implémenter un énumérateur foreach personnalisé en remplaçant les méthodes et propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="6a8b8-113">Développement d’une interface utilisateur pour un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="6a8b8-114">Explique comment implémenter la classe d'interface utilisateur et le formulaire servant à configurer l'énumérateur foreach personnalisé.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="6a8b8-115">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6a8b8-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="6a8b8-116">Informations communes à tous les objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="6a8b8-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="6a8b8-117">Pour obtenir les informations communes à tous les types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a8b8-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="6a8b8-118">Développement d’objets personnalisés pour Integration Services</span><span class="sxs-lookup"><span data-stu-id="6a8b8-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="6a8b8-119">Décrit les étapes de base permettant d’implémenter tous les types d’objets personnalisés pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a8b8-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="6a8b8-120">Persistance des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="6a8b8-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="6a8b8-121">Décrit la persistance personnalisée et explique les situations dans lesquelles elle est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="6a8b8-122">Génération, déploiement et débogage d’objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="6a8b8-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="6a8b8-123">Décrit les techniques permettant de générer, signer, déployer et déboguer des objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="6a8b8-124">Informations sur les autres objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="6a8b8-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="6a8b8-125">Pour plus d’informations sur les autres types d’objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a8b8-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="6a8b8-126">Développement d’une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="6a8b8-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="6a8b8-127">Explique comment programmer des tâches personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="6a8b8-128">Développement d’un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="6a8b8-129">Explique comment programmer des gestionnaires de connexions personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="6a8b8-130">Développement d’un module fournisseur d’informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="6a8b8-131">Explique comment programmer des modules fournisseurs d'informations personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="6a8b8-132">Développement d’un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="6a8b8-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="6a8b8-133">Explique comment programmer des sources, des transformations et des destinations de flux de données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="6a8b8-134">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6a8b8-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6a8b8-135">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="6a8b8-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6a8b8-136">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="6a8b8-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6a8b8-137">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="6a8b8-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
