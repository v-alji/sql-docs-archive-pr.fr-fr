---
title: Développement d’un module fournisseur d’informations personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601617"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="65dff-102">Développement d'un module fournisseur d'informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="65dff-102">Developing a Custom Log Provider</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="65dff-103">possède des fonctions de journalisation étendues qui permettent de capturer les événements qui se produisent pendant l'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="65dff-103">has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="65dff-104">inclut divers modules fournisseurs d’informations qui permettent de créer et de stocker des journaux dans différents formats, tels que XML, texte et base de données ou dans le journal des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="65dff-104">includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="65dff-105">Si les modules fournisseurs d'informations et les formats de sortie fournis ne répondent pas totalement à vos besoin, vous pouvez créer un module fournisseur d'informations personnalisé.</span><span class="sxs-lookup"><span data-stu-id="65dff-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="65dff-106">Pour créer un module fournisseur d'informations personnalisé, vous devez créer une classe qui hérite de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, appliquer l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> à la nouvelle classe et substituer les méthodes et propriétés importantes de la classe de base, notamment la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> et la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="65dff-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="65dff-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="65dff-107">In This Section</span></span>
 <span data-ttu-id="65dff-108">Cette section explique comment créer, configurer et coder un module fournisseur d'informations personnalisé.</span><span class="sxs-lookup"><span data-stu-id="65dff-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="65dff-109">[Création d’un module fournisseur d’informations personnalisé](creating-a-custom-log-provider.md) Décrit comment créer les classes d’un projet de module fournisseur d’informations personnalisé.</span><span class="sxs-lookup"><span data-stu-id="65dff-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="65dff-110">[Codage d’un module fournisseur d’informations personnalisé](coding-a-custom-log-provider.md) Décrit comment implémenter un module fournisseur d’informations personnalisé en substituant les méthodes et les propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="65dff-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="65dff-111">[Développement d’une interface utilisateur pour un module fournisseur d’informations personnalisé](developing-a-user-interface-for-a-custom-log-provider.md) Les interfaces utilisateur personnalisées pour les modules fournisseurs d’informations personnalisés ne sont pas prises en charge dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65dff-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="65dff-112">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="65dff-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="65dff-113">Informations communes à tous les objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="65dff-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="65dff-114">Pour obtenir les informations communes à tous les types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="65dff-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="65dff-115">[Développement d’objets personnalisés pour Integration Services](../developing-custom-objects-for-integration-services.md) Décrit les étapes de base de l’implémentation de tous les types d’objets personnalisés pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65dff-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="65dff-116">[Persistance des objets personnalisés](../persisting-custom-objects.md) Décrit la persistance personnalisée et explique quand elle est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="65dff-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="65dff-117">[Génération, déploiement et débogage d’objets personnalisés](../building-deploying-and-debugging-custom-objects.md) Décrit les techniques permettant de générer, signer, déployer et déboguer des objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="65dff-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="65dff-118">Informations sur les autres objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="65dff-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="65dff-119">Pour plus d’informations sur les autres types d’objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="65dff-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="65dff-120">[Développement d’une tâche personnalisée](../task/developing-a-custom-task.md) Explique comment programmer des tâches personnalisées.</span><span class="sxs-lookup"><span data-stu-id="65dff-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="65dff-121">[Développement d’un gestionnaire de connexions personnalisé](../connection-manager/developing-a-custom-connection-manager.md) Explique comment programmer des gestionnaires de connexions personnalisés.</span><span class="sxs-lookup"><span data-stu-id="65dff-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="65dff-122">[Développement d’un énumérateur foreach personnalisé](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Explique comment programmer des énumérateurs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="65dff-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="65dff-123">[Développement d’un composant de workflow de données personnalisé](../data-flow/developing-a-custom-data-flow-component.md) Explique comment programmer des sources, des transformations et des destinations de workflow de données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="65dff-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="65dff-124">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="65dff-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="65dff-125">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="65dff-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="65dff-126">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="65dff-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="65dff-127">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="65dff-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


