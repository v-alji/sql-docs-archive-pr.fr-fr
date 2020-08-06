---
title: Présentation des différences entre l’exécution locale et l’exécution distante | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698442"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="26159-102">Présentation des différences entre l'exécution locale et l'exécution distante</span><span class="sxs-lookup"><span data-stu-id="26159-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="26159-103">Les développeurs et administrateurs de packages doivent savoir qu'il existe des restrictions quant à l'emplacement d'exécution d'un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26159-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="26159-104">**Un package s’exécute sur le même ordinateur que le programme qui le lance**.</span><span class="sxs-lookup"><span data-stu-id="26159-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="26159-105">Même lorsqu'un programme charge un package stocké à distance sur un autre serveur, le package s'exécute sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="26159-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="26159-106">**Vous pouvez exécuter un package à l’extérieur de l’environnement de développement uniquement sur un ordinateur où est installé Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="26159-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="26159-107">Vous ne pouvez pas exécuter de packages en dehors de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] sur un ordinateur client sur lequel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'est pas installé, et les termes de votre licence [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent ne pas vous permettre d'installer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur d'autres ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="26159-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="26159-108">([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est un composant serveur et n'est pas redistribuable aux ordinateurs clients.)</span><span class="sxs-lookup"><span data-stu-id="26159-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="26159-109">Pour exécuter des packages à partir d'un ordinateur client, vous devez les lancer de manière à garantir leur exécution sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="26159-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="26159-110">Pour plus d'informations sur le chargement et l'exécution d'un package enregistré, consultez :</span><span class="sxs-lookup"><span data-stu-id="26159-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="26159-111">Chargement et exécution d’un package local par programmation</span><span class="sxs-lookup"><span data-stu-id="26159-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="26159-112">Chargement et exécution d’un package distant par programmation</span><span class="sxs-lookup"><span data-stu-id="26159-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="26159-113">Pour plus d'informations sur l'exécution d'un package et le chargement de sa sortie dans un programme personnalisé, consultez :</span><span class="sxs-lookup"><span data-stu-id="26159-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="26159-114">Chargement de la sortie d’un package local</span><span class="sxs-lookup"><span data-stu-id="26159-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="26159-115">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="26159-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="26159-116">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="26159-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="26159-117">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="26159-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="26159-118">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="26159-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26159-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26159-119">See Also</span></span>  
 <span data-ttu-id="26159-120">[Chargement et exécution d’un package local par programmation](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="26159-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="26159-121">[Chargement et exécution d’un package distant par programme](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="26159-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="26159-122">Chargement de la sortie d'un package local</span><span class="sxs-lookup"><span data-stu-id="26159-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
