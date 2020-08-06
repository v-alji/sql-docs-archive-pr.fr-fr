---
title: Mise à jour de colonnes UDT avec DataAdapters | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- ADO.NET [CLR integration]
- updating data [CLR integration]
- populating DataSet
- datasets [CLR integration]
- UDTs [CLR integration], ADO.NET
- updating UDT columns
- user-defined types [CLR integration], ADO.NET
- data adapters [CLR integration]
ms.assetid: 4489c938-ba03-4fdb-b533-cc3f5975ae50
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b908db850b1b77216824a5225d9bd8874387f78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611831"
---
# <a name="updating-udt-columns-with-dataadapters"></a><span data-ttu-id="f006c-102">Mise à jour de colonnes UDT avec DataAdapters</span><span class="sxs-lookup"><span data-stu-id="f006c-102">Updating UDT Columns with DataAdapters</span></span>
  <span data-ttu-id="f006c-103">Les types définis par l'utilisateur (UDT) sont pris en charge en utilisant un `System.Data.DataSet` et un `System.Data.SqlClient.SqlDataAdapter` pour extraire et modifier des données.</span><span class="sxs-lookup"><span data-stu-id="f006c-103">User-defined types (UDTs) are supported by using a `System.Data.DataSet` and a `System.Data.SqlClient.SqlDataAdapter` to retrieve and modify data.</span></span>  
  
