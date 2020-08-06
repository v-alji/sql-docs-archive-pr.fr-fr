---
title: Procédures stockées CLR | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration], stored procedures
- stored procedures [CLR integration]
- common language runtime [SQL Server], stored procedures
- building database objects [CLR integration], stored procedures
- output parameters [CLR integration]
- tabular results
ms.assetid: bbdd51b2-a9b4-4916-ba6f-7957ac6c3f33
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f8c69435e28bfa67c72e26b7a54e419cd91ef220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602992"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="1f3a2-102">Procédures stockées CLR</span><span class="sxs-lookup"><span data-stu-id="1f3a2-102">CLR Stored Procedures</span></span>
  <span data-ttu-id="1f3a2-103">Les procédures stockées sont des routines que vous ne pouvez pas utiliser dans des expressions scalaires.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="1f3a2-104">Contrairement aux fonctions scalaires, elles peuvent retourner des résultats scalaires et des messages au client, appeler des instructions DDL (Data Definition Language) et DML (Data Manipulation Language) et retourner des paramètres de sortie.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-104">Unlike scalar functions, they can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span> <span data-ttu-id="1f3a2-105">Pour plus d’informations sur les avantages de l’intégration du CLR et le choix entre le code managé et [!INCLUDE[tsql](../../includes/tsql-md.md)] , consultez [vue d’ensemble de l’intégration du CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f3a2-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-stored-procedures"></a><span data-ttu-id="1f3a2-106">Configuration requise pour les procédures stockées CLR</span><span class="sxs-lookup"><span data-stu-id="1f3a2-106">Requirements for CLR Stored Procedures</span></span>  
 <span data-ttu-id="1f3a2-107">Dans le common language runtime (CLR), les procédures stockées sont implémentées en tant que méthodes statiques publiques sur une classe dans un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-107">In the common language runtime (CLR), stored procedures are implemented as public static methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly.</span></span> <span data-ttu-id="1f3a2-108">La méthode statique peut soit être déclarée de type « void », soit retourner une valeur entière.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-108">The static method can either be declared as void, or return an integer value.</span></span> <span data-ttu-id="1f3a2-109">Si elle retourne une valeur entière, l'entier retourné est traité comme le code de retour de la procédure.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-109">If it returns an integer value, the integer returned is treated as the return code from the procedure.</span></span> <span data-ttu-id="1f3a2-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-110">For example:</span></span>  
  
 `EXECUTE @return_status = procedure_name`  
  
 <span data-ttu-id="1f3a2-111">La @return_status variable contient la valeur retournée par la méthode.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-111">The @return_status variable will contain the value returned by the method.</span></span> <span data-ttu-id="1f3a2-112">Si la méthode est déclarée de type void, le code de retour est 0.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-112">If the method is declared void, the return code is 0.</span></span>  
  
 <span data-ttu-id="1f3a2-113">Si la méthode accepte des paramètres, le nombre de paramètres dans l'implémentation [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] doit être identique au nombre de paramètres employés dans la déclaration [!INCLUDE[tsql](../../includes/tsql-md.md)] de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-113">If the method takes parameters, the number of parameters in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] implementation should be the same as the number of parameters used in the [!INCLUDE[tsql](../../includes/tsql-md.md)] declaration of the stored procedure.</span></span>  
  
 <span data-ttu-id="1f3a2-114">Les paramètres passés à une procédure stockée CLR peuvent être de n'importe quel type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doté d'un équivalent en code managé.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-114">Parameters passed to a CLR stored procedure can be any of the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types that have an equivalent in managed code.</span></span> <span data-ttu-id="1f3a2-115">Pour que la syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] crée la procédure, ces types doivent être spécifiés avec le type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] natif équivalent le mieux approprié.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-115">For the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax to create the procedure, these types should be specified with the most appropriate native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type equivalent.</span></span> <span data-ttu-id="1f3a2-116">Pour plus d’informations sur les conversions de type, consultez [mappage des données de paramètres CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="1f3a2-116">For more information about type conversions, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="1f3a2-117">Paramètres table</span><span class="sxs-lookup"><span data-stu-id="1f3a2-117">Table-Valued Parameters</span></span>  
 <span data-ttu-id="1f3a2-118">Les paramètres table (types de tables définis par l'utilisateur et passés dans une procédure ou une fonction) offrent un moyen efficace pour passer plusieurs lignes de données au serveur.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-118">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="1f3a2-119">Ils procurent une fonctionnalité semblable aux tableaux de paramètres, mais offrent une meilleure souplesse et une intégration plus étroite à [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3a2-119">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1f3a2-120">Ils sont également susceptibles de générer de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-120">They also provide the potential for better performance.</span></span> <span data-ttu-id="1f3a2-121">Les paramètres table aident également à réduire le nombre d'allers-retours au serveur.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-121">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="1f3a2-122">Au lieu d'envoyer plusieurs demandes au serveur, comme avec une liste de paramètres scalaires, les données peuvent être envoyées au serveur en tant que paramètres table.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-122">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="1f3a2-123">Un type de table défini par l'utilisateur ne peut pas être passé en tant que paramètre table à une fonction ou à une procédure stockée managée s'exécutant dans le processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ni être retourné à partir de ces dernières.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-123">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="1f3a2-124">Pour plus d’informations sur TVP, consultez [utiliser des paramètres Table &#40;Moteur de base de données&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="1f3a2-124">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="returning-results-from-clr-stored-procedures"></a><span data-ttu-id="1f3a2-125">Retour des résultats des procédures stockées CLR</span><span class="sxs-lookup"><span data-stu-id="1f3a2-125">Returning Results from CLR Stored Procedures</span></span>  
 <span data-ttu-id="1f3a2-126">Plusieurs moyens permettent de retourner des informations des procédures stockées [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3a2-126">Information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures in several ways.</span></span> <span data-ttu-id="1f3a2-127">Il peut s'agir notamment de paramètres de sortie, de résultats sous forme de tableau et de messages.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-127">This includes output parameters, tabular results, and messages.</span></span>  
  
### <a name="output-parameters-and-clr-stored-procedures"></a><span data-ttu-id="1f3a2-128">Paramètres OUTPUT et procédures stockées CLR</span><span class="sxs-lookup"><span data-stu-id="1f3a2-128">OUTPUT Parameters and CLR Stored Procedures</span></span>  
 <span data-ttu-id="1f3a2-129">Tout comme avec les procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)], des informations peuvent être retournées de procédures stockées [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] à l'aide de paramètres OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-129">As with [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, information may be returned from [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures using OUTPUT parameters.</span></span> <span data-ttu-id="1f3a2-130">La syntaxe DML [!INCLUDE[tsql](../../includes/tsql-md.md)] utilisée pour créer des procédures stockées [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] est le même que celle employée pour créer des procédures stockées écrites dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3a2-130">The [!INCLUDE[tsql](../../includes/tsql-md.md)] DML syntax used for creating [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stored procedures is the same as that used for creating stored procedures written in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1f3a2-131">Le paramètre correspondant du code d'implémentation dans la classe [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] doit utiliser un paramètre passé par référence en guise d'argument.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-131">The corresponding parameter in the implementation code in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="1f3a2-132">Notez que Visual Basic ne prend pas en charge les paramètres de sortie de la même façon que C#.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-132">Note that Visual Basic does not support output parameters in the same way that C# does.</span></span> <span data-ttu-id="1f3a2-133">Vous devez spécifier le paramètre par référence et appliquer l' \<Out()> attribut pour représenter un paramètre de sortie, comme suit :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-133">You must specify the parameter by reference and apply the \<Out()> attribute to represent an OUTPUT parameter, as in the following:</span></span>  
  
```vb
Imports System.Runtime.InteropServices  
...  
Public Shared Sub PriceSum ( <Out()> ByRef value As SqlInt32)  
```  
  
 <span data-ttu-id="1f3a2-134">Le code ci-dessous présente une procédure stockée qui retourne des informations par le biais d'un paramètre OUTPUT :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-134">The following shows a stored procedure returning information through an OUTPUT parameter:</span></span>  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void PriceSum(out SqlInt32 value)  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         value = 0;  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT Price FROM Products", connection);  
         SqlDataReader reader = command.ExecuteReader();  
  
         using (reader)  
         {  
            while( reader.Read() )  
            {  
               value += reader.GetSqlInt32(0);  
            }  
         }           
      }  
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
Imports System.Runtime.InteropServices  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Executes a query and iterates over the results to perform a summation.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
  
        Using connection As New SqlConnection("context connection=true")  
           value = 0  
           Connection.Open()  
           Dim command As New SqlCommand("SELECT Price FROM Products", connection)  
           Dim reader As SqlDataReader  
           reader = command.ExecuteReader()  
  
           Using reader  
              While reader.Read()  
                 value += reader.GetSqlInt32(0)  
              End While  
           End Using  
        End Using          
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1f3a2-135">Une fois que l’assembly contenant la procédure stockée CLR ci-dessus a été généré et créé sur le serveur, le code suivant [!INCLUDE[tsql](../../includes/tsql-md.md)] est utilisé pour créer la procédure dans la base de données et spécifie *Sum* comme paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-135">Once the assembly containing the above CLR stored procedure has been built and created on the server, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] is used to create the procedure in the database, and specifies *sum* as an OUTPUT parameter.</span></span>  
  
