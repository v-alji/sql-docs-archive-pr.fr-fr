---
title: Vue d’ensemble des attributs personnalisés d’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601079"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="668a6-102">Vue d'ensemble des attributs personnalisés de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="668a6-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="668a6-103">Le CLR (Common Language Runtime) du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] autorise l'utilisation de mots clés descriptifs, appelés attributs.</span><span class="sxs-lookup"><span data-stu-id="668a6-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="668a6-104">Ces attributs fournissent des informations supplémentaires sur de nombreux éléments, comme les méthodes et les classes.</span><span class="sxs-lookup"><span data-stu-id="668a6-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="668a6-105">Ils sont enregistrés dans l'assembly avec les métadonnées de l'objet et peuvent être utilisés pour décrire votre code à d'autres outils de développement ou pour affecter le comportement au moment de l'exécution au sein de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668a6-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="668a6-106">Lorsque vous enregistrez une routine CLR avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ce dernier dérive un jeu de propriétés relatives à la routine.</span><span class="sxs-lookup"><span data-stu-id="668a6-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="668a6-107">Ces propriétés déterminent les fonctionnalités de la routine, notamment sa capacité d'indexation.</span><span class="sxs-lookup"><span data-stu-id="668a6-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="668a6-108">Par exemple, l'affectation de la valeur `DataAccess` à la propriété `DataAccessKind.Read` vous permet d'accéder aux données des tables utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au sein d'une fonction CLR.</span><span class="sxs-lookup"><span data-stu-id="668a6-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="668a6-109">L’exemple suivant montre un cas simple dans lequel la `DataAccess` propriété est définie pour faciliter l’accès aux données à partir d’une table utilisateur **table1**.</span><span class="sxs-lookup"><span data-stu-id="668a6-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="668a6-110">Pour les routines [!INCLUDE[tsql](../../includes/tsql-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dérive directement leurs propriétés de leur définition.</span><span class="sxs-lookup"><span data-stu-id="668a6-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="668a6-111">Pour les routines CLR, le serveur n'analyse pas le corps de la routine pour dériver ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="668a6-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="668a6-112">À la place, vous pouvez utiliser des attributs personnalisés pour les classes et les membres des classes implémentés dans un langage du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668a6-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="668a6-113">Les attributs personnalisés nécessaires pour les routines CLR, les types définis par l'utilisateur et les agrégats sont définis dans l'espace de noms `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="668a6-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668a6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="668a6-114">See Also</span></span>  
 [<span data-ttu-id="668a6-115">Attributs personnalisés pour les routines CLR</span><span class="sxs-lookup"><span data-stu-id="668a6-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
