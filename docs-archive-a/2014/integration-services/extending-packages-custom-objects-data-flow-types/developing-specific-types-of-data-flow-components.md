---
title: Développement de types spécifiques de composants de flux de données | Microsoft Docs
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705311"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="40a33-102">Développement de types spécifiques de composants de flux de données</span><span class="sxs-lookup"><span data-stu-id="40a33-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="40a33-103">Cette section explique de manière détaillée comment développer des composants source, des composants de transformation à sorties synchrones, des composants de transformation à sorties asynchrones et des composants de destination.</span><span class="sxs-lookup"><span data-stu-id="40a33-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="40a33-104">Pour plus d’informations sur le développement de composants, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="40a33-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40a33-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="40a33-105">In This Section</span></span>  
 [<span data-ttu-id="40a33-106">Développement d’un composant source personnalisé</span><span class="sxs-lookup"><span data-stu-id="40a33-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="40a33-107">Contient des informations sur le développement d'un composant qui accède aux données d'une source de données externe et qui les fournit à des composants situés en aval du flux de données.</span><span class="sxs-lookup"><span data-stu-id="40a33-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="40a33-108">Développement d’un composant de transformation personnalisé avec des sorties synchrones</span><span class="sxs-lookup"><span data-stu-id="40a33-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="40a33-109">Contient des informations sur le développement d'un composant de transformation dont les sorties sont synchrones avec ses entrées.</span><span class="sxs-lookup"><span data-stu-id="40a33-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="40a33-110">Ces composants n'ajoutent pas de données au flux de données, mais traitent les données pendant leur transfert.</span><span class="sxs-lookup"><span data-stu-id="40a33-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="40a33-111">Développement d’un composant de transformation personnalisé avec des sorties asynchrones</span><span class="sxs-lookup"><span data-stu-id="40a33-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="40a33-112">Contient des informations sur le développement d'un composant de transformation dont les sorties ne sont pas synchrones avec ses entrées.</span><span class="sxs-lookup"><span data-stu-id="40a33-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="40a33-113">Ces composants reçoivent des données des composants en amont, mais ils ajoutent également des données au flux de données.</span><span class="sxs-lookup"><span data-stu-id="40a33-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="40a33-114">Développement d’un composant de destination personnalisé</span><span class="sxs-lookup"><span data-stu-id="40a33-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="40a33-115">Contient des informations sur le développement d'un composant qui reçoit des lignes des composants situés en amont du flux de données et qui les écrit dans une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="40a33-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="40a33-116">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="40a33-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="40a33-117">Contient les classes et les interfaces qui permettent de créer des composants de flux de données personnalisés.</span><span class="sxs-lookup"><span data-stu-id="40a33-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="40a33-118">Contient les classes et interfaces non managées de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="40a33-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="40a33-119">Les développeurs utilisent ces dernières, ainsi que l'espace de noms <xref:Microsoft.SqlServer.Dts.Pipeline> managé, lorsqu'ils génèrent un flux de données par programme ou qu'ils créent des composants de flux de données personnalisés.</span><span class="sxs-lookup"><span data-stu-id="40a33-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="40a33-120">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="40a33-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="40a33-121">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="40a33-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="40a33-122">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="40a33-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="40a33-123">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="40a33-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a33-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40a33-124">See Also</span></span>  
 <span data-ttu-id="40a33-125">[Comparaison des solutions de script et des objets personnalisés](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="40a33-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="40a33-126">Développement de types spécifiques de composants Script</span><span class="sxs-lookup"><span data-stu-id="40a33-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
