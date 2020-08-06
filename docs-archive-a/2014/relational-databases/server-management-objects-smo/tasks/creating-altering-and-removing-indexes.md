---
title: Création, modification et suppression d’index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- indexes [SMO]
ms.assetid: ad1befa5-46e0-4895-b9d3-42852e07607b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc5c565dbade0849c8cedb584abaa102a71808f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612210"
---
# <a name="creating-altering-and-removing-indexes"></a><span data-ttu-id="2b96f-102">Création, modification et suppression d'index</span><span class="sxs-lookup"><span data-stu-id="2b96f-102">Creating, Altering, and Removing Indexes</span></span>
  <span data-ttu-id="2b96f-103">Dans la hiérarchie SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects), les index sont représentés par l'objet <xref:Microsoft.SqlServer.Management.Smo.Index>.</span><span class="sxs-lookup"><span data-stu-id="2b96f-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) hierarchy, indexes are represented by the <xref:Microsoft.SqlServer.Management.Smo.Index> object.</span></span> <span data-ttu-id="2b96f-104">Les colonnes indexées sont représentées par une collection d'objets <xref:Microsoft.SqlServer.Management.Smo.IndexedColumn> représentés par la propriété <xref:Microsoft.SqlServer.Management.Smo.Index.IndexedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b96f-104">The indexed columns are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.IndexedColumn> objects represented by the <xref:Microsoft.SqlServer.Management.Smo.Index.IndexedColumns%2A> property.</span></span>  
  
 <span data-ttu-id="2b96f-105">Vous pouvez créer un index sur une colonne XML en spécifiant la propriété <xref:Microsoft.SqlServer.Management.Smo.Index.IsXmlIndex%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Index>.</span><span class="sxs-lookup"><span data-stu-id="2b96f-105">You can create an index on a XML column by specifying the <xref:Microsoft.SqlServer.Management.Smo.Index.IsXmlIndex%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Index> object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2b96f-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="2b96f-106">Examples</span></span>  
 <span data-ttu-id="2b96f-107">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="2b96f-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="2b96f-108">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="2b96f-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-non-clustered-composite-index-in-visual-basic"></a><span data-ttu-id="2b96f-109">Création d'un index composite non cluster en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b96f-109">Creating a Non-Clustered, Composite Index in Visual Basic</span></span>  
 <span data-ttu-id="2b96f-110">Cet exemple de code montre comment créer un index composite non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-110">This code example demonstrates how to create a composite, nonclustered index.</span></span> <span data-ttu-id="2b96f-111">Pour un index composite, ajoutez plusieurs colonnes à l'index.</span><span class="sxs-lookup"><span data-stu-id="2b96f-111">For a composite index, add more than one column to the index.</span></span> <span data-ttu-id="2b96f-112">Affectez à la propriété <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> la valeur `False` pour un index non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-112">Set the <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> property to `False` for a nonclustered index.</span></span>  
  
```vb
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.SqlEnum.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Public Class A  
    Public Shared Sub Main()  
        ' Connect to the local, default instance of SQL Server.   
        Dim srv As Server  
        srv = New Server()  
  
        ' Reference the AdventureWorks2012 database.   
        Dim db As Database  
        db = srv.Databases("AdventureWorks2012")  
  
        ' Declare a Table object and reference the HumanResources table.   
        Dim tb As Table  
        tb = db.Tables("Employee", "HumanResources")  
  
        ' Define an Index object variable by providing the parent table and index name in the constructor.   
        Dim idx As Index  
        idx = New Index(tb, "TestIndex")  
  
        ' Add indexed columns to the index.   
        Dim icol1 As IndexedColumn  
        icol1 = New IndexedColumn(idx, "BusinessEntityID", True)  
        idx.IndexedColumns.Add(icol1)  
        Dim icol2 As IndexedColumn  
        icol2 = New IndexedColumn(idx, "HireDate", True)  
        idx.IndexedColumns.Add(icol2)  
  
        ' Set the index properties.   
        idx.IndexKeyType = IndexKeyType.DriUniqueKey  
        idx.IsClustered = False  
        idx.FillFactor = 50  
  
        ' Create the index on the instance of SQL Server.   
        idx.Create()  
  
        ' Modify the page locks property.   
        idx.DisallowPageLocks = True  
  
        ' Run the Alter method to make the change on the instance of SQL Server.   
        idx.Alter()  
  
        ' Remove the index from the table.   
        idx.Drop()  
    End Sub  
End Class
```  
  
