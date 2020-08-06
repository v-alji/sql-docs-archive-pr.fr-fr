---
title: Utiliser les valeurs des variables et des paramètres dans un package enfant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611858"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="e131a-102">Utiliser les valeurs des variables et des paramètres dans un package enfant</span><span class="sxs-lookup"><span data-stu-id="e131a-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="e131a-103">Cette procédure explique comment créer une configuration de package qui utilise le type de configuration de variable parent.</span><span class="sxs-lookup"><span data-stu-id="e131a-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="e131a-104">Ce type de configuration active un package enfant exécuté à partir d'un package parent pour accéder à une variable dans le parent.</span><span class="sxs-lookup"><span data-stu-id="e131a-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e131a-105">Vous pouvez également passer les valeurs à un package enfant en configurant la tâche d'exécution afin de mapper les variables ou paramètres du package parent, ou les paramètres du projet, aux paramètres du package enfant.</span><span class="sxs-lookup"><span data-stu-id="e131a-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="e131a-106">Pour plus d’informations, consultez [Tâche d’exécution de package](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="e131a-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="e131a-107">Il n'est pas nécessaire de créer la variable dans le package parent avant de créer la configuration de package dans le package enfant.</span><span class="sxs-lookup"><span data-stu-id="e131a-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="e131a-108">Vous pouvez ajouter la variable au package parent à tout moment, mais vous devez utiliser le nom exact de la variable parent dans la configuration du package.</span><span class="sxs-lookup"><span data-stu-id="e131a-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="e131a-109">Cependant, avant que vous puissiez créer une configuration de variable parent, la configuration doit pouvoir mettre à jour une variable existante dans le package enfant.</span><span class="sxs-lookup"><span data-stu-id="e131a-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="e131a-110">Pour plus d’informations sur l’ajout et la configuration de variables, consultez [Ajouter, supprimer, modifier l’étendue de la variable définie par l’utilisateur dans un package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="e131a-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="e131a-111">La portée de la variable dans le package parent utilisé dans une configuration de variable parent peut être définie à la tâche d'exécution de package, au conteneur qui détient la tâche ou au package.</span><span class="sxs-lookup"><span data-stu-id="e131a-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="e131a-112">Si plusieurs variables portant le même nom sont définies dans un package, la variable la plus proche en portée de la tâche d'exécution de package est employée.</span><span class="sxs-lookup"><span data-stu-id="e131a-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="e131a-113">La portée la plus proche de la tâche d'exécution de package est la tâche proprement dite.</span><span class="sxs-lookup"><span data-stu-id="e131a-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="e131a-114">Pour ajouter une variable à un package parent</span><span class="sxs-lookup"><span data-stu-id="e131a-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="e131a-115">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package auquel vous voulez ajouter une variable à transmettre à un package enfant.</span><span class="sxs-lookup"><span data-stu-id="e131a-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="e131a-116">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="e131a-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e131a-117">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , pour définir la portée de la variable, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e131a-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="e131a-118">Pour définir la portée du package, cliquez n’importe où sur l’aire de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="e131a-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="e131a-119">Pour définir la portée à un conteneur parent de la tâche d'exécution de package, cliquez sur le conteneur.</span><span class="sxs-lookup"><span data-stu-id="e131a-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="e131a-120">Pour définir la portée de la tâche d'exécution de package, cliquez sur la tâche.</span><span class="sxs-lookup"><span data-stu-id="e131a-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="e131a-121">Ajoutez et configurez une variable.</span><span class="sxs-lookup"><span data-stu-id="e131a-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e131a-122">Sélectionnez un type de données compatible avec les données que la variable stockera.</span><span class="sxs-lookup"><span data-stu-id="e131a-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="e131a-123">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="e131a-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="e131a-124">Pour ajouter une variable à un package enfant</span><span class="sxs-lookup"><span data-stu-id="e131a-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="e131a-125">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package auquel vous souhaitez ajouter une configuration de variable parent.</span><span class="sxs-lookup"><span data-stu-id="e131a-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="e131a-126">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="e131a-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e131a-127">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , pour définir la portée au package, cliquez n’importe où sur la zone de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="e131a-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="e131a-128">Ajoutez et configurez une variable.</span><span class="sxs-lookup"><span data-stu-id="e131a-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e131a-129">Sélectionnez un type de données compatible avec les données que la variable stockera.</span><span class="sxs-lookup"><span data-stu-id="e131a-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="e131a-130">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="e131a-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="e131a-131">Pour ajouter une configuration de package parent à un package enfant</span><span class="sxs-lookup"><span data-stu-id="e131a-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="e131a-132">S’il n’est pas déjà ouvert, ouvrez le package enfant dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e131a-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e131a-133">Cliquez dans la zone de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="e131a-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="e131a-134">Dans le menu **SSIS** , cliquez sur **Configurations du package**.</span><span class="sxs-lookup"><span data-stu-id="e131a-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="e131a-135">Dans la boîte de dialogue **Bibliothèque des configurations du package** , sélectionnez **Activer les configurations du package**et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e131a-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="e131a-136">Dans la page Assistant Configuration de package, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e131a-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="e131a-137">Dans la page Sélectionner le type de configuration, dans la liste **Type de configuration** , sélectionnez **Variable de package parent** et effectuez l’une des interventions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e131a-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="e131a-138">Sélectionnez **Spécifier directement les paramètres de configuration**, et dans la zone **Variable parent** , fournissez le nom de la variable dans le package parent à utiliser dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="e131a-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="e131a-139">Les noms des variables tiennent compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="e131a-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="e131a-140">Sélectionnez **L’emplacement de la configuration est stocké dans une variable d’environnement** , puis dans la **liste Variable d’environnement**, sélectionnez la variable d’environnement qui contient le nom de la variable.</span><span class="sxs-lookup"><span data-stu-id="e131a-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="e131a-141">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e131a-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="e131a-142">Dans la page Sélectionner la propriété cible, développez le nœud **Variable** , puis développez le nœud **Propriétés** de la variable à configurer, puis cliquez sur la propriété devant être définie par la configuration.</span><span class="sxs-lookup"><span data-stu-id="e131a-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="e131a-143">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e131a-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="e131a-144">Dans la page Fin de l'Assistant, modifiez facultativement le nom par défaut de la configuration, puis vérifiez les informations de configuration.</span><span class="sxs-lookup"><span data-stu-id="e131a-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="e131a-145">Cliquez sur **Terminer** pour mettre fin à l’Assistant et revenir à la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="e131a-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="e131a-146">Dans la boîte de dialogue **Bibliothèque des configurations du package** , la zone **Configuration** présente la nouvelle configuration.</span><span class="sxs-lookup"><span data-stu-id="e131a-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="e131a-147">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e131a-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e131a-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e131a-148">See Also</span></span>  
 <span data-ttu-id="e131a-149">[Configurations du package](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="e131a-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="e131a-150">[Créer des configurations de package](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="e131a-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="e131a-151">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e131a-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="e131a-152">Utiliser des variables dans des packages</span><span class="sxs-lookup"><span data-stu-id="e131a-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
