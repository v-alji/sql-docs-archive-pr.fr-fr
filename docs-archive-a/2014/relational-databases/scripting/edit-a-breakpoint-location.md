---
title: Modifier un emplacement de point d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599864"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="09b3a-102">Modifier un emplacement de point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="09b3a-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="09b3a-103">L'emplacement du point d'arrêt spécifie la ligne et le caractère où réside ce point d'arrêt dans un fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09b3a-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="09b3a-104">Vous pouvez modifier cet emplacement pour déplacer le point d'arrêt vers un autre emplacement du script ou vers un script différent.</span><span class="sxs-lookup"><span data-stu-id="09b3a-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="09b3a-105">Modification d'un emplacement</span><span class="sxs-lookup"><span data-stu-id="09b3a-105">Editing a Location</span></span>  
 <span data-ttu-id="09b3a-106">Lorsque vous modifiez l'emplacement d'un point d'arrêt, ce point d'arrêt se déplace jusqu'à son nouvel emplacement et conserve toutes ses propriétés existantes, telles que le nombre d'accès ou la condition.</span><span class="sxs-lookup"><span data-stu-id="09b3a-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="09b3a-107">Pour modifier l'emplacement d'un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="09b3a-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="09b3a-108">Dans la fenêtre de l’éditeur, cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Emplacement** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="09b3a-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="09b3a-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="09b3a-109">-or-</span></span>  
  
     <span data-ttu-id="09b3a-110">Dans la fenêtre **Points d’arrêt** , cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Emplacement** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="09b3a-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="09b3a-111">Dans la boîte de dialogue **Point d’arrêt sur fichier** , modifiez **Fichier** pour spécifier un nouveau fichier, **Ligne** pour spécifier une nouvelle ligne ou **Caractère** pour spécifier un nouvel emplacement dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="09b3a-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="09b3a-112">Si le nouveau fichier que vous spécifiez est déjà ouvert dans une fenêtre de l'éditeur de requête, le point d'arrêt est déplacé vers cette fenêtre de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="09b3a-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="09b3a-113">Si le fichier n'est pas ouvert, une nouvelle fenêtre d'éditeur s'ouvre, le fichier y est chargé et le point d'arrêt est déplacé vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="09b3a-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="09b3a-114">L’option **Permettre que le code source soit différent de la version d’origine** n’a aucun effet lors du débogage de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09b3a-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b3a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09b3a-115">See Also</span></span>  
 <span data-ttu-id="09b3a-116">[Spécifier un nombre d’accès](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="09b3a-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="09b3a-117">[Spécifier une action de point d’arrêt](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="09b3a-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="09b3a-118">[Spécifier une condition de point d’arrêt](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="09b3a-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="09b3a-119">Pour spécifier un filtre de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="09b3a-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
