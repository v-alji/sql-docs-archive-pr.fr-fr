---
title: Traiter les codes de retour et les paramètres de sortie (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- return codes [ODBC]
- output parameters [ODBC]
ms.assetid: 102ae1d0-973d-4e12-992c-d844bf05160d
author: rothja
ms.author: jroth
ms.openlocfilehash: b119d43806dafa68fe049595d94e909a5a1bb896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605378"
---
# <a name="process-return-codes-and-output-parameters-odbc"></a><span data-ttu-id="96a45-102">Traiter les codes de retour et les paramètres de sortie (ODBC)</span><span class="sxs-lookup"><span data-stu-id="96a45-102">Process Return Codes and Output Parameters (ODBC)</span></span>
  <span data-ttu-id="96a45-103">Les procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent avoir des codes de retour et des paramètres de sortie de type entier.</span><span class="sxs-lookup"><span data-stu-id="96a45-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures can have integer return codes and output parameters.</span></span> <span data-ttu-id="96a45-104">Les codes de retour et paramètres de sortie sont envoyés dans le dernier paquet du serveur et ne sont pas disponibles pour l'application tant que [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) n'a pas retourné SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="96a45-104">The return codes and output parameters are sent in the last packet from the server and are not available to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="96a45-105">Si une erreur est retournée à partir d’une procédure stockée, appelez SQLMoreResults pour passer au résultat suivant jusqu’à ce que SQL_NO_DATA soit retourné.</span><span class="sxs-lookup"><span data-stu-id="96a45-105">If an error is returned from a stored procedure, call SQLMoreResults to advance to the next result until SQL_NO_DATA is returned.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="96a45-106">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="96a45-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="96a45-107">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="96a45-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="96a45-108">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="96a45-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="96a45-109">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="96a45-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-process-return-codes-and-output-parameters"></a><span data-ttu-id="96a45-110">Pour traiter des codes de retour et des paramètres de sortie</span><span class="sxs-lookup"><span data-stu-id="96a45-110">To process return codes and output parameters</span></span>  
  
1.  <span data-ttu-id="96a45-111">Construisez une instruction SQL qui utilise la séquence d'échappement ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="96a45-111">Construct an SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="96a45-112">L'instruction doit utiliser des marqueurs de paramètre pour chaque paramètre d'entrée, d'entrée/sortie et de sortie et pour la valeur de retour de la procédure (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="96a45-112">The statement should use parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
2.  <span data-ttu-id="96a45-113">Appelez [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) pour chaque paramètre d'entrée, d'entrée/sortie et de sortie et pour la valeur de retour de la procédure (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="96a45-113">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="96a45-114">Exécutez l'instruction avec `SQLExecDirect`.</span><span class="sxs-lookup"><span data-stu-id="96a45-114">Execute the statement with `SQLExecDirect`.</span></span>  
  
4.  <span data-ttu-id="96a45-115">Traitez les jeux de résultats jusqu'à ce que `SQLFetch` ou `SQLFetchScroll` retourne SQL_NO_DATA lors du traitement du dernier jeu de résultats ou jusqu'à ce que `SQLMoreResults` retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="96a45-115">Process result sets until `SQLFetch` or `SQLFetchScroll` returns SQL_NO_DATA while processing the last result set or until `SQLMoreResults` returns SQL_NO_DATA.</span></span> <span data-ttu-id="96a45-116">À ce stade, les variables liées au code de retour et aux paramètres de sortie sont remplies avec les valeurs de données retournées.</span><span class="sxs-lookup"><span data-stu-id="96a45-116">At this point, the variables bound to the return code and output parameters are filled with returned data values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96a45-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="96a45-117">Example</span></span>  
 <span data-ttu-id="96a45-118">Cet exemple montre le traitement d'un code de retour et d'un paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="96a45-118">This sample shows processing a return code and output parameter.</span></span> <span data-ttu-id="96a45-119">Cet exemple n'est pas pris en charge sur la plateforme IA64.</span><span class="sxs-lookup"><span data-stu-id="96a45-119">This sample is not supported on IA64.</span></span> <span data-ttu-id="96a45-120">Cet exemple a été développé pour la version 3.0 d'ODBC ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="96a45-120">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
 <span data-ttu-id="96a45-121">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="96a45-121">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="96a45-122">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="96a45-122">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="96a45-123">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="96a45-123">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="96a45-124">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="96a45-124">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="96a45-125">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="96a45-125">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="96a45-126">Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="96a45-126">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="96a45-127">La première liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) crée une procédure stockée utilisée par cet exemple.</span><span class="sxs-lookup"><span data-stu-id="96a45-127">The first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates a stored procedure used by this sample.</span></span>  
  
 <span data-ttu-id="96a45-128">Compilez la deuxième liste de code (C++)  avec odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="96a45-128">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="96a45-129">Puis, exécutez le programme.</span><span class="sxs-lookup"><span data-stu-id="96a45-129">Then, execute the program.</span></span>  
  
 <span data-ttu-id="96a45-130">La troisième liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) supprime la procédure stockée utilisée par cet exemple.</span><span class="sxs-lookup"><span data-stu-id="96a45-130">The third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the stored procedure used by this sample.</span></span>  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'TestParm')  
   DROP PROCEDURE TestParm  
GO  
  
CREATE PROCEDURE TestParm   
@OutParm int OUTPUT   
AS  
SELECT Name FROM Purchasing.Vendor  
SELECT @OutParm = 88  
RETURN 99  
go  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 255  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   // SQLBindParameter variables.  
   SWORD sParm1 = 0, sParm2 = 1;  
   SQLLEN cbParm1 = SQL_NTS;  
   SQLLEN cbParm2 = SQL_NTS;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // This sample use Integrated Security. Create the SQL Server DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Bind the return code to variable sParm1.  
   retcode = SQLBindParameter(hstmt1, 1, SQL_PARAM_OUTPUT, SQL_C_SSHORT, SQL_INTEGER, 0, 0, &sParm1, 0, &cbParm1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter(sParm1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Bind the output parameter to variable sParm2.  
   retcode = SQLBindParameter(hstmt1, 2, SQL_PARAM_OUTPUT, SQL_C_SSHORT, SQL_INTEGER, 0, 0, &sParm2, 0, &cbParm2);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter(sParm2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the command.   
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"{? = call TestParm(?)}", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Show parameters are not filled.  
   printf("Before result sets cleared: RetCode = %d, OutParm = %d.\n", sParm1, sParm2);  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA )  
      ;  
  
   // Show parameters are now filled.  
   printf("After result sets drained: RetCode = %d, OutParm = %d.\n", sParm1, sParm2);  
  
   // Clean up.   
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
DROP PROCEDURE TestParm  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="96a45-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96a45-131">See Also</span></span>  
 [<span data-ttu-id="96a45-132">Rubriques de procédures relatives à l’exécution de procédures stockées &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="96a45-132">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
