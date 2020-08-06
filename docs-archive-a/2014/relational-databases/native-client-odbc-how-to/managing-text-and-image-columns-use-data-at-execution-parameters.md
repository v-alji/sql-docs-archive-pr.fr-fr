---
title: Utiliser des paramètres de données en cours d’exécution (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 2a738aef-c991-4f62-bdab-a5221c335f31
author: rothja
ms.author: jroth
ms.openlocfilehash: cf87309f1e325b94ff455d446fbd2e76d5c06ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706448"
---
# <a name="use-data-at-execution-parameters-odbc"></a><span data-ttu-id="c1651-102">Utiliser des paramètres de données en cours d'exécution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c1651-102">Use Data-at-Execution Parameters (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-parameters"></a><span data-ttu-id="c1651-103">Pour utiliser des paramètres text, ntext ou image de données en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="c1651-103">To use data-at-execution text, ntext, or image parameters</span></span>  
  
1.  <span data-ttu-id="c1651-104">Quand vous appelez [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) pour lier une mémoire tampon de programme au paramètre d’instruction :</span><span class="sxs-lookup"><span data-stu-id="c1651-104">When calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind a program buffer to the statement parameter:</span></span>  
  
    -   <span data-ttu-id="c1651-105">Pour le dernier paramètre, utilisez SQL_LEN_DATA_AT_EXEC (*longueur*) où *longueur* représente la longueur totale des `text` données du `ntext` paramètre, ou `image` en octets.</span><span class="sxs-lookup"><span data-stu-id="c1651-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(*length*) where *length* is the total length of the `text`, `ntext`, or `image` parameter data in bytes.</span></span>  
  
    -   <span data-ttu-id="c1651-106">Utilisez un `rgbValue` (huitième paramètre) d'un identificateur de paramètre défini par le programme.</span><span class="sxs-lookup"><span data-stu-id="c1651-106">Use an `rgbValue` (eighth parameter) of a program-defined parameter identifier.</span></span>  
  
2.  <span data-ttu-id="c1651-107">Le fait d'appeler [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) ou [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) retourne SQL_NEED_DATA, ce qui indique que les paramètres de données en cours d'exécution sont prêts à être traités.</span><span class="sxs-lookup"><span data-stu-id="c1651-107">Calling [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) or [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA, which indicates that data-at-execution parameters are ready for processing.</span></span>  
  
3.  <span data-ttu-id="c1651-108">Pour chaque paramètre de données en cours d'exécution :</span><span class="sxs-lookup"><span data-stu-id="c1651-108">For each data-at-execution parameter:</span></span>  
  
    -   <span data-ttu-id="c1651-109">Appelez [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) pour obtenir l'ID du paramètre défini par le programme.</span><span class="sxs-lookup"><span data-stu-id="c1651-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the program-defined parameter ID.</span></span> <span data-ttu-id="c1651-110">SQL_NEED_DATA est retourné s'il existe un autre paramètre de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c1651-110">It will return SQL_NEED_DATA if there is another data-at-execution parameter.</span></span>  
  
    -   <span data-ttu-id="c1651-111">Appelez [SQLPutData](../native-client-odbc-api/sqlputdata.md) une ou plusieurs fois pour envoyer les données du paramètre jusqu'à ce que toute la longueur soit envoyée.</span><span class="sxs-lookup"><span data-stu-id="c1651-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times, to send the parameter data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="c1651-112">Appelez [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) pour indiquer que toutes les données du dernier paramètre de données en cours d'exécution ont été envoyées.</span><span class="sxs-lookup"><span data-stu-id="c1651-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution parameter is sent.</span></span> <span data-ttu-id="c1651-113">SQL_NEED_DATA n'est pas retourné.</span><span class="sxs-lookup"><span data-stu-id="c1651-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1651-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="c1651-114">Example</span></span>  
 <span data-ttu-id="c1651-115">Cet exemple montre comment lire des données de type caractères SQL_LONG variables à l'aide de SQLParamData et SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="c1651-115">The sample shows how to read SQL_LONG variable character data using SQLParamData and SQLPutData.</span></span> <span data-ttu-id="c1651-116">Cet exemple n'est pas pris en charge sur la plateforme IA64.</span><span class="sxs-lookup"><span data-stu-id="c1651-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="c1651-117">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c1651-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="c1651-118">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="c1651-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="c1651-119">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="c1651-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="c1651-120">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c1651-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="c1651-121">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="c1651-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="c1651-122">Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="c1651-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="c1651-123">Exécutez la première liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) pour créer la table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="c1651-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="c1651-124">Compilez la deuxième liste de code (C++)  avec odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="c1651-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="c1651-125">Exécutez ensuite le programme.</span><span class="sxs-lookup"><span data-stu-id="c1651-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="c1651-126">Exécutez la troisième liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) pour supprimer la table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="c1651-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp4 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define TEXTSIZE  12000  
#define MAXBUFLEN 256  
  
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
   SQLLEN cbTextSize, lbytes;  
  
   // SQLParamData variable.  
   PTR pParmID;  
  
   // SQLPutData variables.  
   UCHAR  Data[] =   
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyz";  
  
   SDWORD cbBatch = (SDWORD)sizeof(Data) - 1;  
  
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
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
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
  
   // Set parameters based on total data to send.  
   lbytes = (SDWORD)TEXTSIZE;  
   cbTextSize = SQL_LEN_DATA_AT_EXEC(lbytes);  
  
   // Bind the parameter marker.  
   retcode = SQLBindParameter (hstmt1,           // hstmt  
                               1,                // ipar  
                               SQL_PARAM_INPUT,  // fParamType  
                               SQL_C_CHAR,       // fCType  
                               SQL_LONGVARCHAR,  // FSqlType  
                               lbytes,           // cbColDef  
                               0,                // ibScale  
                               (VOID *)1,        // rgbValue  
                               0,                // cbValueMax  
                               &cbTextSize);     // pcbValue  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the command.  
   retcode =   
      SQLExecDirect(hstmt1, (UCHAR*)"INSERT INTO emp4 VALUES('Paul Borm', 46,'1950-11-12 00:00:00', ?)", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_NEED_DATA) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Check to see if NEED_DATA; if yes, use SQLPutData.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if (retcode == SQL_NEED_DATA) {  
      while (lbytes > cbBatch) {  
         SQLPutData(hstmt1, Data, cbBatch);  
         lbytes -= cbBatch;  
      }  
      // Put final batch.  
      retcode = SQLPutData(hstmt1, Data, lbytes);   
   }  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Make final SQLParamData call.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("Final SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clean up.  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp4')  
     DROP TABLE emp4  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1651-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1651-127">See Also</span></span>  
 [<span data-ttu-id="c1651-128">Rubriques de procédures relatives à la gestion des colonnes de texte et d’image &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c1651-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
