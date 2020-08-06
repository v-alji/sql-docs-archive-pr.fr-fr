---
title: Fonctions table CLR | Microsoft Docs
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
- Transact-SQL table-valued functions
- table-valued functions [CLR integration]
- TVFs [CLR integration]
ms.assetid: 9a6133ea-36e9-45bf-b572-1c0df3d6c194
author: rothja
ms.author: jroth
ms.openlocfilehash: b700aba5a753ecd8ee50ee9b7679cafb2f1f8581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610688"
---
# <a name="clr-table-valued-functions"></a><span data-ttu-id="4e352-102">Fonctions table CLR</span><span class="sxs-lookup"><span data-stu-id="4e352-102">CLR Table-Valued Functions</span></span>
  <span data-ttu-id="4e352-103">Une fonction table est une fonction définie par l'utilisateur qui retourne une table.</span><span class="sxs-lookup"><span data-stu-id="4e352-103">A table-valued function is a user-defined function that returns a table.</span></span>  
  
 <span data-ttu-id="4e352-104">Depuis [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étend les fonctionnalités des fonctions table en vous permettant de définir une fonction table dans n'importe quel langage managé.</span><span class="sxs-lookup"><span data-stu-id="4e352-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extends the functionality of table-valued functions by allowing you to define a table-valued function in any managed language.</span></span> <span data-ttu-id="4e352-105">Les données sont retournées à partir d'une fonction table via un objet `IEnumerable` ou `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="4e352-105">Data is returned from a table-valued function through an `IEnumerable` or `IEnumerator` object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e352-106">Pour les fonctions table, les colonnes du type de la table de retour ne peuvent pas inclure de colonnes timestamp ou de colonnes de type de données chaîne non-Unicode (par exemple `char`, `varchar` et `text`).</span><span class="sxs-lookup"><span data-stu-id="4e352-106">For table-valued functions, the columns of the return table type cannot include timestamp columns or non-Unicode string data type columns (such as `char`, `varchar`, and `text`).</span></span> <span data-ttu-id="4e352-107">La contrainte NOT NULL n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4e352-107">The NOT NULL constraint is not supported.</span></span>  
  
## <a name="differences-between-transact-sql-and-clr-table-valued-functions"></a><span data-ttu-id="4e352-108">Différences entre les fonctions table Transact-SQL et CLR</span><span class="sxs-lookup"><span data-stu-id="4e352-108">Differences Between Transact-SQL and CLR Table-Valued Functions</span></span>  
 <span data-ttu-id="4e352-109">Les fonctions table [!INCLUDE[tsql](../../includes/tsql-md.md)] matérialisent les résultats de l'appel de la fonction dans une table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="4e352-109">[!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued functions materialize the results of calling the function into an intermediate table.</span></span> <span data-ttu-id="4e352-110">Dans la mesure où elles utilisent une table intermédiaire, elles peuvent prendre en charge des contraintes et des index uniques sur les résultats.</span><span class="sxs-lookup"><span data-stu-id="4e352-110">Since they use an intermediate table, they can support constraints and unique indexes over the results.</span></span> <span data-ttu-id="4e352-111">Ces fonctionnalités peuvent être extrêmement utiles lorsque des résultats sont retournés en grande quantité.</span><span class="sxs-lookup"><span data-stu-id="4e352-111">These features can be extremely useful when large results are returned.</span></span>  
  
 <span data-ttu-id="4e352-112">Par opposition, les fonctions table CLR représentent une solution d'accès en continu.</span><span class="sxs-lookup"><span data-stu-id="4e352-112">In contrast, CLR table-valued functions represent a streaming alternative.</span></span> <span data-ttu-id="4e352-113">Il n'est pas obligatoire que le jeu de résultats entier soit matérialisé dans une table unique.</span><span class="sxs-lookup"><span data-stu-id="4e352-113">There is no requirement that the entire set of results be materialized in a single table.</span></span> <span data-ttu-id="4e352-114">L'objet `IEnumerable` retourné par la fonction managée est appelé directement par le plan d'exécution de la requête qui appelle la fonction table ; par ailleurs, les résultats sont consommés de façon incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="4e352-114">The `IEnumerable` object returned by the managed function is directly called by the execution plan of the query that calls the table-valued function, and the results are consumed in an incremental manner.</span></span> <span data-ttu-id="4e352-115">Ce modèle d'accès en continu garantit que les résultats peuvent être consommés dès que la première ligne est disponible, au lieu d'attendre le remplissage de la table entière.</span><span class="sxs-lookup"><span data-stu-id="4e352-115">This streaming model ensures that results can be consumed immediately after the first row is available, instead of waiting for the entire table to be populated.</span></span> <span data-ttu-id="4e352-116">Il s'agit également d'une solution plus appropriée si de très nombreuses lignes sont retournées, car elles n'ont pas à être matérialisées en totalité en mémoire.</span><span class="sxs-lookup"><span data-stu-id="4e352-116">It is also a better alternative if you have very large numbers of rows returned, because they do not have to be materialized in memory as a whole.</span></span> <span data-ttu-id="4e352-117">Par exemple, une fonction table managée peut être utilisée pour analyser un fichier texte et retourner chaque ligne de texte sous forme de ligne de table.</span><span class="sxs-lookup"><span data-stu-id="4e352-117">For example, a managed table-valued function could be used to parse a text file and return each line as a row.</span></span>  
  
## <a name="implementing-table-valued-functions"></a><span data-ttu-id="4e352-118">Implémentation de fonctions table</span><span class="sxs-lookup"><span data-stu-id="4e352-118">Implementing Table-Valued Functions</span></span>  
 <span data-ttu-id="4e352-119">Vous devez implémenter les fonctions table en tant que méthodes d'une classe dans un assembly [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e352-119">Implement table-valued functions as methods on a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework assembly.</span></span> <span data-ttu-id="4e352-120">Le code de votre fonction table doit implémenter l'interface `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="4e352-120">Your table-valued function code must implement the `IEnumerable` interface.</span></span> <span data-ttu-id="4e352-121">L'interface `IEnumerable` est définie dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e352-121">The `IEnumerable` interface is defined in the .NET Framework.</span></span> <span data-ttu-id="4e352-122">Les types qui représentent des tableaux et des collections dans le .NET Framework implémentent déjà l'interface `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="4e352-122">Types representing arrays and collections in the .NET Framework already implement the `IEnumerable` interface.</span></span> <span data-ttu-id="4e352-123">Cela facilite l'écriture de fonctions table qui convertissent une collection ou un tableau en un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="4e352-123">This makes it easy for writing table-valued functions that convert a collection or an array into a result set.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="4e352-124">Paramètres table</span><span class="sxs-lookup"><span data-stu-id="4e352-124">Table-Valued Parameters</span></span>  
 <span data-ttu-id="4e352-125">Les paramètres table sont des types de tables définis par l'utilisateur et passés à une procédure ou une fonction, et qui offrent un moyen efficace pour passer plusieurs lignes de données au serveur.</span><span class="sxs-lookup"><span data-stu-id="4e352-125">Table-valued parameters are user-defined table types that are passed into a procedure or function and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="4e352-126">Ils procurent une fonctionnalité semblable aux tableaux de paramètres, mais offrent une meilleure souplesse et une intégration plus étroite à [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e352-126">Table-valued parameters provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4e352-127">Ils sont également susceptibles de générer de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="4e352-127">They also provide the potential for better performance.</span></span> <span data-ttu-id="4e352-128">Les paramètres table permettent également de réduire le nombre d’allers-retours au serveur.</span><span class="sxs-lookup"><span data-stu-id="4e352-128">Table-valued parameters also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="4e352-129">Au lieu d’envoyer plusieurs demandes au serveur, comme avec une liste de paramètres scalaires, les données peuvent être envoyées au serveur en tant que paramètre table.</span><span class="sxs-lookup"><span data-stu-id="4e352-129">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a table-valued parameter.</span></span> <span data-ttu-id="4e352-130">Un type de table défini par l'utilisateur ne peut pas être passé en tant que paramètre table à une fonction ou à une procédure stockée managée s'exécutant dans le processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ni être retourné à partir de ces dernières.</span><span class="sxs-lookup"><span data-stu-id="4e352-130">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="4e352-131">Pour plus d’informations sur les paramètres table, consultez [Utiliser les paramètres table &#40;moteur de base de données&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="4e352-131">For more information about table-valued parameters, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="output-parameters-and-table-valued-functions"></a><span data-ttu-id="4e352-132">Paramètres de sortie et fonctions table</span><span class="sxs-lookup"><span data-stu-id="4e352-132">Output Parameters and Table-Valued Functions</span></span>  
 <span data-ttu-id="4e352-133">Des informations peuvent être retournées à partir de fonctions table via des paramètres de sortie.</span><span class="sxs-lookup"><span data-stu-id="4e352-133">Information may be returned from table-valued functions using output parameters.</span></span> <span data-ttu-id="4e352-134">Le paramètre correspondant de la fonction table du code d'implémentation doit utiliser un paramètre passé par référence en guise d'argument.</span><span class="sxs-lookup"><span data-stu-id="4e352-134">The corresponding parameter in the implementation code table-valued function should use a pass-by-reference parameter as the argument.</span></span> <span data-ttu-id="4e352-135">Notez que Visual Basic ne prend pas en charge les paramètres de sortie de la même manière que Visual C#.</span><span class="sxs-lookup"><span data-stu-id="4e352-135">Note that Visual Basic does not support output parameters in the same way that Visual C# does.</span></span> <span data-ttu-id="4e352-136">Vous devez spécifier le paramètre par référence et appliquer l' \<Out()> attribut pour représenter un paramètre de sortie, comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e352-136">You must specify the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
...  
Public Shared Sub FillRow ( <Out()> ByRef value As SqlInt32)  
```  
  
### <a name="defining-a-table-valued-function-in-transact-sql"></a><span data-ttu-id="4e352-137">Définition d'une fonction table dans Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e352-137">Defining a Table-Valued Function in Transact-SQL</span></span>  
 <span data-ttu-id="4e352-138">La syntaxe permettant de définir une fonction table CLR est semblable à celle d'une fonction table [!INCLUDE[tsql](../../includes/tsql-md.md)], avec l'ajout de la clause `EXTERNAL NAME`.</span><span class="sxs-lookup"><span data-stu-id="4e352-138">The syntax for defining a CLR table-valued function is similar to that of a [!INCLUDE[tsql](../../includes/tsql-md.md)] table-valued function, with the addition of the `EXTERNAL NAME` clause.</span></span> <span data-ttu-id="4e352-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4e352-139">For example:</span></span>  
  
```  
CREATE FUNCTION GetEmpFirstLastNames()  
RETURNS TABLE (FirstName NVARCHAR(4000), LastName NVARCHAR(4000))  
EXTERNAL NAME MyDotNETAssembly.[MyNamespace.MyClassname]. GetEmpFirstLastNames;  
```  
  
 <span data-ttu-id="4e352-140">Les fonctions table sont utilisées pour représenter les données sous forme relationnelle pour un traitement supplémentaire dans les requêtes, par exemple :</span><span class="sxs-lookup"><span data-stu-id="4e352-140">Table-valued functions are used to represent data in relational form for further processing in queries such as:</span></span>  
  
```  
select * from function();  
select * from tbl join function() f on tbl.col = f.col;  
select * from table t cross apply function(t.column);  
```  
  
 <span data-ttu-id="4e352-141">Les fonctions table peuvent retourner une table dans les circonstances suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e352-141">Table-valued functions can return a table when:</span></span>  
  
-   <span data-ttu-id="4e352-142">Les fonctions table sont créées à partir d'arguments d'entrée scalaires.</span><span class="sxs-lookup"><span data-stu-id="4e352-142">Created from scalar input arguments.</span></span> <span data-ttu-id="4e352-143">Par exemple, une fonction table peut accepter une chaîne de nombres délimités par des virgules et retourner ces derniers sous forme de table.</span><span class="sxs-lookup"><span data-stu-id="4e352-143">For example, a table-valued function that takes a comma-delimited string of numbers and pivots them into a table.</span></span>  
  
-   <span data-ttu-id="4e352-144">Les fonctions table sont générées à partir de données externes.</span><span class="sxs-lookup"><span data-stu-id="4e352-144">Generated from external data.</span></span> <span data-ttu-id="4e352-145">Par exemple, une fonction table peut lire le journal des événements et l'exposer sous forme de table.</span><span class="sxs-lookup"><span data-stu-id="4e352-145">For example, a table-valued function that reads the event log and exposes it as a table.</span></span>  
  
 <span data-ttu-id="4e352-146">**Remarque** Une fonction table peut uniquement effectuer l’accès aux données par le biais d’une [!INCLUDE[tsql](../../includes/tsql-md.md)] requête dans la `InitMethod` méthode, et non dans la `FillRow` méthode.</span><span class="sxs-lookup"><span data-stu-id="4e352-146">**Note** A table-valued function can only perform data access through a [!INCLUDE[tsql](../../includes/tsql-md.md)] query in the `InitMethod` method, and not in the `FillRow` method.</span></span> <span data-ttu-id="4e352-147">La méthode `InitMethod` doit être marquée avec la propriété d'attribut `SqlFunction.DataAccess.Read` si une requête [!INCLUDE[tsql](../../includes/tsql-md.md)] est effectuée.</span><span class="sxs-lookup"><span data-stu-id="4e352-147">The `InitMethod` should be marked with the `SqlFunction.DataAccess.Read` attribute property if a [!INCLUDE[tsql](../../includes/tsql-md.md)] query is performed.</span></span>  
  
## <a name="a-sample-table-valued-function"></a><span data-ttu-id="4e352-148">Exemple de fonction table</span><span class="sxs-lookup"><span data-stu-id="4e352-148">A Sample Table-Valued Function</span></span>  
 <span data-ttu-id="4e352-149">La fonction table suivante retourne des informations du journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="4e352-149">The following table-valued function returns information from the system event log.</span></span> <span data-ttu-id="4e352-150">La fonction accepte un seul argument de chaîne contenant le nom du journal des événements à lire.</span><span class="sxs-lookup"><span data-stu-id="4e352-150">The function takes a single string argument containing the name of the event log to read.</span></span>  
  
###### <a name="sample-code"></a><span data-ttu-id="4e352-151">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="4e352-151">Sample Code</span></span>  
  
```csharp  
using System;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Collections;  
using System.Data.SqlTypes;  
using System.Diagnostics;  
  
public class TabularEventLog  
{  
    [SqlFunction(FillRowMethodName = "FillRow")]  
    public static IEnumerable InitMethod(String logname)  
    {  
        return new EventLog(logname).Entries;    }  
  
    public static void FillRow(Object obj, out SqlDateTime timeWritten, out SqlChars message, out SqlChars category, out long instanceId)  
    {  
        EventLogEntry eventLogEntry = (EventLogEntry)obj;  
        timeWritten = new SqlDateTime(eventLogEntry.TimeWritten);  
        message = new SqlChars(eventLogEntry.Message);  
        category = new SqlChars(eventLogEntry.Category);  
        instanceId = eventLogEntry.InstanceId;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data.Sql  
Imports Microsoft.SqlServer.Server  
Imports System.Collections  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Public Class TabularEventLog  
    <SqlFunction(FillRowMethodName:="FillRow")> _  
    Public Shared Function InitMethod(ByVal logname As String) As IEnumerable  
        Return New EventLog(logname).Entries  
    End Function  
  
    Public Shared Sub FillRow(ByVal obj As Object, <Out()> ByRef timeWritten As SqlDateTime, <Out()> ByRef message As SqlChars, <Out()> ByRef category As SqlChars, <Out()> ByRef instanceId As Long)  
        Dim eventLogEnTry As EventLogEntry = CType(obj, EventLogEntry)  
        timeWritten = New SqlDateTime(eventLogEnTry.TimeWritten)  
        message = New SqlChars(eventLogEnTry.Message)  
        category = New SqlChars(eventLogEnTry.Category)  
        instanceId = eventLogEnTry.InstanceId  
    End Sub  
End Class  
```  
  
###### <a name="declaring-and-using-the-sample-table-valued-function"></a><span data-ttu-id="4e352-152">Déclaration et utilisation de l'exemple de fonction table</span><span class="sxs-lookup"><span data-stu-id="4e352-152">Declaring and Using the Sample Table-Valued Function</span></span>  
 <span data-ttu-id="4e352-153">Une fois l'exemple de fonction table compilé, il peut être déclaré en [!INCLUDE[tsql](../../includes/tsql-md.md)] comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e352-153">After the sample table-valued function has been compiled, it can be declared in [!INCLUDE[tsql](../../includes/tsql-md.md)] like this:</span></span>  
  
```  
use master;  
-- Replace SQL_Server_logon with your SQL Server user credentials.  
GRANT EXTERNAL ACCESS ASSEMBLY TO [SQL_Server_logon];   
-- Modify the following line to specify a different database.  
ALTER DATABASE master SET TRUSTWORTHY ON;  
  
-- Modify the next line to use the appropriate database.  
CREATE ASSEMBLY tvfEventLog   
FROM 'D:\assemblies\tvfEventLog\tvfeventlog.dll'   
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
GO  
CREATE FUNCTION ReadEventLog(@logname nvarchar(100))  
RETURNS TABLE   
(logTime datetime,Message nvarchar(4000),Category nvarchar(4000),InstanceId bigint)  
AS   
EXTERNAL NAME tvfEventLog.TabularEventLog.InitMethod;  
GO  
```  
  
 <span data-ttu-id="4e352-154">L'exécution des objets de base de données Visual C++ compilés avec /clr:pure n'est pas prise en charge sur [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e352-154">Visual C++ database objects compiled with /clr:pure are not supported for execution on [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="4e352-155">Par exemple, de tels objets de base de données incluent des fonctions table.</span><span class="sxs-lookup"><span data-stu-id="4e352-155">For example, such database objects include table-valued functions.</span></span>  
  
 <span data-ttu-id="4e352-156">Pour tester l'exemple, essayez le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant :</span><span class="sxs-lookup"><span data-stu-id="4e352-156">To test the sample, try the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
```  
-- Select the top 100 events,  
SELECT TOP 100 *  
FROM dbo.ReadEventLog(N'Security') as T;  
go  
  
-- Select the last 10 login events.  
SELECT TOP 10 T.logTime, T.Message, T.InstanceId   
FROM dbo.ReadEventLog(N'Security') as T  
WHERE T.Category = N'Logon/Logoff';  
go  
```  
  
## <a name="sample-returning-the-results-of-a-sql-server-query"></a><span data-ttu-id="4e352-157">Exemple : retour des résultats d'une requête SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e352-157">Sample: Returning the Results of a SQL Server Query</span></span>  
 <span data-ttu-id="4e352-158">L'exemple suivant illustre une fonction table qui interroge une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e352-158">The following sample shows a table-valued function that queries a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4e352-159">Cet exemple utilise la base de données AdventureWorks Light de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e352-159">This sample uses the AdventureWorks Light database from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="4e352-160">[https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843)Pour plus d’informations sur le téléchargement d’AdventureWorks, consultez.</span><span class="sxs-lookup"><span data-stu-id="4e352-160">See [https://www.codeplex.com/sqlserversamples](https://go.microsoft.com/fwlink/?LinkId=87843) for more information on downloading AdventureWorks.</span></span>  
  
 <span data-ttu-id="4e352-161">Attribuez à votre fichier de code source le nom FindInvalidEmails.cs ou FindInvalidEmails.vb.</span><span class="sxs-lookup"><span data-stu-id="4e352-161">Name your source code file FindInvalidEmails.cs or FindInvalidEmails.vb.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
  
using Microsoft.SqlServer.Server;  
  
public partial class UserDefinedFunctions {  
   private class EmailResult {  
      public SqlInt32 CustomerId;  
      public SqlString EmailAdress;  
  
      public EmailResult(SqlInt32 customerId, SqlString emailAdress) {  
         CustomerId = customerId;  
         EmailAdress = emailAdress;  
      }  
   }  
  
   public static bool ValidateEmail(SqlString emailAddress) {  
      if (emailAddress.IsNull)  
         return false;  
  
      if (!emailAddress.Value.EndsWith("@adventure-works.com"))  
         return false;  
  
      // Validate the address. Put any more rules here.  
      return true;  
   }  
  
   [SqlFunction(  
       DataAccess = DataAccessKind.Read,  
       FillRowMethodName = "FindInvalidEmails_FillRow",  
       TableDefinition="CustomerId int, EmailAddress nvarchar(4000)")]  
   public static IEnumerable FindInvalidEmails(SqlDateTime modifiedSince) {  
      ArrayList resultCollection = new ArrayList();  
  
      using (SqlConnection connection = new SqlConnection("context connection=true")) {  
         connection.Open();  
  
         using (SqlCommand selectEmails = new SqlCommand(  
             "SELECT " +  
             "[CustomerID], [EmailAddress] " +  
             "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " +  
             "WHERE [ModifiedDate] >= @modifiedSince",  
             connection)) {  
            SqlParameter modifiedSinceParam = selectEmails.Parameters.Add(  
                "@modifiedSince",  
                SqlDbType.DateTime);  
            modifiedSinceParam.Value = modifiedSince;  
  
            using (SqlDataReader emailsReader = selectEmails.ExecuteReader()) {  
               while (emailsReader.Read()) {  
                  SqlString emailAddress = emailsReader.GetSqlString(1);  
                  if (ValidateEmail(emailAddress)) {  
                     resultCollection.Add(new EmailResult(  
                         emailsReader.GetSqlInt32(0),  
                         emailAddress));  
                  }  
               }  
            }  
         }  
      }  
  
      return resultCollection;  
   }  
  
   public static void FindInvalidEmails_FillRow(  
       object emailResultObj,  
       out SqlInt32 customerId,  
       out SqlString emailAdress) {  
      EmailResult emailResult = (EmailResult)emailResultObj;  
  
      customerId = emailResult.CustomerId;  
      emailAdress = emailResult.EmailAdress;  
   }  
};  
```  
  
```vb  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, ByRef customerId As SqlInt32, ByRef emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End ClassImports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Public Partial Class UserDefinedFunctions  
   Private Class EmailResult  
      Public CustomerId As SqlInt32  
      Public EmailAdress As SqlString  
  
      Public Sub New(customerId__1 As SqlInt32, emailAdress__2 As SqlString)  
         CustomerId = customerId__1  
         EmailAdress = emailAdress__2  
      End Sub  
   End Class  
  
   Public Shared Function ValidateEmail(emailAddress As SqlString) As Boolean  
      If emailAddress.IsNull Then  
         Return False  
      End If  
  
      If Not emailAddress.Value.EndsWith("@adventure-works.com") Then  
         Return False  
      End If  
  
      ' Validate the address. Put any more rules here.  
      Return True  
   End Function  
  
   <SqlFunction(DataAccess := DataAccessKind.Read, FillRowMethodName := "FindInvalidEmails_FillRow", TableDefinition := "CustomerId int, EmailAddress nvarchar(4000)")> _  
   Public Shared Function FindInvalidEmails(modifiedSince As SqlDateTime) As IEnumerable  
      Dim resultCollection As New ArrayList()  
  
      Using connection As New SqlConnection("context connection=true")  
         connection.Open()  
  
         Using selectEmails As New SqlCommand("SELECT " & "[CustomerID], [EmailAddress] " & "FROM [AdventureWorksLT2008].[SalesLT].[Customer] " & "WHERE [ModifiedDate] >= @modifiedSince", connection)  
            Dim modifiedSinceParam As SqlParameter = selectEmails.Parameters.Add("@modifiedSince", SqlDbType.DateTime)  
            modifiedSinceParam.Value = modifiedSince  
  
            Using emailsReader As SqlDataReader = selectEmails.ExecuteReader()  
               While emailsReader.Read()  
                  Dim emailAddress As SqlString = emailsReader.GetSqlString(1)  
                  If ValidateEmail(emailAddress) Then  
                     resultCollection.Add(New EmailResult(emailsReader.GetSqlInt32(0), emailAddress))  
                  End If  
               End While  
            End Using  
         End Using  
      End Using  
  
      Return resultCollection  
   End Function  
  
   Public Shared Sub FindInvalidEmails_FillRow(emailResultObj As Object, customerId As SqlInt32, emailAdress As SqlString)  
      Dim emailResult As EmailResult = DirectCast(emailResultObj, EmailResult)  
  
      customerId = emailResult.CustomerId  
      emailAdress = emailResult.EmailAdress  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="4e352-162">Compilez le code source dans une DLL et copiez la DLL dans le répertoire racine de votre lecteur C.</span><span class="sxs-lookup"><span data-stu-id="4e352-162">Compile the source code to a DLL and copy the DLL to the root directory of your C drive.</span></span>  <span data-ttu-id="4e352-163">Exécutez ensuite la requête [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante.</span><span class="sxs-lookup"><span data-stu-id="4e352-163">Then, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] query.</span></span>  
  
```  
use AdventureWorksLT2008;  
go  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'FindInvalidEmails')  
   DROP FUNCTION FindInvalidEmails;  
go  
  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'MyClrCode')  
   DROP ASSEMBLY MyClrCode;  
go  
  
CREATE ASSEMBLY MyClrCode FROM 'C:\FindInvalidEmails.dll'  
WITH PERMISSION_SET = SAFE -- EXTERNAL_ACCESS;  
GO  
  
CREATE FUNCTION FindInvalidEmails(@ModifiedSince datetime)   
RETURNS TABLE (  
   CustomerId int,  
   EmailAddress nvarchar(4000)  
)  
AS EXTERNAL NAME MyClrCode.UserDefinedFunctions.[FindInvalidEmails];  
go  
  
SELECT * FROM FindInvalidEmails('2000-01-01');  
go  
```  
  
