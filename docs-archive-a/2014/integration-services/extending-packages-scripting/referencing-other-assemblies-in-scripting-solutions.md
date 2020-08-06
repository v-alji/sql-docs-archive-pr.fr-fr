---
title: Référencement d’autres assemblys dans les solutions de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602210"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="3a422-102">Référencement d'autres assemblys dans les solutions de script</span><span class="sxs-lookup"><span data-stu-id="3a422-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="3a422-103">La bibliothèque de classes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fournit au développeur de scripts un ensemble d’outils performants permettant d’implémenter des fonctionnalités personnalisées dans des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a422-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="3a422-104">La tâche de script et le composant Script peuvent également utiliser des assemblys managés personnalisés.</span><span class="sxs-lookup"><span data-stu-id="3a422-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="3a422-105">Pour permettre à vos packages d’utiliser les objets et méthodes d’un service web, utilisez la commande **Ajouter une référence web** disponible dans [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="3a422-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="3a422-106">Dans les versions antérieures de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vous deviez générer une classe proxy pour utiliser un service Web.</span><span class="sxs-lookup"><span data-stu-id="3a422-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="3a422-107">Utilisation d'un assembly managé</span><span class="sxs-lookup"><span data-stu-id="3a422-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="3a422-108">Pour que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] trouve un assembly managé au moment de la conception, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a422-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="3a422-109">Stockez l'assembly managé dans un dossier sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3a422-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3a422-110">Dans les versions antérieures de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vous pouviez uniquement ajouter une référence à un assembly managé qui était stocké dans le dossier %windir%\Microsoft.NET\Framework\vx.x.xxxxx ou le dossier %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="3a422-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="3a422-111">Ajoutez une référence à l'assembly managé.</span><span class="sxs-lookup"><span data-stu-id="3a422-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="3a422-112">Pour ajouter la référence, dans VSTA, dans la boîte de dialogue **Ajouter une référence**, sous l’onglet **Parcourir**, localisez et ajoutez l’assembly managé.</span><span class="sxs-lookup"><span data-stu-id="3a422-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="3a422-113">Pour que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] recherche l'assembly managé au moment de l'exécution, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a422-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="3a422-114">Signez l'assembly managé avec un nom fort.</span><span class="sxs-lookup"><span data-stu-id="3a422-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="3a422-115">Installez l'assembly dans le Global Assembly Cache sur l'ordinateur sur lequel le package est exécuté.</span><span class="sxs-lookup"><span data-stu-id="3a422-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="3a422-116">Pour plus d’informations, consultez [Génération, déploiement et débogage d’objets personnalisés](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="3a422-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="3a422-117">Utilisation de la bibliothèque de classes Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a422-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="3a422-118">La tâche de script et le composant Script peuvent tirer parti de tous les autres objets et fonctionnalités exposés par la bibliothèque de classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a422-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="3a422-119">Par exemple, en utilisant [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vous pouvez extraire des informations sur votre environnement et interagir avec l'ordinateur qui exécute le package.</span><span class="sxs-lookup"><span data-stu-id="3a422-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="3a422-120">Cette liste décrit plusieurs classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] figurant parmi les plus fréquemment utilisées :</span><span class="sxs-lookup"><span data-stu-id="3a422-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="3a422-121">`System.Data`Contient l’architecture ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="3a422-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="3a422-122">`System.IO`Fournit une interface au système de fichiers et aux flux.</span><span class="sxs-lookup"><span data-stu-id="3a422-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="3a422-123">`System.Windows.Forms`Fournit la création de formulaire.</span><span class="sxs-lookup"><span data-stu-id="3a422-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="3a422-124">`System.Text.RegularExpressions`Fournit des classes pour l’utilisation d’expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="3a422-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="3a422-125">`System.Environment`Retourne des informations sur l’ordinateur local, l’utilisateur actuel et les paramètres de l’ordinateur et de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3a422-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="3a422-126">`System.Net`Fournit des communications réseau.</span><span class="sxs-lookup"><span data-stu-id="3a422-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="3a422-127">`System.DirectoryServices`Expose Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a422-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="3a422-128">`System.Drawing`Fournit de nombreuses bibliothèques de manipulation d’images.</span><span class="sxs-lookup"><span data-stu-id="3a422-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="3a422-129">`System.Threading`Active la programmation multithread.</span><span class="sxs-lookup"><span data-stu-id="3a422-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="3a422-130">Pour plus d'informations sur le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consultez MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3a422-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="3a422-131">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3a422-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3a422-132">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="3a422-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3a422-133">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="3a422-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3a422-134">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="3a422-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a422-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a422-135">See Also</span></span>
 [<span data-ttu-id="3a422-136">Extension de packages avec des scripts</span><span class="sxs-lookup"><span data-stu-id="3a422-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


