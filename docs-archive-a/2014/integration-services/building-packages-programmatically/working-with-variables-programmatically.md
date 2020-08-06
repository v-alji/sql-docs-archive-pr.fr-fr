---
title: Utilisation de variables par programmation | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706696"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="d4e1b-102">Utilisation de variables par programmation</span><span class="sxs-lookup"><span data-stu-id="d4e1b-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="d4e1b-103">Les variables constituent un moyen de définir des valeurs et de contrôler des processus dans les packages, conteneurs, tâches et gestionnaires d'événements de manière dynamique.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="d4e1b-104">Les variables peuvent également être utilisées par les contraintes de précédence pour contrôler la direction du flux de données vers différentes tâches.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="d4e1b-105">Les variables ont diverses utilisations :</span><span class="sxs-lookup"><span data-stu-id="d4e1b-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="d4e1b-106">Mise à jour des propriétés d'un package au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="d4e1b-107">Remplissage de valeurs de paramètres pour des instructions Transact-SQL au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="d4e1b-108">Contrôle du flux d'une boucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="d4e1b-109">Pour plus d’informations, consultez [Ajouter une énumération à un flux de contrôle](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="d4e1b-110">Contrôle d'une contrainte de précédence par son utilisation dans une expression.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="d4e1b-111">Une contrainte de précédence peut inclure des variables dans la définition de contrainte.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="d4e1b-112">Pour plus d’informations, consultez [Ajouter des expressions aux contraintes de précédence](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="d4e1b-113">Contrôle de la répétition conditionnelle d'un conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="d4e1b-114">Pour plus d’informations, consultez [Ajouter une itération à un flux de contrôle](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="d4e1b-115">Création d’expressions qui incluent des valeurs de variables.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="d4e1b-116">Vous pouvez créer des variables personnalisées pour tous les types de conteneurs : packages, conteneurs de **boucles Foreach**, conteneurs de **boucles For**, conteneurs de **séquences**, TaskHosts et gestionnaires d’événements.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="d4e1b-117">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="d4e1b-118">Étendue</span><span class="sxs-lookup"><span data-stu-id="d4e1b-118">Scope</span></span>
 <span data-ttu-id="d4e1b-119">Chaque conteneur possède sa propre collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables>.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="d4e1b-120">Lorsqu'une nouvelle variable est créée, elle se trouve dans la portée de son conteneur parent.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="d4e1b-121">Le conteneur de packages se trouvant au sommet de la hiérarchie de conteneurs, les variables avec une portée de package fonctionnent comme les variables globales et sont visibles pour tous les conteneurs contenus dans le package.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="d4e1b-122">La collection de variables du conteneur est également accessible par les enfants du conteneur via la collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, en utilisant le nom de variable ou l'index de la variable dans la collection.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="d4e1b-123">Parce que la visibilité d'une variable s'étend du haut vers le bas, les variables déclarées au niveau du package sont visibles pour tous les conteneurs situés dans le package.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="d4e1b-124">Par conséquent, la collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables> sur un conteneur inclut toutes les variables qui appartiennent à son parent en plus de ses propres variables.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="d4e1b-125">Inversement, les variables contenues dans une tâche sont limitées en termes de portée et de visibilité et sont uniquement visibles pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="d4e1b-126">Si un package exécute d'autres packages, les variables définies dans la portée du package appelant sont disponibles pour le package appelé.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="d4e1b-127">La seule exception se produit lorsqu'une variable de même nom existe dans le package appelé.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="d4e1b-128">Lorsque cette collision se produit, la valeur de la variable dans le package appelé remplace celle du package appelant.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="d4e1b-129">Les variables définies dans la portée du package appelé ne sont jamais de nouveau disponibles pour le package appelant.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="d4e1b-130">L'exemple de code suivant crée une variable, `myCustomVar`, par programme, à la portée du package, puis parcourt toutes les variables visibles pour le package, en imprimant leur nom, leur type de données et leur valeur.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="d4e1b-131">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="d4e1b-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="d4e1b-132">Notez que toutes les variables délimitées à l’espace de noms **System** sont disponibles dans le package.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="d4e1b-133">Pour plus d’informations, consultez [Variables système](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="d4e1b-134">Espaces de noms</span><span class="sxs-lookup"><span data-stu-id="d4e1b-134">Namespaces</span></span>
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d4e1b-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) fournit deux espaces de noms par défaut dans lesquels résident les variables : **User** et **System**.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="d4e1b-136">Par défaut, toute variable personnalisée créée par le développeur est ajoutée à l’espace de noms **User**.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="d4e1b-137">Les variables système résident dans l’espace de noms **System**.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="d4e1b-138">Vous pouvez créer d’autres espaces de noms dans lesquels placer des variables personnalisées en plus de l’espace de noms **User** et modifier le nom de l’espace de noms **User**. En revanche, vous ne pouvez pas ajouter ou modifier des variables dans l’espace de noms **System**, ni assigner des variables système à un autre espace de noms.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="d4e1b-139">Les variables système qui sont disponibles diffèrent selon le type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="d4e1b-140">Pour obtenir la liste des variables système disponibles pour les packages, conteneurs, tâches et gestionnaires d’événements, consultez [Variables système](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="d4e1b-141">Valeur</span><span class="sxs-lookup"><span data-stu-id="d4e1b-141">Value</span></span>
 <span data-ttu-id="d4e1b-142">La valeur d'une variable personnalisée peut être un littéral ou une expression :</span><span class="sxs-lookup"><span data-stu-id="d4e1b-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="d4e1b-143">Si vous souhaitez que la variable contienne une valeur littérale, définissez la valeur de sa propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="d4e1b-144">Si vous souhaitez que la variable contienne une expression, afin de pouvoir utiliser les résultats de l'expression en tant que valeur, définissez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> de la variable sur `true` et fournissez une expression dans la propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="d4e1b-145">Au moment de l'exécution, l'expression est évaluée et son résultat est utilisé en tant que valeur de la variable.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="d4e1b-146">Par exemple, si la propriété de l'expression d'une variable est `"100 * 2""100 * 2"` , la variable est évaluée à une valeur de 200.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="d4e1b-147">Pour une variable, vous ne pouvez pas définir explicitement la valeur de sa propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="d4e1b-148">La valeur <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> est déduite de la valeur initiale assignée à la variable et ne peut pas être changée par la suite.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="d4e1b-149">Pour plus d’informations sur les types de données de variable, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="d4e1b-150">L'exemple de code suivant crée une variable, définit la propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> sur `true`, assigne l'expression `"100 * 2"` à la propriété de l'expression de la variable, puis calcule la valeur de la variable.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="d4e1b-151">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="d4e1b-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="d4e1b-152">L'expression doit être une expression valide qui utilise la syntaxe d'expression [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4e1b-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="d4e1b-153">Les littéraux sont autorisés dans les expressions variables, en plus des opérateurs et fonctions que la syntaxe d'expression fournit, mais les expressions ne peuvent pas référencer d'autres variables ou colonnes.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="d4e1b-154">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="d4e1b-155">Fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="d4e1b-155">Configuration Files</span></span>
 <span data-ttu-id="d4e1b-156">Si un fichier de configuration inclut une variable personnalisée, la variable peut être mise à jour au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="d4e1b-157">Cela signifie que lorsque le package s'exécute, la valeur de la variable qui se trouvait à l'origine dans le package est remplacée par une nouvelle valeur provenant du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="d4e1b-158">Cette technique de remplacement s'avère utile lorsqu'un package est déployé sur plusieurs serveurs qui requièrent des valeurs de variables différentes.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="d4e1b-159">Par exemple, une variable peut spécifier combien de fois un conteneur de **boucles Foreach** répète son flux de travail, répertorier les destinataires auxquels un gestionnaire d’événements envoie des e-mails lorsqu’une erreur est déclenchée ou changer le nombre d’erreurs pouvant se produire avant que le package n’échoue.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="d4e1b-160">Ces variables sont fournies de manière dynamique dans des fichiers de configuration pour chaque environnement.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="d4e1b-161">Par conséquent, seules les variables accessibles en lecture/écriture sont autorisées dans les fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="d4e1b-162">Pour plus d’informations, consultez [Créer des configurations de package](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d4e1b-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="d4e1b-163">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d4e1b-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d4e1b-164">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="d4e1b-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d4e1b-165">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="d4e1b-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d4e1b-166">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="d4e1b-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4e1b-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4e1b-167">See Also</span></span>
 <span data-ttu-id="d4e1b-168">[Integration Services &#40;les variables de&#41; SSIS](../integration-services-ssis-variables.md) [utilisent des variables dans des packages](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="d4e1b-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


