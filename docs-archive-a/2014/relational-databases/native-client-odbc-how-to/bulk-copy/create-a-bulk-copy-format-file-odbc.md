---
title: Créer un fichier de format de copie en bloc (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC], data files
ms.assetid: 0572fef3-daf5-409e-b557-c2a632f9a06d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d35342b2f6b25a129df968383d204931d64bfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600876"
---
# <a name="create-a-bulk-copy-format-file-odbc"></a><span data-ttu-id="4f05c-102">Créer un fichier de format de copie en bloc (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4f05c-102">Create a Bulk Copy Format File (ODBC)</span></span>
  <span data-ttu-id="4f05c-103">Cet exemple illustre comment utiliser des fonctions de copie en bloc pour créer un fichier de données et un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="4f05c-103">This sample shows how to use bulk copy functions to create both a data file and a format file.</span></span> <span data-ttu-id="4f05c-104">Cet exemple a été développé pour la version 3.0 d'ODBC ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4f05c-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f05c-105">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="4f05c-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="4f05c-106">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="4f05c-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="4f05c-107">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="4f05c-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="4f05c-108">Si vous devez conserver des informations d’identification, vous devez les chiffrer avec l' [API de chiffrement Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="4f05c-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-create-a-bulk-copy-format-file"></a><span data-ttu-id="4f05c-109">Pour créer un fichier de format de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="4f05c-109">To create a bulk copy format file</span></span>  
  
1.  <span data-ttu-id="4f05c-110">Allouez un handle d'environnement et un handle de connexion.</span><span class="sxs-lookup"><span data-stu-id="4f05c-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="4f05c-111">Définissez SQL_COPT_SS_BCP et SQL_BCP_ON de façon à activer les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4f05c-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="4f05c-112">Connectez-vous à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f05c-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="4f05c-113">Appelez [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) pour définir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4f05c-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="4f05c-114">Nom de la table ou de la vue à partir de laquelle ou vers laquelle effectuer la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4f05c-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="4f05c-115">Nom du fichier de données qui contient les données à copier dans la base de données ou qui reçoit les données lors de la copie à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4f05c-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="4f05c-116">Nom d'un fichier de données devant recevoir tous les messages d'erreur de copie en bloc (spécifiez NULL si vous ne souhaitez pas de fichier de message).</span><span class="sxs-lookup"><span data-stu-id="4f05c-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="4f05c-117">Direction de la copie : DB_OUT vers le fichier à partir de la table ou vue.</span><span class="sxs-lookup"><span data-stu-id="4f05c-117">The direction of the copy: DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="4f05c-118">Appelez [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) pour définir le nombre de colonnes.</span><span class="sxs-lookup"><span data-stu-id="4f05c-118">Call [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to set the number of columns.</span></span>  
  
6.  <span data-ttu-id="4f05c-119">Appelez [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) pour chaque colonne pour définir ses caractéristiques dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="4f05c-119">Call [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column to define its characteristics in the data file.</span></span>  
  
7.  <span data-ttu-id="4f05c-120">Appelez [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) pour créer un fichier de format décrivant le fichier de données à créer par l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4f05c-120">Call [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) to create a format file describing the data file to be created by the bulk copy operation.</span></span>  
  
8.  <span data-ttu-id="4f05c-121">Appelez [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) pour exécuter l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4f05c-121">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="4f05c-122">Une opération de copie en bloc exécutée de cette manière crée à la fois un fichier de données contenant les données copiées en bloc et un fichier de format décrivant la mise en page du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="4f05c-122">A bulk copy operation run in this way creates both a data file containing the bulk copied data and a format file describing the layout of the data file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f05c-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="4f05c-123">Example</span></span>  
 <span data-ttu-id="4f05c-124">Vous aurez besoin d'une source de données ODBC nommée AdventureWorks, dont la base de données par défaut est l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4f05c-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="4f05c-125">(Vous pouvez télécharger l’exemple de base de données AdventureWorks à partir de la page d’hébergement [exemples et projets de la communauté Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384) .) Cette source de données doit être basée sur le pilote ODBC fourni par le système d’exploitation (le nom du pilote est « SQL Server »).</span><span class="sxs-lookup"><span data-stu-id="4f05c-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="4f05c-126">Si vous générez et exécutez cet exemple comme une application 32 bits sur un système d'exploitation 64 bits, vous devez créer la source de données ODBC avec l'administrateur ODBC dans %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="4f05c-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="4f05c-127">Cet exemple vous permet de vous connecter à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par défaut de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4f05c-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="4f05c-128">Pour vous connecter à une instance nommée, modifiez la définition de la source de données ODBC pour spécifier l'instance en utilisant le format suivant : serveur\namedinstance.</span><span class="sxs-lookup"><span data-stu-id="4f05c-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="4f05c-129">Par défaut, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] est installé dans une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="4f05c-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="4f05c-130">Exécutez la première liste de code ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) pour créer la table que l'exemple utilisera.</span><span class="sxs-lookup"><span data-stu-id="4f05c-130">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="4f05c-131">Compilez la deuxième liste de code (C++) avec odbc32.lib et odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="4f05c-131">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span>  
  
 <span data-ttu-id="4f05c-132">Exécutez la troisième liste de code ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) pour supprimer la table que l'exemple a utilisée.</span><span class="sxs-lookup"><span data-stu-id="4f05c-132">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```  
use AdventureWorks  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
  
CREATE TABLE BCPDate (cola int, colb datetime)  
insert BCPDate(cola) values(1)   
insert BCPDate(cola) values(2)   
insert BCPDate(cola) values(3)   
insert BCPDate(cola) values(4)  
```  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
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
  
   // BCP variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
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
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_OUT);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the number of output columns.  
   retcode = bcp_columns(hdbc1, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 1 in the data file.  
   retcode = bcp_colfmt(hdbc1, 1, SQLCHARACTER, -1, 5, NULL, 0, 1);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 2 in the data file.  
   retcode = bcp_colfmt(hdbc1, 2, SQLCHARACTER, -1, 20, NULL, 0, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Create the format file.  
   retcode = bcp_writefmt(hdbc1, "c:\\BCPFMT.fmt");  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
   return(0);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f05c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f05c-133">See Also</span></span>  
 <span data-ttu-id="4f05c-134">[Rubriques de procédures relatives à la copie en bloc avec le SQL Server ODBC Driver &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="4f05c-134">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="4f05c-135">Utilisation de fichiers de données et de format</span><span class="sxs-lookup"><span data-stu-id="4f05c-135">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
