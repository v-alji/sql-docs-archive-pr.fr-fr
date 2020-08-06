---
title: SqlPipe, objet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- custom result sets [CLR integration]
- SqlPipe object
- tabular results
ms.assetid: 3e090faf-085f-4c01-a565-79e3f1c36e3b
author: rothja
ms.author: jroth
ms.openlocfilehash: 0044815a0b20d72b48b87bfe8f693d7196aaeaf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611120"
---
# <a name="sqlpipe-object"></a><span data-ttu-id="9ccc0-102">Objet SqlPipe</span><span class="sxs-lookup"><span data-stu-id="9ccc0-102">SqlPipe Object</span></span>
  <span data-ttu-id="9ccc0-103">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il est très fréquent d'écrire une procédure stockée (ou une procédure stockée étendue) qui envoie des résultats ou des paramètres de sortie au client appelant.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-103">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is very common to write a stored procedure (or an extended stored procedure) that sends results or output parameters to the calling client.</span></span>  
  
 <span data-ttu-id="9ccc0-104">Dans une procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)], toute instruction `SELECT` qui retourne zéro ou plusieurs lignes envoie les résultats au « canal » de l'appelant connecté.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-104">In a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, any `SELECT` statement that returns zero or more rows sends the results to the connected caller's "pipe."</span></span>  
  
 <span data-ttu-id="9ccc0-105">Pour les objets de base de données du CLR (Common Language Runtime) qui s'exécutent dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez envoyer les résultats au canal connecté à l'aide des méthodes `Send` de l'objet `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-105">For common language runtime (CLR) database objects running in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can send results to the connected pipe using the `Send` methods of the `SqlPipe` object.</span></span> <span data-ttu-id="9ccc0-106">Accédez à la propriété `Pipe` de l'objet `SqlContext` pour obtenir l'objet `SqlPipe`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-106">Access the `Pipe` property of the `SqlContext` object to obtain the `SqlPipe` object.</span></span> <span data-ttu-id="9ccc0-107">La classe `SqlPipe` est similaire sur le plan conceptuel à la classe `Response` présente dans ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-107">The `SqlPipe` class is conceptually similar to the `Response` class found in ASP.NET.</span></span> <span data-ttu-id="9ccc0-108">Pour plus d'informations, consultez la documentation de référence sur la classe SqlPipe dans le kit de développement logiciel (SDK) du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-108">For more information, see the SqlPipe Class reference documentation in the .NET Framework software development kit.</span></span>  
  
## <a name="returning-tabular-results-and-messages"></a><span data-ttu-id="9ccc0-109">Retour de résultats sous forme de tableau et de messages</span><span class="sxs-lookup"><span data-stu-id="9ccc0-109">Returning Tabular Results and Messages</span></span>  
 <span data-ttu-id="9ccc0-110">La classe `SqlPipe` possède une méthode `Send` avec trois surcharges.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-110">The `SqlPipe` has a `Send` method, which has three overloads.</span></span> <span data-ttu-id="9ccc0-111">Il s'agit de :</span><span class="sxs-lookup"><span data-stu-id="9ccc0-111">They are:</span></span>  
  
-   `void Send(string message)`  
  
-   `void Send(SqlDataReader reader)`  
  
