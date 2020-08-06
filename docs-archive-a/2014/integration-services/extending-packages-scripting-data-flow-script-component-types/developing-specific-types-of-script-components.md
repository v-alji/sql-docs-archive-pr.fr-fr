---
title: Développement de types spécifiques de composants Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610730"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="371db-102">Développement de types spécifiques de composants Script</span><span class="sxs-lookup"><span data-stu-id="371db-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="371db-103">Le composant Script est un outil configurable que vous pouvez utiliser dans le flux de données d'un package pour remplir presque toutes les conditions qui ne sont pas satisfaites par les sources, les transformations et les destinations incluses dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="371db-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="371db-104">Cette section contient des exemples de code du composant Script qui illustrent les quatre options de configuration du composant Script :</span><span class="sxs-lookup"><span data-stu-id="371db-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="371db-105">en tant que source ;</span><span class="sxs-lookup"><span data-stu-id="371db-105">As a source.</span></span>  
  
-   <span data-ttu-id="371db-106">en tant que transformation à sorties synchrones ;</span><span class="sxs-lookup"><span data-stu-id="371db-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="371db-107">en tant que transformation à sorties asynchrones ;</span><span class="sxs-lookup"><span data-stu-id="371db-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="371db-108">en tant que destination.</span><span class="sxs-lookup"><span data-stu-id="371db-108">As a destination.</span></span>  
  
 <span data-ttu-id="371db-109">Pour obtenir des exemples supplémentaires du composant Script, consultez [Exemples supplémentaires du composant Script](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="371db-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="371db-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="371db-110">In This Section</span></span>  
 [<span data-ttu-id="371db-111">Création d’une source à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="371db-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="371db-112">Explique et montre comment créer une source de flux de données en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="371db-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="371db-113">Création d’une transformation synchrone à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="371db-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="371db-114">Explique et montre comment créer une transformation de flux de données à sorties synchrones en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="371db-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="371db-115">Ce type de transformation modifie des lignes de données en place lorsqu'elles franchissent le composant.</span><span class="sxs-lookup"><span data-stu-id="371db-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="371db-116">Création d’une transformation asynchrone à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="371db-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="371db-117">Explique et montre comment créer une transformation de flux de données à sorties asynchrones en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="371db-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="371db-118">Ce type de transformation doit lire toutes les lignes de données avant de pouvoir ajouter d'autres informations, telles que des agrégats calculés, aux données qui franchissent le composant.</span><span class="sxs-lookup"><span data-stu-id="371db-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="371db-119">Création d’une destination à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="371db-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="371db-120">Explique et montre comment créer une destination de flux de données en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="371db-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="371db-121">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="371db-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="371db-122">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="371db-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="371db-123">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="371db-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="371db-124">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="371db-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371db-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="371db-125">See Also</span></span>  
 <span data-ttu-id="371db-126">[Comparaison des solutions de script et des objets personnalisés](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="371db-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="371db-127">Développement de types spécifiques de composants de flux de données</span><span class="sxs-lookup"><span data-stu-id="371db-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
