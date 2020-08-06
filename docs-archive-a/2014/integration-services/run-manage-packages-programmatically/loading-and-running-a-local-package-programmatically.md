---
title: Chargement et exécution d’un package local par programmation | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696915"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="5d391-102">Chargement et exécution d'un package local par programme</span><span class="sxs-lookup"><span data-stu-id="5d391-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="5d391-103">Vous pouvez exécuter des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] selon les besoins ou à des moments prédéterminés à l’aide des méthodes décrites dans [Exécution de packages](../packages/run-integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="5d391-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="5d391-104">Toutefois, quelques lignes de code vous suffisent pour exécuter également un package à partir d'une application personnalisée, telle qu'une application Windows Forms, une application console, un ASP.NET Web Form, un service Web ASP.NET ou un service Windows.</span><span class="sxs-lookup"><span data-stu-id="5d391-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="5d391-105">Cette rubrique traite des points suivants :</span><span class="sxs-lookup"><span data-stu-id="5d391-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="5d391-106">Chargement d’un package par programmation</span><span class="sxs-lookup"><span data-stu-id="5d391-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="5d391-107">Exécution d'un package par programme</span><span class="sxs-lookup"><span data-stu-id="5d391-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="5d391-108">Toutes les méthodes utilisées dans cette rubrique pour charger et exécuter des packages requièrent une référence à l'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="5d391-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="5d391-109">Après avoir ajouté la référence à un nouveau projet, importez l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> à l'aide d'une instruction `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="5d391-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="5d391-110">Chargement d'un package par programme</span><span class="sxs-lookup"><span data-stu-id="5d391-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="5d391-111">Pour charger par programme un package sur l'ordinateur local, que le package soit stocké localement ou à distance, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d391-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="5d391-112">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="5d391-112">Storage Location</span></span>|<span data-ttu-id="5d391-113">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="5d391-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="5d391-114">Fichier</span><span class="sxs-lookup"><span data-stu-id="5d391-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="5d391-115">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="5d391-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5d391-116">Les méthodes de la classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> qui permettent d'utiliser le magasin de packages SSIS prennent uniquement en charge « . », localhost ou le nom du serveur local.</span><span class="sxs-lookup"><span data-stu-id="5d391-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="5d391-117">Vous ne pouvez pas utiliser « (local) ».</span><span class="sxs-lookup"><span data-stu-id="5d391-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="5d391-118">Exécution d’un package par programmation</span><span class="sxs-lookup"><span data-stu-id="5d391-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="5d391-119">Le développement d'une application personnalisée dans du code managé qui exécute un package sur l'ordinateur local requiert la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="5d391-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="5d391-120">Les étapes résumées ci-dessous sont présentées dans l'exemple d'application console qui suit.</span><span class="sxs-lookup"><span data-stu-id="5d391-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="5d391-121">Pour exécuter par programme un package sur l'ordinateur local</span><span class="sxs-lookup"><span data-stu-id="5d391-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="5d391-122">Démarrez l'environnement de développement Visual Studio et créez une application dans votre langage de développement par défaut.</span><span class="sxs-lookup"><span data-stu-id="5d391-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="5d391-123">Cet exemple utilise une application console. Cependant, vous pouvez également exécuter un package à partir d'une application Windows Forms, un ASP.NET Web Form, un service Web ASP.NET ou un service Windows.</span><span class="sxs-lookup"><span data-stu-id="5d391-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="5d391-124">Dans le menu **Projet**, cliquez sur **Ajouter une référence**, puis ajoutez une référence à **Microsoft.SqlServer.ManagedDTS.dll**.</span><span class="sxs-lookup"><span data-stu-id="5d391-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="5d391-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d391-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="5d391-126">Utilisez l' `Imports` instruction Visual Basic ou l' `using` instruction C# pour importer l’espace de noms **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="5d391-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="5d391-127">Ajoutez le code suivant dans la routine principale.</span><span class="sxs-lookup"><span data-stu-id="5d391-127">Add the following code in the main routine.</span></span> <span data-ttu-id="5d391-128">L'application console terminée doit ressembler à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="5d391-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5d391-129">L'exemple de code montre le chargement du package à partir du système de fichiers à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d391-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="5d391-130">Toutefois, vous pouvez également charger le package à partir de la base de données MSDB en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>, ou à partir du magasin de packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d391-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="5d391-131">Exécutez le projet.</span><span class="sxs-lookup"><span data-stu-id="5d391-131">Run the project.</span></span> <span data-ttu-id="5d391-132">L’exemple de code exécute l’exemple de package CalculatedColumns installé avec les exemples [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d391-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="5d391-133">Le résultat de l'exécution du package est affiché dans la fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="5d391-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="5d391-134">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="5d391-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="5d391-135">Capture d'événements à partir d'un package en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="5d391-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="5d391-136">Lorsque vous exécutez un package par programme comme dans l'exemple précédent, vous pouvez également capturer les erreurs et les autres événements qui se produisent lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="5d391-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="5d391-137">Pour cela, vous devez ajouter une classe qui hérite de la classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> et passer une référence à cette classe lorsque vous chargez le package.</span><span class="sxs-lookup"><span data-stu-id="5d391-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="5d391-138">Bien que l'exemple suivant capture uniquement l'événement <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>, la classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> vous permet de capturer de nombreux autres événements.</span><span class="sxs-lookup"><span data-stu-id="5d391-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="5d391-139">Pour exécuter par programme un package sur l'ordinateur local et capturer les événements du package</span><span class="sxs-lookup"><span data-stu-id="5d391-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="5d391-140">Suivez les étapes dans l'exemple précédent pour créer un projet à utiliser dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="5d391-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="5d391-141">Ajoutez le code suivant dans la routine principale.</span><span class="sxs-lookup"><span data-stu-id="5d391-141">Add the following code in the main routine.</span></span> <span data-ttu-id="5d391-142">L'application console terminée doit ressembler à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="5d391-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="5d391-143">Exécutez le projet.</span><span class="sxs-lookup"><span data-stu-id="5d391-143">Run the project.</span></span> <span data-ttu-id="5d391-144">L’exemple de code exécute l’exemple de package CalculatedColumns installé avec les exemples [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d391-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="5d391-145">Le résultat de l'exécution du package est affiché dans la fenêtre de la console, avec toutes les erreurs qui se sont éventuellement produites.</span><span class="sxs-lookup"><span data-stu-id="5d391-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="5d391-146">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="5d391-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="5d391-147">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5d391-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5d391-148">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5d391-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5d391-149">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5d391-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5d391-150">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5d391-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d391-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d391-151">See Also</span></span>  
 <span data-ttu-id="5d391-152">[Comprendre les différences entre l’exécution locale et l’exécution distante](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="5d391-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="5d391-153">[Chargement et exécution d’un package distant par programme](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="5d391-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="5d391-154">Chargement de la sortie d'un package local</span><span class="sxs-lookup"><span data-stu-id="5d391-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
