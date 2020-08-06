---
title: Comparaison des solutions de script et des objets personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: acf6faf9cdd78e951b8298c4e3b144d3444fb1ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601609"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a><span data-ttu-id="41c00-102">Comparaison des solutions de script et des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="41c00-102">Comparing Scripting Solutions and Custom Objects</span></span>
  <span data-ttu-id="41c00-103">Une tâche de script [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou un composant Script peuvent implémenter un bon nombre des mêmes fonctionnalités possibles dans une tâche managée personnalisée ou un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="41c00-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task or Script component can implement much of the same functionality that is possible in a custom managed task or data flow component.</span></span> <span data-ttu-id="41c00-104">Voici quelques éléments à considérer pour choisir le type de tâche approprié à vos besoins :</span><span class="sxs-lookup"><span data-stu-id="41c00-104">Here are some considerations to help you choose the appropriate type of task for your needs:</span></span>  
  
-   <span data-ttu-id="41c00-105">Si la configuration ou les fonctionnalités sont propres à un package individuel, vous devez utiliser la tâche de script ou le composant Script au lieu de développer un objet personnalisé.</span><span class="sxs-lookup"><span data-stu-id="41c00-105">If the configuration or functionality is specific to an individual package, you should use the Script task or the Script component instead of a developing a custom object.</span></span>  
  
-   <span data-ttu-id="41c00-106">Si les fonctionnalités sont génériques et pourront être utilisées ultérieurement pour d'autres packages et par d'autres développeurs, vous devez créer un objet personnalisé au lieu d'utiliser une solution de script.</span><span class="sxs-lookup"><span data-stu-id="41c00-106">If the functionality is generic, and might be used in the future for other packages and by other developers, you should create a custom object instead of using a scripting solution.</span></span> <span data-ttu-id="41c00-107">Vous pouvez utiliser un objet personnalisé dans tout package, alors qu'un script peut uniquement être utilisé dans le package pour lequel il a été créé.</span><span class="sxs-lookup"><span data-stu-id="41c00-107">You can use a custom object in any package, whereas a script can be used only in the package for which it was created.</span></span>  
  
-   <span data-ttu-id="41c00-108">Si le code sera réutilisé dans le même package, vous devez envisager de créer un objet personnalisé.</span><span class="sxs-lookup"><span data-stu-id="41c00-108">If the code will be reused within the same package, you should consider creating a custom object.</span></span> <span data-ttu-id="41c00-109">La copie de code depuis une tâche de script ou un composant Script vers une autre tâche ou un autre composant en réduit la facilité de gestion en rendant plus difficiles la gestion et la mise à jour des multiples copies du code.</span><span class="sxs-lookup"><span data-stu-id="41c00-109">Copying code from one Script task or component to another leads to reduced maintainability by making it more difficult to maintain and update multiple copies of the code.</span></span>  
  
-   <span data-ttu-id="41c00-110">Si l'implémentation va changer avec le temps, envisagez d'utiliser un objet personnalisé.</span><span class="sxs-lookup"><span data-stu-id="41c00-110">If the implementation will change over time, consider using a custom object.</span></span> <span data-ttu-id="41c00-111">Les objets personnalisés peuvent être développés et déployés séparément du package parent, alors qu'une mise à jour apportée à une solution de script requiert le redéploiement du package entier.</span><span class="sxs-lookup"><span data-stu-id="41c00-111">Custom objects can be developed and deployed separately from the parent package, whereas an update made to a scripting solution requires the redeployment of the whole package.</span></span>  
  
<span data-ttu-id="41c00-112">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="41c00-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="41c00-113">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="41c00-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="41c00-114">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="41c00-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="41c00-115">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="41c00-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c00-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41c00-116">See Also</span></span>  
 [<span data-ttu-id="41c00-117">Extension de packages avec des objets personnalisés</span><span class="sxs-lookup"><span data-stu-id="41c00-117">Extending Packages with Custom Objects</span></span>](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  
