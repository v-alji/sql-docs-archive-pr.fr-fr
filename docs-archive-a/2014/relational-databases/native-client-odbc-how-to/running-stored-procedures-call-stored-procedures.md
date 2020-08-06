---
title: Appeler des procédures stockées (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605386"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="ff76e-102">Appeler des procédures stockées (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ff76e-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="ff76e-103">Lorsqu’une instruction SQL appelle une procédure stockée à l’aide de la clause ODBC CALL Escape, le pilote Microsoft SQL Server envoie la procédure à SQL Server à l’aide du mécanisme d’appel de procédure stockée distante (RPC).</span><span class="sxs-lookup"><span data-stu-id="ff76e-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="ff76e-104">Les demandes RPC, qui contournent une grande partie de l'analyse des instructions et du traitement des paramètres dans SQL Server, sont plus rapides que l'instruction Transact-SQL EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="ff76e-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="ff76e-105">Pour obtenir un exemple d’application qui illustre cette fonctionnalité, consultez [traiter les codes de retour et les paramètres de sortie &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ff76e-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="ff76e-106">Pour exécuter une procédure en tant qu'appel RPC</span><span class="sxs-lookup"><span data-stu-id="ff76e-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="ff76e-107">Construisez une instruction SQL qui utilise la séquence d'échappement ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="ff76e-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="ff76e-108">L'instruction utilise des marqueurs de paramètre pour chaque entrée, entrée/sortie et paramètre de sortie, et pour la valeur de retour de la procédure (le cas échéant) :</span><span class="sxs-lookup"><span data-stu-id="ff76e-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="ff76e-109">Appelez [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) pour chaque paramètre d'entrée, d'entrée/sortie et de sortie et pour la valeur de retour de la procédure (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="ff76e-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="ff76e-110">Exécutez l'instruction avec [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="ff76e-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff76e-111">Si une application soumet une procédure à l'aide de la syntaxe Transact-SQL EXECUTE (par opposition à la séquence d'échappement ODBC CALL), le pilote ODBC de SQL Server passe l'appel de procédure à SQL Server en tant qu'instruction SQL et non en tant qu'appel RPC.</span><span class="sxs-lookup"><span data-stu-id="ff76e-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="ff76e-112">Par ailleurs, les paramètres de sortie ne sont pas retournés si l'instruction Transact-SQL EXECUTE est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ff76e-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff76e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff76e-113">See Also</span></span>  
 <span data-ttu-id="ff76e-114">[Rubriques de procédures relatives à l’exécution de procédures stockées &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="ff76e-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="ff76e-115">[Traitement par lot des appels de procédure stockée](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="ff76e-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="ff76e-116">[Exécution de procédures stockées](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff76e-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="ff76e-117">[Appel d’une procédure stockée](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff76e-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="ff76e-118">Procédures</span><span class="sxs-lookup"><span data-stu-id="ff76e-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