## <a name="populating-a-dataset"></a><span data-ttu-id="f006c-104">Remplissage d'un dataset</span><span class="sxs-lookup"><span data-stu-id="f006c-104">Populating a Dataset</span></span>  
 <span data-ttu-id="f006c-105">Vous pouvez utiliser une instruction SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)] pour sélectionner des valeurs de colonne UDT pour remplir un dataset à l'aide d'un adaptateur de données.</span><span class="sxs-lookup"><span data-stu-id="f006c-105">You can use a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement to select UDT column values to populate a dataset using a data adapter.</span></span> <span data-ttu-id="f006c-106">L’exemple suivant suppose que vous avez une table de **points** définie avec la structure suivante et des exemples de données.</span><span class="sxs-lookup"><span data-stu-id="f006c-106">The following example assumes that you have a **Points** table defined with the following structure and some sample data.</span></span> <span data-ttu-id="f006c-107">Les [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions suivantes créent la table **points** et insèrent quelques lignes.</span><span class="sxs-lookup"><span data-stu-id="f006c-107">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements create the **Points** table and insert a few rows.</span></span>  
  
```  
CREATE TABLE dbo.Points (id int PRIMARY Key, p Point);  
  
INSERT INTO dbo.Points VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points VALUES (4, CONVERT(Point, '4,6'));  
GO  
```  
  
 <span data-ttu-id="f006c-108">Le fragment de code ADO.NET suivant récupère une chaîne de connexion valide, crée un nouveau `SqlDataAdapter` et remplit un `System.Data.DataTable` avec les lignes de données de la table des **points** .</span><span class="sxs-lookup"><span data-stu-id="f006c-108">The following ADO.NET code fragment retrieves a valid connection string, creates a new `SqlDataAdapter`, and populates a `System.Data.DataTable` with the rows of data from the **Points** table.</span></span>  
  
```vb  
Dim da As New SqlDataAdapter( _  
    "SELECT id, p FROM dbo.Points", connectionString)  
Dim datTable As New DataTable("Points")  
da.Fill(datTable)  
```  
  
```csharp  
SqlDataAdapter da = new SqlDataAdapter(  
   "SELECT id, p FROM dbo.Points", connectionString);  
DataTable datTable = new DataTable("Points");  
da.Fill(datTable);  
```  
  
## <a name="updating-udt-data-in-a-dataset"></a><span data-ttu-id="f006c-109">Mise à jour de données UDT dans un dataset</span><span class="sxs-lookup"><span data-stu-id="f006c-109">Updating UDT Data in a Dataset</span></span>  
 <span data-ttu-id="f006c-110">Vous pouvez utiliser deux méthodes pour mettre à jour une colonne UDT dans un `DataSet` :</span><span class="sxs-lookup"><span data-stu-id="f006c-110">You can use two methods to update a UDT column in a `DataSet`:</span></span>  
  
-   <span data-ttu-id="f006c-111">Fournissez des objets `InsertCommand`, `UpdateCommand` et `DeleteCommand` personnalisés pour un objet `SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f006c-111">Provide custom `InsertCommand`, `UpdateCommand` and `DeleteCommand` objects for a `SqlDataAdapter` object.</span></span>  
  
-   <span data-ttu-id="f006c-112">Utilisez le générateur de commandes (`System.Data.SqlClient.SqlCommandBuilder`) pour créer automatiquement les commandes INSERT, UPDATE et DELETE.</span><span class="sxs-lookup"><span data-stu-id="f006c-112">Use the command builder (`System.Data.SqlClient.SqlCommandBuilder`) to create automatically the INSERT, UPDATE, and DELETE commands for you.</span></span> <span data-ttu-id="f006c-113">Pour utiliser la détection de conflit, ajoutez une colonne `timestamp` (alias `rowversion`) à la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contient l'UDT.</span><span class="sxs-lookup"><span data-stu-id="f006c-113">In order to have conflict detection, add a `timestamp` column (alias `rowversion`) to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table that contains the UDT.</span></span> <span data-ttu-id="f006c-114">Le type de données `timestamp` vous permet de marquer la version des lignes dans une table. Il est unique dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="f006c-114">The `timestamp` data type allows you to version-stamp the rows in a table, and is guaranteed to be unique within a database.</span></span> <span data-ttu-id="f006c-115">Lorsqu'une valeur dans la table est modifiée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] met à jour automatiquement le nombre binaire de huit octets pour la ligne affectée par la modification.</span><span class="sxs-lookup"><span data-stu-id="f006c-115">When a value in the table is changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically updates the eight-byte binary number for the row affected by the change.</span></span>  
  
 <span data-ttu-id="f006c-116">Notez que le `SqlCommandBuilder` ne considère pas l'UDT pour la détection de conflit à moins qu'une colonne `timestamp` ne se trouve dans la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="f006c-116">Note that the `SqlCommandBuilder` does not consider the UDT for conflict detection unless there is a `timestamp` column in the underlying table.</span></span> <span data-ttu-id="f006c-117">Les UDT pouvant être comparables ou non, ils ne sont pas inclus dans la clause WHERE lorsque l'option de comparaison des valeurs d'origine est utilisée pour générer une commande.</span><span class="sxs-lookup"><span data-stu-id="f006c-117">UDTs may or may not be comparable, so they are not included in the WHERE clause when the "compare original values" option is used to generate a command.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f006c-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="f006c-118">Example</span></span>  
 <span data-ttu-id="f006c-119">L'exemple suivant requiert la création d'une deuxième table contenant la colonne UDT `Point` et une colonne `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="f006c-119">The following example requires the creation of a second table containing the `Point` UDT column as well as a `timestamp` column.</span></span> <span data-ttu-id="f006c-120">Les deux tables sont utilisées pour illustrer comment créer des objets de commande personnalisés pour mettre à jour des données et comment effectuer la mise à jour à l'aide d'une colonne `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="f006c-120">Both tables are used to illustrate how to create custom command objects to update data, and how to update using a `timestamp` column.</span></span> <span data-ttu-id="f006c-121">Exécutez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes pour créer la deuxième table et la remplir avec des exemples de données.</span><span class="sxs-lookup"><span data-stu-id="f006c-121">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to create the second table and populate it with sample data.</span></span>  
  
```  
CREATE TABLE dbo.Points_ts (id int PRIMARY KEY, p Point, ts timestamp);  
  
INSERT INTO dbo.Points_ts (id, p) VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (4, CONVERT(Point, '4,6'));  
```  
  
 <span data-ttu-id="f006c-122">L'exemple ADO.NET suivant contient deux méthodes :</span><span class="sxs-lookup"><span data-stu-id="f006c-122">The following ADO.NET example has two methods:</span></span>  
  
-   <span data-ttu-id="f006c-123">`UserProvidedCommands`, qui montre comment fournir `InsertCommand` `UpdateCommand` des objets, et `DeleteCommand` pour mettre à jour le `Point` type défini par l’utilisateur dans la table **points** (qui ne contient pas de `timestamp` colonne).</span><span class="sxs-lookup"><span data-stu-id="f006c-123">`UserProvidedCommands`, which demonstrates how to supply `InsertCommand`, `UpdateCommand`, and `DeleteCommand` objects for updating the `Point` UDT in the **Points** table (which does not contain a `timestamp` column).</span></span>  
  
-   <span data-ttu-id="f006c-124">`CommandBuilder`, qui montre comment utiliser un `SqlCommandBuilder` dans la table **Points_ts** qui contient la `timestamp` colonne.</span><span class="sxs-lookup"><span data-stu-id="f006c-124">`CommandBuilder`, which demonstrates how to use a `SqlCommandBuilder` in the **Points_ts** table that contains the `timestamp` column.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
    ' Retrieves the connection string  
    Private connString As String = GetConnectionString()  
  
    Sub Main()  
        UserProvidedCommands()  
        CommandBuilder()  
    End Sub  
  
    Private Sub UserProvidedCommands()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, p FROM dbo.Points", connString)  
  
        ' Setup the INSERT/UPDATE/DELETE commands  
        Dim idParam As SqlParameter  
        Dim pointParam As SqlParameter  
  
        da.InsertCommand = New SqlCommand( _  
          "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)", _  
          da.SelectCommand.Connection)  
        idParam = da.InsertCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.InsertCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.UpdateCommand = New SqlCommand( _  
          "UPDATE dbo.Points SET p = @p WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = _  
           da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.UpdateCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.DeleteCommand = New SqlCommand( _  
          "DELETE dbo.Points WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = da.DeleteCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
  
        ' Fill the DataTable with UDT rows  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(1), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if the DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(1), Point)  
            datTable.Rows(0)(1) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' If we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value.  
        datTable.Rows.Add(100, New Point(100, 200))  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
    Private Sub CommandBuilder()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, ts, p FROM dbo.Points_ts", connString)  
  
        ' Select a few rows with UDTs from the database  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(2), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(2), Point)  
            datTable.Rows(0)(2) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' if we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value  
        datTable.Rows.Add(100, Nothing, New Point(100, 200))  
  
        ' Use the CommandBuilder to generate DML statements  
        Dim bld As New SqlCommandBuilder(da)  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
  Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,   
      ' you can retrieve it from a configuration file.  
     Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
       & "Integrated Security=SSPI"  
   End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
  {  
// Retrieves the connection string  
private string connString = GetConnectionString();  
  
static void Main()  
{  
        UserProvidedCommands();  
        CommandBuilder();  
 }  
    static void UserProvidedCommands()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
          "SELECT id, p FROM dbo.Points", connString);  
  
        // Setup the INSERT/UPDATE/DELETE commands  
        SqlParameter idParam;  
        SqlParameter pointParam;  
  
        da.InsertCommand = new SqlCommand(  
            "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)",   
             da.SelectCommand.Connection);  
        idParam =   
            da.InsertCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.InsertCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";  
  
        da.UpdateCommand = new SqlCommand(  
            "UPDATE dbo.Points SET p = @p WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.UpdateCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";   
  
        da.DeleteCommand = new SqlCommand(  
            "DELETE dbo.Points WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.DeleteCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
  
        // Fill the DataTable with UDT rows  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach(DataRow r in datTable.Rows)   
        {  
            Point p = (Point)r[1];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if the DataTable has at least 1 row  
        if(datTable.Rows.Count > 0 )   
        {   
            Point oldPoint = (Point)datTable.Rows[0][1];  
            datTable.Rows[0][1] =   
                new Point(oldPoint.X+1, oldPoint.Y+1);  
        }  
  
        // Delete the last row  
        if(datTable.Rows.Count > 0 )   
        { // If we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value.  
        datTable.Rows.Add(100, new Point(100, 200));   
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
    static void CommandBuilder()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
            "SELECT id, ts, p FROM dbo.Points_ts", connString);  
  
        // Select a few rows with UDTs from the database  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach (DataRow r in datTable.Rows)  
        {  
            Point p = (Point)r[2];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if DataTable has at least 1 row  
        if (datTable.Rows.Count > 0)  
        {   
            Point oldPoint = (Point)datTable.Rows[0][2];  
            datTable.Rows[0][2] =   
                new Point(oldPoint.X + 1, oldPoint.Y + 1);  
        }  
  
        // Delete the last row  
        if (datTable.Rows.Count > 0)  
        { // if we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value  
        datTable.Rows.Add(100, null, new Point(100, 200));   
  
        // Use the CommandBuilder to generate DML statements  
        SqlCommandBuilder bld = new SqlCommandBuilder(da);  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion;  
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
 static private string GetConnectionString()  
 {  
 // To avoid storing the connection string in your code,   
 // you can retrieve it from a configuration file.  
    return "Data Source=localhost;Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f006c-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f006c-125">See Also</span></span>  
 [<span data-ttu-id="f006c-126">Accès aux types définis par l'utilisateur dans ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f006c-126">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
