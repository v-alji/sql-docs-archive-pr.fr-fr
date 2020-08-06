---
title: Déclenchement d’événements dans le composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611160"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="e82a9-102">Déclenchement d'événements dans le composant Script</span><span class="sxs-lookup"><span data-stu-id="e82a9-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="e82a9-103">Les événements offrent un moyen de signaler des erreurs, des avertissements et d'autres informations, telles que la progression ou l'état d'une tâche, au package conteneur.</span><span class="sxs-lookup"><span data-stu-id="e82a9-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="e82a9-104">Le package fournit des gestionnaires d'événements pour gérer les notifications d'événements.</span><span class="sxs-lookup"><span data-stu-id="e82a9-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="e82a9-105">Le composant Script peut déclencher des événements en appelant des méthodes sur la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> de la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="e82a9-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="e82a9-106">Pour plus d’informations sur la manière dont les packages [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] gèrent les événements, consultez [Gestionnaires d’événements Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="e82a9-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="e82a9-107">Les événements peuvent être journalisés dans tout module fournisseur d'informations activé dans le package.</span><span class="sxs-lookup"><span data-stu-id="e82a9-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="e82a9-108">Les modules fournisseurs d'informations stockent des informations à propos des événements dans une banque de données.</span><span class="sxs-lookup"><span data-stu-id="e82a9-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="e82a9-109">Le composant Script peut également utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> pour journaliser des informations dans un module fournisseur d'informations sans déclencher d'événement.</span><span class="sxs-lookup"><span data-stu-id="e82a9-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="e82a9-110">Pour plus d'informations sur la manière d'utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>, consultez la section suivante.</span><span class="sxs-lookup"><span data-stu-id="e82a9-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="e82a9-111">Pour déclencher un événement, la tâche de script appelle l'une des méthodes suivantes de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> exposée par la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> :</span><span class="sxs-lookup"><span data-stu-id="e82a9-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="e82a9-112">Événement</span><span class="sxs-lookup"><span data-stu-id="e82a9-112">Event</span></span>|<span data-ttu-id="e82a9-113">Description</span><span class="sxs-lookup"><span data-stu-id="e82a9-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="e82a9-114">Déclenche un événement personnalisé défini par l'utilisateur dans le package.</span><span class="sxs-lookup"><span data-stu-id="e82a9-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="e82a9-115">Informe le package d'une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e82a9-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="e82a9-116">Fournit des informations à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e82a9-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="e82a9-117">Informe le package de la progression du composant.</span><span class="sxs-lookup"><span data-stu-id="e82a9-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="e82a9-118">Informe le package que le composant est dans un état qui garantit la notification de l'utilisateur, mais qui n'est pas une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e82a9-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="e82a9-119">Voici un exemple simple de génération d'un événement d'erreur :</span><span class="sxs-lookup"><span data-stu-id="e82a9-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="e82a9-120">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e82a9-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e82a9-121">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="e82a9-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e82a9-122">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="e82a9-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e82a9-123">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="e82a9-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82a9-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e82a9-124">See Also</span></span>  
 <span data-ttu-id="e82a9-125">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="e82a9-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="e82a9-126">Ajouter un gestionnaire d’événements à un package</span><span class="sxs-lookup"><span data-stu-id="e82a9-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
