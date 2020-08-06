---
title: Utiliser des colonnes de données en cours d’exécution (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 4eae58d1-03d4-40ca-8aa1-9b3ea10a38cf
author: rothja
ms.author: jroth
ms.openlocfilehash: 68690208b690f94909100132c966eb59d11e4652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706452"
---
# <a name="use-data-at-execution-columns-odbc"></a><span data-ttu-id="9d856-102">Utiliser des colonnes de données en cours d'exécution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9d856-102">Use Data-at-Execution Columns (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-columns"></a><span data-ttu-id="9d856-103">Pour utiliser des colonnes text, ntext ou image de données en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="9d856-103">To use data-at-execution text, ntext, or image columns</span></span>  
  
1.  <span data-ttu-id="9d856-104">Pour chaque colonne de données en cours d’exécution, entrez des valeurs spéciales dans les mémoires tampon précédemment liées par [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) :</span><span class="sxs-lookup"><span data-stu-id="9d856-104">For each data-at-execution column, put special values into the buffers previously bound by [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span></span>  
  
    -   <span data-ttu-id="9d856-105">Pour le dernier paramètre, utilisez SQL_LEN_DATA_AT_EXEC(longueur) où « longueur » représente la longueur totale des données de colonne text, ntext ou image en octets.</span><span class="sxs-lookup"><span data-stu-id="9d856-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(length) where length is the total length of the text, ntext, or image column data in bytes.</span></span>  
  
    -   <span data-ttu-id="9d856-106">Pour le quatrième paramètre, entrez un identificateur de colonne défini par le programme.</span><span class="sxs-lookup"><span data-stu-id="9d856-106">For the fourth parameter, put a program-defined column identifier.</span></span>  
  
2.  <span data-ttu-id="9d856-107">L'appel de [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) retourne SQL_NEED_DATA, ce qui indique que les colonnes de données en cours d'exécution sont prêtes à être traitées.</span><span class="sxs-lookup"><span data-stu-id="9d856-107">Calling [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) returns SQL_NEED_DATA, which indicates that data-at-execution columns are ready for processing.</span></span>  
  
3.  <span data-ttu-id="9d856-108">Pour chaque colonne de données en cours d'exécution :</span><span class="sxs-lookup"><span data-stu-id="9d856-108">For each data-at-execution column:</span></span>  
  
    -   <span data-ttu-id="9d856-109">Appelez [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) pour obtenir le pointeur du tableau de colonne.</span><span class="sxs-lookup"><span data-stu-id="9d856-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the column array pointer.</span></span> <span data-ttu-id="9d856-110">SQL_NEED_DATA est retourné s'il existe une autre colonne de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9d856-110">It will return SQL_NEED_DATA if there is another data-at-execution column.</span></span>  
  
    -   <span data-ttu-id="9d856-111">Appelez [SQLPutData](../native-client-odbc-api/sqlputdata.md) une ou plusieurs fois pour envoyer les données de la colonne jusqu'à ce que toute la longueur soit envoyée.</span><span class="sxs-lookup"><span data-stu-id="9d856-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times to send the column data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="9d856-112">Appelez [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) pour indiquer que toutes les données de la dernière colonne de données en cours d'exécution ont été envoyées.</span><span class="sxs-lookup"><span data-stu-id="9d856-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution column is sent.</span></span> <span data-ttu-id="9d856-113">SQL_NEED_DATA n'est pas retourné.</span><span class="sxs-lookup"><span data-stu-id="9d856-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d856-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="9d856-114">Example</span></span>  
 <span data-ttu-id="9d856-115">L'exemple suivant montre comment lire des données de type caractères SQL_LONG variables à l'aide de SQLGetData.</span><span class="sxs-lookup"><span data-stu-id="9d856-115">The sample shows how to read a SQL_LONG variable character data using SQLGetData.</span></span> <span data-ttu-id="9d856-116">Cet exemple n'est pas pris en charge sur la plateforme IA64.</span><span class="sxs-lookup"><span data-stu-id="9d856-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="9d856-117">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9d856-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="9d856-118">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="9d856-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="9d856-119">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="9d856-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="9d856-120">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9d856-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="9d856-121">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="9d856-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="9d856-122">Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="9d856-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="9d856-123">Exécutez la première liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) pour créer la table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="9d856-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="9d856-124">Compilez la deuxième liste de code (C++)  avec odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="9d856-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="9d856-125">Exécutez ensuite le programme.</span><span class="sxs-lookup"><span data-stu-id="9d856-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="9d856-126">Exécutez la troisième liste de code ([!INCLUDE[tsql](../../includes/tsql-md.md)]) pour supprimer la table utilisée par l'exemple.</span><span class="sxs-lookup"><span data-stu-id="9d856-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp3 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name1', '12', 'This is the first employee')  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name2', '18', 'This is the second employee')  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define BUFFERSIZE  450  
  
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
};  
  
int main() {  
   RETCODE retcode;  
   SWORD cntr;  
  
   // SQLGetData variables.  
   UCHAR Data[BUFFERSIZE];  
   SDWORD cbBatch = (SDWORD)sizeof(Data)-1;  
   SQLLEN cbTxtSize;  
  
   // Clear data array.  
   for (cntr = 0 ; cntr < BUFFERSIZE ; cntr++)  
      Data[cntr] = 0x00;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle; prepare, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT Memo1 FROM emp3", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get first row.  
   retcode = SQLFetch(hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLFetch(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get the SQL_LONG column.  
   cntr = 1;  
   while ( (retcode = SQLGetData(hstmt1, 1, SQL_C_CHAR, Data, cbBatch, &cbTxtSize)) != SQL_NO_DATA) {  
      printf("GetData iteration %d, pcbValue = %d,\n", cntr++, cbTxtSize);  
      printf("Data = %s\n\n", Data);  
  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("GetData(hstmt1) Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }   
  
   // Clean up  
   //SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp3')  
     DROP TABLE emp3  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d856-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d856-127">See Also</span></span>  
 [<span data-ttu-id="9d856-128">Rubriques de procédures relatives à la gestion des colonnes de texte et d’image &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="9d856-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