## <a name="creating-a-non-clustered-composite-index-in-visual-c"></a><span data-ttu-id="2b96f-113">Création d'un index composite non cluster en Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b96f-113">Creating a Non-Clustered, Composite Index in Visual C#</span></span>  
 <span data-ttu-id="2b96f-114">Cet exemple de code montre comment créer un index composite non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-114">This code example demonstrates how to create a composite, nonclustered index.</span></span> <span data-ttu-id="2b96f-115">Pour un index composite, ajoutez plusieurs colonnes à l'index.</span><span class="sxs-lookup"><span data-stu-id="2b96f-115">For a composite index, add more than one column to the index.</span></span> <span data-ttu-id="2b96f-116">Affectez à la propriété <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> la valeur `False` pour un index non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-116">Set the <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> property to `False` for a nonclustered index.</span></span>  
  
```csharp
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.SqlEnum.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
using Microsoft.SqlServer.Management.Smo;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.   
      Server srv;  
      srv = new Server();  
  
      // Reference the AdventureWorks2012 database.   
      Database db;  
      db = srv.Databases["AdventureWorks2012"];  
  
      // Declare a Table object and reference the HumanResources table.   
      Table tb;  
      tb = db.Tables["Employee", "HumanResources"];  
  
      // Define an Index object variable by providing the parent table and index name in the constructor.   
      Index idx;  
      idx = new Index(tb, "TestIndex");  
  
      // Add indexed columns to the index.   
      IndexedColumn icol1;  
      icol1 = new IndexedColumn(idx, "BusinessEntityID", true);  
      idx.IndexedColumns.Add(icol1);  
      IndexedColumn icol2;  
      icol2 = new IndexedColumn(idx, "HireDate", true);  
      idx.IndexedColumns.Add(icol2);  
  
      // Set the index properties.   
      idx.IndexKeyType = IndexKeyType.DriUniqueKey;  
      idx.IsClustered = false;  
      idx.FillFactor = 50;  
  
      // Create the index on the instance of SQL Server.   
      idx.Create();  
  
      // Modify the page locks property.   
      idx.DisallowPageLocks = true;  
  
      // Run the Alter method to make the change on the instance of SQL Server.   
      idx.Alter();  
  
      // Remove the index from the table.   
      idx.Drop();  
   }  
}
```  
  
## <a name="creating-a-non-clustered-composite-index-in-powershell"></a><span data-ttu-id="2b96f-117">Création d'un index composite non cluster dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b96f-117">Creating a Non-Clustered, Composite Index in PowerShell</span></span>  
 <span data-ttu-id="2b96f-118">Cet exemple de code montre comment créer un index composite non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-118">This code example demonstrates how to create a composite, nonclustered index.</span></span> <span data-ttu-id="2b96f-119">Pour un index composite, ajoutez plusieurs colonnes à l'index.</span><span class="sxs-lookup"><span data-stu-id="2b96f-119">For a composite index, add more than one column to the index.</span></span> <span data-ttu-id="2b96f-120">Affectez à la propriété <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> la valeur `False` pour un index non cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-120">Set the <xref:Microsoft.SqlServer.Management.Smo.Index.IsClustered%2A> property to `False` for a nonclustered index.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and to the  
#database tables in Adventureworks2012  
CD \sql\localhost\default\databases\AdventureWorks2012\Tables\  
  
#Get a reference to the table  
$tb = Get-Item HumanResources.Employee  
  
#Define an Index object variable by providing the parent table and index name in the constructor.
$idx = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Index -argumentlist $tb, "TestIndex"  
  
#Add indexed columns to the index.
$icol1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn `  
-argumentlist $idx, "BusinessEntityId", $true  
$idx.IndexedColumns.Add($icol1)  
  
$icol2 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn `  
-argumentlist $idx, "HireDate", $true  
$idx.IndexedColumns.Add($icol2)  
  
#Set the index properties.
$idx.IndexKeyType = [Microsoft.SqlServer.Management.SMO.IndexKeyType]::DriUniqueKey
$idx.IsClustered = $false  
$idx.FillFactor = 50  
  
#Create the index on the instance of SQL Server.
$idx.Create()  
  
#Modify the page locks property.
$idx.DisallowPageLocks = $true
  
#Run the Alter method to make the change on the instance of SQL Server.
$idx.Alter()  
  
