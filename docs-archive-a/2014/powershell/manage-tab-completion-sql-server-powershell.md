---
title: Gérer la saisie semi-automatique par tabulation (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614692"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="78881-102">Gérer la saisie semi-automatique par tabulation (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="78881-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="78881-103">Les composants logiciels enfichables PowerShell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] introduisent trois variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` et `$SqlServerIncludeSystemObjects`) pour contrôler la saisie semi-automatique par tabulation de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78881-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="78881-104">La saisie semi-automatique par tabulation réduit la quantité de caractères que vous devez taper en renvoyant des tableaux d'éléments dont le nom commence par la chaîne que vous tapez.</span><span class="sxs-lookup"><span data-stu-id="78881-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="78881-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="78881-105">Before You Begin</span></span>  
 <span data-ttu-id="78881-106">Avec la saisie semi-automatique par tabulation de Windows PowerShell, une fois que vous avez tapé une partie d'un chemin d'accès ou d'un nom d'applet de commande, vous pouvez appuyer sur la touche Tab pour obtenir la liste des éléments dont le nom correspond à ce que vous avez déjà tapé.</span><span class="sxs-lookup"><span data-stu-id="78881-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="78881-107">Vous pouvez alors sélectionner l'élément souhaité dans la liste sans avoir à taper le reste du nom.</span><span class="sxs-lookup"><span data-stu-id="78881-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="78881-108">Si vous travaillez dans une base de données qui contient beaucoup d'objets, les listes de saisie semi-automatique par tabulation peuvent devenir très longues.</span><span class="sxs-lookup"><span data-stu-id="78881-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="78881-109">Certains types d'objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , tels que les vues, contiennent également de nombreux objets système.</span><span class="sxs-lookup"><span data-stu-id="78881-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="78881-110">Les composants logiciels enfichables [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] introduisent trois variables système que vous pouvez utiliser pour contrôler la quantité d’informations présentées par le biais de la saisie semi-automatique par tabulation et de **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="78881-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="78881-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="78881-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="78881-112">Spécifie le nombre maximal d'objets à inclure dans une liste de saisie semi-automatique par tabulation.</span><span class="sxs-lookup"><span data-stu-id="78881-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="78881-113">Si vous appuyez sur la touche Tab au niveau d’un nœud de chemin contenant plus de *n* objets, la liste de saisie semi-automatique par tabulation est tronquée au niveau *n*.</span><span class="sxs-lookup"><span data-stu-id="78881-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="78881-114">*n* est un entier.</span><span class="sxs-lookup"><span data-stu-id="78881-114">*n* is an integer.</span></span> <span data-ttu-id="78881-115">Le paramètre par défaut 0 signifie que le nombre d'objets répertoriés est illimité.</span><span class="sxs-lookup"><span data-stu-id="78881-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="78881-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="78881-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="78881-117">Spécifie le nombre maximal d’objets affichés par **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="78881-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="78881-118">Si **Get-ChildItem** est exécuté sur un nœud de chemin contenant plus de *n* objets, la liste est tronquée au niveau *n*.</span><span class="sxs-lookup"><span data-stu-id="78881-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="78881-119">*n* est un entier.</span><span class="sxs-lookup"><span data-stu-id="78881-119">*n* is an integer.</span></span> <span data-ttu-id="78881-120">Le paramètre par défaut 0 signifie que le nombre d'objets répertoriés est illimité.</span><span class="sxs-lookup"><span data-stu-id="78881-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="78881-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="78881-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="78881-122">Si cette variable est définie sur **$True**, les objets système sont affichés par le biais de la saisie semi-automatique par tabulation et de **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="78881-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="78881-123">Si cette variable est définie sur **$False**, aucun objet système n’est affiché.</span><span class="sxs-lookup"><span data-stu-id="78881-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="78881-124">La valeur par défaut est **$False**.</span><span class="sxs-lookup"><span data-stu-id="78881-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="78881-125">Définir les variables de la saisie semi-automatique par tabulation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="78881-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="78881-126">Pour chacune des variables pour lesquelles vous souhaitez utiliser une valeur autre que la valeur par défaut, définissez la nouvelle valeur de la variable.</span><span class="sxs-lookup"><span data-stu-id="78881-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="78881-127">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="78881-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="78881-128">L'exemple suivant définit les trois variables et répertorie leurs paramètres :</span><span class="sxs-lookup"><span data-stu-id="78881-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="78881-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78881-129">See Also</span></span>  
 [<span data-ttu-id="78881-130">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="78881-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
