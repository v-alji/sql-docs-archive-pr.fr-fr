---
title: Accès à la transaction en cours | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709663"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="021a6-102">Accès à la transaction actuelle</span><span class="sxs-lookup"><span data-stu-id="021a6-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="021a6-103">Si une transaction est active au point auquel du code Common Language Runtime (CLR) qui s'exécute sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est entré, la transaction est exposée à travers la classe `System.Transactions.Transaction`.</span><span class="sxs-lookup"><span data-stu-id="021a6-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="021a6-104">La propriété `Transaction.Current` est utilisée pour accéder à la transaction actuelle.</span><span class="sxs-lookup"><span data-stu-id="021a6-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="021a6-105">Dans la plupart des cas il n'est pas nécessaire d'accéder explicitement à la transaction.</span><span class="sxs-lookup"><span data-stu-id="021a6-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="021a6-106">Pour les connexions de base de données, ADO.NET vérifie `Transaction.Current` automatiquement lorsque la méthode `Connection.Open` est appelée et inscrit de façon transparente la connexion dans cette transaction (à moins que le mot clé `Enlist` n'ait la valeur « false » dans la chaîne de connexion).</span><span class="sxs-lookup"><span data-stu-id="021a6-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="021a6-107">Vous souhaiter peut-être utiliser l'objet `Transaction` directement dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="021a6-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="021a6-108">Si vous souhaitez inscrire une ressource qui n'effectue pas d'inscription automatique ou qui, pour une raison quelconque, n'a pas été inscrite pendant l'initialisation.</span><span class="sxs-lookup"><span data-stu-id="021a6-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="021a6-109">Si vous souhaitez inscrire explicitement une ressource dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="021a6-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="021a6-110">Si vous souhaitez mettre fin à la transaction externe à partir de votre procédure stockée ou fonction.</span><span class="sxs-lookup"><span data-stu-id="021a6-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="021a6-111">Dans ce cas, vous utilisez <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="021a6-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="021a6-112">Par exemple, le code suivant restaure la transaction actuelle :</span><span class="sxs-lookup"><span data-stu-id="021a6-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="021a6-113">Le reste de cette rubrique décrit d'autres manières d'annuler une transaction externe.</span><span class="sxs-lookup"><span data-stu-id="021a6-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="021a6-114">Annulation d'une transaction externe</span><span class="sxs-lookup"><span data-stu-id="021a6-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="021a6-115">Vous pouvez annuler des transactions externes à partir d'une procédure ou fonction managée des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="021a6-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="021a6-116">La procédure ou fonction managée peut renvoyer une valeur en utilisant un paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="021a6-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="021a6-117">La procédure [!INCLUDE[tsql](../../includes/tsql-md.md)] appelante peut vérifier la valeur renvoyée et, le cas échéant, exécuter `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="021a6-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="021a6-118">La procédure ou fonction managée peut lever une exception personnalisée.</span><span class="sxs-lookup"><span data-stu-id="021a6-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="021a6-119">La procédure appelante [!INCLUDE[tsql](../../includes/tsql-md.md)] peut intercepter l’exception levée par la procédure ou fonction managée dans un bloc try/catch et exécuter `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="021a6-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="021a6-120">La procédure ou fonction managée peut annuler la transaction actuelle en appelant la méthode `Transaction.Rollback` si une certaine condition est remplie.</span><span class="sxs-lookup"><span data-stu-id="021a6-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="021a6-121">Lorsqu'elle est appelée dans une procédure ou fonction managée, la méthode `Transaction.Rollback` lève une exception avec un message d'erreur ambigu et peut être encapsulée dans un bloc try/catch.</span><span class="sxs-lookup"><span data-stu-id="021a6-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="021a6-122">Le message d'erreur ressemble au suivant :</span><span class="sxs-lookup"><span data-stu-id="021a6-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="021a6-123">Cette exception est attendue et le bloc try/catch est nécessaire pour que l'exécution du code continue.</span><span class="sxs-lookup"><span data-stu-id="021a6-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="021a6-124">Sans le bloc try/catch, l'exception est levée immédiatement pour la procédure [!INCLUDE[tsql](../../includes/tsql-md.md)] appelante et l'exécution du code managé se termine.</span><span class="sxs-lookup"><span data-stu-id="021a6-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="021a6-125">Lorsque l'exécution du code managé se termine, une autre exception est levée :</span><span class="sxs-lookup"><span data-stu-id="021a6-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="021a6-126">Cette exception est également attendue et, pour que l'exécution continue, vous devez avoir un bloc try/catch autour de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] qui effectue l'action qui active le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="021a6-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="021a6-127">Malgré les deux exceptions levées, la transaction est restaurée et les modifications ne sont pas validées.</span><span class="sxs-lookup"><span data-stu-id="021a6-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="021a6-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="021a6-128">Example</span></span>  
 <span data-ttu-id="021a6-129">Voici un exemple de transaction restaurée à partir d'une procédure managée à l'aide de la méthode `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="021a6-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="021a6-130">Remarquez le bloc try/catch autour de la méthode `Transaction.Rollback` dans le code managé.</span><span class="sxs-lookup"><span data-stu-id="021a6-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="021a6-131">Le script [!INCLUDE[tsql](../../includes/tsql-md.md)] crée un assembly et une procédure stockée managée.</span><span class="sxs-lookup"><span data-stu-id="021a6-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="021a6-132">Sachez que l' `EXEC uspRollbackFromProc` instruction est encapsulée dans un bloc try/catch, afin que l’exception levée lorsque l’exécution de la procédure managée se termine est interceptée.</span><span class="sxs-lookup"><span data-stu-id="021a6-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="021a6-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="021a6-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="021a6-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="021a6-134">See Also</span></span>  
 [<span data-ttu-id="021a6-135">Intégration et transactions du CLR</span><span class="sxs-lookup"><span data-stu-id="021a6-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