#Remove the index from the table.
$idx.Drop();  
```  
  
## <a name="creating-an-xml-index-in-visual-basic"></a><span data-ttu-id="2b96f-121">Création d'un index XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b96f-121">Creating an XML Index in Visual Basic</span></span>  
 <span data-ttu-id="2b96f-122">Cet exemple de code montre comment créer un index XML sur un type de données XML.</span><span class="sxs-lookup"><span data-stu-id="2b96f-122">This code example shows how to create an XML index on an XML data type.</span></span> <span data-ttu-id="2b96f-123">Le type de données XML est une collection de schémas XML appelée MySampleCollection, créée dans [Using XML Schemas](using-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="2b96f-123">The XML data type is an XML schema collection called MySampleCollection, which is created in [Using XML Schemas](using-xml-schemas.md).</span></span> <span data-ttu-id="2b96f-124">Les index XML présentent quelques restrictions, notamment ils doivent être créés sur une table possédant déjà une clé primaire en cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-124">XML indexes have some restrictions, one of which is that it must be created on a table that already has a clustered, primary key.</span></span>  
  
```vb
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.SqlEnum.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
    Public Shared Sub Main()  
        ' Connect to the local, default instance of SQL Server.   
        Dim srv As Server  
        srv = New Server()  
        Dim db1 As Database = srv.Databases("TESTDB")  
        ' Define a Table object variable and add an XML type column.   
        Dim tb As New Table(db1, "XmlTable3")  
  
        Dim mySample As New XmlSchemaCollection(db1, "Sample4", "dbo")  
        mySample.Text = "<xsd:schema xmlns:xsd=""http://www.w3.org/2001/XMLSchema"" targetNamespace=""NS2""> <xsd:element name=""elem1"" type=""xsd:integer""/></xsd:schema>"  
        mySample.Create()  
  
        Dim col11 As Column  
  
        ' This sample requires that an XML schema type called MySampleCollection exists on the database.   
        col11 = New Column(tb, "XMLValue", DataType.Xml("Sample4"))  
  
        ' Add another integer column that can be made into a unique, primary key.   
        tb.Columns.Add(col11)  
        Dim col21 As Column  
        col21 = New Column(tb, "Number", DataType.Int)  
        col21.Nullable = False  
        tb.Columns.Add(col21)  
  
        ' Create the table of the instance of SQL Server.   
        tb.Create()  
  
        ' Create a unique, clustered, primary key index on the integer column. This is required for an XML index.   
        Dim cp As Index  
        cp = New Index(tb, "clusprimindex3")  
        cp.IsClustered = True  
        cp.IndexKeyType = IndexKeyType.DriPrimaryKey  
        Dim cpcol As IndexedColumn  
        cpcol = New IndexedColumn(cp, "Number", True)  
        cp.IndexedColumns.Add(cpcol)  
        cp.Create()  
  
        ' Define and XML Index object variable by supplying the parent table and the XML index name arguments in the constructor.   
        Dim i As Index  
        i = New Index(tb, "xmlindex")  
        Dim ic As IndexedColumn  
        ic = New IndexedColumn(i, "XMLValue", True)  
        i.IndexedColumns.Add(ic)  
  
        ' Create the XML index on the instance of SQL Server.   
        i.Create()  
    End Sub  
