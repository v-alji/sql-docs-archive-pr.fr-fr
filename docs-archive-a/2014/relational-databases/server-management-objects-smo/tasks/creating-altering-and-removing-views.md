---
title: Création, modification et suppression de vues | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- views [SMO]
ms.assetid: 7d445c0e-77ef-4734-993b-e022de31df23
author: stevestein
ms.author: sstein
ms.openlocfilehash: fd8d75e413b1871ce4b8784f5087cb08ed08da73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613933"
---
# <a name="creating-altering-and-removing-views"></a><span data-ttu-id="d742a-102">Création, modification et suppression de vues</span><span class="sxs-lookup"><span data-stu-id="d742a-102">Creating, Altering, and Removing Views</span></span>
  <span data-ttu-id="d742a-103">Dans SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects), les vues [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sont représentées par l'objet <xref:Microsoft.SqlServer.Management.Smo.View>.</span><span class="sxs-lookup"><span data-stu-id="d742a-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] views are represented by the <xref:Microsoft.SqlServer.Management.Smo.View> object.</span></span>  
  
 <span data-ttu-id="d742a-104">La propriété <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.View> définit la vue.</span><span class="sxs-lookup"><span data-stu-id="d742a-104">The <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.View> object defines the view.</span></span> <span data-ttu-id="d742a-105">Cela revient à utiliser l'instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] SELECT pour créer une vue.</span><span class="sxs-lookup"><span data-stu-id="d742a-105">It is the equivalent of the [!INCLUDE[tsql](../../../includes/tsql-md.md)] SELECT statement for creating a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d742a-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="d742a-106">Example</span></span>  
 <span data-ttu-id="d742a-107">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="d742a-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="d742a-108">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="d742a-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-view-in-visual-basic"></a><span data-ttu-id="d742a-109">Création, modification et suppression d'une vue en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d742a-109">Creating, Altering, and Removing a View in Visual Basic</span></span>  
 <span data-ttu-id="d742a-110">Cet exemple de code montre comment créer une vue de deux tables en utilisant une jointure interne.</span><span class="sxs-lookup"><span data-stu-id="d742a-110">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="d742a-111">La vue est créée en utilisant le mode texte, donc la propriété <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> doit être définie.</span><span class="sxs-lookup"><span data-stu-id="d742a-111">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBViews1](SMO How to#SMO_VBViews1)]  -->  
  
## <a name="creating-altering-and-removing-a-view-in-visual-c"></a><span data-ttu-id="d742a-112">Création, modification et suppression d'une vue en Visual C#</span><span class="sxs-lookup"><span data-stu-id="d742a-112">Creating, Altering, and Removing a View in Visual C#</span></span>  
 <span data-ttu-id="d742a-113">Cet exemple de code montre comment créer une vue de deux tables en utilisant une jointure interne.</span><span class="sxs-lookup"><span data-stu-id="d742a-113">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="d742a-114">La vue est créée en utilisant le mode texte, donc la propriété <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> doit être définie.</span><span class="sxs-lookup"><span data-stu-id="d742a-114">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```csharp
{  
        //Connect to the local, default instance of SQL Server.   
        Server srv;   
        srv = new Server();   
        //Reference the AdventureWorks2012 database.   
        Database db;   
        db = srv.Databases["AdventureWorks2012"];   
        //Define a View object variable by supplying the parent database, view name and schema in the constructor.   
        View myview;   
        myview = new View(db, "Test_View", "Sales");   
        //Set the TextHeader and TextBody property to define the view.   
        myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS";   
        myview.TextBody = "SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID";   
        //Create the view on the instance of SQL Server.   
        myview.Create();   
        //Remove the view.   
        myview.Drop();   
        }  
```  
  
## <a name="creating-altering-and-removing-a-view-in-powershell"></a><span data-ttu-id="d742a-115">Création, modification et suppression d'une vue dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="d742a-115">Creating, Altering, and Removing a View in PowerShell</span></span>  
 <span data-ttu-id="d742a-116">Cet exemple de code montre comment créer une vue de deux tables en utilisant une jointure interne.</span><span class="sxs-lookup"><span data-stu-id="d742a-116">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="d742a-117">La vue est créée en utilisant le mode texte, donc la propriété <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> doit être définie.</span><span class="sxs-lookup"><span data-stu-id="d742a-117">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a View object variable by supplying the parent database, view name and schema in the constructor.
$myview  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.View -argumentlist $db, "Test_View", "Sales"  
  
# Set the TextHeader and TextBody property to define the view.
$myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS"  
$myview.TextBody ="SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID"  
  
# Create the view on the instance of SQL Server.
$myview.Create()  
  
# Remove the view
$myview.Drop();  
```  
  
## <a name="see-also"></a><span data-ttu-id="d742a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d742a-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.View>  
