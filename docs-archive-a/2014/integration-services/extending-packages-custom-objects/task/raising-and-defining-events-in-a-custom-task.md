---
title: Déclenchement et définition d’événements dans une tâche personnalisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS events, custom
- status information [SQL Server], task events
- custom tasks [Integration Services], events
- SSIS custom tasks, events
- IDTSComponentEvents interface
- events [Integration Services], custom
- events [Integration Services], runtime
- custom events [Integration Services]
- SSIS events, runtime
- IDTSEvents interface
ms.assetid: e0898aa1-e90c-4c4e-99d4-708a76efddfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb41ee60543a05b6cf10b3acda43372e20288d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611911"
---
# <a name="raising-and-defining-events-in-a-custom-task"></a><span data-ttu-id="b5968-102">Déclenchement et définition d'événements dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="b5968-102">Raising and Defining Events in a Custom Task</span></span>
  <span data-ttu-id="b5968-103">Le moteur d’exécution [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] propose une collection d’événements qui fournissent l’état d’avancement d’une tâche lors de sa validation et de son exécution.</span><span class="sxs-lookup"><span data-stu-id="b5968-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine provides a collection of events that provide status on the progress of a task as the task is validated and executed.</span></span> <span data-ttu-id="b5968-104">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> définit ces événements et elle est fournie aux tâches en tant que paramètre pour les méthodes <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5968-104">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface defines these events, and is provided to tasks as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="b5968-105">Il existe un autre jeu d'événements, définis dans l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>, déclenchée de la part de la tâche par l'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="b5968-105">There is another set of events, which are defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface, that are raised on behalf of the task by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="b5968-106">L'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> déclenche des événements qui se produisent avant et après la validation et l'exécution, tandis que la tâche déclenche des événements qui se produisent pendant l'exécution et la validation.</span><span class="sxs-lookup"><span data-stu-id="b5968-106">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> raises events that occur before and after validation and execution, whereas the task raises the events that occur during execution and validation.</span></span>  
  
## <a name="creating-custom-events"></a><span data-ttu-id="b5968-107">Création d'événements personnalisés</span><span class="sxs-lookup"><span data-stu-id="b5968-107">Creating Custom Events</span></span>  
 <span data-ttu-id="b5968-108">Les développeurs de tâches personnalisées peuvent définir de nouveaux événements personnalisés en créant un objet <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> dans leur implémentation substituée de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5968-108">Custom task developers can define new, custom events by creating a new <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> in their overridden implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A> method.</span></span> <span data-ttu-id="b5968-109">Une fois que l'objet <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> est créé, il est ajouté à la collection `EventInfos` à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5968-109">After the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> is created, it is added to the `EventInfos` collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method.</span></span> <span data-ttu-id="b5968-110">La signature de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> est la suivante :</span><span class="sxs-lookup"><span data-stu-id="b5968-110">The method signature of the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method is as follows:</span></span>  
  
 `public void Add(string eventName, string description, bool allowEventHandlers, string[] parameterNames, TypeCode[] parameterTypes, string[] parameterDescriptions);`  
  
 <span data-ttu-id="b5968-111">L'exemple de code suivant présente la méthode `InitializeTask` d'une tâche personnalisée, où deux événements personnalisés sont créés et leurs propriétés sont définies.</span><span class="sxs-lookup"><span data-stu-id="b5968-111">The following code sample shows the `InitializeTask` method of a custom task, where two custom events are created and their properties are set.</span></span> <span data-ttu-id="b5968-112">Les nouveaux événements sont ensuite ajoutés à la collection <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>.</span><span class="sxs-lookup"><span data-stu-id="b5968-112">The new events are then added to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection.</span></span>  
  
 <span data-ttu-id="b5968-113">Pour le premier événement personnalisé, *eventName* a la valeur « **OnBeforeIncrement** » et *description* a la valeur « **Fires after the initial value is updated.** ».</span><span class="sxs-lookup"><span data-stu-id="b5968-113">The first custom event has an *eventName* of "**OnBeforeIncrement**" and *description* of "**Fires after the initial value is updated.**"</span></span> <span data-ttu-id="b5968-114">Le paramètre suivant, la valeur `true` indique que cet événement doit autoriser la création d'un conteneur de gestionnaire d'événements pour gérer l'événement.</span><span class="sxs-lookup"><span data-stu-id="b5968-114">The next parameter, the `true` value, indicates that this event should allow an event handler container to be created to handle the event.</span></span> <span data-ttu-id="b5968-115">Le gestionnaire d'événements est un conteneur qui fournit une structure dans un package et des services à des tâches, comme d'autres conteneurs tels que le package, Séquence, ForLoop et ForEachLoop.</span><span class="sxs-lookup"><span data-stu-id="b5968-115">The event handler is a container that provides structure in a package and services to tasks, like other containers such as the package, Sequence, ForLoop, and ForEachLoop.</span></span> <span data-ttu-id="b5968-116">Lorsque le paramètre *AllowEventHandlers* a la la `true` , les <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objets sont créés pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="b5968-116">When the *allowEventHandlers* parameter is `true`, <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are created for the event.</span></span> <span data-ttu-id="b5968-117">Tous les paramètres définis pour l'événement sont maintenant disponibles pour l'objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> dans la collection de variables de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b5968-117">Any parameters that were defined for the event are now available to the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> in the variables collection of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span></span>  
  
