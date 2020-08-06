---
title: Fenêtre Commande
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613407"
---
# <a name="command-window"></a><span data-ttu-id="f8078-102">Fenêtre Commande</span><span class="sxs-lookup"><span data-stu-id="f8078-102">Command Window</span></span>
  <span data-ttu-id="f8078-103">Utilisez la **Fenêtre Commande** pour exécuter des commandes, telles que les commandes de débogage et de modification, sur le code contenu dans la fenêtre de l’éditeur de requête du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en cours de débogage.</span><span class="sxs-lookup"><span data-stu-id="f8078-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="f8078-104">Vous devez être en mode débogage pour pouvoir utiliser la **Fenêtre Commande**.</span><span class="sxs-lookup"><span data-stu-id="f8078-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="f8078-105">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] prend en charge la plupart des commandes qui sont également prises en charge dans la fenêtre [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span><span class="sxs-lookup"><span data-stu-id="f8078-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="f8078-106">Pour plus d’informations, consultez [Fenêtre Commande de Visual Studio](https://go.microsoft.com/fwlink/?LinkId=112007).</span><span class="sxs-lookup"><span data-stu-id="f8078-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f8078-107">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="f8078-107">Task List</span></span>  
 <span data-ttu-id="f8078-108">**Pour accéder à la Fenêtre Commande**</span><span class="sxs-lookup"><span data-stu-id="f8078-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="f8078-109">Dans le menu **Déboguer** , cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="f8078-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="f8078-110">**Pour imprimer la valeur d'une variable**</span><span class="sxs-lookup"><span data-stu-id="f8078-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="f8078-111">Dans **CommandWindow**, tapez \*\*Debug. Print \<VariableName> \*\*, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="f8078-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="f8078-112">**Pour afficher des informations sur le thread actuel**</span><span class="sxs-lookup"><span data-stu-id="f8078-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="f8078-113">Dans **CommandWindow**, tapez `Debug.ListThread` , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="f8078-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="f8078-114">**Pour ajouter une variable à la fenêtre Espion express**</span><span class="sxs-lookup"><span data-stu-id="f8078-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="f8078-115">Dans **CommandWindow**, tapez \*\*Debug. espion Express \<VariableName> \*\*, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="f8078-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8078-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8078-116">See Also</span></span>  
 [<span data-ttu-id="f8078-117">Débogueur Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f8078-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
