---
title: Ajout de tâches par programmation | Microsoft Docs
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
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604100"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="b1307-102">Ajout de tâches par programme</span><span class="sxs-lookup"><span data-stu-id="b1307-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="b1307-103">Il est possible d'ajouter des tâches aux types d'objets suivants dans le moteur d'exécution :</span><span class="sxs-lookup"><span data-stu-id="b1307-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="b1307-104">Ces classes, considérées comme des conteneurs, héritent toutes de la propriété <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1307-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="b1307-105">Des conteneurs peuvent contenir une collection de tâches, qui sont des objets exécutables traités par le runtime au cours de l'exécution du conteneur.</span><span class="sxs-lookup"><span data-stu-id="b1307-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="b1307-106">L'ordre d'exécution des objets dans la collection est déterminé par n'importe quel ensemble <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> sur chaque tâche dans les conteneurs.</span><span class="sxs-lookup"><span data-stu-id="b1307-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="b1307-107">Les contraintes de précédence permettent la création de branches d'exécution basées sur le succès, l'échec ou l'achèvement d'un <xref:Microsoft.SqlServer.Dts.Runtime.Executable> dans la collection.</span><span class="sxs-lookup"><span data-stu-id="b1307-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="b1307-108">Chaque conteneur possède une collection <xref:Microsoft.SqlServer.Dts.Runtime.Executables> qui contient les objets <xref:Microsoft.SqlServer.Dts.Runtime.Executable> individuels.</span><span class="sxs-lookup"><span data-stu-id="b1307-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="b1307-109">Chaque tâche exécutable hérite des méthodes <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> et les implémente.</span><span class="sxs-lookup"><span data-stu-id="b1307-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="b1307-110">Ces deux méthodes sont appelées par le moteur d'exécution pour traiter chaque <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="b1307-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="b1307-111">Pour ajouter une tâche à un package, vous avez besoin d'un conteneur avec une collection <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existante.</span><span class="sxs-lookup"><span data-stu-id="b1307-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="b1307-112">Généralement, la tâche ajoutée à la collection est un package.</span><span class="sxs-lookup"><span data-stu-id="b1307-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="b1307-113">Pour ajouter la nouvelle tâche exécutable dans la collection pour ce conteneur, vous devez appeler la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1307-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="b1307-114">La méthode possède un seul paramètre, une chaîne, qui contient le CLSID, le PROGID, le moniker STOCK, ou le <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> de la tâche que vous ajoutez.</span><span class="sxs-lookup"><span data-stu-id="b1307-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="b1307-115">Nom des tâches</span><span class="sxs-lookup"><span data-stu-id="b1307-115">Task Names</span></span>  
 <span data-ttu-id="b1307-116">Bien qu'il soit possible de spécifier une tâche par son nom ou son ID, le moniker `STOCK` est le paramètre le plus souvent utilisé dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1307-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="b1307-117">Pour ajouter une tâche à un fichier exécutable identifié par le moniker `STOCK`, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="b1307-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="b1307-118">La liste suivante présente les noms de chaque tâche figurant à la suite du moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="b1307-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="b1307-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="b1307-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="b1307-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="b1307-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="b1307-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="b1307-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="b1307-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="b1307-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="b1307-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="b1307-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="b1307-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="b1307-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="b1307-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="b1307-125">FTPTask</span></span>  
  
-   <span data-ttu-id="b1307-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="b1307-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="b1307-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="b1307-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="b1307-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="b1307-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="b1307-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="b1307-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="b1307-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="b1307-130">SQLTask</span></span>  
  