```csharp  
public override void InitializeTask(Connections connections,  
   VariableDispenser variables, IDTSInfoEvents events,  
   IDTSLogging log, EventInfos eventInfos,  
   LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
{  
    this.eventInfos = eventInfos;  
    string[] paramNames = new string[1];  
    TypeCode[] paramTypes = new TypeCode[1]{TypeCode.Int32};  
    string[] paramDescriptions = new string[1];  
  
    paramNames[0] = "InitialValue";  
    paramDescriptions[0] = "The value before it is incremented.";  
  
    this.eventInfos.Add("OnBeforeIncrement",   
      "Fires before the task increments the value.",  
      true,paramNames,paramTypes,paramDescriptions);  
    this.onBeforeIncrement = this.eventInfos["OnBeforeIncrement"];  
  
    paramDescriptions[0] = "The value after it has been incremented.";  
    this.eventInfos.Add("OnAfterIncrement",  
      "Fires after the initial value is updated.",  
      true,paramNames, paramTypes,paramDescriptions);  
    this.onAfterIncrement = this.eventInfos["OnAfterIncrement"];  
}  
```  
  
```vb  
Public Overrides Sub InitializeTask(ByVal connections As Connections, _  
ByVal variables As VariableDispenser, ByVal events As IDTSInfoEvents, _  
ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, _  
ByVal logEntryInfos As LogEntryInfos, ByVal refTracker As ObjectReferenceTracker)   
  
    Dim paramNames(0) As String  
    Dim paramTypes(0) As TypeCode = {TypeCode.Int32}  
    Dim paramDescriptions(0) As String  
  
    Me.eventInfos = eventInfos  
  
    paramNames(0) = "InitialValue"  
    paramDescriptions(0) = "The value before it is incremented."  
  
    Me.eventInfos.Add("OnBeforeIncrement", _  
      "Fires before the task increments the value.", _  
      True, paramNames, paramTypes, paramDescriptions)  
    Me.onBeforeIncrement = Me.eventInfos("OnBeforeIncrement")  
  
    paramDescriptions(0) = "The value after it has been incremented."  
    Me.eventInfos.Add("OnAfterIncrement", _  
      "Fires after the initial value is updated.", True, _  
      paramNames, paramTypes, paramDescriptions)  
    Me.onAfterIncrement = Me.eventInfos("OnAfterIncrement")  
  
End Sub  
```  
  
## <a name="raising-custom-events"></a><span data-ttu-id="b5968-118">Déclenchement d'événements personnalisés</span><span class="sxs-lookup"><span data-stu-id="b5968-118">Raising Custom Events</span></span>  
 <span data-ttu-id="b5968-119">Les événements personnalisés sont déclenchés en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5968-119">Custom events are raised by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="b5968-120">La ligne de code suivante déclenche un événement personnalisé.</span><span class="sxs-lookup"><span data-stu-id="b5968-120">The following line of code raises a custom event.</span></span>  
  