```sql
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
-- if StoredProcedures class was inside a namespace, called MyNS,  
-- you would use:  
-- AS EXTERNAL NAME TestStoredProc.[MyNS.StoredProcedures].PriceSum  
```  
  
 <span data-ttu-id="1f3a2-136">Notez que *Sum* est déclaré en tant que `int` type de données SQL Server et que le paramètre *value* défini dans la procédure stockée CLR est spécifié en tant que type de `SqlInt32` données CLR.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-136">Note that *sum* is declared as an `int` SQL Server data type, and that the *value* parameter defined in the CLR stored procedure is specified as a `SqlInt32` CLR data type.</span></span> <span data-ttu-id="1f3a2-137">Lorsqu’un programme appelant exécute la procédure stockée CLR, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convertit automatiquement le `SqlInt32` type de données CLR en un `int` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type de données.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-137">When a calling program executes the CLR stored procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically converts the `SqlInt32` CLR data type to an `int`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  <span data-ttu-id="1f3a2-138">Pour plus d’informations sur les types de données CLR qui peuvent et ne peuvent pas être convertis, consultez [mappage des données de paramètres CLR](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="1f3a2-138">For more information about which CLR data types can and cannot be converted, see [Mapping CLR Parameter Data](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
### <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="1f3a2-139">Retour de résultats sous forme de tableau et de messages</span><span class="sxs-lookup"><span data-stu-id="1f3a2-139">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="1f3a2-140">Le retour au client de résultats sous forme de tableau et de messages s'effectue via l'objet `SqlPipe` obtenu en utilisant la propriété `Pipe` de la classe `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-140">Returning tabular results and messages to the client is done through the `SqlPipe` object, which is obtained by using the `Pipe` property of the `SqlContext` class.</span></span> <span data-ttu-id="1f3a2-141">L'objet `SqlPipe` emploie une méthode `Send`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-141">The `SqlPipe` object has a `Send` method.</span></span> <span data-ttu-id="1f3a2-142">En appelant la méthode `Send`, vous pouvez transmettre des données à l'application appelante par l'intermédiaire du canal.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-142">By calling the `Send` method, you can transmit data through the pipe to the calling application.</span></span>  
  
 <span data-ttu-id="1f3a2-143">Il existe plusieurs surcharges de la méthode `SqlPipe.Send`. L'une d'elles permet d'envoyer un `SqlDataReader`, une autre de simplement transmettre une chaîne de texte.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-143">These are several overloads of the `SqlPipe.Send` method, including one that sends a `SqlDataReader` and another that simply sends a text string.</span></span>  
  
###### <a name="returning-messages"></a><span data-ttu-id="1f3a2-144">Retour de messages</span><span class="sxs-lookup"><span data-stu-id="1f3a2-144">Returning Messages</span></span>  
 <span data-ttu-id="1f3a2-145">Utilisez `SqlPipe.Send(string)` pour envoyer des messages à l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-145">Use `SqlPipe.Send(string)` to send messages to the client application.</span></span> <span data-ttu-id="1f3a2-146">Le texte du message est limité à 8 000 caractères.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-146">The text of the message is limited to 8000 characters.</span></span> <span data-ttu-id="1f3a2-147">Si le message dépasse cette limite, il sera tronqué.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-147">If the message exceeds 8000 characters, it will be truncated.</span></span>  
  
###### <a name="returning-tabular-results"></a><span data-ttu-id="1f3a2-148">Retour de résultats sous forme de tableau</span><span class="sxs-lookup"><span data-stu-id="1f3a2-148">Returning Tabular Results</span></span>  
 <span data-ttu-id="1f3a2-149">Pour envoyer directement les résultats d'une requête au client, appliquez l'une des surcharges de la méthode `Execute` à l'objet `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-149">To send the results of a query directly to the client, use one of the overloads of the `Execute` method on the `SqlPipe` object.</span></span> <span data-ttu-id="1f3a2-150">C'est le moyen le plus efficace de retourner des résultats au client puisque les données sont transférées vers les tampons réseau sans être copiées dans la mémoire managée.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-150">This is the most efficient way to return results to the client, since the data is transferred to the network buffers without being copied into managed memory.</span></span> <span data-ttu-id="1f3a2-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-151">For example:</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the results to the client directly.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void ExecuteToClient()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version", connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
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
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub ExecuteToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1f3a2-152">Pour envoyer les résultats d'une requête exécutée précédemment via le fournisseur in-process (ou pour pré-traiter les données à l'aide d'une implémentation personnalisée de `SqlDataReader`), utilisez la surcharge de la méthode `Send` qui accepte un `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-152">To send the results of a query that was executed previously through the in-process provider (or to pre-process the data using a custom implementation of `SqlDataReader`), use the overload of the `Send` method that takes a `SqlDataReader`.</span></span> <span data-ttu-id="1f3a2-153">Cette méthode s'avère légèrement plus lente que la méthode directe décrite ci-avant mais offre une plus grande souplesse pour manipuler les données avant qu'elles ne soient transmises au client.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-153">This method is slightly slower than the direct method described previously, but it offers greater flexibility to manipulate the data before it is sent to the client.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Execute a command and send the resulting reader to the client  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendReaderToClient()  
   {  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("select @@version", connection);  
         SqlDataReader r = command.ExecuteReader();  
         SqlContext.Pipe.Send(r);  
      }  
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
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendReaderToClient()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1f3a2-154">Pour créer un jeu de résultats dynamique, le remplir et le transmettre au client, vous pouvez créer des enregistrements de la connexion actuelle et les envoyer à l'aide de la méthode `SqlPipe.Send`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-154">To create a dynamic result set, populate it and send it to the client, you can create records from the current connection and send them using `SqlPipe.Send`.</span></span>  
  
```csharp  
using System.Data;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
using System.Data.SqlTypes;  
  
public class StoredProcedures   
{  
   /// <summary>  
   /// Create a result set on the fly and send it to the client.  
   /// </summary>  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void SendTransientResultSet()  
   {  
      // Create a record object that represents an individual row, including it's metadata.  
      SqlDataRecord record = new SqlDataRecord(new SqlMetaData("stringcol", SqlDbType.NVarChar, 128));  
  
      // Populate the record.  
      record.SetSqlString(0, "Hello World!");  
  
      // Send the record to the client.  
      SqlContext.Pipe.Send(record);  
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
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub SendTransientResultSet()  
        ' Create a record object that represents an individual row, including it's metadata.  
        Dim record As New SqlDataRecord(New SqlMetaData("stringcol", SqlDbType.NVarChar, 128) )  
  
        ' Populate the record.  
        record.SetSqlString(0, "Hello World!")  
  
        ' Send the record to the client.  
        SqlContext.Pipe.Send(record)          
    End Sub  
End Class   
```  
  
 <span data-ttu-id="1f3a2-155">Voici un exemple d'envoi d'un résultat sous forme de tableau et d'un message via `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-155">Here is an example of sending a tabular result and a message through `SqlPipe`.</span></span>  
  
```csharp  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void HelloWorld()  
   {  
      SqlContext.Pipe.Send("Hello world! It's now " + System.DateTime.Now.ToString()+"\n");  
      using(SqlConnection connection = new SqlConnection("context connection=true"))   
      {  
         connection.Open();  
         SqlCommand command = new SqlCommand("SELECT ProductNumber FROM ProductMaster", connection);  
         SqlDataReader reader = command.ExecuteReader();  
         SqlContext.Pipe.Send(reader);  
      }  
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
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class StoredProcedures   
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub HelloWorld()  
        SqlContext.Pipe.Send("Hello world! It's now " & System.DateTime.Now.ToString() & "\n")  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT ProductNumber FROM ProductMaster", connection)  
            Dim reader As SqlDataReader  
            reader = command.ExecuteReader()  
            SqlContext.Pipe.Send(reader)  
        End Using  
    End Sub  
End Class   
```  
  
 <span data-ttu-id="1f3a2-156">La première méthode  `Send` envoie un message au client tandis que la deuxième transmet un résultat sous forme de tableau à l'aide de `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-156">The first `Send` sends a message to the client, while the second sends a tabular result using `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="1f3a2-157">Notez que ces exemples sont uniquement fournis à des fins d'illustration.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-157">Note that these examples are for illustrative purposes only.</span></span> <span data-ttu-id="1f3a2-158">Pour les applications qui exigent des calculs intensifs, les fonctions CLR conviennent mieux que de simples instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3a2-158">CLR functions are more appropriate than simple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for computation-intensive applications.</span></span> <span data-ttu-id="1f3a2-159">Une procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] quasi équivalente de l'exemple précédent est la suivante :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-159">An almost equivalent [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure to the previous example is:</span></span>  
  
```sql
CREATE PROCEDURE HelloWorld() AS  
BEGIN  
PRINT('Hello world!')  
SELECT ProductNumber FROM ProductMaster  
END;  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1f3a2-160">Les messages et les jeux de résultats sont extraits différemment dans l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-160">Messages and result sets are retrieved differently in the client application.</span></span> <span data-ttu-id="1f3a2-161">Par exemple, les [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] jeux de résultats s’affichent dans la vue **résultats** et les messages s’affichent dans le volet **messages** .</span><span class="sxs-lookup"><span data-stu-id="1f3a2-161">For instance, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] result sets appear in the **Results** view, and messages appear in the **Messages** pane.</span></span>  
  
 <span data-ttu-id="1f3a2-162">Si le code Visual C# ci-avant est enregistré dans un fichier MyFirstUdp.cs et compilé avec :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-162">If the above Visual C# code is saved in a file MyFirstUdp.cs and compiled with:</span></span>  
  
```console
csc /t:library /out:MyFirstUdp.dll MyFirstUdp.cs   
```  
  
 <span data-ttu-id="1f3a2-163">Ou si le code Visual Basic ci-dessus est enregistré dans un fichier MyFirstUdp.vb et compilé avec :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-163">Or, if the above Visual Basic code is saved in a file MyFirstUdp.vb and compiled with:</span></span>  
  
```console
vbc /t:library /out:MyFirstUdp.dll MyFirstUdp.vb   
```  
  
> [!NOTE]  
>  <span data-ttu-id="1f3a2-164">Depuis [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], les objets de base de données Visual C++ (notamment les procédures stockées) compilés avec `/clr:pure` ne sont pas pris en charge pour l'exécution.</span><span class="sxs-lookup"><span data-stu-id="1f3a2-164">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], Visual C++ database objects (such as stored procedures) compiled with `/clr:pure` are not supported for execution.</span></span>  
  
 <span data-ttu-id="1f3a2-165">L'assembly obtenu peut être inscrit et le point d'entrée appelé avec le DDL suivant :</span><span class="sxs-lookup"><span data-stu-id="1f3a2-165">The resulting assembly can be registered, and the entry point invoked, with the following DDL:</span></span>  
  
```sql
CREATE ASSEMBLY MyFirstUdp FROM 'C:\Programming\MyFirstUdp.dll';  
CREATE PROCEDURE HelloWorld  
AS EXTERNAL NAME MyFirstUdp.StoredProcedures.HelloWorld;  
EXEC HelloWorld;  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f3a2-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f3a2-166">See Also</span></span>  
 <span data-ttu-id="1f3a2-167">[Fonctions CLR définies par l’utilisateur](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="1f3a2-167">[CLR User-Defined Functions](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="1f3a2-168">[Types CLR définis par l’utilisateur](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="1f3a2-168">[CLR User-Defined Types](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 [<span data-ttu-id="1f3a2-169">Déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="1f3a2-169">CLR Triggers</span></span>](../../../2014/database-engine/dev-guide/clr-triggers.md)  
  
  
