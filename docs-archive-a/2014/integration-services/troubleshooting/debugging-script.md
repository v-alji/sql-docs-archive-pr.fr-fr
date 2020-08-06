---
title: Script de débogage | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705247"
---
# <a name="debugging-script"></a><span data-ttu-id="6395e-102">Script de débogage</span><span class="sxs-lookup"><span data-stu-id="6395e-102">Debugging Script</span></span>
  <span data-ttu-id="6395e-103">Vous écrivez les scripts utilisés par la tâche de script et le composant de script dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="6395e-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="6395e-104">Vous définissez et écrivez les points d'arrêt dans VSTA.</span><span class="sxs-lookup"><span data-stu-id="6395e-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="6395e-105">Vous pouvez gérer les points d’arrêt dans VSTA, mais également avec la boîte de dialogue **Définir des points d’arrêt** fournie par le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6395e-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="6395e-106">Pour plus d’informations, consultez [Débogage du flux de contrôle](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="6395e-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="6395e-107">La boîte de dialogue **Définir des points d’arrêt** inclut les points d’arrêt du script.</span><span class="sxs-lookup"><span data-stu-id="6395e-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="6395e-108">Ces points d'arrêt apparaissent au bas de la liste des points d'arrêt et mentionnent le numéro de ligne et le nom de la fonction dans laquelle le point d'arrêt apparaît.</span><span class="sxs-lookup"><span data-stu-id="6395e-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="6395e-109">Vous pouvez supprimer un point d’arrêt de script à partir de la boîte de dialogue **Définir des points d’arrêt** .</span><span class="sxs-lookup"><span data-stu-id="6395e-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="6395e-110">Au moment de l'exécution, les points d'arrêt définis sur des lignes de code dans le script sont intégrés à ceux définis sur le package ou sur les tâches et conteneurs du package.</span><span class="sxs-lookup"><span data-stu-id="6395e-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="6395e-111">Le débogueur peut s'exécuter à partir d'un point d'arrêt dans le script jusqu'à un point d'arrêt défini sur le package, la tâche ou le conteneur, et inversement.</span><span class="sxs-lookup"><span data-stu-id="6395e-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="6395e-112">Par exemple, un package peut contenir des points d’arrêt définis sur les conditions d’arrêt qui se produisent quand le package reçoit les événements **OnPreExecute** et **OnPostExecute** , et peut aussi contenir une tâche de script qui contient des points d’arrêt sur des lignes de son script.</span><span class="sxs-lookup"><span data-stu-id="6395e-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="6395e-113">Dans ce scénario, l’exécution du package peut être suspendue selon la condition d’arrêt associée à l’événement **OnPreExecute** , se poursuivre jusqu’aux points d’arrêt du script, puis continuer jusqu’à la condition d’arrêt associée à l’événement **OnPostExecute** .</span><span class="sxs-lookup"><span data-stu-id="6395e-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="6395e-114">Pour plus d’informations sur le débogage de la tâche de Script et du composant Script, consultez [Codage et débogage de la tâche de script](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) et [Codage et débogage du composant Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="6395e-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="6395e-115">Pour définir un point d'arrêt dans Visual Studio for Applications</span><span class="sxs-lookup"><span data-stu-id="6395e-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="6395e-116">Déboguer un script en définissant des points d’arrêt dans une tâche de script et un composant de script</span><span class="sxs-lookup"><span data-stu-id="6395e-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="6395e-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6395e-117">See Also</span></span>  
 [<span data-ttu-id="6395e-118">Outils de dépannage pour le développement des packages</span><span class="sxs-lookup"><span data-stu-id="6395e-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
