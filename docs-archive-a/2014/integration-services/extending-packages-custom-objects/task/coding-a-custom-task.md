---
title: Codage d’une tâche personnalisée | Microsoft Docs
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
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611179"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="5837b-102">Codage d'une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="5837b-102">Coding a Custom Task</span></span>
  <span data-ttu-id="5837b-103">Après avoir créé une classe qui hérite de la classe de base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), puis appliqué l’attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> à cette classe, vous devez substituer l’implémentation des propriétés et des méthodes de la classe de base afin de fournir vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="5837b-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="5837b-104">Configuration de la tâche</span><span class="sxs-lookup"><span data-stu-id="5837b-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="5837b-105">Validation de la tâche</span><span class="sxs-lookup"><span data-stu-id="5837b-105">Validating the Task</span></span>
 <span data-ttu-id="5837b-106">Lorsque vous concevez un package [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vous pouvez utiliser la validation pour vérifier des paramètres sur chaque tâche, afin d'intercepter les paramètres incorrects ou inappropriés dès qu'ils sont définis, au lieu de détecter toutes les erreurs uniquement au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="5837b-107">L'objectif de la validation est de déterminer si la tâche contient des paramètres ou connexions non valides qui l'empêcheront de s'exécuter avec succès.</span><span class="sxs-lookup"><span data-stu-id="5837b-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="5837b-108">Elle permet de veiller à ce que le package contienne des tâches qui ont de bonnes chances de s'exécuter dès leur premier essai.</span><span class="sxs-lookup"><span data-stu-id="5837b-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="5837b-109">Vous pouvez implémenter la validation à l'aide de la méthode `Validate` dans du code personnalisé.</span><span class="sxs-lookup"><span data-stu-id="5837b-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="5837b-110">Le moteur d'exécution valide une tâche en appelant la méthode `Validate` sur cette tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="5837b-111">Il incombe au développeur de la tâche de définir les critères d'une validation de tâche réussie ou non réussie, et de notifier le moteur d'exécution du résultat de cette évaluation.</span><span class="sxs-lookup"><span data-stu-id="5837b-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="5837b-112">Classe de base abstraite d'une tâche</span><span class="sxs-lookup"><span data-stu-id="5837b-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="5837b-113">La classe de base abstraite [Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) fournit la `Validate` méthode que chaque tâche remplace pour définir ses critères de validation.</span><span class="sxs-lookup"><span data-stu-id="5837b-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="5837b-114">Le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] appelle automatiquement la méthode `Validate` à plusieurs reprises lors de la conception du package, puis fournit des signaux visuels à l'utilisateur lorsque des avertissements ou erreurs se produisent afin de permettre d'identifier des problèmes liés à la configuration de la tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="5837b-115">Les tâches fournissent les résultats de la validation en renvoyant une valeur de l'énumération <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, puis en déclenchant des événements d'avertissement et d'erreur.</span><span class="sxs-lookup"><span data-stu-id="5837b-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="5837b-116">Ces événements contiennent des informations qui s'affichent pour l'utilisateur dans le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5837b-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="5837b-117">Voici quelques exemples pour la validation :</span><span class="sxs-lookup"><span data-stu-id="5837b-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="5837b-118">Un gestionnaire de connexions valide le nom de fichier spécifique.</span><span class="sxs-lookup"><span data-stu-id="5837b-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="5837b-119">Un gestionnaire de connexions confirme que le type d'entrée correspond au type attendu, tel qu'un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="5837b-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="5837b-120">Une tâche qui attend une entrée de base de données vérifie qu'elle ne reçoit pas de données provenant d'une connexion autre qu'une connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="5837b-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="5837b-121">Une tâche garantit qu'aucune de ses propriétés ne contredit l'autre jeu de propriétés sur la même tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="5837b-122">Une tâche garantit que toutes les ressources requises utilisées par la tâche au moment de l'exécution sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="5837b-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="5837b-123">Les performances sont un élément à prendre en compte pour déterminer ce qui est validé et ce qui ne l'est pas.</span><span class="sxs-lookup"><span data-stu-id="5837b-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="5837b-124">Par exemple, l'entrée d'une tâche peut être une connexion sur un réseau dont la bande passante est faible ou le trafic encombré.</span><span class="sxs-lookup"><span data-stu-id="5837b-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="5837b-125">La validation risque de nécessiter plusieurs secondes de traitement si vous décidez de valider la disponibilité de la ressource.</span><span class="sxs-lookup"><span data-stu-id="5837b-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="5837b-126">Une autre validation peut provoquer un aller-retour vers un serveur très demandé et la routine de validation peut être lente.</span><span class="sxs-lookup"><span data-stu-id="5837b-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="5837b-127">Bien qu'il existe de nombreuses propriétés et paramètres pouvant être validés, tout ne doit pas être validé.</span><span class="sxs-lookup"><span data-stu-id="5837b-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="5837b-128">Le code inclus dans la méthode `Validate` est également appelé par l'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> avant que la tâche soit exécutée, et l'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> annule l'exécution si la validation échoue.</span><span class="sxs-lookup"><span data-stu-id="5837b-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="5837b-129">Considérations liées à l'interface utilisateur pendant la validation</span><span class="sxs-lookup"><span data-stu-id="5837b-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="5837b-130">[Microsoft. SqlServer. Dts. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) comprend une <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface en tant que paramètre de la `Validate` méthode.</span><span class="sxs-lookup"><span data-stu-id="5837b-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="5837b-131">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contient les méthodes appelées par la tâche afin de déclencher des événements pour le moteur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="5837b-132">Les méthodes <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> sont appelées lorsqu'un avertissement ou une condition d'erreur se produisent pendant la validation.</span><span class="sxs-lookup"><span data-stu-id="5837b-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="5837b-133">Ces deux méthodes d'avertissement requièrent les mêmes paramètres, qui incluent un code d'erreur, un composant source, une description, un fichier d'aide et des informations d'aide contextuelles.</span><span class="sxs-lookup"><span data-stu-id="5837b-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="5837b-134">Le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilise ces informations pour afficher des signaux visuels sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="5837b-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="5837b-135">Les signaux visuels fournis par le concepteur incluent une icône d'exclamation qui apparaît en regard de la tâche sur l'aire du concepteur.</span><span class="sxs-lookup"><span data-stu-id="5837b-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="5837b-136">Ce signal visuel indique à l'utilisateur que la tâche requiert une configuration supplémentaire pour que l'exécution puisse continuer.</span><span class="sxs-lookup"><span data-stu-id="5837b-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="5837b-137">L'icône d'exclamation affiche également une info-bulle qui contient un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="5837b-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="5837b-138">Le message d'erreur est fourni par la tâche dans le paramètre de description de l'événement.</span><span class="sxs-lookup"><span data-stu-id="5837b-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="5837b-139">Les messages d’erreur sont également affichés dans le volet **Liste des tâches** de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], lequel fournit à l’utilisateur un emplacement central pour consulter toutes les erreurs de validation.</span><span class="sxs-lookup"><span data-stu-id="5837b-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="5837b-140">Exemple de validation</span><span class="sxs-lookup"><span data-stu-id="5837b-140">Validation Example</span></span>
 <span data-ttu-id="5837b-141">L'exemple de code suivant présente une tâche avec une propriété `UserName`.</span><span class="sxs-lookup"><span data-stu-id="5837b-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="5837b-142">Cette propriété a été spécifiée comme requis pour que la validation réussisse.</span><span class="sxs-lookup"><span data-stu-id="5837b-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="5837b-143">Si la propriété n'est pas définie, la tâche publie une erreur et retourne l'objet <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> de l'énumération <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="5837b-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="5837b-144">La méthode `Validate` est encapsulée dans un bloc try/catch et fait échouer la validation si une exception se produit.</span><span class="sxs-lookup"><span data-stu-id="5837b-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="5837b-145">Persistance de la tâche</span><span class="sxs-lookup"><span data-stu-id="5837b-145">Persisting the Task</span></span>
 <span data-ttu-id="5837b-146">En règle générale, vous n'avez pas à implémenter une persistance personnalisée pour une tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="5837b-147">Une persistance personnalisée est uniquement requise lorsque les propriétés d'un objet utilisent des types de données complexes.</span><span class="sxs-lookup"><span data-stu-id="5837b-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="5837b-148">Pour plus d’informations, consultez [Développement d’objets personnalisés pour Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="5837b-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="5837b-149">Exécution de la tâche</span><span class="sxs-lookup"><span data-stu-id="5837b-149">Executing the Task</span></span>
 <span data-ttu-id="5837b-150">Cette section décrit comment utiliser la méthode `Execute` qui est héritée et remplacée par des tâches.</span><span class="sxs-lookup"><span data-stu-id="5837b-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="5837b-151">Elle explique également les différentes façons de fournir des informations concernant les résultats de l'exécution des tâches.</span><span class="sxs-lookup"><span data-stu-id="5837b-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="5837b-152">Méthode Execute</span><span class="sxs-lookup"><span data-stu-id="5837b-152">Execute Method</span></span>
 <span data-ttu-id="5837b-153">Tâches contenues dans l'exécution d'un package lorsque le runtime [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] appelle leur méthode `Execute`.</span><span class="sxs-lookup"><span data-stu-id="5837b-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="5837b-154">Les tâches implémentent leur logique métier principale et leurs fonctionnalités dans cette méthode, et fournissent les résultats de l’exécution en publiant des messages, en retournant une valeur de l' <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> énumération et en substituant la propriété `get` de la `ExecutionValue` propriété.</span><span class="sxs-lookup"><span data-stu-id="5837b-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="5837b-155">La classe de base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) fournit une implémentation par défaut de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="5837b-156">Les tâches personnalisées substituent cette méthode pour définir leurs fonctionnalités d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="5837b-157">L'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> encapsule la tâche, en l'isolant du moteur d'exécution et des autres objets compris dans le package.</span><span class="sxs-lookup"><span data-stu-id="5837b-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="5837b-158">En raison de cette isolation, la tâche n'a pas connaissance de son emplacement dans le package pour ce qui est de son ordre d'exécution et elle s'exécute uniquement lorsqu'elle est appelée par le runtime.</span><span class="sxs-lookup"><span data-stu-id="5837b-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="5837b-159">Cette architecture empêche certains problèmes qui peuvent se produire lorsque les tâches modifient le package pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="5837b-160">La tâche peut accéder aux autres objets compris dans le package uniquement via les objets qui lui sont fournis comme paramètres dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="5837b-161">Ces paramètres permettent aux tâches de déclencher des événements, d'écrire des entrées dans le journal des événements, d'accéder à la collection de variables et d'inscrire des connexions aux sources de données dans les transactions, tout en maintenant quand même l'isolation nécessaire pour garantir la stabilité et la fiabilité du package.</span><span class="sxs-lookup"><span data-stu-id="5837b-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="5837b-162">Le tableau suivant répertorie les paramètres fournis à la tâche dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="5837b-163">Paramètre</span><span class="sxs-lookup"><span data-stu-id="5837b-163">Parameter</span></span>|<span data-ttu-id="5837b-164">Description</span><span class="sxs-lookup"><span data-stu-id="5837b-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="5837b-165">Contient une collection d'objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> disponibles pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="5837b-166">Contient les variables disponibles pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-166">Contains the variables available to the task.</span></span> <span data-ttu-id="5837b-167">Les tâches utilisent des variables via VariableDispenser ; les tâches n'utilisent pas des variables directement.</span><span class="sxs-lookup"><span data-stu-id="5837b-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="5837b-168">Le distributeur de variables verrouille et déverrouille les variables, et empêche les blocages ou les remplacements.</span><span class="sxs-lookup"><span data-stu-id="5837b-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="5837b-169">Contient les méthodes appelées par la tâche pour déclencher des événements pour le moteur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="5837b-170">Contient les méthodes et propriétés utilisées par la tâche pour écrire des entrées dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="5837b-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="5837b-171">Object</span><span class="sxs-lookup"><span data-stu-id="5837b-171">Object</span></span>|<span data-ttu-id="5837b-172">Contient l'objet de transaction dont le conteneur fait partie, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="5837b-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="5837b-173">Cette valeur est transmise en tant que paramètre à la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> d'un objet <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="5837b-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="5837b-174">Envoi de commentaires d'exécution</span><span class="sxs-lookup"><span data-stu-id="5837b-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="5837b-175">Les tâches encapsulent leur code dans des blocs `try/catch` pour empêcher le déclenchement d'exceptions sur le moteur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="5837b-176">Cela permet de veiller à ce que le package finisse l'exécution et ne s'arrête pas de façon inattendue.</span><span class="sxs-lookup"><span data-stu-id="5837b-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="5837b-177">Toutefois, le moteur d'exécution fournit d'autres mécanismes pour gérer les conditions d'erreur qui peuvent se produire pendant l'exécution d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="5837b-178">Ceux-ci incluent la publication de messages d'erreur et d'avertissement, le renvoi d'une valeur de la structure <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, la publication de messages, le renvoi de la valeur <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> et la divulgation d'informations sur les résultats de l'exécution des tâches via la propriété <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="5837b-179">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> contient les méthodes <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>, qui peuvent être appelées par la tâche pour publier des messages d'erreur et d'avertissement sur le moteur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="5837b-180">Ces deux méthodes requièrent des paramètres tels qu'un code d'erreur, un composant source, une description, un fichier d'aide et des informations d'aide contextuelles.</span><span class="sxs-lookup"><span data-stu-id="5837b-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="5837b-181">Selon la configuration de la tâche, le runtime répond à ces messages en déclenchant des événements et des points d'arrêt, ou en écrivant des informations dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="5837b-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="5837b-182">L'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> fournit également la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> qui peut être utilisée pour fournir des informations supplémentaires à propos des résultats de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="5837b-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="5837b-183">Par exemple, si une tâche supprime des lignes d'une table dans le cadre de sa méthode `Execute`, elle peut retourner le nombre de lignes supprimées sous la forme de la valeur de la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="5837b-184">En outre, l'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> fournit la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>.</span><span class="sxs-lookup"><span data-stu-id="5837b-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="5837b-185">Cette propriété permet à l'utilisateur de mapper la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> renvoyée à partir de la tâche vers toute variable visible pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="5837b-186">Il est alors possible d'utiliser la variable spécifiée pour établir des contraintes de précédence entre les tâches.</span><span class="sxs-lookup"><span data-stu-id="5837b-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="5837b-187">Exemple d'exécution</span><span class="sxs-lookup"><span data-stu-id="5837b-187">Execution Example</span></span>
 <span data-ttu-id="5837b-188">L'exemple de code suivant montre une implémentation de la méthode `Execute` et affiche une propriété `ExecutionValue` substituée.</span><span class="sxs-lookup"><span data-stu-id="5837b-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="5837b-189">La tâche supprime le fichier spécifié par la propriété `fileName` de la tâche.</span><span class="sxs-lookup"><span data-stu-id="5837b-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="5837b-190">La tâche publie un avertissement si le fichier n'existe pas ou si la propriété `fileName` est une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="5837b-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="5837b-191">La tâche renvoie une valeur `Boolean` dans la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> pour indiquer si le fichier a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="5837b-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="5837b-192">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5837b-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5837b-193">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5837b-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5837b-194">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5837b-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5837b-195">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5837b-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="5837b-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5837b-196">See Also</span></span>
 <span data-ttu-id="5837b-197">[Création](creating-a-custom-task.md) d’une tâche personnalisée [codage d’une tâche personnalisée](coding-a-custom-task.md) [développement d’une interface utilisateur pour une tâche personnalisée](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="5837b-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


