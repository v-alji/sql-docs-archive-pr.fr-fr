---
title: Récupération de données UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611834"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="e3d18-102">Extraction de données UDT</span><span class="sxs-lookup"><span data-stu-id="e3d18-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="e3d18-103">Pour créer un type défini par l'utilisateur (UDT) sur le client, l'assembly enregistré comme UDT dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être accessible par l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="e3d18-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="e3d18-104">L'assembly de type défini par l'utilisateur (UDT) peut être placé dans le même répertoire que l'application, ou dans le Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="e3d18-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="e3d18-105">Vous pouvez également définir une référence à l'assembly dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="e3d18-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="e3d18-106">Conditions requises pour utiliser les UDT dans ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3d18-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="e3d18-107">L'assembly chargé dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et l'assembly sur le client doivent être compatibles pour que l'UDT puisse être créé sur le client.</span><span class="sxs-lookup"><span data-stu-id="e3d18-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="e3d18-108">Pour les UDT définis avec le format de sérialisation `Native`, les assemblys doivent être structurellement compatibles.</span><span class="sxs-lookup"><span data-stu-id="e3d18-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="e3d18-109">Pour les assemblys définis avec le format `UserDefined`, l'assembly doit être disponible sur le client.</span><span class="sxs-lookup"><span data-stu-id="e3d18-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="e3d18-110">Vous n'avez pas besoin d'une copie de l'assembly UDT sur le client pour extraire les données brutes d'une colonne UDT d'une table.</span><span class="sxs-lookup"><span data-stu-id="e3d18-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3d18-111">**SqlClient** peut ne pas réussir à charger un UDT en cas de versions incompatibles UDT ou d’autres problèmes.</span><span class="sxs-lookup"><span data-stu-id="e3d18-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="e3d18-112">Dans ce cas, utilisez les mécanismes de résolution des problèmes traditionnels pour déterminer pourquoi l'application appelante ne peut pas trouver l'assembly contenant l'UDT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="e3d18-113">Pour plus d'informations, lisez la rubrique intitulée « Diagnostic d'erreurs avec les Assistants de débogage managés » dans la documentation du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3d18-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="e3d18-114">Accès aux UDT avec un SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="e3d18-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="e3d18-115">Un `System.Data.SqlClient.SqlDataReader` peut être utilisé à partir du code client pour extraire un jeu de résultats contenant une colonne UDT, exposée comme instance de l'objet.</span><span class="sxs-lookup"><span data-stu-id="e3d18-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3d18-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="e3d18-116">Example</span></span>  
 <span data-ttu-id="e3d18-117">Cet exemple montre comment utiliser la méthode `Main` pour créer un nouvel objet `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="e3d18-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="e3d18-118">Les actions suivantes se produisent dans l'exemple de code :</span><span class="sxs-lookup"><span data-stu-id="e3d18-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="e3d18-119">La méthode Main crée un nouvel objet `SqlDataReader` et extrait les valeurs de la table Points, qui possède une colonne UDT intitulée Point.</span><span class="sxs-lookup"><span data-stu-id="e3d18-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="e3d18-120">L'UDT Point expose les coordonnées X et Y définies comme entiers.</span><span class="sxs-lookup"><span data-stu-id="e3d18-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="e3d18-121">L'UDT définit une méthode `Distance` et une méthode `GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="e3d18-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="e3d18-122">L'exemple de code extrait les valeurs de la clé primaire et les colonnes UDT pour montrer les fonctions de l'UDT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="e3d18-123">L'exemple de code appelle les méthodes `Point.Distance` et `Point.GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="e3d18-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="e3d18-124">Les résultats s'affichent dans la fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="e3d18-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3d18-125">L'application doit déjà avoir une référence à l'assembly UDT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="e3d18-126">Liaison des UDT comme octets</span><span class="sxs-lookup"><span data-stu-id="e3d18-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="e3d18-127">Dans certaines situations, vous pouvez extraire les données brutes de la colonne UDT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="e3d18-128">Peut-être le type n'est-il pas disponible localement ou ne souhaitez-vous pas instancier une instance de l'UDT.</span><span class="sxs-lookup"><span data-stu-id="e3d18-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="e3d18-129">Vous pouvez lire les octets bruts dans un tableau d’octets à l’aide de la méthode **GetBytes** d’un `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="e3d18-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="e3d18-130">Cette méthode lit un flux d'octets à partir de l'offset de colonne spécifié dans la mémoire tampon d'un tableau commençant à un offset de mémoire tampon donné.</span><span class="sxs-lookup"><span data-stu-id="e3d18-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="e3d18-131">Une autre option consiste à utiliser l’une des méthodes **GetSqlBytes** ou **GetSqlBinary** et à lire tout le contenu en une seule opération.</span><span class="sxs-lookup"><span data-stu-id="e3d18-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="e3d18-132">Dans l'un et l'autre cas, comme l'objet UDT n'est jamais instancié, vous n'avez pas besoin de définir une référence à l'UDT dans l'assembly client.</span><span class="sxs-lookup"><span data-stu-id="e3d18-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3d18-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="e3d18-133">Example</span></span>  
 <span data-ttu-id="e3d18-134">Cet exemple montre comment récupérer les données de **point** en tant qu’octets bruts dans un tableau d’octets à l’aide d’un `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="e3d18-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="e3d18-135">Le code utilise un `System.Text.StringBuilder` pour convertir les octets bruts en une représentation sous forme de chaîne à afficher dans la fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="e3d18-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="e3d18-136">Exemple utilisant GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="e3d18-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="e3d18-137">Cet exemple montre comment récupérer les données de **point** en tant qu’octets bruts en une seule opération à l’aide de la méthode **GetSqlBytes** .</span><span class="sxs-lookup"><span data-stu-id="e3d18-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="e3d18-138">Le code utilise un `StringBuilder` pour convertir les octets bruts en une représentation sous forme de chaîne à afficher dans la fenêtre de la console.</span><span class="sxs-lookup"><span data-stu-id="e3d18-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="e3d18-139">Utilisation des paramètres UDT</span><span class="sxs-lookup"><span data-stu-id="e3d18-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="e3d18-140">Les paramètres UDT peuvent être utilisés comme paramètres d'entrée et de sortie dans votre code ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e3d18-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="e3d18-141">Utilisation des UDT dans les paramètres de requête</span><span class="sxs-lookup"><span data-stu-id="e3d18-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="e3d18-142">Les UDT peuvent être utilisés comme valeurs de paramètre lors de la définition d'un `SqlParameter` pour un objet `System.Data.SqlClient.SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="e3d18-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="e3d18-143">L'énumération `SqlDbType.Udt` d'un objet `SqlParameter` est utilisée pour indiquer que le paramètre est un UDT lors de l'appel de la méthode `Add` à la collection `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="e3d18-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="e3d18-144">La `UdtTypeName` propriété d’un `SqlCommand` objet est utilisée pour spécifier le nom complet de l’UDT dans la base de données à l’aide de la syntaxe *Database. schema_name. object_name* .</span><span class="sxs-lookup"><span data-stu-id="e3d18-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="e3d18-145">Sans être obligatoire, l'utilisation du nom complet supprime l'ambiguïté de votre code.</span><span class="sxs-lookup"><span data-stu-id="e3d18-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3d18-146">Une copie locale de l'assembly UDT doit être accessible par le projet client.</span><span class="sxs-lookup"><span data-stu-id="e3d18-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3d18-147">Exemple</span><span class="sxs-lookup"><span data-stu-id="e3d18-147">Example</span></span>  
 <span data-ttu-id="e3d18-148">Le code de cet exemple crée les objets `SqlCommand` et `SqlParameter` pour insérer les données dans une colonne UDT d'une table.</span><span class="sxs-lookup"><span data-stu-id="e3d18-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="e3d18-149">Le code utilise l'énumération `SqlDbType.Udt` pour spécifier le type de données et la propriété `UdtTypeName` de l'objet `SqlParameter` pour spécifier le nom complet de l'UDT dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e3d18-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3d18-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e3d18-150">See Also</span></span>  
 [<span data-ttu-id="e3d18-151">Accès aux types définis par l'utilisateur dans ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3d18-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
