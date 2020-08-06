---
title: Fenêtre Variables | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611852"
---
# <a name="variables-window"></a><span data-ttu-id="bb1cb-102">Fenêtre Variables</span><span class="sxs-lookup"><span data-stu-id="bb1cb-102">Variables Window</span></span>
  <span data-ttu-id="bb1cb-103">La fenêtre **Variables** permet de créer et de modifier les variables définies par l’utilisateur et d’afficher les variables système.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="bb1cb-104">Par défaut, la fenêtre **Variables** se trouve sous la zone **Gestionnaires de connexions** du concepteur SSIS, dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb1cb-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="bb1cb-105">Si vous ne voyez pas la fenêtre **Variables**, cliquez sur **Variables** dans le menu **SSIS** pour l’afficher.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="bb1cb-106">Vous pouvez éventuellement afficher la fenêtre **Variables** en mappant la commande View.Variables avec une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="bb1cb-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb1cb-107">Les valeurs des propriétés `Name` et `Namespace` doivent commencer par une lettre, conformément à la convention Unicode Standard 2.0, ou par un trait de soulignement (_).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="bb1cb-108">Les caractères suivants peuvent être des lettres ou des chiffres, conformément à la convention Unicode standard 2.0, ou un trait de soulignement (\_).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb1cb-109">Options</span><span class="sxs-lookup"><span data-stu-id="bb1cb-109">Options</span></span>  
 <span data-ttu-id="bb1cb-110">**Ajouter une variable**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-110">**Add Variable**</span></span>  
 <span data-ttu-id="bb1cb-111">Ajoutez une variable définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="bb1cb-112">**Déplacer la variable**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-112">**Move Variable**</span></span>  
 <span data-ttu-id="bb1cb-113">Cliquez sur une variable dans la liste, puis cliquez sur **Déplacer la variable** pour modifier l’étendue de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="bb1cb-114">Dans la boîte de dialogue **Sélectionner une nouvelle étendue** , sélectionnez le package ou un conteneur, une tâche ou un gestionnaire d'événements dans le package pour modifier l'étendue de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="bb1cb-115">Pour plus d’informations sur la portée des variables, consultez [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="bb1cb-116">**Supprimer une variable**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-116">**Delete Variable**</span></span>  
 <span data-ttu-id="bb1cb-117">Sélectionnez une variable dans la liste, puis cliquez sur **Supprimer une variable**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="bb1cb-118">**Options de la grille**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-118">**Grid Options**</span></span>  
 <span data-ttu-id="bb1cb-119">Cliquez sur cette option pour ouvrir la boîte de dialogue **Options de grille variables** où vous pouvez modifier la sélection des colonnes et appliquer des filtres à la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="bb1cb-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="bb1cb-120">Pour plus d'informations, consultez [Options de grille variables](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="bb1cb-121">Affichez le nom de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-121">View the variable name.</span></span> <span data-ttu-id="bb1cb-122">Vous pouvez mettre à jour le nom des variables définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="bb1cb-123">**Portée**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-123">**Scope**</span></span>  
 <span data-ttu-id="bb1cb-124">Affichez l'étendue de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-124">View the scope of the variable.</span></span> <span data-ttu-id="bb1cb-125">Une variable a l'étendue du package entier ou celle d'un conteneur ou d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="bb1cb-126">L'étendue de la variable doit être suffisante pour qu'elle soit visible pour tout autre composant ou tâche qui doit lire ou définir ses valeurs.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="bb1cb-127">Vous pouvez modifier l'étendue en cliquant sur la variable puis en cliquant sur **Déplacer la variable** dans la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="bb1cb-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="bb1cb-128">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-128">**Data Type**</span></span>  
 <span data-ttu-id="bb1cb-129">Affichez le type de données de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-129">View the data type of the variable.</span></span> <span data-ttu-id="bb1cb-130">Vous pouvez sélectionner le type de données dans la liste des variables définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb1cb-131">Si vous affectez une expression à la variable, vous ne pouvez pas modifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="bb1cb-132">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-132">**Value**</span></span>  
 <span data-ttu-id="bb1cb-133">Affichez la valeur de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-133">View the variable value.</span></span> <span data-ttu-id="bb1cb-134">Vous pouvez mettre à jour la valeur des variables définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="bb1cb-135">Cette valeur peut être un littéral ou une expression. En outre, la valeur peut être une chaîne multiligne.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="bb1cb-136">Pour affecter une expression à la variable, cliquez sur le bouton d'ellipse qui est en regard de la colonne **Expression** dans la fenêtre **Variables** .</span><span class="sxs-lookup"><span data-stu-id="bb1cb-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="bb1cb-137">Affichez le nom de l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-137">View the namespace name.</span></span> <span data-ttu-id="bb1cb-138">Les variables définies par l’utilisateur sont initialement créées dans l’espace de noms **User** , mais vous pouvez modifier le nom de l’espace de noms dans le `Namespace` champ.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="bb1cb-139">Pour afficher cette colonne, cliquez sur **Options de la grille**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="bb1cb-140">**Déclencher l'événement lorsque la valeur de la variable change**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="bb1cb-141">Indiquez si l'événement `OnVariableValueChanged` est déclenché lors de la modification d'une valeur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="bb1cb-142">Vous pouvez mettre à jour la valeur des variables système définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="bb1cb-143">Par défaut, la fenêtre **Variables** ne répertorie pas cette colonne.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="bb1cb-144">Pour afficher cette colonne, cliquez sur **Options de la grille**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="bb1cb-145">**Description**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-145">**Description**</span></span>  
 <span data-ttu-id="bb1cb-146">Affichez la description de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-146">View the variable description.</span></span> <span data-ttu-id="bb1cb-147">Vous pouvez modifier la description des variables définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="bb1cb-148">Par défaut, la fenêtre **Variables** ne répertorie pas cette colonne.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="bb1cb-149">Pour afficher cette colonne, cliquez sur **Options de la grille**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="bb1cb-150">**Expression**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-150">**Expression**</span></span>  
 <span data-ttu-id="bb1cb-151">Affichez l'expression affectée à la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="bb1cb-152">Pour affecter une expression, cliquez sur le bouton d'ellipse.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="bb1cb-153">Si vous affectez une expression à une variable, un marqueur spécial sous la forme d'une icône s'affiche en regard de la variable.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="bb1cb-154">Ce marqueur d'icône spécial s'affiche également en regard des gestionnaires de connexions et des tâches contenant des expressions.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1cb-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb1cb-155">See Also</span></span>  
 <span data-ttu-id="bb1cb-156">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="bb1cb-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="bb1cb-157">[Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="bb1cb-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="bb1cb-158">[Integration Services &#40;des expressions de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="bb1cb-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="bb1cb-159">Générer de fichiers de vidage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="bb1cb-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
