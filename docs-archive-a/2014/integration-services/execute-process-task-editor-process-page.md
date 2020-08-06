---
title: Éditeur de tâche d’exécution de processus (page traiter) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694663"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="7a85e-102">Execute Process Task Editor (Process Page)</span><span class="sxs-lookup"><span data-stu-id="7a85e-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="7a85e-103">Utilisez la page **Traiter** de la boîte de dialogue **Éditeur de tâche d'exécution de processus** pour configurer les options qui exécutent le processus.</span><span class="sxs-lookup"><span data-stu-id="7a85e-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="7a85e-104">Ces options comprennent l'exécutable à lancer, son emplacement, les arguments de l'invite de commandes et les variables qui fournissent l'entrée et la sortie de capture.</span><span class="sxs-lookup"><span data-stu-id="7a85e-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="7a85e-105">Pour en savoir plus sur cette tâche, consultez [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="7a85e-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a85e-106">Options</span><span class="sxs-lookup"><span data-stu-id="7a85e-106">Options</span></span>  
 <span data-ttu-id="7a85e-107">**RequireFullFileName**</span><span class="sxs-lookup"><span data-stu-id="7a85e-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="7a85e-108">Indiquez si la tâche doit échouer si l'exécutable est introuvable à l'emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="7a85e-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="7a85e-109">**Exécutable**</span><span class="sxs-lookup"><span data-stu-id="7a85e-109">**Executable**</span></span>  
 <span data-ttu-id="7a85e-110">Tapez le nom de l'exécutable à lancer.</span><span class="sxs-lookup"><span data-stu-id="7a85e-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="7a85e-111">**Arguments**</span><span class="sxs-lookup"><span data-stu-id="7a85e-111">**Arguments**</span></span>  
 <span data-ttu-id="7a85e-112">Fournissez les arguments de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="7a85e-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="7a85e-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="7a85e-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="7a85e-114">Tapez le chemin du dossier qui contient l’exécutable ou cliquez sur le bouton Parcourir **(...)** , puis recherchez le dossier.</span><span class="sxs-lookup"><span data-stu-id="7a85e-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="7a85e-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="7a85e-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="7a85e-116">Sélectionnez une variable pour fournir l’entrée au processus ou cliquez sur \<**New variable...**> pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="7a85e-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="7a85e-117">**Rubriques connexes :**  [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="7a85e-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="7a85e-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="7a85e-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="7a85e-119">Sélectionnez une variable pour capturer la sortie du processus ou cliquez sur \<**New variable...**> pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="7a85e-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="7a85e-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="7a85e-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="7a85e-121">Sélectionnez une variable pour capturer la sortie d’erreur du processus ou cliquez sur \<**New variable...**> pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="7a85e-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="7a85e-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="7a85e-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="7a85e-123">Indiquez si la tâche échoue quand le code de sortie du processus est différent de la valeur spécifiée dans **SuccessValue**.</span><span class="sxs-lookup"><span data-stu-id="7a85e-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="7a85e-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="7a85e-124">**SuccessValue**</span></span>  
 <span data-ttu-id="7a85e-125">Spécifiez la valeur retournée par l'exécutable pour indiquer le succès de l'opération.</span><span class="sxs-lookup"><span data-stu-id="7a85e-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="7a85e-126">Cette valeur est définie par défaut sur **0**.</span><span class="sxs-lookup"><span data-stu-id="7a85e-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="7a85e-127">**TimeOut**</span><span class="sxs-lookup"><span data-stu-id="7a85e-127">**TimeOut**</span></span>  
 <span data-ttu-id="7a85e-128">Spécifiez la durée en secondes de l'exécution du processus.</span><span class="sxs-lookup"><span data-stu-id="7a85e-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="7a85e-129">Une valeur **0** indique qu’aucun délai d’attente n’est utilisé et que l’exécution du processus dure tant que ce dernier n’est pas terminé ou tant qu’aucune erreur ne se produit.</span><span class="sxs-lookup"><span data-stu-id="7a85e-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="7a85e-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="7a85e-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="7a85e-131">Indiquez si le processus doit se terminer après le délai d’attente spécifié par l’option **TimeOut** .</span><span class="sxs-lookup"><span data-stu-id="7a85e-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="7a85e-132">Cette option est uniquement disponible si la valeur de l'option **TimeOut** n'est pas **0**.</span><span class="sxs-lookup"><span data-stu-id="7a85e-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="7a85e-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="7a85e-133">**WindowStyle**</span></span>  
 <span data-ttu-id="7a85e-134">Spécifiez le style de la fenêtre dans lequel le processus est exécuté.</span><span class="sxs-lookup"><span data-stu-id="7a85e-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a85e-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a85e-135">See Also</span></span>  
 <span data-ttu-id="7a85e-136">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7a85e-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="7a85e-137">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="7a85e-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
