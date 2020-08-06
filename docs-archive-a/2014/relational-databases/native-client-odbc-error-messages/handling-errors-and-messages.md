---
title: Gestion des erreurs et des messages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698184"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="feb52-102">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="feb52-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="feb52-103">Lorsqu'une application appelle une fonction ODBC, le pilote exécute la fonction et retourne les informations de diagnostic de deux façons : un code de retour indique le succès ou l'échec total d'une fonction ODBC et les enregistrements de diagnostic fournissent des informations détaillées sur la fonction.</span><span class="sxs-lookup"><span data-stu-id="feb52-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="feb52-104">Les enregistrements de diagnostic comportent un enregistrement d'en-tête et des enregistrements d'état.</span><span class="sxs-lookup"><span data-stu-id="feb52-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="feb52-105">Au moins un enregistrement de diagnostic, l'enregistrement d'en-tête, est retourné même si la fonction réussit.</span><span class="sxs-lookup"><span data-stu-id="feb52-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="feb52-106">Les informations de diagnostic sont utilisées au moment du développement pour intercepter les erreurs de programmation, telles que les handles non valides et les erreurs de syntaxe dans les instructions SQL codées de manière irréversible.</span><span class="sxs-lookup"><span data-stu-id="feb52-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="feb52-107">Elles sont également utilisées au moment de l'exécution pour intercepter les avertissements et les erreurs d'exécution, tels que la troncation de données, les violations de règle et les erreurs de syntaxe des instructions SQL saisies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="feb52-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="feb52-108">La logique du programme repose en général sur des codes de retour.</span><span class="sxs-lookup"><span data-stu-id="feb52-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="feb52-109">Par exemple, après qu’une application a appelé **SQLFetch** pour extraire les lignes d’un jeu de résultats, le code de retour indique si la fin du jeu de résultats a été atteinte (SQL_NO_DATA), si des messages d’information ont été retournés (SQL_SUCCESS_WITH_INFO) ou si une erreur s’est produite (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="feb52-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="feb52-110">Si le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client retourne une valeur autre que SQL_SUCCESS, l’application peut **appeler SQLGetDiagRec** pour récupérer les messages d’information ou d’erreur.</span><span class="sxs-lookup"><span data-stu-id="feb52-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="feb52-111">Utilisez **SQLGetDiagRec** pour faire défiler vers le haut et vers le haut l’ensemble de messages s’il y a plusieurs messages.</span><span class="sxs-lookup"><span data-stu-id="feb52-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="feb52-112">Le code de retour SQL_INVALID_HANDLE indique toujours une erreur de programmation et ne doit jamais se rencontrer au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="feb52-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="feb52-113">Tous les autres codes de retour fournissent des informations d'exécution, bien que SQL_ERROR puisse indiquer une erreur de programmation.</span><span class="sxs-lookup"><span data-stu-id="feb52-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="feb52-114">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] API native d’origine, DB-Library pour C, permet à une application d’installer les fonctions de gestion des erreurs de rappel et de gestion des messages qui retournent des erreurs ou des messages.</span><span class="sxs-lookup"><span data-stu-id="feb52-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="feb52-115">Certaines instructions [!INCLUDE[tsql](../../includes/tsql-md.md)], telles que PRINT, RAISERROR, DBCC et SET, retournent leurs résultats à la fonction gestionnaire des messages de DB-Library et non dans un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="feb52-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="feb52-116">Toutefois, l'API ODBC n'a aucune fonction de rappel similaire.</span><span class="sxs-lookup"><span data-stu-id="feb52-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="feb52-117">Lorsque le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client détecte des messages provenant de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , il définit le code de retour odbc sur SQL_SUCCESS_WITH_INFO ou SQL_ERROR et retourne le message sous la forme d’un ou de plusieurs enregistrements de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="feb52-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="feb52-118">Par conséquent, une application ODBC doit tester avec soin ces codes de retour et appeler **SQLGetDiagRec** pour extraire les données de message.</span><span class="sxs-lookup"><span data-stu-id="feb52-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="feb52-119">Pour plus d’informations sur le suivi des erreurs, consultez [Suivi de l’accès aux données](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="feb52-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="feb52-120">Pour plus d’informations sur les améliorations du suivi des erreurs ajoutées dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], consultez [Accès aux informations de diagnostic dans le journal des événements étendus](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="feb52-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="feb52-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="feb52-121">In This Section</span></span>  
  
-   [<span data-ttu-id="feb52-122">Traitement des instructions qui génèrent des messages</span><span class="sxs-lookup"><span data-stu-id="feb52-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="feb52-123">Enregistrements et champs de diagnostic</span><span class="sxs-lookup"><span data-stu-id="feb52-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="feb52-124">Numéros des erreurs natives</span><span class="sxs-lookup"><span data-stu-id="feb52-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="feb52-125">SQLSTATE &#40;codes d’erreur ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="feb52-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="feb52-126">Messages d’erreur</span><span class="sxs-lookup"><span data-stu-id="feb52-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="feb52-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="feb52-127">See Also</span></span>  
 [<span data-ttu-id="feb52-128">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="feb52-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
