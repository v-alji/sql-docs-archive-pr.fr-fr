---
title: Appel de fonctions d’agrégation CLR définies par l’utilisateur | Microsoft Docs
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
- aggregate functions [CLR integration]
- invoking user-defined aggregate functions
- user-defined functions [CLR integration]
ms.assetid: 5a188b50-7170-4069-acad-5de5c915f65d
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e92563e01d0065c40619f3208aaf74691496c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610686"
---
# <a name="invoking-clr-user-defined-aggregate-functions"></a><span data-ttu-id="39bd5-102">Appel de fonctions d'agrégation CLR définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="39bd5-102">Invoking CLR User-Defined Aggregate Functions</span></span>
  <span data-ttu-id="39bd5-103">Dans les instructions SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)] , vous pouvez appeler les agrégats CLR (Common Language Runtime) définis par l'utilisateur et soumis à toutes les règles qui s'appliquent aux fonctions d'agrégation système.</span><span class="sxs-lookup"><span data-stu-id="39bd5-103">In [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements, you can invoke common language runtime (CLR) user-defined aggregates, subject to all the rules that apply to system aggregate functions.</span></span>  
  
 <span data-ttu-id="39bd5-104">Les règles suivantes supplémentaires s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="39bd5-104">The following additional rules apply:</span></span>  
  
-   <span data-ttu-id="39bd5-105">L'utilisateur en cours doit disposer de l'autorisation `EXECUTE` sur l'agrégat défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="39bd5-105">The current user must have `EXECUTE` permission on the user-defined aggregate.</span></span>  
  
-   <span data-ttu-id="39bd5-106">Les agrégats définis par l'utilisateur doivent être appelés à l'aide d'un nom en deux parties, sous la forme *nom_schéma.nom_udagg*.</span><span class="sxs-lookup"><span data-stu-id="39bd5-106">User-defined aggregates must be invoked using a two-part name in the form of *schema_name.udagg_name*.</span></span>  
  
-   <span data-ttu-id="39bd5-107">Le type d’argument de l’agrégat défini par l’utilisateur doit correspondre ou être implicitement convertible en *INPUT_TYPE* de l’agrégat, comme défini dans l' `CREATE AGGREGATE` instruction.</span><span class="sxs-lookup"><span data-stu-id="39bd5-107">The argument type of the user-defined aggregate must match or be implicitly convertible to the *input_type* of the aggregate, as defined in the `CREATE AGGREGATE` statement.</span></span>  
  
