---
title: Ajout de la prise en charge du débogage dans une tâche personnalisée | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611182"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="2f71e-102">Ajout de la prise en charge du débogage dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="2f71e-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="2f71e-103">Le moteur d'exécution [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permet aux packages, tâches et autres types de conteneurs d'être suspendus pendant l'exécution à l'aide de points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2f71e-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="2f71e-104">L'utilisation de points d'arrêt vous permet d'examiner et de corriger les erreurs qui empêchent votre application ou vos tâches de s'exécuter correctement.</span><span class="sxs-lookup"><span data-stu-id="2f71e-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="2f71e-105">L'architecture de point d'arrêt permet au client d'évaluer la valeur d'exécution des objets contenus dans le package aux points d'exécution définis pendant la suspension du traitement de la tâche.</span><span class="sxs-lookup"><span data-stu-id="2f71e-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="2f71e-106">Les développeurs de tâches personnalisées peuvent utiliser cette architecture pour créer des cibles de points d'arrêt personnalisées en utilisant l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> et son interface parente <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="2f71e-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="2f71e-107">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> définit l'interaction entre le moteur d'exécution et la tâche pour créer et gérer des sites ou des cibles de points d'arrêt personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2f71e-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="2f71e-108">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> fournit des méthodes et propriétés appelées par le moteur d'exécution pour notifier la tâche de suspendre ou reprendre son exécution.</span><span class="sxs-lookup"><span data-stu-id="2f71e-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="2f71e-109">Un site ou une cible de point d'arrêt est un point dans l'exécution de la tâche où le traitement peut être suspendu.</span><span class="sxs-lookup"><span data-stu-id="2f71e-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="2f71e-110">Les utilisateurs sélectionnent un site de point d’arrêt parmi les sites disponibles dans la boîte de dialogue **Définir des points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="2f71e-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="2f71e-111">Par exemple, outre les options de point d'arrêt par défaut, le conteneur de boucle Foreach propose l'option « Arrêter au début de chaque itération de la boucle ».</span><span class="sxs-lookup"><span data-stu-id="2f71e-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="2f71e-112">Lorsqu'une tâche atteint une cible de point d'arrêt pendant l'exécution, elle évalue cette cible de point d'arrêt pour déterminer si un point d'arrêt est activé.</span><span class="sxs-lookup"><span data-stu-id="2f71e-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="2f71e-113">Celui-ci indique que l'utilisateur souhaite que l'exécution s'arrête à ce point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2f71e-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="2f71e-114">Si le point d'arrêt est activé, la tâche déclenche l'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> pour le moteur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="2f71e-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="2f71e-115">Le moteur d'exécution répond à l'événement en appelant la méthode `Suspend` de chaque tâche qui est en cours d'exécution dans le package.</span><span class="sxs-lookup"><span data-stu-id="2f71e-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="2f71e-116">L'exécution de la tâche reprend lorsque l'exécution appelle la méthode `ResumeExecution` de la tâche suspendue.</span><span class="sxs-lookup"><span data-stu-id="2f71e-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="2f71e-117">Les tâches qui n'utilisent pas de points d'arrêt doivent encore implémenter les interfaces <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> et <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="2f71e-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="2f71e-118">Cette implémentation garantit que la tâche est correctement suspendue lorsque d'autres objets contenus dans le package déclenchent des événements <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f71e-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="2f71e-119">Interface IDTSBreakpointSite et BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="2f71e-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="2f71e-120">Les tâches créent des cibles de points d'arrêt en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, ce qui permet de fournir un ID entier et une description de chaîne comme paramètres.</span><span class="sxs-lookup"><span data-stu-id="2f71e-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="2f71e-121">Lorsque la tâche atteint le point dans son code qui contient une cible de point d'arrêt, elle évalue la cible de point d'arrêt en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> pour déterminer si ce point d'arrêt est activé.</span><span class="sxs-lookup"><span data-stu-id="2f71e-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="2f71e-122">Si la valeur est `true`, la tâche notifie le moteur d'exécution en déclenchant l'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f71e-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="2f71e-123">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> définit une méthode unique, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, appelée par le moteur d'exécution pendant la création de la tâche.</span><span class="sxs-lookup"><span data-stu-id="2f71e-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="2f71e-124">Cette méthode fournit comme paramètre l'objet <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, utilisé ensuite par la tâche pour créer et gérer ses points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2f71e-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="2f71e-125">Les tâches doivent stocker localement l'objet <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> pour l'utiliser pendant les méthodes `Validate` et `Execute`.</span><span class="sxs-lookup"><span data-stu-id="2f71e-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="2f71e-126">L'exemple de code suivant montre comment créer une cible de point d'arrêt en utilisant l'objet <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span><span class="sxs-lookup"><span data-stu-id="2f71e-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="2f71e-127">L'exemple permet d'appeler la méthode <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> pour déclencher l'événement.</span><span class="sxs-lookup"><span data-stu-id="2f71e-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="2f71e-128">Interface IDTSSuspend</span><span class="sxs-lookup"><span data-stu-id="2f71e-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="2f71e-129">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> définit les méthodes appelées par le moteur d'exécution lorsqu'il suspend ou reprend l'exécution d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="2f71e-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="2f71e-130">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> est implémentée par l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> et ses méthodes `Suspend` et `ResumeExecution` sont généralement remplacées par la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2f71e-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="2f71e-131">Lorsque le moteur d'exécution reçoit un événement `OnBreakpointHit` d'une tâche, il appelle la méthode `Suspend` de chaque tâche en cours d'exécution, en notifiant les tâches de se suspendre.</span><span class="sxs-lookup"><span data-stu-id="2f71e-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="2f71e-132">Lorsque le client reprend l'exécution, le moteur d'exécution appelle la méthode `ResumeExecution` des tâches suspendues.</span><span class="sxs-lookup"><span data-stu-id="2f71e-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="2f71e-133">La suspension et la reprise de l'exécution d'une tâche impliquent l'interruption et la reprise du thread d'exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="2f71e-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="2f71e-134">En code managé, vous procédez ainsi à l'aide de la classe `ManualResetEvent` dans l'espace de noms `System.Threading` du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f71e-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2f71e-135">L'exemple de code suivant montre la suspension et la reprise de l'exécution d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="2f71e-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="2f71e-136">Remarquez que la méthode `Execute` a changé depuis l'exemple de code précédent et que le thread d'exécution est interrompu lors du déclenchement du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2f71e-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="2f71e-137">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2f71e-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2f71e-138">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="2f71e-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2f71e-139">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="2f71e-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2f71e-140">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="2f71e-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f71e-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f71e-141">See Also</span></span>  
 [<span data-ttu-id="2f71e-142">Débogage du flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="2f71e-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
