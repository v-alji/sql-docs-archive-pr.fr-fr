---
title: Ajouter, supprimer et modifier l’étendue d’une variable définie par l’utilisateur dans un package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604702"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="3e1a3-102">Ajouter, supprimer, modifier l'étendue de la variable définie par l'utilisateur dans un package</span><span class="sxs-lookup"><span data-stu-id="3e1a3-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="3e1a3-103">Les procédures suivantes expliquent comment ajouter, supprimer et modifier l’étendue d’une variable définie par l’utilisateur dans un package, à l’aide de la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="3e1a3-104">Pour plus d’informations sur la portée des variables, consultez [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3e1a3-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="3e1a3-105">fournit également des variables système qui rendent disponibles les informations système au moment de l'exécution, pour être utilisées dans des conteneurs tels que des packages et des gestionnaires d'événements.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-105">also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="3e1a3-106">Vous ne pouvez pas supprimer des variables système.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="3e1a3-107">Pour ajouter une variable</span><span class="sxs-lookup"><span data-stu-id="3e1a3-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="3e1a3-108">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="3e1a3-109">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e1a3-110">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , pour définir la portée de la variable, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e1a3-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="3e1a3-111">Pour définir la portée du package, cliquez n’importe où sur l’aire de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="3e1a3-112">Pour définir la portée d’un gestionnaire d’événements, sélectionnez un exécutable et un gestionnaire d’événements sur l’aire de conception de l’onglet **Gestionnaire d’événements** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="3e1a3-113">Pour définir la portée d’une tâche ou d’un conteneur, cliquez sur une tâche ou un conteneur sur l’aire de conception de l’onglet **Flux de contrôle** ou de l’onglet **Gestionnaire d’événements** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="3e1a3-114">Dans le menu **SSIS** , cliquez sur **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3e1a3-115">Vous pouvez éventuellement afficher la fenêtre **Variables** en mappant la commande View.Variables avec une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="3e1a3-116">Dans la fenêtre **variables** , cliquez sur l’icône **Ajouter une variable** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="3e1a3-117">La nouvelle variable est ajoutée à la liste.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="3e1a3-118">Dans la boîte de dialogue **Options de la grille** , sélectionnez des colonnes supplémentaires à afficher dans la boîte de dialogue **Options de la grille de variables** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="3e1a3-119">Éventuellement, définissez les propriétés d'une variable.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="3e1a3-120">Pour plus d’informations, consultez [Définir les propriétés d'une variable définie par l'utilisateur](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span><span class="sxs-lookup"><span data-stu-id="3e1a3-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="3e1a3-121">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="3e1a3-122">Pour supprimer une variable.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="3e1a3-123">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3e1a3-124">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e1a3-125">Dans le menu **SSIS** , cliquez sur **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3e1a3-126">Vous pouvez éventuellement afficher la fenêtre **Variables** en mappant la commande View.Variables avec une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="3e1a3-127">Sélectionnez la variable à supprimer, puis cliquez sur **Supprimer la variable**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="3e1a3-128">Si vous ne voyez pas la variable dans la fenêtre variables, cliquez sur options de la **grille** , puis sélectionnez **afficher les variables de toutes les étendues**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="3e1a3-129">Si la boîte de dialogue **Confirmer la suppression des variables** apparaît, cliquez sur **Oui** pour confirmer.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="3e1a3-130">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="3e1a3-131">Pour modifier l'étendue d'une variable</span><span class="sxs-lookup"><span data-stu-id="3e1a3-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="3e1a3-132">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3e1a3-133">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3e1a3-134">Dans le menu **SSIS** , cliquez sur **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="3e1a3-135">Vous pouvez éventuellement afficher la fenêtre **Variables** en mappant la commande View.Variables avec une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="3e1a3-136">Sélectionnez la variable, puis cliquez sur **Déplacer la variable**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="3e1a3-137">Si vous ne voyez pas la variable dans la fenêtre variables, cliquez sur options de la **grille** , puis sélectionnez **afficher les variables de toutes les étendues**.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="3e1a3-138">Dans la boîte de dialogue **Sélectionner une nouvelle étendue** , sélectionnez le package ou un conteneur, une tâche ou un gestionnaire d'événements dans le package pour modifier l'étendue de la variable.</span><span class="sxs-lookup"><span data-stu-id="3e1a3-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="3e1a3-139">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="3e1a3-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1a3-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e1a3-140">See Also</span></span>  
 <span data-ttu-id="3e1a3-141">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3e1a3-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="3e1a3-142">[Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3e1a3-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="3e1a3-143">[Définir les propriétés d’une variable définie par l’utilisateur](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="3e1a3-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="3e1a3-144">Utiliser les valeurs des variables et des paramètres dans un package enfant</span><span class="sxs-lookup"><span data-stu-id="3e1a3-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
