---
title: Options de grille variables | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602187"
---
# <a name="variable-grid-options"></a><span data-ttu-id="e7059-102">Options de grille variables</span><span class="sxs-lookup"><span data-stu-id="e7059-102">Variable Grid Options</span></span>
  <span data-ttu-id="e7059-103">Utilisez la boîte de dialogue **Options de grille variables** pour sélectionner les colonnes qui s'affichent dans la fenêtre **Variables** et sélectionner les filtres à appliquer à la liste des variables.</span><span class="sxs-lookup"><span data-stu-id="e7059-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="e7059-104">Pour plus d'informations sur les propriétés de variable correspondantes, consultez [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e7059-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="e7059-105">Options pour le filtre</span><span class="sxs-lookup"><span data-stu-id="e7059-105">Options for Filter</span></span>  
 <span data-ttu-id="e7059-106">**Afficher les variables système**</span><span class="sxs-lookup"><span data-stu-id="e7059-106">**Show system variables**</span></span>  
 <span data-ttu-id="e7059-107">Sélectionnez cette option pour répertorier les variables système dans la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="e7059-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="e7059-108">Les variables système sont prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="e7059-108">System variables are predefined.</span></span> <span data-ttu-id="e7059-109">Vous ne pouvez pas ajouter ou supprimer des variables système.</span><span class="sxs-lookup"><span data-stu-id="e7059-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="e7059-110">Vous pouvez modifier le paramètre de la propriété **RaiseChangedEvent** .</span><span class="sxs-lookup"><span data-stu-id="e7059-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="e7059-111">Cette liste est codée par couleur.</span><span class="sxs-lookup"><span data-stu-id="e7059-111">This list is color coded.</span></span> <span data-ttu-id="e7059-112">Les variables système sont en gris et les variables définies par l'utilisateur en noir.</span><span class="sxs-lookup"><span data-stu-id="e7059-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="e7059-113">**Afficher les variables de toutes les étendues**</span><span class="sxs-lookup"><span data-stu-id="e7059-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="e7059-114">Sélectionnez cette option pour afficher les variables dans l'étendue du package et dans l'étendue des conteneurs, des tâches et des gestionnaires d'événements dans le package.</span><span class="sxs-lookup"><span data-stu-id="e7059-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="e7059-115">Désactivez cette option pour afficher uniquement les variables dans l'étendue du package et dans l'étendue d'un conteneur, d'une tâche ou d'un gestionnaire d'événements donné.</span><span class="sxs-lookup"><span data-stu-id="e7059-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="e7059-116">Pour plus d’informations sur la portée des variables, consultez [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e7059-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="e7059-117">Options pour les colonnes</span><span class="sxs-lookup"><span data-stu-id="e7059-117">Options for Columns</span></span>  
 <span data-ttu-id="e7059-118">Sélectionnez les colonnes que vous souhaitez afficher dans la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="e7059-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="e7059-119">**Portée**</span><span class="sxs-lookup"><span data-stu-id="e7059-119">**Scope**</span></span>  
  
-   <span data-ttu-id="e7059-120">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e7059-120">**Data type**</span></span>  
  
-   <span data-ttu-id="e7059-121">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="e7059-121">**Value**</span></span>  
  
-   <span data-ttu-id="e7059-122">**Espace de noms**</span><span class="sxs-lookup"><span data-stu-id="e7059-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="e7059-123">**Déclencher l'événement lorsque la valeur de la variable change**</span><span class="sxs-lookup"><span data-stu-id="e7059-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="e7059-124">**Description**</span><span class="sxs-lookup"><span data-stu-id="e7059-124">**Description**</span></span>  
  
-   <span data-ttu-id="e7059-125">**Expression**</span><span class="sxs-lookup"><span data-stu-id="e7059-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7059-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7059-126">See Also</span></span>  
 <span data-ttu-id="e7059-127">[Fenêtre variables](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="e7059-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="e7059-128">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e7059-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="e7059-129">[Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="e7059-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="e7059-130">Gestionnaires d’événements Integration Services &#40;SSIS&#41</span><span class="sxs-lookup"><span data-stu-id="e7059-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