-   `void Send(SqlDataRecord record)`  
  
 <span data-ttu-id="9ccc0-112">La méthode `Send` envoie des données directement au client ou à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-112">The `Send` method sends data straight to the client or caller.</span></span> <span data-ttu-id="9ccc0-113">C'est généralement le client qui utilise la sortie de la méthode `SqlPipe`, mais dans le cas de procédures stockées CLR imbriquées, le consommateur de sortie peut également être une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-113">It is usually the client that consumes the output from the `SqlPipe`, but in the case of nested CLR stored procedures the output consumer can also be a stored procedure.</span></span> <span data-ttu-id="9ccc0-114">Par exemple, Procedure1 appelle SqlCommand.ExecuteReader() avec le texte de commande "EXEC Procedure2".</span><span class="sxs-lookup"><span data-stu-id="9ccc0-114">For example, Procedure1 calls SqlCommand.ExecuteReader() with the command text "EXEC Procedure2".</span></span> <span data-ttu-id="9ccc0-115">Procedure2 est également une procédure stockée managée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-115">Procedure2 is also a managed stored procedure.</span></span> <span data-ttu-id="9ccc0-116">Si Procedure2 appelle maintenant SqlPipe.Send( SqlDataRecord), la ligne est envoyée au lecteur de Procedure1, pas au client.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-116">If Procedure2 now calls SqlPipe.Send( SqlDataRecord ), the row is sent to Procedure1's reader, not the client.</span></span>  
  
 <span data-ttu-id="9ccc0-117">La méthode `Send` envoie un message de chaîne qui apparaît sur le client sous forme de message d'information, équivalent à PRINT dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ccc0-117">The `Send` method sends a string message that appears on the client as an information message, equivalent to PRINT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9ccc0-118">Elle peut également envoyer un jeu de résultats à ligne unique à l'aide de `SqlDataRecord` ou un jeu de résultats à plusieurs ligne à l'aide d'un `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-118">It can also send a single-row result-set using `SqlDataRecord`, or a multi-row result-set using a `SqlDataReader`.</span></span>  
  
 <span data-ttu-id="9ccc0-119">L'objet `SqlPipe` possède également une méthode `ExecuteAndSend`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-119">The `SqlPipe` object also has an `ExecuteAndSend` method.</span></span> <span data-ttu-id="9ccc0-120">Cette méthode peut être utilisée pour exécuter une commande (passée en tant qu'objet `SqlCommand`) et renvoyer les résultats directement à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-120">This method can be used to execute a command (passed as a `SqlCommand` object) and send results directly back to the caller.</span></span> <span data-ttu-id="9ccc0-121">Si la commande qui a été envoyée contient des erreurs, des exceptions sont envoyées au canal, mais une copie est également envoyée au code managé appelant.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-121">If there are errors in the command that was submitted, exceptions are sent to the pipe, but a copy is also sent to calling managed code.</span></span> <span data-ttu-id="9ccc0-122">Si le code appelant n'intercepte pas l'exception, elle se propage vers le haut de la pile jusqu'au code [!INCLUDE[tsql](../../includes/tsql-md.md)] et apparaît deux fois dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-122">If the calling code does not catch the exception, it propagates up the stack to the [!INCLUDE[tsql](../../includes/tsql-md.md)] code and appears in the output twice.</span></span> <span data-ttu-id="9ccc0-123">Si le code appelant intercepte l'exception, le consommateur du canal continue à voir l'erreur, mais il n'y a pas d'erreur de duplication.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-123">If the calling code does catch the exception, the pipe consumer still sees the error, but there is not a duplicate error.</span></span>  
  
 <span data-ttu-id="9ccc0-124">Elle peut uniquement accepter un `SqlCommand` associé à la connexion contextuelle ; elle ne peut pas accepter de commande associée à la connexion non contextuelle.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-124">It can only take a `SqlCommand` that is associated with the context connection; it cannot take a command that is associated with the non-context connection.</span></span>  
  
## <a name="returning-custom-result-sets"></a><span data-ttu-id="9ccc0-125">Retour de jeux de résultats personnalisés</span><span class="sxs-lookup"><span data-stu-id="9ccc0-125">Returning Custom Result Sets</span></span>  
 <span data-ttu-id="9ccc0-126">Les procédures stockées managées peuvent envoyer des jeux de résultats qui ne proviennent pas d'un `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-126">Managed stored procedures can send result sets that do not come from a `SqlDataReader`.</span></span> <span data-ttu-id="9ccc0-127">La méthode `SendResultsStart`, ainsi que `SendResultsRow` et `SendResultsEnd`, permettent aux procédures stockées d'envoyer des jeux de résultats personnalisés au client.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-127">The `SendResultsStart` method, along with `SendResultsRow` and `SendResultsEnd`, allows stored procedures to send custom result sets to the client.</span></span>  
  
 <span data-ttu-id="9ccc0-128">`SendResultsStart` accepte un `SqlDataRecord` en tant qu'entrée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-128">`SendResultsStart` takes a `SqlDataRecord` as an input.</span></span> <span data-ttu-id="9ccc0-129">Elle  marque le début d'un jeu de résultats et utilise les métadonnées d'enregistrement pour construire les métadonnées qui décrivent le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-129">It marks the beginning of a result set and uses the record metadata to construct the metadata that describes the result set.</span></span> <span data-ttu-id="9ccc0-130">Elle n'envoie pas la valeur de l'enregistrement avec `SendResultsStart`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-130">It does not send the value of the record with `SendResultsStart`.</span></span> <span data-ttu-id="9ccc0-131">Toutes les lignes suivantes, envoyées à l'aide de `SendResultsRow`, doivent correspondre à cette définition des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-131">All the subsequent rows, sent using `SendResultsRow`, must match that metadata definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ccc0-132">Après l'appel de la méthode `SendResultsStart`, seules `SendResultsRow` et `SendResultsEnd` peuvent être appelées.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-132">After calling the `SendResultsStart` method only `SendResultsRow` and `SendResultsEnd` can be called.</span></span> <span data-ttu-id="9ccc0-133">L'appel de toute autre méthode dans la même instance de `SqlPipe` entraîne `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-133">Calling any other method in the same instance of `SqlPipe` causes an `InvalidOperationException`.</span></span> <span data-ttu-id="9ccc0-134">`SendResultsEnd` rétablit `SqlPipe` à son état initial, dans lequel d'autres méthodes peuvent être appelées.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-134">`SendResultsEnd` sets `SqlPipe` back to the initial state in which other methods can be called.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9ccc0-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ccc0-135">Example</span></span>  
 <span data-ttu-id="9ccc0-136">La procédure stockée `uspGetProductLine` retourne les nom, numéro de produit, couleur et tarif de tous les produits dans une ligne de produit spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-136">The `uspGetProductLine` stored procedure returns the name, product number, color, and list price of all products within a specified product line.</span></span> <span data-ttu-id="9ccc0-137">Cette procédure stockée accepte des correspondances exactes pour *prodLine*.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-137">This stored procedure accepts exact matches for *prodLine*.</span></span>  
  
 <span data-ttu-id="9ccc0-138">C#</span><span class="sxs-lookup"><span data-stu-id="9ccc0-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspGetProductLine(SqlString prodLine)  
{  
    // Connect through the context connection.  
    using (SqlConnection connection = new SqlConnection("context connection=true"))  
    {  
        connection.Open();  
  
        SqlCommand command = new SqlCommand(  
            "SELECT Name, ProductNumber, Color, ListPrice " +  
            "FROM Production.Product " +   
            "WHERE ProductLine = @prodLine;", connection);  
  
        command.Parameters.AddWithValue("@prodLine", prodLine);  
  
        try  
        {  
            // Execute the command and send the results to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command);  
        }  
        catch (System.Data.SqlClient.SqlException ex)  
        {  
            // An error occurred executing the SQL command.  
        }  
     }  
}  
};  
```  
  
 <span data-ttu-id="9ccc0-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ccc0-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub uspGetProductLine(ByVal prodLine As SqlString)  
    Dim command As SqlCommand  
  
    ' Connect through the context connection.  
    Using connection As New SqlConnection("context connection=true")  
        connection.Open()  
  
        command = New SqlCommand( _  
        "SELECT Name, ProductNumber, Color, ListPrice " & _  
        "FROM Production.Product " & _  
        "WHERE ProductLine = @prodLine;", connection)  
        command.Parameters.AddWithValue("@prodLine", prodLine)  
  
        Try  
            ' Execute the command and send the results   
            ' directly to the caller.  
            SqlContext.Pipe.ExecuteAndSend(command)  
        Catch ex As System.Data.SqlClient.SqlException  
            ' An error occurred executing the SQL command.  
        End Try  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="9ccc0-140">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante exécute la procédure `uspGetProduct`, qui retourne une liste de vélos de randonnée.</span><span class="sxs-lookup"><span data-stu-id="9ccc0-140">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement executes the `uspGetProduct` procedure, which returns a list of touring bike products.</span></span>  
  
```  
EXEC uspGetProductLineVB 'T';  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ccc0-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ccc0-141">See Also</span></span>  
 <span data-ttu-id="9ccc0-142">[SqlDataRecord, objet](sqldatarecord-object.md) </span><span class="sxs-lookup"><span data-stu-id="9ccc0-142">[SqlDataRecord Object](sqldatarecord-object.md) </span></span>  
 <span data-ttu-id="9ccc0-143">[Procédures stockées CLR](../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9ccc0-143">[CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="9ccc0-144">Extensions spécifiques in-process de SQL Server à ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ccc0-144">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
