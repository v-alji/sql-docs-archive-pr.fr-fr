---
title: Éditeur de tâche de script (page script) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695835"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="8055a-102">Éditeur de tâche de script (page Script)</span><span class="sxs-lookup"><span data-stu-id="8055a-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="8055a-103">Utilisez la page **Script** de la boîte de dialogue **Éditeur de tâche de script** pour définir les propriétés du script et vérifier les variables auxquelles le script peut accéder.</span><span class="sxs-lookup"><span data-stu-id="8055a-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8055a-104">Dans [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] et les versions ultérieures, tous les scripts sont précompilés.</span><span class="sxs-lookup"><span data-stu-id="8055a-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="8055a-105">Dans les versions antérieures, vous définissez une propriété **PrecompileScriptIntoBinaryCode** pour spécifier que le script a été précompilé.</span><span class="sxs-lookup"><span data-stu-id="8055a-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="8055a-106">Pour en savoir plus sur la tâche de script, consultez [Script Task](control-flow/script-task.md) et [Configuration de la tâche de script dans l'éditeur de tâche de script](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8055a-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="8055a-107">Pour en savoir plus sur la programmation de la tâche de script, consultez [Extension du package à l'aide de la tâche de script](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="8055a-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8055a-108">Options</span><span class="sxs-lookup"><span data-stu-id="8055a-108">Options</span></span>  
 <span data-ttu-id="8055a-109">**ScriptLanguage**</span><span class="sxs-lookup"><span data-stu-id="8055a-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="8055a-110">Sélectionnez le langage de script pour la tâche, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic ou [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8055a-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="8055a-111">Après avoir créé un script pour la tâche, vous ne pouvez pas modifier la valeur de la propriété **ScriptLanguage** .</span><span class="sxs-lookup"><span data-stu-id="8055a-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="8055a-112">Pour définir le langage de script par défaut pour la tâche de script, utilisez l'option **Langage de script** dans la page **Général** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="8055a-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="8055a-113">Pour plus d'informations, consultez [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="8055a-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="8055a-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="8055a-114">**EntryPoint**</span></span>  
 <span data-ttu-id="8055a-115">Spécifiez la méthode que le runtime [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] appelle comme point d’entrée dans le code de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="8055a-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="8055a-116">La méthode spécifiée doit se trouver dans la classe ScriptMain du [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projet Tools for Applications (VSTA) la classe ScriptMain est la classe par défaut générée par les modèles de script.</span><span class="sxs-lookup"><span data-stu-id="8055a-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="8055a-117">Si vous modifiez le nom de la méthode dans le projet VSTA, vous devez modifier la valeur de la propriété **EntryPoint** .</span><span class="sxs-lookup"><span data-stu-id="8055a-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="8055a-118">**ReadOnlyVariables**</span><span class="sxs-lookup"><span data-stu-id="8055a-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="8055a-119">Tapez une liste séparée par des virgules des variables en lecture seule accessibles au script ou cliquez sur le bouton de sélection (**...**) et sélectionnez les variables dans la boîte de dialogue **Sélectionner des variables** .</span><span class="sxs-lookup"><span data-stu-id="8055a-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8055a-120">Les noms des variables tiennent compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="8055a-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="8055a-121">**ReadWriteVariables**</span><span class="sxs-lookup"><span data-stu-id="8055a-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="8055a-122">Tapez une liste séparée par des virgules des variables en lecture/écriture accessibles au script ou cliquez sur le bouton de sélection (**...**) et sélectionnez les variables dans la boîte de dialogue **Sélectionner des variables** .</span><span class="sxs-lookup"><span data-stu-id="8055a-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8055a-123">Les noms des variables tiennent compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="8055a-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="8055a-124">**Modifier le script**</span><span class="sxs-lookup"><span data-stu-id="8055a-124">**Edit Script**</span></span>  
 <span data-ttu-id="8055a-125">Ouvre l'environnement de développement intégré VSTA dans lequel vous pouvez créer ou modifier le script.</span><span class="sxs-lookup"><span data-stu-id="8055a-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8055a-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8055a-126">See Also</span></span>  
 <span data-ttu-id="8055a-127">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8055a-128">[Page général](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8055a-129">[Éditeur de tâche de script &#40;page général&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="8055a-130">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="8055a-131">[Exemples de tâche de script](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="8055a-132">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8055a-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="8055a-133">Ajouter, supprimer, modifier l'étendue de la variable définie par l'utilisateur dans un package</span><span class="sxs-lookup"><span data-stu-id="8055a-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
