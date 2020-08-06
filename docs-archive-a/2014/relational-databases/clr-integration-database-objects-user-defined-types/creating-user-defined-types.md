---
title: Création d’un type défini par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], creating
- UDTs [CLR integration], creating
ms.assetid: 0feb8b08-4062-467b-8433-e88e4e302738
author: rothja
ms.author: jroth
ms.openlocfilehash: bdbfc0ca605437bf0e55e8812faebafd0fa4bcc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602164"
---
# <a name="creating-a-user-defined-type"></a><span data-ttu-id="c9b5f-102">Création d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9b5f-102">Creating a User-Defined Type</span></span>
  <span data-ttu-id="c9b5f-103">Pour créer un type défini par l'utilisateur capable d'être installé dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez créer tout d'abord une classe dans l'un des langages de programmation .NET Framework pris en charge, tels que Visual C# ou Visual Basic, conforme aux spécifications de création de types définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-103">To create a user-defined type (UDT) capable of being installed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must first create a class in one of the supported .NET Framework programming languages, such as Visual C# or  Visual Basic, which conforms to the specifications for creating UDTs.</span></span> <span data-ttu-id="c9b5f-104">La classe peut ensuite être compilée en tant que bibliothèque de liens dynamiques (DLL), qui peut être chargée dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9b5f-104">The class can then be compiled as a dynamic-link library (DLL), which can be loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9b5f-105">Vous pouvez également créer et déployer des types définis par l'utilisateur à l'aide de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-105">You can also create and deploy UDTs using Visual Studio.</span></span>  
  
 <span data-ttu-id="c9b5f-106">La fonctionnalité d'exécution du code CLR est désactivée par défaut dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9b5f-106">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9b5f-107">Le CLR peut être activé en utilisant la procédure stockée système `sp_configure`, comme illustré dans les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9b5f-107">The CLR can be enabled by using the `sp_configure` system stored procedure, as shown in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