```csharp  
componentEvents.FireCustomEvent(this.onBeforeIncrement.Name,  
   this.onBeforeIncrement.Description, ref arguments,  
   null, ref bFireOnBeforeIncrement);  
```  
  
```vb  
componentEvents.FireCustomEvent(Me.onBeforeIncrement.Name, _  
Me.onBeforeIncrement.Description, arguments, _  
Nothing,  bFireOnBeforeIncrement)  
```  
  
## <a name="sample"></a><span data-ttu-id="b5968-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="b5968-121">Sample</span></span>  
 <span data-ttu-id="b5968-122">L'exemple suivant montre une tâche qui définit un événement personnalisé dans la méthode `InitializeTask`, qui ajoute l'événement personnalisé à la collection <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>, puis qui déclenche l'événement personnalisé pendant sa méthode `Execute` en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5968-122">The following example shows a task that defines a custom event in the `InitializeTask` method, adds the custom event to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection, and then raises the custom event during its `Execute` method by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span>  
  
```csharp  
[DtsTask(DisplayName = "CustomEventTask")]  
    public class CustomEventTask : Task  
    {  
        public override DTSExecResult Execute(Connections connections,   
          VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,  
           IDTSLogging log, object transaction)  
        {  
            bool fireAgain;  
            object[] args = new object[1] { "The value of the parameter." };  
            componentEvents.FireCustomEvent( "MyCustomEvent",   
              "Firing the custom event.", ref args,  
              "CustomEventTask" , ref fireAgain );  
            return DTSExecResult.Success;  
        }  
  
        public override void InitializeTask(Connections connections,  
          VariableDispenser variableDispenser, IDTSInfoEvents events,  
          IDTSLogging log, EventInfos eventInfos,  
          LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
        {  
            string[] names = new string[1] {"Parameter1"};  
            TypeCode[] types = new TypeCode[1] {TypeCode.String};  
            string[] descriptions = new string[1] {"Parameter description." };  
  
            eventInfos.Add("MyCustomEvent",  
             "Fires when my interesting event happens.",  
             true, names, types, descriptions);  
  
        }  
   }  
```  
  
```vb  
<DtsTask(DisplayName = "CustomEventTask")> _   
    Public Class CustomEventTask  
     Inherits Task  
        Public Overrides Function Execute(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser, _  
          ByVal componentEvents As IDTSComponentEvents, _  
          ByVal log As IDTSLogging, ByVal transaction As Object) _  
          As DTSExecResult  
  
            Dim fireAgain As Boolean  
            Dim args() As Object =  New Object(1) {"The value of the parameter."}  
  
            componentEvents.FireCustomEvent("MyCustomEvent", _  
              "Firing the custom event.", args, _  
              "CustomEventTask" ,  fireAgain)  
            Return DTSExecResult.Success  
        End Function  
  
        Public Overrides  Sub InitializeTask(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser,  
          ByVal events As IDTSInfoEvents,  
          ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, ByVal logEnTryInfos As LogEnTryInfos, ByVal refTracker As ObjectReferenceTracker)  
  
            Dim names() As String =  New String(1) {"Parameter1"}  
            Dim types() As TypeCode =  New TypeCode(1) {TypeCode.String}  
            Dim descriptions() As String =  New String(1) {"Parameter description."}  
  
            eventInfos.Add("MyCustomEvent", _  
              "Fires when my interesting event happens.", _  
              True, names, types, descriptions)  
  
        End Sub  
  
    End Class  
```  
  
<span data-ttu-id="b5968-123">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b5968-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b5968-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="b5968-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b5968-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="b5968-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b5968-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="b5968-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5968-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5968-127">See Also</span></span>  
 <span data-ttu-id="b5968-128">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="b5968-128">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="b5968-129">Ajouter un gestionnaire d’événements à un package</span><span class="sxs-lookup"><span data-stu-id="b5968-129">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
