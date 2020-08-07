---
title: Exemples supplémentaires du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: 849dd38a-abb5-4702-a413-882aae3980a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 897ca075674f5c3dbaf355390fe8346580bf638a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611177"
---
# <a name="additional-script-component-examples"></a><span data-ttu-id="cd4d6-102">Exemples supplémentaires du composant Script</span><span class="sxs-lookup"><span data-stu-id="cd4d6-102">Additional Script Component Examples</span></span>
  <span data-ttu-id="cd4d6-103">Le composant Script est un outil configurable que vous pouvez utiliser dans le flux de données d'un package pour remplir presque toutes les conditions qui ne sont pas satisfaites par les sources, les transformations et les destinations incluses dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd4d6-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="cd4d6-104">Cette section contient des exemples de code du composant Script qui montrent les divers types de fonctionnalités disponibles.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-104">This section contains Script component code samples that demonstrate the various types of functionality that are available.</span></span>  
  
 <span data-ttu-id="cd4d6-105">Pour obtenir des exemples montrant comment configurer le composant Script en tant que source, transformation ou destination de base, consultez [Développement de types spécifiques de composants Script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="cd4d6-105">For samples that demonstrate how to configure the Script component as a basic source, transformation, or destination, see [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd4d6-106">Si vous souhaitez créer des composants que vous pouvez réutiliser plus facilement dans plusieurs tâches de flux de données et plusieurs packages, envisagez d'utiliser le code présenté dans ces exemples du composant Script comme point de départ pour vos composants de flux de données personnalisés.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-106">If you want to create components that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in these Script component samples as the starting point for custom data flow components.</span></span> <span data-ttu-id="cd4d6-107">Pour plus d’informations, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cd4d6-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd4d6-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cd4d6-108">In This Section</span></span>  
 [<span data-ttu-id="cd4d6-109">Simulation d'une sortie d'erreur pour le composant Script</span><span class="sxs-lookup"><span data-stu-id="cd4d6-109">Simulating an Error Output for the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md)  
 <span data-ttu-id="cd4d6-110">Le composant Script ne prend pas en charge une sortie d'erreur standard, mais vous pouvez simuler une sortie d'erreur standard avec peu de configuration et codage supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-110">The Script component does not support a standard error output, but you can simulate a standard error output with very little additional configuration and coding.</span></span>  
  
 [<span data-ttu-id="cd4d6-111">Amélioration d'une sortie d'erreur à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="cd4d6-111">Enhancing an Error Output with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/enhancing-an-error-output-with-the-script-component.md)  
 <span data-ttu-id="cd4d6-112">Explique et montre comment ajouter des informations supplémentaires à une sortie d'erreur standard en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-112">Explains and demonstrates how to add additional information to a standard error output by using the Script component.</span></span>  
  
 [<span data-ttu-id="cd4d6-113">Création d'une destination ODBC à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="cd4d6-113">Creating an ODBC Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/creating-an-odbc-destination-with-the-script-component.md)  
 <span data-ttu-id="cd4d6-114">Explique et montre comment créer une destination de flux de données ODBC en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-114">Explains and demonstrates how to create an ODBC data flow destination by using the Script component.</span></span>  
  
 [<span data-ttu-id="cd4d6-115">Analyse de formats de fichiers texte non standard à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="cd4d6-115">Parsing Non-Standard Text File Formats with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/parsing-non-standard-text-file-formats-with-the-script-component.md)  
 <span data-ttu-id="cd4d6-116">Explique et montre comment analyser deux formats de fichiers texte non standard différents dans des tables de destination.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-116">Explains and demonstrates how to parse two different non-standard text file formats into destination tables.</span></span>  
  
<span data-ttu-id="cd4d6-117">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cd4d6-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cd4d6-118">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="cd4d6-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cd4d6-119">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="cd4d6-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cd4d6-120">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="cd4d6-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