-   <span data-ttu-id="b1307-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="b1307-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="b1307-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="b1307-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="b1307-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="b1307-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="b1307-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="b1307-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="b1307-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="b1307-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="b1307-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="b1307-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="b1307-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="b1307-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="b1307-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="b1307-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="b1307-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="b1307-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="b1307-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="b1307-140">XMLTask</span></span>  
  
 <span data-ttu-id="b1307-141">Si vous préférez une syntaxe plus explicite, ou si la tâche à ajouter n'a pas de moniker STOCK, vous pouvez ajouter la tâche au fichier exécutable à l'aide de son nom long.</span><span class="sxs-lookup"><span data-stu-id="b1307-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="b1307-142">Cette syntaxe requiert que vous spécifiiez également le numéro de version de la tâche.</span><span class="sxs-lookup"><span data-stu-id="b1307-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="b1307-143">Vous pouvez obtenir le nom long de la tâche par programmation, sans devoir spécifier la version de la tâche, à l’aide de la propriété **AssemblyQualifiedName** de la classe, comme indiqué dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="b1307-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="b1307-144">Cet exemple requiert une référence à l'assembly Microsoft.SqlServer.SQLTask.</span><span class="sxs-lookup"><span data-stu-id="b1307-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="b1307-145">L'exemple de code suivant montre comment créer une collection <xref:Microsoft.SqlServer.Dts.Runtime.Executables> à partir d'un nouveau package, puis ajouter une tâche de système de fichiers et une tâche d'insertion en bloc à la collection, à l'aide de leur moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="b1307-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="b1307-146">Cet exemple requiert une référence aux assemblys Microsoft.SqlServer.FileSystemTask et Microsoft.SqlServer.BulkInsertTask.</span><span class="sxs-lookup"><span data-stu-id="b1307-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="b1307-147">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="b1307-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="b1307-148">Conteneur TaskHost</span><span class="sxs-lookup"><span data-stu-id="b1307-148">TaskHost Container</span></span>  
 <span data-ttu-id="b1307-149">La classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> est un conteneur très important pour la programmation, même s'il n'apparaît pas dans l'interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="b1307-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="b1307-150">Cette classe sert de wrapper pour chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="b1307-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="b1307-151">Les tâches qui, à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>, sont ajoutées au package en tant qu'objet <xref:Microsoft.SqlServer.Dts.Runtime.Executable> peuvent être converties en objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="b1307-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="b1307-152">Lorsqu'une tâche est convertie en <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, vous pouvez lui appliquer des propriétés et des méthodes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b1307-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="b1307-153">Par ailleurs, la tâche elle-même est accessible par l'intermédiaire de la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="b1307-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="b1307-154">Selon vos besoins, vous pouvez décider de conserver la tâche sous la forme d'un objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> afin de pouvoir vous servir des propriétés de la tâche par le biais de la collection <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1307-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="b1307-155"><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> a pour avantage de vous permettre d'écrire plus de code générique.</span><span class="sxs-lookup"><span data-stu-id="b1307-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="b1307-156">Si vous avez besoin d'utiliser du code très spécifique pour une tâche, vous devez effectuer un cast de la tâche en son objet approprié.</span><span class="sxs-lookup"><span data-stu-id="b1307-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="b1307-157">L'exemple de code suivant indique comment effectuer un cast de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, qui contient <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, en objet <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>.</span><span class="sxs-lookup"><span data-stu-id="b1307-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="b1307-158">L'exemple de code suivant montre comment effectuer un cast du fichier exécutable en <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, puis comment utiliser la propriété <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> pour identifier le type de fichier exécutable que contient l'hôte.</span><span class="sxs-lookup"><span data-stu-id="b1307-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="b1307-159">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="b1307-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="b1307-160">L'instruction <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> retourne un fichier exécutable converti en objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> à partir de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.Executable> créé récemment.</span><span class="sxs-lookup"><span data-stu-id="b1307-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="b1307-161">Pour définir des propriétés ou appeler des méthodes sur le nouvel objet, vous disposez de deux options :</span><span class="sxs-lookup"><span data-stu-id="b1307-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="b1307-162">Utilisez la collection <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="b1307-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="b1307-163">Par exemple, pour obtenir une propriété à partir de l’objet, utilisez `th.Properties["propertyname"].GetValue(th))`.</span><span class="sxs-lookup"><span data-stu-id="b1307-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="b1307-164">Pour définir une propriété, utilisez `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="b1307-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="b1307-165">Effectuez un cast de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> vers la classe de tâche.</span><span class="sxs-lookup"><span data-stu-id="b1307-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="b1307-166">Par exemple, pour effectuer un cast de la tâche d'insertion en bloc en <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> une fois qu'elle a été ajoutée à un package en tant que <xref:Microsoft.SqlServer.Dts.Runtime.Executable>, puis convertie en <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, utilisez `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="b1307-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="b1307-167">Utiliser la classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> dans le code, au lieu d'effectuer un cast vers la classe spécifique à une tâche présente les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="b1307-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="b1307-168">Le fournisseur <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> ne requiert pas de référence à l’assembly dans le code.</span><span class="sxs-lookup"><span data-stu-id="b1307-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="b1307-169">Vous pouvez coder des routines génériques qui fonctionnent avec toutes les tâches, car vous n'avez pas besoin de connaître le nom de la tâche au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="b1307-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="b1307-170">Ces routines génériques incluent des méthodes dans lesquelles vous pouvez passer le nom de la tâche et dont le code fonctionne avec toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="b1307-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="b1307-171">C'est une méthode pratique pour écrire un code de test.</span><span class="sxs-lookup"><span data-stu-id="b1307-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="b1307-172">Effectuer un cast à partir de <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> vers la classe spécifique à une tâche présente les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="b1307-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="b1307-173">Le projet Visual Studio propose la saisie semi-automatique des instructions (IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="b1307-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="b1307-174">Le code peut s'exécuter plus rapidement.</span><span class="sxs-lookup"><span data-stu-id="b1307-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="b1307-175">Les objets spécifiques à une tâche prennent en charge la liaison anticipée et les optimisations qui en résultent.</span><span class="sxs-lookup"><span data-stu-id="b1307-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="b1307-176">Pour plus d'informations sur la liaison anticipée et tardive, consultez la rubrique sur les liaisons anticipées et les liaisons tardives dans les concepts de langage de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b1307-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="b1307-177">L'exemple de code suivant développe le concept de réutilisation du code de tâche.</span><span class="sxs-lookup"><span data-stu-id="b1307-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="b1307-178">Au lieu d'effectuer un cast des tâches en leurs équivalents dans une classe spécifique, l'exemple de code montre comment effectuer un cast du fichier exécutable en <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, puis il utilise <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> pour écrire du code générique pour toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="b1307-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
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
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="b1307-179">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="b1307-179">External Resources</span></span>  
 <span data-ttu-id="b1307-180">Entrée de blog, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="b1307-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="b1307-181">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b1307-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b1307-182">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="b1307-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b1307-183">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="b1307-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b1307-184">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="b1307-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1307-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1307-185">See Also</span></span>  
 [<span data-ttu-id="b1307-186">Connexion de tâches par programme</span><span class="sxs-lookup"><span data-stu-id="b1307-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
