---
title: Information sur les paramètres (IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613413"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="7a5fd-102">Information sur les paramètres (IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="7a5fd-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="7a5fd-103">L’option [!INCLUDE[msCoName](../../includes/msconame-md.md)] Informations sur les paramètres **de** IntelliSense ouvre une liste de paramètres qui fournit des informations sur le nombre, le nom et le type des paramètres requis par une fonction ou une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="7a5fd-104">Le paramètre en gras indique le prochain paramètre requis lorsque vous tapez une fonction ou une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="7a5fd-105">La liste des paramètres est également affichée pour les fonctions imbriquées.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="7a5fd-106">Si vous tapez une fonction comme paramètre d'une autre fonction, la liste affiche dans un premier temps les paramètres de la fonction interne.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="7a5fd-107">Dans un second temps, la liste affiche les paramètres de la fonction externe.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="7a5fd-108">Pour afficher l'option Informations sur les paramètres pour les fonctions ou les procédures stockées</span><span class="sxs-lookup"><span data-stu-id="7a5fd-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="7a5fd-109">À la suite du nom de la fonction, tapez une parenthèse ouvrante comme vous le feriez normalement pour ouvrir une liste de paramètres.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="7a5fd-110">Après avoir tapé le nom d'une procédure stockée, tapez un espace comme vous le feriez normalement pour obtenir des informations à propos des paramètres d'une procédure.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="7a5fd-111">IntelliSense affiche la déclaration complète de la fonction ou les paramètres de la procédure stockée dans une fenêtre indépendante, juste sous le point d'insertion.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="7a5fd-112">Le premier paramètre de la liste est affiché en gras.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="7a5fd-113">À mesure que vous tapez les paramètres, le paramètre suivant à entrer vous est indiqué en gras.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="7a5fd-114">Appuyez sur ÉCHAP pour fermer la liste ou continuez à taper la fonction jusqu'à la fin.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="7a5fd-115">Dans le cas d'une fonction, si vous tapez la parenthèse fermante, vous fermez également la liste des paramètres.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="7a5fd-116">Pour démarrer manuellement l'option Informations sur les paramètres</span><span class="sxs-lookup"><span data-stu-id="7a5fd-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="7a5fd-117">Dans le menu **Edition** , sélectionnez **IntelliSense** , puis **Informations sur les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="7a5fd-118">Utilisez le raccourci clavier CTRL+MAJ+ESPACE.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="7a5fd-119">Pour plus d’informations, consultez [Configurer IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7a5fd-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a5fd-120">L’option **Informations sur les paramètres** est uniquement disponible pour l’éditeur de requête [!INCLUDE[ssDE](../../includes/ssde-md.md)] et l’Éditeur de requête XML.</span><span class="sxs-lookup"><span data-stu-id="7a5fd-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