Reconfigure  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="c9b5f-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c9b5f-108">In This Section</span></span>  
 [<span data-ttu-id="c9b5f-109">Configuration requise pour les types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9b5f-109">User-Defined Type Requirements</span></span>](creating-user-defined-types-requirements.md)  
 <span data-ttu-id="c9b5f-110">Décrit les spécifications de codage des types définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-110">Describes the requirements for coding user-defined types.</span></span>  
  
 [<span data-ttu-id="c9b5f-111">Codage de types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9b5f-111">Coding User-Defined Types</span></span>](creating-user-defined-types-coding.md)  
 <span data-ttu-id="c9b5f-112">Illustre des techniques de codage impliquées dans la création des types définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-112">Demonstrates coding techniques involved in creating user-defined types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9b5f-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="c9b5f-113">Example</span></span>  
 <span data-ttu-id="c9b5f-114">La liste de code suivante définit l’UDT Point, qui est décrit en détail dans [codage des types définis par l’utilisateur](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="c9b5f-114">The following code listing defines the Point UDT, which is described in detail in [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="c9b5f-115">Le code complet pour les autres exemples discutés dans cette section peut être obtenu en installant les exemples CLR.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-115">The complete code listings for the other examples discussed in this section can be obtained by installing the CLR samples.</span></span> <span data-ttu-id="c9b5f-116">Pour obtenir des instructions sur l’installation de ces exemples, consultez [SQL Server moteur de base de données des exemples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="c9b5f-116">For instructions on installing these samples, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="c9b5f-117">C#</span><span class="sxs-lookup"><span data-stu-id="c9b5f-117">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Text;  
  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
     IsByteOrdered=true, ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
    private bool is_Null;  
    private Int32 _x;  
    private Int32 _y;  
  
    public bool IsNull  
    {  
        get  
        {  
            return (is_Null);  
        }  
    }  
  
    public static Point Null  
    {  
        get  
        {  
            Point pt = new Point();  
            pt.is_Null = true;  
            return pt;  
        }  
    }  
  
    // Use StringBuilder to provide string representation of UDT.  
    public override string ToString()  
    {  
        // Since InvokeIfReceiverIsNull defaults to 'true'  
        // this test is unnecessary if Point is only being called  
        // from SQL.  
        if (this.IsNull)  
            return "NULL";  
        else  
        {  
            StringBuilder builder = new StringBuilder();  
            builder.Append(_x);  
            builder.Append(",");  
            builder.Append(_y);  
            return builder.ToString();  
        }  
    }  
  
    [SqlMethod(OnNullCall = false)]  
    public static Point Parse(SqlString s)  
    {  
        // With OnNullCall=false, this check is unnecessary if   
        // Point only called from SQL.  
        if (s.IsNull)  
            return Null;  
  
        // Parse input string to separate out points.  
        Point pt = new Point();  
        string[] xy = s.Value.Split(",".ToCharArray());  
        pt.X = Int32.Parse(xy[0]);  
        pt.Y = Int32.Parse(xy[1]);  
  
        // Call ValidatePoint to enforce validation  
        // for string conversions.  
        if (!pt.ValidatePoint())   
            throw new ArgumentException("Invalid XY coordinate values.");  
        return pt;  
    }  
  
    // X and Y coordinates exposed as properties.  
    public Int32 X  
    {  
        get  
        {  
            return this._x;  
        }  
        // Call ValidatePoint to ensure valid range of Point values.  
        set   
        {  
            Int32 temp = _x;  
            _x = value;  
            if (!ValidatePoint())  
            {  
                _x = temp;  
                throw new ArgumentException("Invalid X coordinate value.");  
            }  
        }  
    }  
  
    public Int32 Y  
    {  
        get  
        {  
            return this._y;  
        }  
        set  
        {  
            Int32 temp = _y;  
            _y = value;  
            if (!ValidatePoint())  
            {  
                _y = temp;  
                throw new ArgumentException("Invalid Y coordinate value.");  
            }  
        }  
    }  
  
    // Validation method to enforce valid X and Y values.  
    private bool ValidatePoint()  
    {  
        // Allow only zero or positive integers for X and Y coordinates.  
        if ((_x >= 0) && (_y >= 0))  
        {  
            return true;  
        }  
        else  
        {  
            return false;  
        }  
    }  
  
    // Distance from 0 to Point method.  
    [SqlMethod(OnNullCall = false)]  
    public Double Distance()  
    {  
        return DistanceFromXY(0, 0);  
    }  
  
    // Distance from Point to the specified point method.  
    [SqlMethod(OnNullCall = false)]  
    public Double DistanceFrom(Point pFrom)  
    {  
        return DistanceFromXY(pFrom.X, pFrom.Y);  
    }  
  
    // Distance from Point to the specified x and y values method.  
    [SqlMethod(OnNullCall = false)]  
    public Double DistanceFromXY(Int32 iX, Int32 iY)  
    {  
        return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
    }  
}  
```  
  
 <span data-ttu-id="c9b5f-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9b5f-118">Visual Basic</span></span>  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Text  
  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
    Implements INullable  
  
    Private is_Null As Boolean  
    Private _x As Int32  
    Private _y As Int32  
  
    Public ReadOnly Property IsNull() As Boolean _  
       Implements INullable.IsNull  
        Get  
            Return (is_Null)  
        End Get  
    End Property  
  
    Public Shared ReadOnly Property Null() As Point  
        Get  
            Dim pt As New Point  
            pt.is_Null = True  
            Return (pt)  
        End Get  
    End Property  
  
    ' Use StringBuilder to provide string representation of UDT.  
    Public Overrides Function ToString() As String  
        ' Since InvokeIfReceiverIsNull defaults to 'true'  
        ' this test is unnecessary if Point is only being called  
        ' from SQL.  
        If Me.IsNull Then  
            Return "NULL"  
        Else  
            Dim builder As StringBuilder = New StringBuilder  
            builder.Append(_x)  
            builder.Append(",")  
            builder.Append(_y)  
            Return builder.ToString  
        End If  
    End Function  
  
    <SqlMethod(OnNullCall:=False)> _  
    Public Shared Function Parse(ByVal s As SqlString) As Point  
        ' With OnNullCall=False, this check is unnecessary if  
        ' Point only being called from SQL.  
        If s.IsNull Then  
            Return Null  
        End If  
  
        ' Parse input string here to separate out points.  
        Dim pt As New Point()  
        Dim xy() As String = s.Value.Split(",".ToCharArray())  
        pt.X = Int32.Parse(xy(0))  
        pt.Y = Int32.Parse(xy(1))  
  
        ' Call ValidatePoint to enforce validation  
        ' for string conversions.  
        If Not pt.ValidatePoint() Then  
            Throw New ArgumentException("Invalid XY coordinate values.")  
        End If  
        Return pt  
    End Function  
  
    ' X and Y coordinates are exposed as properties.  
    Public Property X() As Int32  
        Get  
            Return (Me._x)  
        End Get  
  
        Set(ByVal Value As Int32)  
            Dim temp As Int32 = _x  
            _x = Value  
            If Not ValidatePoint() Then  
                _x = temp  
                Throw New ArgumentException("Invalid X coordinate value.")  
            End If  
        End Set  
    End Property  
  
    Public Property Y() As Int32  
        Get  
            Return (Me._y)  
        End Get  
  
        Set(ByVal Value As Int32)  
            Dim temp As Int32 = _y  
            _y = Value  
            If Not ValidatePoint() Then  
                _y = temp  
                Throw New ArgumentException("Invalid Y coordinate value.")  
            End If  
        End Set  
    End Property  
  
    ' Validation method to enforce valid X and Y values.  
    Private Function ValidatePoint() As Boolean  
        ' Allow only zero or positive integers for X and Y coordinates.  
        If (_x >= 0) And (_y >= 0) Then  
            Return True  
        Else  
            Return False  
        End If  
    End Function  
  
    ' Distance from 0 to Point method.  
    <SqlMethod(OnNullCall:=False)> _  
  Public Function Distance() As Double  
        Return DistanceFromXY(0, 0)  
    End Function  
  
    ' Distance from Point to the specified point method.  
    <SqlMethod(OnNullCall:=False)> _  
    Public Function DistanceFrom(ByVal pFrom As Point) As Double  
        Return DistanceFromXY(pFrom.X, pFrom.Y)  
    End Function  
  
    ' Distance from Point to the specified x and y values method.  
    <SqlMethod(OnNullCall:=False)> _  
    Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
        As Double  
        Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
    End Function  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9b5f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9b5f-119">See Also</span></span>  
 [<span data-ttu-id="c9b5f-120">Types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9b5f-120">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
