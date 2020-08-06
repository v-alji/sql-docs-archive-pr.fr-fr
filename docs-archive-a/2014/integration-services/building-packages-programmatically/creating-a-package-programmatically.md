---
title: Création d’un package par programmation | Microsoft Docs
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
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700151"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="15c07-102">Création d'un package par programme</span><span class="sxs-lookup"><span data-stu-id="15c07-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="15c07-103">L'objet <xref:Microsoft.SqlServer.Dts.Runtime.Package> correspond au conteneur de niveau supérieur de tous les autres objets inclus dans une solution de projet [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c07-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="15c07-104">En tant que conteneur de niveau supérieur, le package est le premier objet créé, puis des objets suivants lui sont ajoutés, puis ils sont exécutés dans le contexte du package.</span><span class="sxs-lookup"><span data-stu-id="15c07-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="15c07-105">Le package lui-même ne déplace pas et ne transforme pas de données.</span><span class="sxs-lookup"><span data-stu-id="15c07-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="15c07-106">Il se repose sur les tâches qu'il contient pour effectuer le travail.</span><span class="sxs-lookup"><span data-stu-id="15c07-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="15c07-107">Les tâches effectuent la plupart du travail d'un package et définissent ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="15c07-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="15c07-108">Un package est créé et exécuté avec seulement trois lignes de code, mais différentes tâches et objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> sont ajoutés pour lui donner des fonctionnalités supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="15c07-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="15c07-109">Cette section décrit comment créer un package par programme.</span><span class="sxs-lookup"><span data-stu-id="15c07-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="15c07-110">Elle ne fournit pas d'informations sur la manière de créer les tâches ou les objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="15c07-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="15c07-111">Ceux-ci sont traités dans les sections ultérieures.</span><span class="sxs-lookup"><span data-stu-id="15c07-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15c07-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="15c07-112">Example</span></span>  
 <span data-ttu-id="15c07-113">Pour écrire du code à l'aide de l'environnement de développement intégré Visual Studio, une référence à Microsoft.SqlServer.ManagedDTS.DLL est requise afin de créer une instruction `using` (`Imports` dans Visual Basic .NET) dans Microsoft.SqlServer.Dts.Runtime.</span><span class="sxs-lookup"><span data-stu-id="15c07-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="15c07-114">L'exemple de code suivant présente la création d'un package vide.</span><span class="sxs-lookup"><span data-stu-id="15c07-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="15c07-115">Pour compiler et exécuter l'exemple, appuyez sur F5 dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="15c07-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="15c07-116">Pour générer le code à l’aide du compilateur C#, **csc.exe**, à l’invite de commandes à compiler, utilisez la commande et les références de fichiers suivantes, en remplaçant *\<filename>* par le nom du fichier .cs ou .vb et en lui attribuant une valeur *\<outputfilename>* de votre choix.</span><span class="sxs-lookup"><span data-stu-id="15c07-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="15c07-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="15c07-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="15c07-118">Pour générer le code à l’aide du compilateur Visual Basic .NET, **vbc.exe**, à l’invite de commandes de compilation, utilisez la commande et les références de fichiers suivantes.</span><span class="sxs-lookup"><span data-stu-id="15c07-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="15c07-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="15c07-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="15c07-120">Vous pouvez également créer un package en chargeant un package existant enregistré sur le disque, dans le système de fichiers ou dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15c07-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="15c07-121">La différence est que l'objet <xref:Microsoft.SqlServer.Dts.Runtime.Application> est d'abord créé, puis l'objet de package est renseigné par l'une des méthodes surchargées de l'application : `LoadPackage` pour les fichiers plats, `LoadFromSQLServer` pour les packages enregistrés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> pour les packages enregistrés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="15c07-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="15c07-122">L'exemple suivant charge un package existant à partir du disque, puis consulte plusieurs propriétés sur le package.</span><span class="sxs-lookup"><span data-stu-id="15c07-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="15c07-123">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="15c07-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="15c07-124">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="15c07-124">External Resources</span></span>  
  
-   <span data-ttu-id="15c07-125">Entrée de blog, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="15c07-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="15c07-126">Entrée de blog, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="15c07-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="15c07-127">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="15c07-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="15c07-128">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="15c07-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="15c07-129">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="15c07-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="15c07-130">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="15c07-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c07-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15c07-131">See Also</span></span>  
 [<span data-ttu-id="15c07-132">Ajout de tâches par programmation</span><span class="sxs-lookup"><span data-stu-id="15c07-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
