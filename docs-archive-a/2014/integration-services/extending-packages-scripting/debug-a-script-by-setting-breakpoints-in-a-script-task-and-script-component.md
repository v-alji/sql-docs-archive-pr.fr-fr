---
title: Déboguer un script en définissant des points d’arrêt dans une tâche de script et un composant de script| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602899"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="ec60b-102">Déboguer un script en définissant des points d'arrêt dans une tâche de script et un composant de script</span><span class="sxs-lookup"><span data-stu-id="ec60b-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="ec60b-103">Cette section décrit la procédure de définition des points d'arrêt dans les scripts utilisés dans la tâche de script et le composant de script.</span><span class="sxs-lookup"><span data-stu-id="ec60b-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="ec60b-104">Après avoir défini les points d’arrêt dans le script, la boîte de dialogue **Définir les points d’arrêt - \<object name>** donne la liste des points d’arrêt avec les points d’arrêt intégrés.</span><span class="sxs-lookup"><span data-stu-id="ec60b-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec60b-105">Dans certains cas, les points d'arrêt de la tâche de script et le composant de script sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="ec60b-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="ec60b-106">Pour plus d’informations, consultez la section **débogage de la tâche de script** dans [codage et débogage de la tâche de script](../control-flow/script-task.md) et la section **débogage du composant script** dans [codage et débogage du composant Script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="ec60b-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="ec60b-107">Pour définir un point d'arrêt dans un script</span><span class="sxs-lookup"><span data-stu-id="ec60b-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="ec60b-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="ec60b-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ec60b-109">Double-cliquez sur le package qui contient le script dans lequel vous souhaitez définir des points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ec60b-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="ec60b-110">Pour ouvrir la tâche de script, cliquez sur l’onglet **Flux de contrôle**, puis double-cliquez sur la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ec60b-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="ec60b-111">Pour ouvrir le composant de script, cliquez sur l’onglet **Flux de données**, puis double-cliquez sur le composant de script.</span><span class="sxs-lookup"><span data-stu-id="ec60b-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="ec60b-112">Cliquez sur **Script**, puis sur **Modifier le script**.</span><span class="sxs-lookup"><span data-stu-id="ec60b-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="ec60b-113">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), recherchez la ligne de script sur laquelle vous voulez définir un point d’arrêt, cliquez dessus avec le bouton droit, pointez sur **Point d’arrêt**, puis sélectionnez **Insérer un point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ec60b-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="ec60b-114">L'icône du point d'arrêt apparaît sur la ligne de code.</span><span class="sxs-lookup"><span data-stu-id="ec60b-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="ec60b-115">Dans le menu **Fichier** , cliquez sur **Quitter**.</span><span class="sxs-lookup"><span data-stu-id="ec60b-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="ec60b-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec60b-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="ec60b-117">Pour enregistrer le package, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="ec60b-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
