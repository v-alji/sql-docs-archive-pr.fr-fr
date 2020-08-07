---
title: Codage et débogage du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611173"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="85c5d-102">Codage et débogage du composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="85c5d-103">Dans le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)], le composant Script propose deux modes : le mode Création des métadonnées et le mode Création du code.</span><span class="sxs-lookup"><span data-stu-id="85c5d-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="85c5d-104">Lorsque vous ouvrez l’**Éditeur de transformation de script**, le composant entre en mode Création des métadonnées, dans lequel vous configurez des métadonnées et définissez les propriétés du composant.</span><span class="sxs-lookup"><span data-stu-id="85c5d-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="85c5d-105">Après avoir défini les propriétés du composant Script et avoir configuré l'entrée et les sorties en mode Création des métadonnées, vous pouvez basculer vers le mode Création du code pour écrire votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="85c5d-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="85c5d-106">Pour plus d’informations sur le mode Création des métadonnées et le mode Création de code, consultez [Configuration du composant Script dans l’Éditeur de composant Script](configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="85c5d-107">Écriture du script en mode Création du code</span><span class="sxs-lookup"><span data-stu-id="85c5d-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="85c5d-108">Environnement de développement du composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-108">Script Component Development Environment</span></span>
 <span data-ttu-id="85c5d-109">Pour écrire votre script, cliquez sur **Modifier le script** dans la page **Script** de l’**Éditeur de transformation de script** afin d’ouvrir l’environnement de développement intégré [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="85c5d-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="85c5d-110">L'environnement de développement intégré VSTA contient l'ensemble des fonctionnalités standard de l'environnement [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET, telles que l'éditeur [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] à code de couleurs, IntelliSense et l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="85c5d-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="85c5d-111">Le code de script est écrit dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="85c5d-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="85c5d-112">Vous spécifiez le langage de script en définissant la propriété **ScriptLanguage** dans l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="85c5d-113">Si vous préférez utiliser un autre langage de programmation, vous pouvez développer un assembly personnalisé dans le langage de votre choix et appeler ses fonctionnalités à partir du code inclus dans le composant Script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="85c5d-114">Le script que vous créez dans le composant Script est stocké dans la définition du package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="85c5d-115">Aucun fichier de script distinct n'est créé.</span><span class="sxs-lookup"><span data-stu-id="85c5d-115">There is no separate script file.</span></span> <span data-ttu-id="85c5d-116">Par conséquent, l'utilisation du composant Script n'affecte pas le déploiement du package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="85c5d-117">Lorsque vous concevez le package, le code de script est écrit temporairement dans un fichier projet.</span><span class="sxs-lookup"><span data-stu-id="85c5d-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="85c5d-118">Étant donné que le stockage d'informations sensibles dans un fichier représente un risque potentiel en termes de sécurité, nous vous recommandons de ne pas inclure d'informations sensibles telles que des mots de passe dans le code de script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="85c5d-119">Par défaut, `Option Strict` est désactivé dans l'environnement de développement intégré.</span><span class="sxs-lookup"><span data-stu-id="85c5d-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="85c5d-120">Structure du projet de composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-120">Script Component Project Structure</span></span>
 <span data-ttu-id="85c5d-121">La force du composant Script réside dans sa capacité à générer un code d'infrastructure qui réduit la quantité de code à écrire.</span><span class="sxs-lookup"><span data-stu-id="85c5d-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="85c5d-122">Cette fonctionnalité repose sur le fait que les entrées et sorties et leurs colonnes et propriétés sont fixes et connues à l'avance.</span><span class="sxs-lookup"><span data-stu-id="85c5d-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="85c5d-123">Par conséquent, toutes les modifications ultérieures que vous apportez aux métadonnées du composant peuvent invalider le code que vous avez écrit.</span><span class="sxs-lookup"><span data-stu-id="85c5d-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="85c5d-124">Cela provoque des erreurs de compilation pendant l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="85c5d-125">Éléments et classe de projet dans le projet de composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="85c5d-126">Lorsque vous basculez en mode Création du code, l'environnement de développement intégré VSTA ouvre et affiche l'élément de projet `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="85c5d-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="85c5d-127">L'élément de projet `ScriptMain` contient la classe `ScriptMain` modifiable, qui sert de point d'entrée pour le script et qui se trouve là où vous écrivez votre code.</span><span class="sxs-lookup"><span data-stu-id="85c5d-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="85c5d-128">Les éléments de code inclus dans la classe varient selon le langage de programmation que vous avez sélectionné pour la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="85c5d-129">Le projet de script contient deux autres éléments de projet en lecture seule générés automatiquement :</span><span class="sxs-lookup"><span data-stu-id="85c5d-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="85c5d-130">L'élément de projet `ComponentWrapper` contient trois classes :</span><span class="sxs-lookup"><span data-stu-id="85c5d-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="85c5d-131">La classe `UserComponent`, qui hérite de l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> et qui contient les méthodes et propriétés que vous utiliserez pour traiter les données et interagir avec le package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="85c5d-132">La classe `ScriptMain` hérite de la classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="85c5d-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="85c5d-133">Une classe de collection `Connections` qui contient des références aux connexions sélectionnées dans la page Gestionnaire de connexions de l'Éditeur de transformation de script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="85c5d-134">`Variables`Classe de collection qui contient des références aux variables entrées dans les `ReadOnlyVariable` Propriétés et de `ReadWriteVariables` la page **script** de l **'éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="85c5d-135">L' `BufferWrapper` élément de projet contient une classe qui hérite de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> pour chaque entrée et sortie configurée dans la page **entrées et sorties** de l **'éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="85c5d-136">Chacune de ces classes contient des propriétés d'accesseur typées qui correspondent aux colonnes d'entrée et de sortie configurées, ainsi que des tampons de flux de données qui contiennent les colonnes.</span><span class="sxs-lookup"><span data-stu-id="85c5d-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="85c5d-137">Pour plus d’informations sur la manière d’utiliser ces objets, méthodes et propriétés, consultez [Présentation du modèle objet du composant Script](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="85c5d-138">Pour plus d’informations sur l’utilisation des méthodes et des propriétés de ces classes dans un type de composant Script particulier, consultez la section [Autres exemples de composants Script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="85c5d-139">Les rubriques d'exemples contiennent également des exemples de code complets.</span><span class="sxs-lookup"><span data-stu-id="85c5d-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="85c5d-140">Lorsque vous configurez le composant Script en tant que transformation, l'élément de projet `ScriptMain` contient le code généré automatiquement suivant.</span><span class="sxs-lookup"><span data-stu-id="85c5d-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="85c5d-141">Le modèle de code fournit également une vue d'ensemble du composant Script, ainsi que des informations supplémentaires sur la récupération et la manipulation des objets SSIS, tels que les variables, les événements et les connexions.</span><span class="sxs-lookup"><span data-stu-id="85c5d-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="85c5d-142">Autres éléments de projet dans le projet de composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="85c5d-143">Le projet de composant Script peut inclure d'autres éléments que l'élément `ScriptMain` par défaut.</span><span class="sxs-lookup"><span data-stu-id="85c5d-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="85c5d-144">Vous pouvez ajouter des classes, des modules, des fichiers de code et des dossiers au projet, et vous pouvez utiliser des dossiers pour organiser des groupes d'éléments.</span><span class="sxs-lookup"><span data-stu-id="85c5d-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="85c5d-145">Tous les éléments que vous ajoutez sont rendus persistants à l'intérieur du package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="85c5d-146">Références dans le projet de composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-146">References in the Script Component Project</span></span>
 <span data-ttu-id="85c5d-147">Vous pouvez ajouter des références aux assemblys managés en cliquant avec le bouton droit sur le projet de tâche de script dans l’**Explorateur de projets**, puis en cliquant sur **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="85c5d-148">Pour plus d’informations, consultez [Référencement d’autres assemblys dans les solutions de script](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="85c5d-149">Vous pouvez consulter des références de projet dans l’environnement de développement intégré VSTA dans l’**Affichage de classes** ou l’**Explorateur de projets**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="85c5d-150">Vous ouvrez l’une ou l’autre de ces fenêtres à partir du menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="85c5d-151">Vous pouvez ajouter une nouvelle référence à partir du menu **Projet**, de l’**Explorateur de projets** ou d’**Affichage de classes**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="85c5d-152">Interaction avec le package dans le composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="85c5d-153">Le script personnalisé que vous écrivez dans le composant Script peut accéder à des variables et gestionnaires de connexions afin de les utiliser, à partir du package conteneur, via des accesseurs fortement typés dans les classes de base générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="85c5d-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="85c5d-154">Toutefois, vous devez configurer à la fois les variables et les gestionnaires de connexions avant de passer en mode Création du code si vous souhaitez les rendre disponibles pour votre script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="85c5d-155">Vous pouvez également déclencher des événements et effectuer une journalisation à partir de votre code de composant Script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="85c5d-156">Les éléments de projet générés automatiquement dans le projet de composant Script fournissent les objets, méthodes et propriétés ci-après pour interagir avec le package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="85c5d-157">Fonctionnalité du package</span><span class="sxs-lookup"><span data-stu-id="85c5d-157">Package Feature</span></span>|<span data-ttu-id="85c5d-158">Méthode d'accès</span><span class="sxs-lookup"><span data-stu-id="85c5d-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="85c5d-159">Variables</span><span class="sxs-lookup"><span data-stu-id="85c5d-159">Variables</span></span>|<span data-ttu-id="85c5d-160">Utilisez les propriétés d'accesseur typées et nommées de la classe de collection `Variables` incluse dans l'élément de projet `ComponentWrapper`, exposées via la propriété `Variables` de la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="85c5d-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="85c5d-161">La méthode `PreExecute` ne peut accéder qu'à des variables en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="85c5d-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="85c5d-162">La méthode `PostExecute` peut accéder à des variables en lecture seule et en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="85c5d-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="85c5d-163">Connexions</span><span class="sxs-lookup"><span data-stu-id="85c5d-163">Connections</span></span>|<span data-ttu-id="85c5d-164">Utilisez les propriétés d'accesseur typées et nommées de la classe de collection `Connections` incluse dans l'élément de projet `ComponentWrapper`, exposées via la propriété `Connections` de la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="85c5d-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="85c5d-165">Événements</span><span class="sxs-lookup"><span data-stu-id="85c5d-165">Events</span></span>|<span data-ttu-id="85c5d-166">Déclenchez des événements à l’aide de la <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> propriété de la `ScriptMain` classe et des méthodes \*\*Fire \<X> \*\* de l' <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span><span class="sxs-lookup"><span data-stu-id="85c5d-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="85c5d-167">Journalisation</span><span class="sxs-lookup"><span data-stu-id="85c5d-167">Logging</span></span>|<span data-ttu-id="85c5d-168">Effectuez la journalisation à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> de la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="85c5d-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="85c5d-169">Débogage du composant Script</span><span class="sxs-lookup"><span data-stu-id="85c5d-169">Debugging the Script Component</span></span>
 <span data-ttu-id="85c5d-170">Pour déboguer le code dans votre composant Script, définissez au moins un point d'arrêt dans le code, puis fermez l'environnement de développement intégré VISTA pour exécuter le package dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85c5d-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="85c5d-171">Lorsque l'exécution du package entre le composant Script, l'environnement de développement intégré s'ouvre à nouveau et affiche votre code en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="85c5d-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="85c5d-172">Lorsque l'exécution atteint le point d'arrêt, vous pouvez examiner les valeurs des variables et exécuter pas à pas le code restant.</span><span class="sxs-lookup"><span data-stu-id="85c5d-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="85c5d-173">Vous ne pouvez pas déboguer un composant Script si vous l'exécutez dans le cadre d'un package enfant exécuté à partir d'une tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="85c5d-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="85c5d-174">Dans ce cas, les points d'arrêt définis dans le composant Script dans le package enfant sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="85c5d-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="85c5d-175">Vous pouvez déboguer normalement le package enfant en l'exécutant séparément.</span><span class="sxs-lookup"><span data-stu-id="85c5d-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="85c5d-176">Lorsque vous déboguez un package qui contient plusieurs composants de script, le débogueur n'en débogue qu'un seul.</span><span class="sxs-lookup"><span data-stu-id="85c5d-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="85c5d-177">Le système peut déboguer un autre composant script si le débogueur a terminé, comme dans le cas d'une boucle Foreach ou du conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="85c5d-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="85c5d-178">Vous pouvez également surveiller l'exécution du composant Script en utilisant les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="85c5d-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="85c5d-179">Interrompez l’exécution et affichez un message modal en utilisant la `MessageBox.Show` méthode de l’espace de noms **System. Windows. Forms** .</span><span class="sxs-lookup"><span data-stu-id="85c5d-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="85c5d-180">(Supprimez ce code une fois que vous avez terminé le processus de débogage.)</span><span class="sxs-lookup"><span data-stu-id="85c5d-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="85c5d-181">Déclenchez des événements pour les messages d'information, les avertissements et les erreurs.</span><span class="sxs-lookup"><span data-stu-id="85c5d-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="85c5d-182">Les méthodes FireInformation, FireWarning et FireError affichent la description des événements dans la fenêtre **Sortie** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85c5d-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="85c5d-183">Toutefois, les méthodes FireProgress, Console.Write et Console.WriteLine n’affichent aucune information dans la fenêtre **Sortie**.</span><span class="sxs-lookup"><span data-stu-id="85c5d-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="85c5d-184">Les messages de l’événement FireProgress apparaissent sous l’onglet **Progression** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85c5d-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="85c5d-185">Pour plus d’informations, consultez [Déclenchement d’événements dans le composant Script](../../data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="85c5d-186">Journalisez les événements ou les messages définis par l'utilisateur dans les modules fournisseurs d'informations activés.</span><span class="sxs-lookup"><span data-stu-id="85c5d-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="85c5d-187">Pour plus d’informations, consultez [Journalisation dans le composant Script](logging-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="85c5d-188">Si vous souhaitez simplement examiner la sortie d’un composant Script configuré en tant que source ou transformation, sans enregistrer les données dans une destination, vous pouvez arrêter le flux de données avec une [transformation Nombre de lignes](../../data-flow/transformations/row-count-transformation.md) et attacher une visionneuse de données à la sortie du composant Script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="85c5d-189">Pour plus d’informations sur les visionneuses de données, consultez [Débogage d’un flux de données](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="85c5d-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="85c5d-190">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="85c5d-190">In This Section</span></span>
 <span data-ttu-id="85c5d-191">Pour plus d'informations sur le codage du composant Script, consultez les rubriques suivantes de cette section.</span><span class="sxs-lookup"><span data-stu-id="85c5d-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="85c5d-192">[Fonctionnement du modèle d’objet de composant script](understanding-the-script-component-object-model.md) Explique comment utiliser les objets, les méthodes et les propriétés disponibles dans le composant script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="85c5d-193">[Référencement d’autres assemblys dans des solutions de script](../referencing-other-assemblies-in-scripting-solutions.md) Explique comment référencer des objets de la [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bibliothèque de classes dans le composant script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="85c5d-194">[Simulation d’une sortie d’erreur pour le composant script](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explique comment simuler une sortie d’erreur pour les lignes qui génèrent des erreurs lors du traitement par le composant script.</span><span class="sxs-lookup"><span data-stu-id="85c5d-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="85c5d-195">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="85c5d-195">External Resources</span></span>

-   <span data-ttu-id="85c5d-196">Entrée de blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="85c5d-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="85c5d-197">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="85c5d-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="85c5d-198">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="85c5d-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="85c5d-199">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="85c5d-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="85c5d-200">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="85c5d-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="85c5d-201">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85c5d-201">See Also</span></span>
 [<span data-ttu-id="85c5d-202">Configuration du composant Script dans l’éditeur de composant de script</span><span class="sxs-lookup"><span data-stu-id="85c5d-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


