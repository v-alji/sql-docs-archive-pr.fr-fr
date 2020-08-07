---
title: Gestion d’événements par programmation | Microsoft Docs
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
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603592"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="e2a0c-102">Gestion d'événements par programme</span><span class="sxs-lookup"><span data-stu-id="e2a0c-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="e2a0c-103">Le Runtime [!INCLUDE[ssIS](../../includes/ssis-md.md)] fournit une collection d'événements qui se produisent avant, pendant et après la validation et l'exécution d'un package.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="e2a0c-104">Ces événements peuvent être capturés de deux manières.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-104">These events can be captured in two ways.</span></span> <span data-ttu-id="e2a0c-105">La première méthode consiste à implémenter l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> dans une classe et à fournir la classe en tant que paramètre aux méthodes `Execute` et `Validate` du package.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="e2a0c-106">La deuxième méthode consiste à créer des objets <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>, qui peuvent contenir d'autres objets [!INCLUDE[ssIS](../../includes/ssis-md.md)], tels que des tâches et des boucles, exécutés lorsqu'un événement se produit dans <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="e2a0c-107">Cette section décrit ces deux méthodes et fournit des exemples de code pour illustrer leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="e2a0c-108">Réception de rappels IDTSEvents</span><span class="sxs-lookup"><span data-stu-id="e2a0c-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="e2a0c-109">Les développeurs qui créent et exécutent des packages par programme peuvent recevoir des notifications d'événements au cours du processus de validation et d'exécution à l'aide de l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="e2a0c-110">Cette opération s'effectue en créant une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> et en fournissant cette classe en tant que paramètre aux méthodes `Validate` et `Execute` d'un package.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="e2a0c-111">Les méthodes de la classe sont ensuite appelées par le moteur d'exécution lorsque les événements se produisent.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="e2a0c-112"><xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> est une classe qui implémente déjà l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> ; par conséquent, une autre manière d'implémenter directement l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> consiste à la dériver de la classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> et à substituer les événements spécifiques auxquels vous souhaitez répondre.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="e2a0c-113">Vous fournissez alors votre classe en tant que paramètre aux méthodes `Validate` et `Execute` du <xref:Microsoft.SqlServer.Dts.Runtime.Package> pour recevoir des rappels d'événements.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="e2a0c-114">L'exemple de code suivant présente une classe qui dérive de <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> et qui substitue la méthode <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="e2a0c-115">La classe est ensuite fournie en tant que aparameter `Validate` aux `Execute` méthodes et du package.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="e2a0c-116">Création d'objets DtsEventHandler</span><span class="sxs-lookup"><span data-stu-id="e2a0c-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="e2a0c-117">Le moteur d'exécution fournit un système de gestion et de notification d'événements fiable et très souple par le biais de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="e2a0c-118">Ces objets vous permettent de concevoir des flux de travail complets dans le gestionnaire d'événements, qui s'exécutent uniquement lorsque l'événement auquel le gestionnaire d'événements appartient se produit.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="e2a0c-119">L'objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> est un conteneur qui s'exécute lors du déclenchement de l'événement correspondant sur son objet parent.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="e2a0c-120">Cette architecture vous permet de créer des flux de travail isolés qui s'exécutent en réponse à des événements qui se produisent sur un conteneur.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="e2a0c-121">Comme les objets <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> sont synchrones, l'exécution s'arrête tant que les gestionnaires d'événements attachés à l'événement ne sont pas retournés.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="e2a0c-122">Le code suivant montre comment créer un objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="e2a0c-123">Le code ajoute <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> à la collection <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> du package, puis crée un objet <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> pour l'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> de la tâche.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="e2a0c-124"><xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> est ajouté au gestionnaire d'événements, qui s'exécute lorsque l'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> se produit pour le premier <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="e2a0c-125">Cet exemple suppose que vous disposez d'un fichier nommé C:\Windows\Temp\DemoFile.txt à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="e2a0c-126">La première fois que vous exécutez l'exemple, le fichier est correctement copié et le gestionnaire d'événements n'est pas appelé.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="e2a0c-127">La deuxième fois vous exécutez l'exemple, le premier <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> ne parvient pas à copier le fichier (à cause de la valeur de <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> est `false`), le gestionnaire d'événements est appelé, le deuxième <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> supprime le fichier source, puis le package signale l'échec due à l'erreur rencontrée.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2a0c-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="e2a0c-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="e2a0c-129">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e2a0c-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e2a0c-130">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="e2a0c-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e2a0c-131">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="e2a0c-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e2a0c-132">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="e2a0c-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a0c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2a0c-133">See Also</span></span>  
 <span data-ttu-id="e2a0c-134">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="e2a0c-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="e2a0c-135">Ajouter un gestionnaire d’événements à un package</span><span class="sxs-lookup"><span data-stu-id="e2a0c-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
