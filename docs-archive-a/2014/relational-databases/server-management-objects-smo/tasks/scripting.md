---
title: Scripts | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700926"
---
# <a name="scripting"></a><span data-ttu-id="50e41-102">Création de scripts</span><span class="sxs-lookup"><span data-stu-id="50e41-102">Scripting</span></span>
  <span data-ttu-id="50e41-103">L'écriture de scripts dans SMO est contrôlée par l'objet <xref:Microsoft.SqlServer.Management.Smo.Scripter> et ses objets enfants ou par la méthode `Script` sur des objets individuels.</span><span class="sxs-lookup"><span data-stu-id="50e41-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="50e41-104">L' <xref:Microsoft.SqlServer.Management.Smo.Scripter> objet contrôle le mappage à partir des relations de dépendance pour les objets sur une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50e41-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="50e41-105">L'écriture de scripts avancés à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.Scripter> et ses objets enfants est un processus en trois phases :</span><span class="sxs-lookup"><span data-stu-id="50e41-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="50e41-106">Découverte</span><span class="sxs-lookup"><span data-stu-id="50e41-106">Discovery</span></span>  
  
2.  <span data-ttu-id="50e41-107">Génération de la liste</span><span class="sxs-lookup"><span data-stu-id="50e41-107">List generation</span></span>  
  
3.  <span data-ttu-id="50e41-108">Génération du script</span><span class="sxs-lookup"><span data-stu-id="50e41-108">Script generation</span></span>  
  
 <span data-ttu-id="50e41-109">La phase de découverte utilise l'objet <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>.</span><span class="sxs-lookup"><span data-stu-id="50e41-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="50e41-110">À partir d'une liste URN d'objets, la méthode <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> retourne un objet <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> pour les objets de la liste URN.</span><span class="sxs-lookup"><span data-stu-id="50e41-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="50e41-111">Le paramètre booléen *fParents* est utilisé pour déterminer si les parents ou les enfants de l’objet spécifié doivent être découverts.</span><span class="sxs-lookup"><span data-stu-id="50e41-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="50e41-112">L'arborescence des dépendances peut être modifiée à ce stade.</span><span class="sxs-lookup"><span data-stu-id="50e41-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="50e41-113">Dans la phase de la génération de la liste, l'arborescence est transmise et la liste résultante est retournée.</span><span class="sxs-lookup"><span data-stu-id="50e41-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="50e41-114">Cette liste d'objets suit l'ordre d'écriture du script et peut être manipulée.</span><span class="sxs-lookup"><span data-stu-id="50e41-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="50e41-115">Les phases de génération de la liste utilisent la méthode <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> pour retourner un objet <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="50e41-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="50e41-116">L'objet <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> peut être modifié à ce stade.</span><span class="sxs-lookup"><span data-stu-id="50e41-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="50e41-117">Au cours de la troisième et dernière phase, un script est généré à l'aide de la liste et des options spécifiées.</span><span class="sxs-lookup"><span data-stu-id="50e41-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="50e41-118">Le résultat est retourné sous la forme d'un objet système <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="50e41-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="50e41-119">Au cours de cette phase, les noms des objets dépendants sont extraits de la collection Items des objets et propriétés <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>, comme <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> et <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="50e41-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50e41-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="50e41-120">Example</span></span>  
 <span data-ttu-id="50e41-121">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="50e41-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="50e41-122">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="50e41-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="50e41-123">Cet exemple de code requiert une instruction `Imports` pour l'espace de noms System.Collections.Specialized.</span><span class="sxs-lookup"><span data-stu-id="50e41-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="50e41-124">Insérez-la avec les autres instructions Imports, avant toute autre déclaration dans l'application.</span><span class="sxs-lookup"><span data-stu-id="50e41-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="50e41-125">Écriture sous forme de scripts des dépendances pour une base de données en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50e41-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="50e41-126">Cet exemple de code montre comment découvrir les dépendances et parcourir la liste pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="50e41-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="50e41-127">Écriture sous forme de scripts des dépendances pour une base de données en Visual C#</span><span class="sxs-lookup"><span data-stu-id="50e41-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="50e41-128">Cet exemple de code montre comment découvrir les dépendances et parcourir la liste pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="50e41-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="50e41-129">Écriture sous forme de scripts des dépendances pour une base de données dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="50e41-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="50e41-130">Cet exemple de code montre comment découvrir les dépendances et parcourir la liste pour afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="50e41-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
