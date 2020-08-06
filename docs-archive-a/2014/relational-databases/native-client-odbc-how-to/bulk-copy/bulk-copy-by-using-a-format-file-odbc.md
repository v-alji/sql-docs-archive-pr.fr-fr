---
title: Copie en bloc à l’aide d’un fichier de format (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709359"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="89d19-102">Effectuer une copie en bloc à l'aide d'un fichier de format (ODBC)</span><span class="sxs-lookup"><span data-stu-id="89d19-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="89d19-103">Cet exemple montre comment utiliser la fonction ODBC bcp_init avec un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="89d19-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="89d19-104">Pour effectuer une copie en bloc à l'aide d'un fichier de format</span><span class="sxs-lookup"><span data-stu-id="89d19-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="89d19-105">Allouez un handle d'environnement et un handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="89d19-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="89d19-106">Définissez SQL_COPT_SS_BCP et SQL_BCP_ON de façon à activer les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="89d19-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="89d19-107">Connectez-vous à Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89d19-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="89d19-108">Appelez [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) pour définir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="89d19-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="89d19-109">Nom de la table ou de la vue à partir de laquelle ou vers laquelle effectuer la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="89d19-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="89d19-110">Nom du fichier de données qui contient les données à copier dans la base de données ou qui reçoit les données lors de la copie à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="89d19-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="89d19-111">Nom d'un fichier de données devant recevoir tous les messages d'erreur de copie en bloc (spécifiez NULL si vous ne souhaitez pas de fichier de message).</span><span class="sxs-lookup"><span data-stu-id="89d19-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="89d19-112">Direction de la copie : DB_IN du fichier vers la table ou vue.</span><span class="sxs-lookup"><span data-stu-id="89d19-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="89d19-113">Appelez [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) pour lire le fichier de format décrivant le fichier de données à utiliser par l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="89d19-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="89d19-114">Appelez [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) pour exécuter l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="89d19-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89d19-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="89d19-115">Example</span></span>  
 <span data-ttu-id="89d19-116">Cet exemple n'est pas pris en charge sur la plateforme IA64.</span><span class="sxs-lookup"><span data-stu-id="89d19-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="89d19-117">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="89d19-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="89d19-118">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="89d19-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="89d19-119">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="89d19-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="89d19-120">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="89d19-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="89d19-121">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="89d19-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="89d19-122">Par défaut, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="89d19-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="89d19-123">Exécutez la première liste de code ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) pour créer la table que l'exemple utilisera.</span><span class="sxs-lookup"><span data-stu-id="89d19-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="89d19-124">Copiez la deuxième liste de code et collez-la dans un fichier appelé Bcpfmt.fmt.</span><span class="sxs-lookup"><span data-stu-id="89d19-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="89d19-125">Chaque colonne de la table est séparée par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="89d19-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="89d19-126">Copiez la troisième liste de code et collez-la dans un fichier appelé Bcpodbc.bcp.</span><span class="sxs-lookup"><span data-stu-id="89d19-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="89d19-127">Une tabulation précède chaque retour chariot dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="89d19-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="89d19-128">Compilez la quatrième liste de code (C++) avec odbc32.lib et odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="89d19-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="89d19-129">Si vous avez effectué la génération avec MSBuild.exe, copiez Bcpfmt.fmt et Bcpodbc.bcp à partir du répertoire de projet dans le répertoire avec le fichier .exe, puis appelez le fichier .exe.</span><span class="sxs-lookup"><span data-stu-id="89d19-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="89d19-130">Exécutez la cinquième liste de code ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) pour supprimer la table que l'exemple a utilisée.</span><span class="sxs-lookup"><span data-stu-id="89d19-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="89d19-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89d19-131">See Also</span></span>  
 <span data-ttu-id="89d19-132">[Rubriques de procédures relatives à la copie en bloc avec le SQL Server ODBC Driver &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="89d19-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="89d19-133">Utilisation de fichiers de données et de format</span><span class="sxs-lookup"><span data-stu-id="89d19-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
