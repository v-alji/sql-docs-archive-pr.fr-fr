---
title: Définir les propriétés d’une variable définie par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709736"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="5fb31-102">Définir les propriétés d’une variable définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5fb31-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="5fb31-103">Pour définir les propriétés d'une variable définie par l'utilisateur dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], vous pouvez utiliser l'une des fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="5fb31-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="5fb31-104">Fenêtre Variables.</span><span class="sxs-lookup"><span data-stu-id="5fb31-104">Variables window.</span></span>  
  
-   <span data-ttu-id="5fb31-105">Fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="5fb31-105">Properties window.</span></span> <span data-ttu-id="5fb31-106">La fenêtre **Propriétés** répertorie les propriétés pour la configuration des variables qui ne sont pas disponibles dans la fenêtre **Variables** : Description, EvaluateAsExpression, Expression, ReadOnly, ValueType et IncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="5fb31-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="5fb31-107">fournit également un ensemble de variables système dont les propriétés ne peuvent pas être mises à jour, à l’exception de la propriété RaiseChangedEvent.</span><span class="sxs-lookup"><span data-stu-id="5fb31-107">also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="5fb31-108">**Définition des expressions dans les variables**</span><span class="sxs-lookup"><span data-stu-id="5fb31-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="5fb31-109">Quand vous utilisez la fenêtre **Propriétés** pour définir des expressions sur une variable définie par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5fb31-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="5fb31-110">La valeur d’une variable peut être définie par la propriété Valeur ou la propriété Expression.</span><span class="sxs-lookup"><span data-stu-id="5fb31-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="5fb31-111">Par défaut, la propriété EvaluateAsExpression est définie sur `False` et la valeur de la variable est définie par la propriété Value.</span><span class="sxs-lookup"><span data-stu-id="5fb31-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="5fb31-112">Pour utiliser une expression pour définir la valeur, vous devez d’abord définir EvaluateAsExpression sur `True` , puis fournir une expression dans la propriété expression.</span><span class="sxs-lookup"><span data-stu-id="5fb31-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="5fb31-113">Le résultat de l’évaluation de l’expression est automatiquement affecté à la propriété Valeur.</span><span class="sxs-lookup"><span data-stu-id="5fb31-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="5fb31-114">La propriété ValueType contient le type de données de la valeur de la propriété Valeur.</span><span class="sxs-lookup"><span data-stu-id="5fb31-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="5fb31-115">Quand Valeur est définie par une expression, ValueType est automatiquement mis à jour avec un type de données compatible avec le résultat de l’évaluation de l’expression.</span><span class="sxs-lookup"><span data-stu-id="5fb31-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="5fb31-116">Par exemple, si la valeur contient 0 et que la propriété ValueType contient **Int32** et que vous affectez ensuite à expression la valeur GETDATE (), value contient la date et l’heure actuelles et ValueType a la valeur `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="5fb31-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="5fb31-117">La fenêtre **Propriétés** pour la variable permet d’accéder à la boîte de dialogue **Générateur d’expressions** .</span><span class="sxs-lookup"><span data-stu-id="5fb31-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="5fb31-118">Vous pouvez utiliser cet outil pour créer, valider et évaluer des expressions.</span><span class="sxs-lookup"><span data-stu-id="5fb31-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="5fb31-119">Pour plus d’informations, consultez [Générateur d’expressions](expressions/expression-builder.md) et [Expressions Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5fb31-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="5fb31-120">Quand vous utilisez la fenêtre **Variables** pour définir des expressions sur une variable définie par l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5fb31-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="5fb31-121">Pour utiliser une expression pour définir la valeur de la variable, vérifiez d’abord que le type de données de la variable est compatible avec le résultat de l’évaluation de l’expression, puis fournissez une expression dans la `Expression` colonne de la fenêtre **variables** .</span><span class="sxs-lookup"><span data-stu-id="5fb31-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="5fb31-122">La propriété EvaluateAsExpression dans la fenêtre **Propriétés** est automatiquement définie sur `True` .</span><span class="sxs-lookup"><span data-stu-id="5fb31-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="5fb31-123">Lorsque vous affectez une expression à une variable, un marqueur spécial sous la forme d'une icône s'affiche en regard de la variable.</span><span class="sxs-lookup"><span data-stu-id="5fb31-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="5fb31-124">Ce marqueur d'icône spécial s'affiche également en regard des gestionnaires de connexions et des tâches contenant des expressions.</span><span class="sxs-lookup"><span data-stu-id="5fb31-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="5fb31-125">La fenêtre **Variables** pour la variable permet d’accéder à la boîte de dialogue **Générateur d’expressions** .</span><span class="sxs-lookup"><span data-stu-id="5fb31-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="5fb31-126">Vous pouvez utiliser cet outil pour créer, valider et évaluer des expressions.</span><span class="sxs-lookup"><span data-stu-id="5fb31-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="5fb31-127">Pour plus d’informations, consultez [Générateur d’expressions](expressions/expression-builder.md) et [Expressions Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5fb31-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="5fb31-128">Dans la fenêtre **variables** et **Propriétés** , si vous affectez une expression à la variable et `EvaluateAsExpression` que a la valeur `True` , vous ne pouvez pas modifier le type de données de la variable.</span><span class="sxs-lookup"><span data-stu-id="5fb31-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="5fb31-129">**Définition de l'espace de noms et des propriétés de nom**</span><span class="sxs-lookup"><span data-stu-id="5fb31-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="5fb31-130">Les valeurs des propriétés `Name` et `Namespace` doivent commencer par une lettre, conformément à la convention Unicode Standard 2.0, ou par un trait de soulignement (_).</span><span class="sxs-lookup"><span data-stu-id="5fb31-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="5fb31-131">Les caractères suivants peuvent être des lettres ou des chiffres, conformément à la convention Unicode standard 2.0, ou un trait de soulignement (\_).</span><span class="sxs-lookup"><span data-stu-id="5fb31-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="5fb31-132">Définition de propriétés à l'aide de la fenêtre Variables</span><span class="sxs-lookup"><span data-stu-id="5fb31-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="5fb31-133">Pour définir les propriétés d'une variable à l'aide de la fenêtre Variables</span><span class="sxs-lookup"><span data-stu-id="5fb31-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="5fb31-134">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="5fb31-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5fb31-135">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5fb31-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="5fb31-136">Dans le menu **SSIS** , cliquez sur **Variables**.</span><span class="sxs-lookup"><span data-stu-id="5fb31-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="5fb31-137">Vous pouvez éventuellement afficher la fenêtre **Variables** en mappant la commande View.Variables avec une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="5fb31-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="5fb31-138">Éventuellement, dans la fenêtre **Variables** cliquez sur **Options de la grille**, puis sélectionnez les colonnes qui apparaissent dans la fenêtre **Variables** et sélectionnez les filtres à appliquer à la liste des variables.</span><span class="sxs-lookup"><span data-stu-id="5fb31-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="5fb31-139">Sélectionnez la variable dans la liste, puis mettez à jour les valeurs dans les `Name` colonnes, **type de données**,,, `Value` déclencher la `Namespace` **modification**, **Description** et `Expression` colonnes.</span><span class="sxs-lookup"><span data-stu-id="5fb31-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="5fb31-140">Sélectionnez la variable dans la liste, puis cliquez sur **Déplacer la variable** pour modifier l’étendue.</span><span class="sxs-lookup"><span data-stu-id="5fb31-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="5fb31-141">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="5fb31-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="5fb31-142">Définition de propriétés à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="5fb31-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="5fb31-143">Pour définir les propriétés d'une variable à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="5fb31-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="5fb31-144">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="5fb31-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5fb31-145">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5fb31-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="5fb31-146">Dans le menu **Affichage** , cliquez sur **Fenêtre Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5fb31-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="5fb31-147">Dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Explorateur de package** , puis développez le nœud Package.</span><span class="sxs-lookup"><span data-stu-id="5fb31-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="5fb31-148">Pour modifier les variables avec une portée de package, développez le nœud Variables. Sinon, développez les nœuds Gestionnaires d'événements ou Exécutables jusqu'à ce que vous trouviez le nœud Variables contenant la variable que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="5fb31-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="5fb31-149">Cliquez sur la variable dont vous souhaitez modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5fb31-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="5fb31-150">Dans la fenêtre **Propriétés** , mettez à jour les propriétés en lecture/écriture de la variable.</span><span class="sxs-lookup"><span data-stu-id="5fb31-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="5fb31-151">Certaines propriétés sont en lecture/lecture uniquement pour les variables définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5fb31-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="5fb31-152">Pour plus d’informations sur les propriétés, consultez [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="5fb31-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="5fb31-153">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="5fb31-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb31-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fb31-154">See Also</span></span>  
 <span data-ttu-id="5fb31-155">[Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="5fb31-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="5fb31-156">[Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="5fb31-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="5fb31-157">Ajouter, supprimer, modifier l'étendue de la variable définie par l'utilisateur dans un package</span><span class="sxs-lookup"><span data-stu-id="5fb31-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