End Class
```  
  
## <a name="creating-an-xml-index-in-visual-c"></a><span data-ttu-id="2b96f-125">Création d'un index XML en Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b96f-125">Creating an XML Index in Visual C#</span></span>  
 <span data-ttu-id="2b96f-126">Cet exemple de code montre comment créer un index XML sur un type de données XML.</span><span class="sxs-lookup"><span data-stu-id="2b96f-126">This code example shows how to create an XML index on an XML data type.</span></span> <span data-ttu-id="2b96f-127">Le type de données XML est une collection de schémas XML appelée MySampleCollection, créée dans [Using XML Schemas](using-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="2b96f-127">The XML data type is an XML schema collection called MySampleCollection, which is created in [Using XML Schemas](using-xml-schemas.md).</span></span> <span data-ttu-id="2b96f-128">Les index XML présentent quelques restrictions, notamment ils doivent être créés sur une table possédant déjà une clé primaire en cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-128">XML indexes have some restrictions, one of which is that it must be created on a table that already has a clustered, primary key.</span></span>  
  
```csharp
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.SqlEnum.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
using Microsoft.SqlServer.Management.Smo;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.   
      Server srv;  
      srv = new Server();  
      Database db1 = srv.Databases["TESTDB"];  
      // Define a Table object variable and add an XML type column.   
      Table tb = new Table(db1, "XmlTable3");  
  
      XmlSchemaCollection mySample = new XmlSchemaCollection(db1, "Sample4", "dbo");  
      mySample.Text = "<xsd:schema xmlns:xsd=\"http://www.w3.org/2001/XMLSchema\" targetNamespace=\"NS2\"> <xsd:element name=\"elem1\" type=\"xsd:integer\"/></xsd:schema>";  
      mySample.Create();  
  
      Column col11;  
  
      // This sample requires that an XML schema type called MySampleCollection exists on the database.   
      col11 = new Column(tb, "XMLValue", DataType.Xml("Sample4"));  
  
      // Add another integer column that can be made into a unique, primary key.   
      tb.Columns.Add(col11);  
      Column col21;  
      col21 = new Column(tb, "Number", DataType.Int);  
      col21.Nullable = false;  
      tb.Columns.Add(col21);  
  
      // Create the table of the instance of SQL Server.   
      tb.Create();  
  
      // Create a unique, clustered, primary key index on the integer column. This is required for an XML index.   
      Index cp;  
      cp = new Index(tb, "clusprimindex3");  
      cp.IsClustered = true;  
      cp.IndexKeyType = IndexKeyType.DriPrimaryKey;  
      IndexedColumn cpcol;  
      cpcol = new IndexedColumn(cp, "Number", true);  
      cp.IndexedColumns.Add(cpcol);  
      cp.Create();  
  
      // Define and XML Index object variable by supplying the parent table and the XML index name arguments in the constructor.   
      Index i;  
      i = new Index(tb, "xmlindex");  
      IndexedColumn ic;  
      ic = new IndexedColumn(i, "XMLValue", true);  
      i.IndexedColumns.Add(ic);  
  
      // Create the XML index on the instance of SQL Server.   
      i.Create();  
   }  
}
```  
  
## <a name="creating-an-xml-index-in-powershell"></a><span data-ttu-id="2b96f-129">Création d'un index XML dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b96f-129">Creating an XML Index in PowerShell</span></span>  
 <span data-ttu-id="2b96f-130">Cet exemple de code montre comment créer un index XML sur un type de données XML.</span><span class="sxs-lookup"><span data-stu-id="2b96f-130">This code example shows how to create an XML index on an XML data type.</span></span> <span data-ttu-id="2b96f-131">Le type de données XML est une collection de schémas XML appelée MySampleCollection, créée dans [Using XML Schemas](using-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="2b96f-131">The XML data type is an XML schema collection called MySampleCollection, which is created in [Using XML Schemas](using-xml-schemas.md).</span></span> <span data-ttu-id="2b96f-132">Les index XML présentent quelques restrictions, notamment ils doivent être créés sur une table possédant déjà une clé primaire en cluster.</span><span class="sxs-lookup"><span data-stu-id="2b96f-132">XML indexes have some restrictions, one of which is that it must be created on a table that already has a clustered, primary key.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to adventureworks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a Table object variable and add an XML type column.
#This sample requires that an XML schema type called MySampleCollection exists on the database.
#See sample on Creating an XML schema to do this  
$tb = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Table -argumentlist $db, "XmlTable"  
$Type = [Microsoft.SqlServer.Management.SMO.DataType]::Xml("MySampleCollection")  
$col1 =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -argumentlist $tb,"XMLValue", $Type  
$tb.Columns.Add($col1)  
  
#Add another integer column that can be made into a unique, primary key.
$Type = [Microsoft.SqlServer.Management.SMO.DataType]::Int  
$col2 =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -argumentlist $tb,"Number", $Type  
$col2.Nullable = $false  
$tb.Columns.Add($col2)  
  
#Create the table of the instance of SQL Server.
$tb.Create()  
  
#Create a unique, clustered, primary key index on the integer column. This is required for an XML index.
#Define an Index object variable by providing the parent table and index name in the constructor.
$cp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Index -argumentlist $tb, "clusprimindex"
$cp.IsClustered = $true;  
$cp.IndexKeyType = [Microsoft.SqlServer.Management.SMO.IndexKeyType]::DriPrimaryKey;  
  
#Create and add an indexed column to the index.
$cpcol = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn -argumentlist $cp, "Number", $true  
$cp.IndexedColumns.Add($cpcol)  
$cp.Create()  
  
#Define and XML Index object variable by supplying the parent table and  
# the XML index name arguments in the constructor.
$i = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Index -argumentlist $tb, "xmlindex"
  
#Create and add an indexed column to the index.
$ic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn -argumentlist $i, "XMLValue", $true
$i.IndexedColumns.Add($ic)  
  
#Create the XML index on the instance of SQL Server  
$i.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b96f-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b96f-133">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Index>  