-   <span data-ttu-id="39bd5-108">Le type de retour de l’agrégat défini par l’utilisateur doit correspondre à la *return_type* dans l' `CREATE AGGREGATE` instruction.</span><span class="sxs-lookup"><span data-stu-id="39bd5-108">The return type of the user-defined aggregate must match the *return_type* in the `CREATE AGGREGATE` statement.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="39bd5-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="39bd5-109">Example 1</span></span>  
 <span data-ttu-id="39bd5-110">Voici un exemple de fonction d'agrégation définie par l'utilisateur qui concatène un jeu de valeurs de chaîne extraites d'une colonne de table :</span><span class="sxs-lookup"><span data-stu-id="39bd5-110">The following is an example of a user-defined aggregate function that concatenates a set of string values taken from a column in a table:</span></span>  
  
 <span data-ttu-id="39bd5-111">[C#]</span><span class="sxs-lookup"><span data-stu-id="39bd5-111">[C#]</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
using System.IO;  
using System.Text;  
  
[Serializable]  
[SqlUserDefinedAggregate(  
    Format.UserDefined, //use clr serialization to serialize the intermediate result  
    IsInvariantToNulls = true, //optimizer property  
    IsInvariantToDuplicates = false, //optimizer property  
    IsInvariantToOrder = false, //optimizer property  
    MaxByteSize = 8000) //maximum size in bytes of persisted value  
]  
public class Concatenate : IBinarySerialize  
{  
    /// <summary>  
    /// The variable that holds the intermediate result of the concatenation  
    /// </summary>  
    private StringBuilder intermediateResult;  
  
    /// <summary>  
    /// Initialize the internal data structures  
    /// </summary>  
    public void Init()  
    {  
        this.intermediateResult = new StringBuilder();  
    }  
  
    /// <summary>  
    /// Accumulate the next value, not if the value is null  
    /// </summary>  
    /// <param name="value"></param>  
    public void Accumulate(SqlString value)  
    {  
        if (value.IsNull)  
        {  
            return;  
        }  
  
        this.intermediateResult.Append(value.Value).Append(',');  
    }  
  
    /// <summary>  
    /// Merge the partially computed aggregate with this aggregate.  
    /// </summary>  
    /// <param name="other"></param>  
    public void Merge(Concatenate other)  
    {  
        this.intermediateResult.Append(other.intermediateResult);  
    }  
  
    /// <summary>  
    /// Called at the end of aggregation, to return the results of the aggregation.  
    /// </summary>  
    /// <returns></returns>  
    public SqlString Terminate()  
    {  
        string output = string.Empty;  
        //delete the trailing comma, if any  
        if (this.intermediateResult != null  
            && this.intermediateResult.Length > 0)  
        {  
            output = this.intermediateResult.ToString(0, this.intermediateResult.Length - 1);  
        }  
  
        return new SqlString(output);  
    }  
  
    public void Read(BinaryReader r)  
    {  
        intermediateResult = new StringBuilder(r.ReadString());  
    }  
  
    public void Write(BinaryWriter w)  
    {  
        w.Write(this.intermediateResult.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="39bd5-112">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="39bd5-112">[Visual Basic]</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.IO  
Imports System.Text  
  
<Serializable(), SqlUserDefinedAggregate(Format.UserDefined, IsInvariantToNulls:=True, IsInvariantToDuplicates:=False, IsInvariantToOrder:=False, MaxByteSize:=8000)> _  
Public Class Concatenate  
    Implements IBinarySerialize  
  
    ''' <summary>  
    ''' The variable that holds the intermediate result of the concatenation  
    ''' </summary>  
    Private intermediateResult As StringBuilder  
  
    ''' <summary>  
    ''' Initialize the internal data structures  
    ''' </summary>  
    Public Sub Init()  
        Me.intermediateResult = New StringBuilder()  
    End Sub  
  
    ''' <summary>  
    ''' Accumulate the next value, not if the value is null  
    ''' </summary>  
    ''' <param name="value"></param>  
    Public Sub Accumulate(ByVal value As SqlString)  
        If value.IsNull Then  
            Return  
        End If  
  
        Me.intermediateResult.Append(value.Value).Append(","c)  
    End Sub  
    ''' <summary>  
    ''' Merge the partially computed aggregate with this aggregate.  
    ''' </summary>  
    ''' <param name="other"></param>  
    Public Sub Merge(ByVal other As Concatenate)  
        Me.intermediateResult.Append(other.intermediateResult)  
    End Sub  
  
    ''' <summary>  
    ''' Called at the end of aggregation, to return the results of the aggregation.  
    ''' </summary>  
    ''' <returns></returns>  
    Public Function Terminate() As SqlString  
        Dim output As String = String.Empty  
  
        'delete the trailing comma, if any  
        If Not (Me.intermediateResult Is Nothing) AndAlso Me.intermediateResult.Length > 0 Then  
            output = Me.intermediateResult.ToString(0, Me.intermediateResult.Length - 1)  
        End If  
  
        Return New SqlString(output)  
    End Function  
  
    Public Sub Read(ByVal r As BinaryReader) Implements IBinarySerialize.Read  
        intermediateResult = New StringBuilder(r.ReadString())  
    End Sub  
  
    Public Sub Write(ByVal w As BinaryWriter) Implements IBinarySerialize.Write  
        w.Write(Me.intermediateResult.ToString())  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="39bd5-113">Une fois que vous avez compilé le code dans **MyAgg.dll**, vous pouvez inscrire l'agrégat dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme suit :</span><span class="sxs-lookup"><span data-stu-id="39bd5-113">Once you compile the code into **MyAgg.dll**, you can register the aggregate in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as follows:</span></span>  
  
```  
CREATE ASSEMBLY MyAgg FROM 'C:\MyAgg.dll';  
GO  
CREATE AGGREGATE MyAgg (@input nvarchar(200)) RETURNS nvarchar(max)  
EXTERNAL NAME MyAgg.Concatenate;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="39bd5-114">L'exécution des objets de base de données Visual C++, tels que les fonctions scalaires, qui ont été compilés avec l'option /clr:pure du compilateur, n'est pas prise en charge dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39bd5-114">Visual C++ database objects, such as scalar-valued functions, that have been compiled with the /clr:pure compiler option are not supported for execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="39bd5-115">Comme dans le cas de la plupart des agrégats, l'essentiel de la logique se trouve dans la méthode `Accumulate`.</span><span class="sxs-lookup"><span data-stu-id="39bd5-115">As with most aggregates, the bulk of the logic is in the `Accumulate` method.</span></span> <span data-ttu-id="39bd5-116">Ici, la chaîne transmise comme paramètre à la méthode `Accumulate` vient s'ajouter à l'objet `StringBuilder` initialisé dans la méthode `Init`.</span><span class="sxs-lookup"><span data-stu-id="39bd5-116">Here, the string that is passed in as a parameter to the `Accumulate` method is appended to the `StringBuilder` object that was initialized in the `Init` method.</span></span> <span data-ttu-id="39bd5-117">En supposant qu'il ne s'agit pas du premier appel de la méthode `Accumulate`, une virgule est également ajoutée à l'objet `StringBuilder` avant l'ajout de la chaîne transmise.</span><span class="sxs-lookup"><span data-stu-id="39bd5-117">Assuming that this is not the first time the `Accumulate` method has been called, a comma is also appended to the `StringBuilder` prior to appending the passed-in string.</span></span> <span data-ttu-id="39bd5-118">À la fin des opérations de calcul, la méthode `Terminate` est appelée et retourne `StringBuilder` en tant que chaîne.</span><span class="sxs-lookup"><span data-stu-id="39bd5-118">At the conclusion of the computational tasks, the `Terminate` method is called, which returns the `StringBuilder` as a string.</span></span>  
  
 <span data-ttu-id="39bd5-119">Imaginons, par exemple, une table avec le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="39bd5-119">For example, consider a table with the following schema:</span></span>  
  
```  
CREATE TABLE BookAuthors  
(  
   BookID   int       NOT NULL,  
   AuthorName    nvarchar(200) NOT NULL  
);  
```  
  
 <span data-ttu-id="39bd5-120">Puis, insérons les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="39bd5-120">Then insert the following rows:</span></span>  
  
```  
INSERT BookAuthors VALUES(1, 'Johnson'),(2, 'Taylor'),(3, 'Steven'),(2, 'Mayler'),(3, 'Roberts'),(3, 'Michaels');  
```  
  
 <span data-ttu-id="39bd5-121">La requête suivante génère alors le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="39bd5-121">The following query would then produce the following result:</span></span>  
  
```  
SELECT BookID, dbo.MyAgg(AuthorName)  
FROM BookAuthors  
GROUP BY BookID;  
```  
  
|<span data-ttu-id="39bd5-122">BookID</span><span class="sxs-lookup"><span data-stu-id="39bd5-122">BookID</span></span>|<span data-ttu-id="39bd5-123">Noms d'auteur</span><span class="sxs-lookup"><span data-stu-id="39bd5-123">Author Names</span></span>|  
|------------|------------------|  
|<span data-ttu-id="39bd5-124">1</span><span class="sxs-lookup"><span data-stu-id="39bd5-124">1</span></span>|<span data-ttu-id="39bd5-125">Johnson</span><span class="sxs-lookup"><span data-stu-id="39bd5-125">Johnson</span></span>|  
|<span data-ttu-id="39bd5-126">2</span><span class="sxs-lookup"><span data-stu-id="39bd5-126">2</span></span>|<span data-ttu-id="39bd5-127">Taylor, Mayler</span><span class="sxs-lookup"><span data-stu-id="39bd5-127">Taylor, Mayler</span></span>|  
|<span data-ttu-id="39bd5-128">3</span><span class="sxs-lookup"><span data-stu-id="39bd5-128">3</span></span>|<span data-ttu-id="39bd5-129">Roberts, Michaels, Steven</span><span class="sxs-lookup"><span data-stu-id="39bd5-129">Roberts, Michaels, Steven</span></span>|  
  
## <a name="example-2"></a><span data-ttu-id="39bd5-130">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="39bd5-130">Example 2</span></span>  
 <span data-ttu-id="39bd5-131">L'exemple suivant illustre un agrégat avec deux paramètres sur la méthode `Accumulate`.</span><span class="sxs-lookup"><span data-stu-id="39bd5-131">The following sample shows an aggregate that has two parameters on the `Accumulate` method.</span></span>  
  
 <span data-ttu-id="39bd5-132">[C#]</span><span class="sxs-lookup"><span data-stu-id="39bd5-132">[C#]</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
[Serializable]  
[SqlUserDefinedAggregate(  
    Format.Native,  
    IsInvariantToDuplicates = false,  
    IsInvariantToNulls = true,  
    IsInvariantToOrder = true,  
    IsNullIfEmpty = true,  
    Name = "WeightedAvg")]  
public struct WeightedAvg  
{  
    /// <summary>  
    /// The variable that holds the intermediate sum of all values multiplied by their weight  
    /// </summary>  
    private long sum;  
  
    /// <summary>  
    /// The variable that holds the intermediate sum of all weights  
    /// </summary>  
    private int count;  
  
    /// <summary>  
    /// Initialize the internal data structures  
    /// </summary>  
    public void Init()  
    {  
        sum = 0;  
        count = 0;  
    }  
  
    /// <summary>  
    /// Accumulate the next value, not if the value is null  
    /// </summary>  
    /// <param name="Value">Next value to be aggregated</param>  
    /// <param name="Weight">The weight of the value passed to Value parameter</param>  
    public void Accumulate(SqlInt32 Value, SqlInt32 Weight)  
    {  
        if (!Value.IsNull && !Weight.IsNull)  
        {  
            sum += (long)Value * (long)Weight;  
            count += (int)Weight;  
        }  
    }  
  
    /// <summary>  
    /// Merge the partially computed aggregate with this aggregate  
    /// </summary>  
    /// <param name="Group">The other partial results to be merged</param>  
    public void Merge(WeightedAvg Group)  
    {  
        sum += Group.sum;  
        count += Group.count;  
    }  
  
    /// <summary>  
    /// Called at the end of aggregation, to return the results of the aggregation.  
    /// </summary>  
    /// <returns>The weighted average of all inputed values</returns>  
    public SqlInt32 Terminate()  
    {  
        if (count > 0)  
        {  
            int value = (int)(sum / count);  
            return new SqlInt32(value);  
        }  
        else  
        {  
            return SqlInt32.Null;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="39bd5-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="39bd5-133">[Visual Basic]</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> _  
<Serializable(), SqlUserDefinedAggregate(Format.Native, _  
IsInvariantToDuplicates:=False, _  
IsInvariantToNulls:=True, _  
IsInvariantToOrder:=True, _  
IsNullIfEmpty:=True, _  
Name:="WeightedAvg")> _  
Public Class WeightedAvg  
  
    ''' <summary>  
    ''' The variable that holds the intermediate sum of all values multiplied by their weight  
    ''' </summary>  
    Private sum As Long  
  
    ''' <summary>  
    ''' The variable that holds the intermediate sum of all weights  
    ''' </summary>  
    Private count As Integer  
  
    ''' <summary>  
    ''' The variable that holds the intermediate sum of all weights  
    ''' </summary>  
    Public Sub Init()  
        sum = 0  
        count = 0  
    End Sub  
  
    ''' <summary>  
    ''' Accumulate the next value, not if the value is null  
    ''' </summary>  
    ''' <param name="Value">Next value to be aggregated</param>  
    ''' <param name="Weight">The weight of the value passed to Value parameter</param>  
    Public Sub Accumulate(ByVal Value As SqlInt32, ByVal Weight As SqlInt32)  
        If Not Value.IsNull AndAlso Not Weight.IsNull Then  
            sum += CType(Value, Long) * CType(Weight, Long)  
            count += CType(Weight, Integer)  
        End If  
    End Sub  
  
    ''' <summary>  
    ''' Merge the partially computed aggregate with this aggregate.  
    ''' </summary>  
    ''' <param name="Group">The other partial results to be merged</param>  
    Public Sub Merge(ByVal Group As WeightedAvg)  
        sum = Group.sum  
        count = Group.count  
    End Sub  
  
    ''' <summary>  
    ''' Called at the end of aggregation, to return the results of the aggregation.  
    ''' </summary>  
    ''' <returns>The weighted average of all inputed values</returns>  
    Public Function Terminate() As SqlInt32  
        If count > 0 Then  
            ''                        int value = (int)(sum / count);  
            ''          return new SqlInt32(value);  
            Dim value As Integer = CType(sum / count, Integer)  
            Return New SqlInt32(value)  
        Else  
            Return SqlInt32.Null  
        End If  
    End Function  
End Class  
```  
  
 <span data-ttu-id="39bd5-134">Après avoir compilé le code source C# ou Visual Basic, exécutez la requête [!INCLUDE[tsql](../../includes/tsql-md.md)]suivante.</span><span class="sxs-lookup"><span data-stu-id="39bd5-134">After you compile the C# or Visual Basic source code, run the following [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="39bd5-135">Ce script part du principe que la DLL est appelée WghtAvg.dll et figure dans le répertoire racine de votre lecteur C.</span><span class="sxs-lookup"><span data-stu-id="39bd5-135">This script assumes that the DLL is called WghtAvg.dll and is in the root directory of your C drive.</span></span>  <span data-ttu-id="39bd5-136">Une base de données appelée test est également prise en compte.</span><span class="sxs-lookup"><span data-stu-id="39bd5-136">A database called test is also assumed.</span></span>  
  
```  
use test;  
go  
  
-- sp_configure 'clr enabled', 1;  
-- go  
  
--- RECONFIGURE WITH OVERRIDE;  
-- go  
  
IF EXISTS (SELECT name FROM systypes WHERE name = 'MyTableType')  
   DROP TYPE MyTableType;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'WeightedAvg')  
   DROP AGGREGATE WeightedAvg;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\WghtAvg.dll';  
GO  
  
CREATE AGGREGATE WeightedAvg (@value int, @weight int) RETURNS int  
EXTERNAL NAME MyClrCode.WeightedAvg;  
go  
  
CREATE TYPE MyTableType AS table (ItemValue int, ItemWeight int);  
go  
  
DECLARE @myTable AS MyTableType;  
  
INSERT INTO @myTable VALUES(1, 4), (6, 1);  
  
SELECT dbo.WeightedAvg(ItemValue, ItemWeight) FROM @myTable;  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="39bd5-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39bd5-137">See Also</span></span>  
 [<span data-ttu-id="39bd5-138">Agrégats CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="39bd5-138">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
  
  
